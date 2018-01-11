---
title: "Pufferüberlauf | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- buffers [C++], character sizes
- buffer overflows [C++]
- MBCS [C++], buffer overflow
ms.assetid: f2b7e40a-f02b-46d8-a449-51d26fc0c663
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4bfad181ee7c6b702af87bc8ff0a49ccfb42cb65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="buffer-overflow"></a>Pufferüberlauf
Zeichengrößen VARYING kann Probleme verursachen, wenn Sie die Zeichen in einen Puffer abgelegt. Betrachten Sie den folgenden Code, der Zeichen aus einer Zeichenfolge kopiert, `sz`, in einen Puffer `rgch`:  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
    rgch[ cb++ ] = *sz++;  
```  
  
 Die Frage ist: der zuletzt kopierte Byte ein führendes Byte wurde? Folgendes ist nicht das Problem, da es möglicherweise den Puffer überlaufen kann:  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 Die `_mbccpy` Aufruf versucht, das richtige tun – kopieren Sie das vollständige Zeichen, ob es sich um 1 oder 2 Bytes ist. Aber sie nimmt nicht berücksichtigt, dass das letzte Zeichen nicht auf den Puffer passt möglicherweise, wenn das Zeichen 2 Bytes breit ist. Die richtige Lösung ist:  
  
```  
cb = 0;  
while( (cb + _mbclen( sz )) <= sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 Dieser Code überprüft mögliche Pufferüberlauf in der Schleife zu testen, mit `_mbclen` So testen Sie die Größe des aktuellen Zeichens verweist `sz`. Von einem Aufruf an die `_mbsnbcpy` -Funktion, ersetzen Sie den Code in der `while` Schleife mit einer einzigen Codezeile. Zum Beispiel:  
  
```  
_mbsnbcpy( rgch, sz, sizeof( rgch ) );  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md)