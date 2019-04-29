---
title: Letztes Zeichen einer Zeichenfolge
ms.date: 11/04/2016
helpviewer_keywords:
- last character in string
- MBCS [C++], last character in string
ms.assetid: 0a180376-4e55-41e8-9c64-539c7b6d8047
ms.openlocfilehash: 4c99628cd12738fabb877a94cfd04a4033ee45aa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410670"
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
