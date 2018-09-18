---
title: 'Ressourcencompiler: Schwerwiegender Fehler RC1120 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC1120
dev_langs:
- C++
helpviewer_keywords:
- RC1120
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62f28e381d4eac0bfd1f010ef3919452635a1b96
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057001"
---
# <a name="resource-compiler-fatal-error-rc1120"></a>Ressourcencompiler: Schwerwiegender Fehler RC1120

nicht genügend Arbeitsspeicher benötigt Anzahl bytes

Der Ressourcencompiler war nicht genügend Speicher für Elemente, die in einen Heap gespeichert wird. In der Regel ist dies das Ergebnis, dass zu viele Symbole.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)

1. Erhöhen Sie die Windows-Auslagerungsdatei. Weitere Informationen zum Erhöhen der Auslagerungsdatei finden Sie unter Virtueller Arbeitsspeicher im Windows-Hilfe.

1. Löschen Sie überflüssige Includedateien, insbesondere dann nicht benötigte `#define`s und Prototypen von Funktionen.

1. Teilen Sie die aktuelle Datei in zwei oder mehr Dateien auf, und kompilieren Sie sie separat.

1. Entfernen Sie andere Programme oder Treiber, die auf dem System, das Menge an Arbeitsspeicher beansprucht werden kann.