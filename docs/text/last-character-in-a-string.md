---
title: Letztes Zeichen einer Zeichenfolge
ms.date: 11/04/2016
helpviewer_keywords:
- last character in string
- MBCS [C++], last character in string
ms.assetid: 0a180376-4e55-41e8-9c64-539c7b6d8047
ms.openlocfilehash: 535c2e58edab49e0e2a9dbc3fce9821d5909f1c5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456263"
---
# <a name="last-character-in-a-string"></a>Letztes Zeichen einer Zeichenfolge

Verwenden Sie die folgenden Tipps:

- Nachfolgendes Byte-Bereiche überschneiden sich in vielen Fällen den ASCII-Zeichensatz. Sie können problemlos byteweise Scanvorgänge für Steuerzeichen (weniger als 32) verwenden.

- Beachten Sie die folgende Zeile des Codes, der überprüft werden kann, um festzustellen, ob das letzte Zeichen in einer Zeichenfolge ein umgekehrter Schrägstrich ist:

    ```cpp
    if ( sz[ strlen( sz ) - 1 ] == '\\' )    // Is last character a '\'?
        // . . .
    ```

   Da `strlen` ist nicht MBCS-fähig ist, wird die Anzahl der Bytes, die nicht die Anzahl der Zeichen in einer multibyte-Zeichenfolge. Beachten Sie auch, die in einigen Codepages (z. B. 932), "\\" (0x5c) ist ein gültiges nachfolgendes Byte (`sz` ist eine C-Zeichenfolge).

   Eine mögliche Lösung ist den Code auf diese Weise neu schreiben:

    ```cpp
    char *pLast;
    pLast = _mbsrchr( sz, '\\' );    // find last occurrence of '\' in sz
    if ( pLast && ( *_mbsinc( pLast ) == '\0' ) )
        // . . .
    ```

   Dieser Code verwendet die MBCS-Funktionen `_mbsrchr` und `_mbsinc`. Da diese Funktionen MBCS-fähig sind, unterscheiden sie zwischen einem "\\'Zeichen und ein nachfolgendes Byte'\\". Der Code führt eine Aktion aus, wenn das letzte Zeichen in der Zeichenfolge ein NULL-Wert ('\0') ist.

## <a name="see-also"></a>Siehe auch

[Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md)<br/>
[Zeichenzuweisungen](../text/character-assignment.md)