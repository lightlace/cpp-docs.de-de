---
title: "Regeln für Moduldefinitionsanweisungen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- .def
dev_langs:
- C++
helpviewer_keywords:
- module definition files, statement syntax
- module definition files
ms.assetid: f65cd3a7-65d7-4d06-939f-a8b1ecd50f2d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 40eb4875b195871aff8d274667e005d63424a110
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="rules-for-module-definition-statements"></a>Regeln für Moduldefinitionsanweisungen
Die folgenden Syntaxregeln gelten für alle Anweisungen in einer DEF-Datei. Andere Regeln, die für bestimmte Anweisungen gelten, werden mit jeder Anweisung beschrieben.  
  
-   Anweisungen, die Attribut-Schlüsselwörter und benutzerdefinierten Bezeichner sind Groß-/Kleinschreibung beachtet.  
  
-   Lange Dateinamen mit Leerzeichen oder ein Semikolon (;) muss in Anführungszeichen (") eingeschlossen werden.  
  
-   Verwenden Sie eine oder mehrere Leerzeichen, Tabstopps oder neue Zeilenumbruchzeichen aus, um ein Anweisungsschlüsselwort von den Argumenten zu trennen und Anweisungen voneinander zu trennen. Ein Doppelpunkt (:) oder Gleichheitszeichen (=), der ein Argument kennzeichnet von 0 (null) oder mehr Leerzeichen, Tabulatoren oder Zeilenvorschubzeichen umgeben ist.  
  
-   Ein **Namen** oder **Bibliothek** -Anweisung, wenn verwendet, muss andere vor allen Anweisungen stehen.  
  
-   Die **Abschnitte** und **EXPORTE** Anweisungen können mehr als einmal in der DEF-Datei angezeigt. Jede Anweisung kann mehrere Spezifikationen annehmen und somit die durch eine oder mehrere Leerzeichen, Tabstopps oder neue Zeilenumbruchzeichen getrennt werden müssen. Das Anweisungsschlüsselwort muss vor der ersten Spezifikation einmal angezeigt werden und kann wiederholt werden, bevor Sie jede zusätzliche Spezifikation.  
  
-   Viele Anweisungen haben eine entsprechende LINK-Befehlszeilenoption. Finden Sie in der Beschreibung der Option zur entsprechenden LINK für zusätzliche Details.  
  
-   Kommentare in der DEF-Datei sind gekennzeichnet durch ein Semikolon (;) am Anfang jeder Kommentarzeile. Ein Kommentar kann nicht Leitung mit einer Anweisung verwendet kann, aber es zwischen Spezifikationen in einer mehrzeiligen Anweisungen. (**Abschnitte** und **EXPORTE** sind mehrzeilige Anweisungen.)  
  
-   Numerische Argumente sind in der Basis 10 angegeben oder im Hexadezimalformat.  
  
-   Wenn ein Argument entspricht einem [reservierten Wort](../../build/reference/reserved-words.md), muss das Argument in doppelte Anführungszeichen (") eingeschlossen werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Moduldefinitionsdateien (.Def)](../../build/reference/module-definition-dot-def-files.md)  