---
title: 'Ressourcencompiler: Schwerwiegender Fehler RC1120'
ms.date: 11/04/2016
f1_keywords:
- RC1120
helpviewer_keywords:
- RC1120
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
ms.openlocfilehash: eff46ddee118c3355e548c73220b407db0561e36
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374251"
---
# <a name="resource-compiler-fatal-error-rc1120"></a>Ressourcencompiler: Schwerwiegender Fehler RC1120

nicht genügend Arbeitsspeicher benötigt Anzahl bytes

Der Ressourcencompiler war nicht genügend Speicher für Elemente, die in einen Heap gespeichert wird. In der Regel ist dies das Ergebnis, dass zu viele Symbole.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)

1. Erhöhen Sie die Windows-Auslagerungsdatei. Weitere Informationen zum Erhöhen der Auslagerungsdatei finden Sie unter Virtueller Arbeitsspeicher im Windows-Hilfe.

1. Löschen Sie überflüssige Includedateien, insbesondere dann nicht benötigte `#define`s und Prototypen von Funktionen.

1. Teilen Sie die aktuelle Datei in zwei oder mehr Dateien auf, und kompilieren Sie sie separat.

1. Entfernen Sie andere Programme oder Treiber, die auf dem System, das Menge an Arbeitsspeicher beansprucht werden kann.