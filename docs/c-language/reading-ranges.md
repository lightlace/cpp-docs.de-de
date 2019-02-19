---
title: Lesen von Bereichen
ms.date: 11/04/2016
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
ms.openlocfilehash: 86bb24647084d8bdc452960bab631587c2413276
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56150492"
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
