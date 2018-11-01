---
title: Linkertoolwarnung LNK4006
ms.date: 11/04/2016
f1_keywords:
- LNK4006
helpviewer_keywords:
- LNK4006
ms.assetid: 3a637d17-1676-4ea6-bd8b-290137d28d3b
ms.openlocfilehash: c81c93a6df8c7eef809f243e3dc56164ea548371
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472227"
---
# <a name="linker-tools-warning-lnk4006"></a>Linkertoolwarnung LNK4006

bereits im Objekt definiertes Symbol zweite Definition wurde ignoriert.

Das gegebene `symbol`, angezeigt in seiner ergänzten Form, wurde mehrfach definiert. Bei dieser Warnung auftreten `symbol` zweimal hinzugefügt werden, aber nur die erste Form verwendet werden.

Sie können diese Warnung erhalten, wenn Sie versuchen, zwei Importbibliotheken in einer Zelle zusammenzuführen.

Wenn Sie die C-Laufzeitbibliothek neu sind, können Sie diese Meldung ignorieren.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)

1. Der angegebene `symbol` möglicherweise eine Paketfunktion, erstellt durch Kompilierung mit [/Gy](../../build/reference/gy-enable-function-level-linking.md). Dieses Symbol in mehr als eine Datei enthalten war, aber zwischen Kompilationen geändert. Kompilieren Sie alle Dateien, enthalten die `symbol`.

1. Der angegebene `symbol` möglicherweise unterschiedlich definiert sein in zwei Memberobjekten in verschiedenen Bibliotheken.

1. Ein absoluter möglicherweise zweimal mit einem anderen Wert in jeder Definition definiert wurden.

1. Wenn die Fehlermeldung, beim Kombinieren von Bibliotheken empfangen wird, `symbol` bereits vorhanden ist, in der Bibliothek hinzugefügt wird.