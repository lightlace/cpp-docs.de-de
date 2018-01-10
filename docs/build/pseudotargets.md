---
title: Pseudoziele | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- makefiles, pseudotargets
- pseudotargets and NMAKE
- NMAKE program, pseudotargets
- timestamps, makefile pseudotargets
- NMAKE program, targets
ms.assetid: c8c479dc-0129-4186-8366-bc6251f2b494
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 761b71f05840c86516563df79d45cc1bb018fbba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="pseudotargets"></a>Pseudoziele
Ein Pseudoziel handelt es sich um eine Bezeichnung, die anstelle der Dateinamen in einer Abhängigkeitszeile verwendet. Es wird als eine Datei interpretiert, die nicht vorhanden, und daher ist veraltet. NMAKE wird davon ausgegangen, dass ein Pseudoziel Zeitstempel der letzten alle abhängigen Elemente ist. Wenn es keine abhängigen Elemente verfügt, wird davon ausgegangen, dass die aktuelle Uhrzeit. Wenn ein Pseudoziel als Ziel verwendet wird, werden die zugehörigen Befehle immer ausgeführt. Ein Pseudoziel als abhängige verwendet, muss auch als Ziel in einer anderen Abhängigkeit angezeigt werden. Allerdings muss diese Abhängigkeit kein Befehlsblock haben.  
  
 Pseudoziel-Namen entsprechen die Filename-Syntaxregeln für Ziele. Jedoch, wenn der Name keine Erweiterung ist (d. h. nicht enthält einen Zeitraum), können die 8-Zeichen-Grenze für Dateinamen überschreiten, und es kann bis zu 256 Zeichen lang sein.  
  
## <a name="see-also"></a>Siehe auch  
 [Ziele](../build/targets.md)