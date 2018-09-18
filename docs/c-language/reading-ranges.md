---
title: Lesen von Bereichen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 76530dfdac917dfbde50bc3fb1b17a3c31178729
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030240"
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