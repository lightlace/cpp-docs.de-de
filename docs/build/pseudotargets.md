---
title: Pseudoziele | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- makefiles, pseudotargets
- pseudotargets and NMAKE
- NMAKE program, pseudotargets
- timestamps, makefile pseudotargets
- NMAKE program, targets
ms.assetid: c8c479dc-0129-4186-8366-bc6251f2b494
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67dbc6ae3ad331ab3297b62d00044c3edf679994
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="pseudotargets"></a>Pseudoziele
Ein Pseudoziel handelt es sich um eine Bezeichnung, die anstelle der Dateinamen in einer Abhängigkeitszeile verwendet. Es wird als eine Datei interpretiert, die nicht vorhanden, und daher ist veraltet. NMAKE wird davon ausgegangen, dass ein Pseudoziel Zeitstempel der letzten alle abhängigen Elemente ist. Wenn es keine abhängigen Elemente verfügt, wird davon ausgegangen, dass die aktuelle Uhrzeit. Wenn ein Pseudoziel als Ziel verwendet wird, werden die zugehörigen Befehle immer ausgeführt. Ein Pseudoziel als abhängige verwendet, muss auch als Ziel in einer anderen Abhängigkeit angezeigt werden. Allerdings muss diese Abhängigkeit kein Befehlsblock haben.  
  
 Pseudoziel-Namen entsprechen die Filename-Syntaxregeln für Ziele. Jedoch, wenn der Name keine Erweiterung ist (d. h. nicht enthält einen Zeitraum), können die 8-Zeichen-Grenze für Dateinamen überschreiten, und es kann bis zu 256 Zeichen lang sein.  
  
## <a name="see-also"></a>Siehe auch  
 [Ziele](../build/targets.md)