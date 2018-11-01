---
title: Schwerwiegender Fehler C1054
ms.date: 11/04/2016
f1_keywords:
- C1054
helpviewer_keywords:
- C1054
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
ms.openlocfilehash: 0bfd0c03378b1a9c616a014ac96153b3ab04af9d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569199"
---
# <a name="fatal-error-c1054"></a>Schwerwiegender Fehler C1054

Compilerlimit: zu tiefe Schachtelung von Initialisierungen

Der Code überschreitet die maximale Schachtelungstiefe auf Initialisierer (abhängig von der Kombination von Typen, die initialisiert wird die Stufen von 10 bis 15).

### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)

1. Vereinfachen Sie die Datentypen, die zur Reduzierung der Schachtelungsebenen initialisiert wird.

1. Initialisieren von Variablen in separaten Anweisungen nach der Deklaration.