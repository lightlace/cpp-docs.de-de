---
title: Zeichenzuweisungen
ms.date: 11/04/2016
helpviewer_keywords:
- characters [C++], assignments
- MBCS [C++], character assignments
ms.assetid: dcc329cd-92df-4e20-817d-364be62ff28f
ms.openlocfilehash: 88c42435d336ba78e87c9acfe3ada5fddbd18fb8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410745"
---
# <a name="character-assignment"></a>Zeichenzuweisungen

Das folgende Beispiel, in dem die **während** Schleife durchsucht eine Zeichenfolge, die alle Zeichen mit Ausnahme von "X" in einer anderen Zeichenfolge kopiert:

```cpp
while( *sz2 )
{
    if( *sz2 != 'X' )
        *sz1++ = *sz2++;
    else
        sz2++;
}
```

Der Code kopiert das Byte am `sz2` auf den Speicherort verweist `sz1`, inkrementiert dann `sz1` das nächste Byte empfangen. Aber wenn das nächste Zeichen im `sz2` ist ein Doppelbyte-Zeichen, die Zuweisung zu `sz1` nur das erste Byte kopiert. Der folgende Code verwendet wird, eine portable Funktion, die die Zeichen sicher zu kopieren und inkrementieren `sz1` und `sz2` richtig:

```cpp
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

[Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md)<br/>
[Zeichenvergleich](../text/character-comparison.md)
