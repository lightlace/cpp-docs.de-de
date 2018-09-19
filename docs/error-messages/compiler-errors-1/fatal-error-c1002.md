---
title: Schwerwiegender Fehler C1002 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1002
dev_langs:
- C++
helpviewer_keywords:
- C1002
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82f08255484b11f9f5d87fb67ac8ac7b401d4f6e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044144"
---
# <a name="fatal-error-c1002"></a>Schwerwiegender Fehler C1002

Im 2. Durchlauf ist kein Heapspeicher mehr für den Compiler verfügbar.

Der Compiler war nicht genügend Speicherplatz für dynamischen Arbeitsspeicher während des zweiten Durchlaufs, wahrscheinlich aufgrund eines Programms durch zu viele Symbole oder komplexe Ausdrücke.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)

1. Unterteilen Sie die Quelldatei, in mehreren kleineren Dateien.

1. Unterteilen Sie Ausdrücke in kleinere Teilausdrücke an.

1. Entfernen Sie andere Programme oder Treiber, die Speicher belegen.