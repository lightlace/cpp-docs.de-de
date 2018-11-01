---
title: 'NMAKE: Schwerwiegender Fehler U1073'
ms.date: 11/04/2016
f1_keywords:
- U1073
helpviewer_keywords:
- U1073
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
ms.openlocfilehash: 2aa02fd86906bd545373a313fa5e6e409ffb3cf9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582272"
---
# <a name="nmake-fatal-error-u1073"></a>NMAKE: Schwerwiegender Fehler U1073

weiß nicht, wie Sie "Zielname"

Das angegebene Ziel ist nicht vorhanden, und ist keine auszuführende Befehl oder Rückschlussregel anzuwenden.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)

1. Überprüfen Sie die Schreibweise der Zielname.

1. Wenn *Targetname* ist ein Pseudoziel, geben Sie es als Ziel in einem anderen Beschreibungsblock.

1. Wenn *Targetname* ein Makroaufruf wird Sie sicher, dass es nicht auf eine null-Zeichenfolge erweitert werden.