---
title: Lesen von Bereichen
ms.date: 11/04/2016
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
ms.openlocfilehash: b5c6a6baf43b8786fbd0301e4b89ea856d839606
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50604106"
---
# <a name="reading-ranges"></a>Lesen von Bereichen

**ANSI 4.9.6.2** Die Interpretation eines Bindestriches (-), der weder das erste noch das letzte Zeichen in der Suchliste der „% [“-Konvertierung in der `fscanf`-Funktion ist

Die folgende Zeile

```
fscanf( fileptr, "%[A-Z]", strptr);
```

liest eine beliebige Anzahl von Zeichen im Bereich von A-Z in der Zeichenfolge, auf die `strptr` zeigt.

## <a name="see-also"></a>Siehe auch

[Bibliotheksfunktionen](../c-language/library-functions.md)