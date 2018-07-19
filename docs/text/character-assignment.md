---
title: Zuweisung Zeichen | Microsoft Docs
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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e403a619fc4c900aca51503862ff8f9dc315c2a3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33856696"
---
# <a name="character-assignment"></a>Zeichenzuweisungen
Betrachten Sie das folgende Beispiel, in dem die `while` Schleife durchsucht eine Zeichenfolge, die alle Zeichen mit Ausnahme von "X" in eine andere Zeichenfolge kopiert:  
  
```  
while( *sz2 )  
{  
    if( *sz2 != 'X' )  
        *sz1++ = *sz2++;  
    else  
        sz2++;  
}  
```  
  
 Kopiert das Byte, ab `sz2` an der Speicherstelle `sz1`, inkrementiert dann `sz1` das nächste Byte empfangen. Jedoch, wenn das nächste Zeichen in `sz2` ist ein Doppelbyte-Zeichen, die Zuweisung zu `sz1` nur das erste Byte kopiert. Der folgende Code verwendet eine portable Funktion, um die Zeichen sicher zu kopieren und inkrementieren `sz1` und `sz2` ordnungsgemäß:  
  
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