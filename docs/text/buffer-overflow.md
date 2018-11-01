---
title: Pufferüberlauf
ms.date: 11/04/2016
helpviewer_keywords:
- buffers [C++], character sizes
- buffer overflows [C++]
- MBCS [C++], buffer overflow
ms.assetid: f2b7e40a-f02b-46d8-a449-51d26fc0c663
ms.openlocfilehash: 97488f3023481c20599e8cf5201fbce68dd23516
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566499"
---
# <a name="buffer-overflow"></a>Pufferüberlauf

Zeichengrößen variieren kann Probleme verursachen, wenn Sie Zeichen in einen Puffer abgelegt. Betrachten Sie den folgenden Code, der Zeichen aus einer Zeichenfolge kopiert, `sz`, in einen Puffer, `rgch`:

```cpp
cb = 0;
while( cb < sizeof( rgch ) )
    rgch[ cb++ ] = *sz++;
```

Die Frage lautet: war das letzte Byte kopiert ein führendes Byte ist? Die folgenden nicht das Problem gelöst, da es unter Umständen ein Überlauf des Puffers kann:

```cpp
cb = 0;
while( cb < sizeof( rgch ) )
{
    _mbccpy( rgch + cb, sz );
    cb += _mbclen( sz );
    sz = _mbsinc( sz );
}
```

Die `_mbccpy` Aufruf wird versucht, das richtige tun – kopieren Sie das vollständige Zeichen, ob es sich um 1 oder 2 Bytes ist. Aber es werden nicht berücksichtigt, dass das letzte Zeichen des Puffers möglicherweise nicht entspricht, wenn das Zeichen mit 2 Bytes breit ist. Die richtige Lösung ist:

```cpp
cb = 0;
while( (cb + _mbclen( sz )) <= sizeof( rgch ) )
{
    _mbccpy( rgch + cb, sz );
    cb += _mbclen( sz );
    sz = _mbsinc( sz );
}
```

Dieser Code überprüft wird, für die möglichen Pufferüberlauf in der Schleife zu testen, mit `_mbclen` So testen Sie die Größe der das aktuelle Zeichen verweist `sz`. Von einem Aufruf an die `_mbsnbcpy` -Funktion, ersetzen Sie den Code in die **während** -Schleife mit einer einzelnen Zeile des Codes. Zum Beispiel:

```cpp
_mbsnbcpy( rgch, sz, sizeof( rgch ) );
```

## <a name="see-also"></a>Siehe auch

[Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md)