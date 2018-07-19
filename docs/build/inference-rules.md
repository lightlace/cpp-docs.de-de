---
title: Rückschlussregeln für | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- NMAKE program, inference rules
ms.assetid: caff320f-fb07-4eea-80c3-a6a2133a8492
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2baa4bdd749e7553d052600cc9efe524ec09910d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368420"
---
# <a name="inference-rules"></a>Rückschlussregeln
Rückschlussregeln geben Befehle zum Aktualisieren von Zielen und abhängigen Elemente für Ziele abzuleiten. Erweiterungen in einer Rückschlussregel entsprechen ein einzelnes Ziel, und abhängig, die den gleichen Basisnamen aufweisen. Rückschlussregeln werden die benutzerdefinierten oder vordefinierten; Vordefinierte Regeln können neu definiert werden.  
  
 Wenn eine veraltete Abhängigkeit keine Befehle aufweist und [. SUFFIXE](../build/dot-directives.md) des abhängigen Erweiterung NMAKE verwendet, die eine Regel, deren Erweiterungen übereinstimmen, das Ziel und eine vorhandene, Datei in der aktuellen oder angegebenen Verzeichnis enthält. Wenn mehr als eine Regel eine Übereinstimmung mit vorhandenen Dateien, die **. SUFFIXE** Liste bestimmt, welche verwenden; Liste Priorität absteigend von links nach rechts. Wenn eine abhängige Datei nicht vorhanden ist und nicht als Ziel in einem anderen Beschreibungsblock aufgelistet ist, kann eine Rückschlussregel die fehlende abhängige aus einer anderen Datei mit den gleichen Basisnamen erstellen. Wenn eine Beschreibung des Blocks Ziel keine abhängigen Dateien oder Befehle verfügt, kann eine Rückschlussregel das Ziel aktualisieren. Rückschlussregeln können ein Befehlszeilen-Ziel erstellen, selbst wenn keine Beschreibungsblock vorhanden ist. NMAKE kann eine Regel für eine hergeleitete abhängige aufrufen, auch wenn eine explizite abhängige angegeben wird.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
 [Definieren einer Regel](../build/defining-a-rule.md)  
  
 [Stapelverarbeitungsregeln](../build/batch-mode-rules.md)  
  
 [Vordefinierte Regeln](../build/predefined-rules.md)  
  
 [Hergeleitete abhängige Dateien und Regeln](../build/inferred-dependents-and-rules.md)  
  
 [Vorrang in Rückschlussregeln](../build/precedence-in-inference-rules.md)  
  
## <a name="see-also"></a>Siehe auch  
 [NMAKE-Referenz](../build/nmake-reference.md)