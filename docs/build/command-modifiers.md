---
title: "Befehlsmodifizierer | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Befehlsmodifizierer"
  - "NMAKE (Programm), Befehlsmodifizierer"
ms.assetid: b661c432-210f-4f05-bc56-744a46e0fc0b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Befehlsmodifizierer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vor einem Befehl können ein Befehlsmodifizierer oder mehrere Befehlsmodifizierer, die optional durch Leerzeichen oder Tabstopps getrennt werden, angegeben werden.  Modifizierer müssen wie Befehle eingerückt sein.  
  
|Modifizierer|Zweck|  
|------------------|-----------|  
|@*command*|Verhindert die Anzeige des Befehls.  Die Anzeige, die durch Befehle ausgelöst wird, wird nicht unterdrückt.  Standardmäßig werden alle ausgeführten Befehle von NMAKE ausgegeben.  Mit **\/S** wird die Anzeige für das gesamte Makefile unterdrückt, mit **.SILENT** wird die Anzeige für einen Teil des Makefiles unterdrückt.|  
|**–**\[`number` \]*command*|Deaktiviert die Fehlerprüfung für *command*.  Standardmäßig wird NMAKE angehalten, wenn ein Befehl einen Exitcode ungleich null zurückgibt.  Wenn **–**`number` verwendet wird, wird NMAKE angehalten, sobald der Exitcode `number` überschreitet.  Leerzeichen oder Tabstopps sind nicht zulässig zwischen dem Gedankenstrich und *number.* Zwischen `number` und *command* muss sich mindestens ein Leerzeichen oder Tabstopp befinden.  Mit **\/I** kann die Fehlerprüfung für das gesamte Makefile deaktiviert werden. Mit **.IGNORE** kann die Fehlerprüfung für einen Teil des Makefiles deaktiviert werden.|  
|**\!** *command*|Führt *command* für jede abhängige Datei aus, wenn *command* $\*\* \(alle abhängigen Dateien der Abhängigkeit\) oder $? \(alle abhängigen Dateien der Abhängigkeit mit einem späteren Timestamp als das Ziel\) verwendet wird.|  
  
## Siehe auch  
 [Befehle in einem Makefile](../build/commands-in-a-makefile.md)