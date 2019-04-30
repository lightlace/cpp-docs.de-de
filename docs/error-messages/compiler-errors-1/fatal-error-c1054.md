---
title: Schwerwiegender Fehler C1054
ms.date: 11/04/2016
f1_keywords:
- C1054
helpviewer_keywords:
- C1054
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
ms.openlocfilehash: 0bfd0c03378b1a9c616a014ac96153b3ab04af9d
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344797"
---
# <a name="fatal-error-c1054"></a>Schwerwiegender Fehler C1054

Compilerlimit: zu tiefe Schachtelung von Initialisierungen

Der Code überschreitet die maximale Schachtelungstiefe auf Initialisierer (abhängig von der Kombination von Typen, die initialisiert wird die Stufen von 10 bis 15).

### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)

1. Vereinfachen Sie die Datentypen, die zur Reduzierung der Schachtelungsebenen initialisiert wird.

1. Initialisieren von Variablen in separaten Anweisungen nach der Deklaration.