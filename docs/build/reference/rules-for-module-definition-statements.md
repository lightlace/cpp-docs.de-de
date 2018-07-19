---
title: Regeln für Moduldefinitionsanweisungen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- .def
dev_langs:
- C++
helpviewer_keywords:
- module definition files, statement syntax
- module definition files
ms.assetid: f65cd3a7-65d7-4d06-939f-a8b1ecd50f2d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3f8de42480dae9be203a132561d722c18d6952c1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376389"
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