---
title: Dokument Konventionen
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor
- preprocessor, conventions
ms.assetid: 469ce448-dc6c-4d0e-ba2b-e2e7a10155e1
ms.openlocfilehash: bb826b879b71edd3631c11a717320cee51c87175
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220374"
---
# <a name="document-conventions"></a>Dokument Konventionen

Die Konventionen verwenden verschiedene Schriftartattribute für unterschiedliche Syntaxkomponenten. Die Symbole und die Schriftarten lauten wie folgt:

| Attribut | Beschreibung |
|---------------|-----------------|
| *nonterminal* | Kursivschrift gibt Nichtterminale an. |
| **#include** | Fett formatierte Terminale sind literale, reservierte Symbole und Wörter, die wie gezeigt eingegeben werden müssen. Bei Zeichen in diesem Kontext wird immer die Groß-/Kleinschreibung beachtet. |
| <sub>opt</sub> | Nichtterminale, auf die <sub>opt</sub> folgt, sind immer optional.|
| Standardschriftart | Zeichen des in dieser Schriftart beschriebenen oder aufgeführten Satzes können als Terminale in C-Anweisungen verwendet werden. |

Ein Doppelpunkt ( **:** ) nach einem Nichtterminal führt ihre Definition ein. Alternative Definitionen werden in separaten Zeilen aufgeführt.

In Code Syntax Blöcken haben diese Symbole in der Standard Schriftart eine besondere Bedeutung:

| Symbol | Beschreibung |
|---|---|
| \[ ] | Eckige Klammern umgeben ein optionales Element. |
| { \| } | Geschweifte Klammern umschließen Alternative Elemente, die durch vertikale Balken voneinander getrennt sind. |
| ... | Gibt an, dass das vorherige Element Muster wiederholt werden kann. |

In Code Syntax Blöcken sind Kommas (`,`), Punkte (`.`), Semikolons (`;`),`:`Doppelzeichen (), Klammern (`( )`), doppelte Anführungszeichen (`"`) und einfache Anführungszeichen (`'`) Literale.

## <a name="see-also"></a>Siehe auch

[Grammatik Zusammenfassung (CC++/)](../preprocessor/grammar-summary-c-cpp.md)
