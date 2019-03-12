---
title: Byte-Indizes
ms.date: 11/04/2016
helpviewer_keywords:
- MBCS [C++], byte indices
- byte indices [C++]
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
ms.openlocfilehash: 5305a977c23d7a978a89c84809cc6fab8c5731eb
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751595"
---
# <a name="byte-indices"></a>Byte-Indizes

Verwenden Sie die folgenden Tipps:

- Arbeiten mit einem byteweisen Index in einer Zeichenfolge stellt detaillierteste zeigermanipulation ähnliche Probleme. Betrachten Sie dieses Beispiel, das eine Zeichenfolge für einen umgekehrten Schrägstrich überprüft:

    ```cpp
    while ( rgch[ i ] != '\\' )
        i++;
    ```

   Dies kann ein nachfolgendes Byte, kein führendes Byte ist, indizieren und kann daher nicht auf verweist eine `character`.

- Verwenden der [_mbclen](../c-runtime-library/reference/mbclen-mblen-mblen-l.md) Funktion, um das vorherige Problem zu lösen:

    ```cpp
    while ( rgch[ i ] != '\\' )
        i += _mbclen ( rgch + i );
    ```

   Dies richtig indiziert, um ein führendes Byte ist, werden daher auf eine `character`. Die `_mbclen` Funktion bestimmt die Größe eines Zeichens (1 oder 2 Bytes).

## <a name="see-also"></a>Siehe auch

[Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md)<br/>
[Letztes Zeichen einer Zeichenfolge](../text/last-character-in-a-string.md)
