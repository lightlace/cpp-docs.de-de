---
title: Zuweisung Zeichen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- characters [C++], assignments
- MBCS [C++], character assignments
ms.assetid: dcc329cd-92df-4e20-817d-364be62ff28f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c5efdaefdfd961a10d40c00855261eb547164f95
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591400"
---
# <a name="character-assignment"></a>Zeichenzuweisungen
Das folgende Beispiel, in dem die **während** Schleife durchsucht eine Zeichenfolge, die alle Zeichen mit Ausnahme von "X" in einer anderen Zeichenfolge kopiert:  
  
```  
while( *sz2 )  
{  
    if( *sz2 != 'X' )  
        *sz1++ = *sz2++;  
    else  
        sz2++;  
}  
```  
  
 Der Code kopiert das Byte am `sz2` auf den Speicherort verweist `sz1`, inkrementiert dann `sz1` das nächste Byte empfangen. Aber wenn das nächste Zeichen im `sz2` ist ein Doppelbyte-Zeichen, die Zuweisung zu `sz1` nur das erste Byte kopiert. Der folgende Code verwendet wird, eine portable Funktion, die die Zeichen sicher zu kopieren und inkrementieren `sz1` und `sz2` richtig:  
  
```  
while( *sz2 )  
{  
    if( *sz2 != 'X' )  
    {  
        _mbscpy_s( sz1, 1, sz2 );  
        sz1 = _mbsinc( sz1 );  
        sz2 = _mbsinc( sz2 );  
    }  
    else  
        sz2 = _mbsinc( sz2 );  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md)   
 [Zeichenvergleich](../text/character-comparison.md)