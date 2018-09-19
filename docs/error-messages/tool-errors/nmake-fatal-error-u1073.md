---
title: 'NMAKE: Schwerwiegender Fehler U1073 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1073
dev_langs:
- C++
helpviewer_keywords:
- U1073
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c309ed94cd1c984406e0d21f0139e35c6e41d7d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053938"
---
# <a name="nmake-fatal-error-u1073"></a>NMAKE: Schwerwiegender Fehler U1073

weiß nicht, wie Sie "Zielname"

Das angegebene Ziel ist nicht vorhanden, und ist keine auszuführende Befehl oder Rückschlussregel anzuwenden.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)

1. Überprüfen Sie die Schreibweise der Zielname.

1. Wenn *Targetname* ist ein Pseudoziel, geben Sie es als Ziel in einem anderen Beschreibungsblock.

1. Wenn *Targetname* ein Makroaufruf wird Sie sicher, dass es nicht auf eine null-Zeichenfolge erweitert werden.