---
title: "Linkertoolwarnung LNK4092 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4092"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4092"
ms.assetid: d569ec47-a338-40e1-940b-8a8061459acb
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Linkertoolwarnung LNK4092
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der freigegebene schreibbare Abschnitt 'Abschnitt' enthält Umsetzungen; Anwendung kann möglicherweise nicht fehlerfrei ausgeführt werden  
  
 Der Linker gibt diese Warnung stets bei Vorhandensein eines gemeinsam genutzten Abschnitts aus, der ernsthafte Probleme verursachen könnte.  
  
 Eine Möglichkeit, Daten zwischen mehreren Prozessen zu nutzen, besteht darin, einen Abschnitt als "freigegeben" zu kennzeichnen. Eine derartige Kennzeichnung eines Abschnitts kann jedoch zu Problemen führen.  Angenommen, eine DLL enthält in einem freigegebenen Datenabschnitt Deklarationen wie die folgenden:  
  
```  
int var = 1;  
int *pvar = &var;  
```  
  
 In diesem Fall kann der Linker `pvar` nicht auflösen, da der Wert davon abhängt, an welcher Stelle die DLL im Arbeitsspeicher geladen wird. Folglich wird ein Umsetzungseintrag in die DLL eingefügt.  Wenn die DLL in den Arbeitsspeicher geladen wird, kann die Adresse von `var` aufgelöst und `pvar` zugewiesen werden.  Falls dieselbe DLL von einem anderen Prozess, jedoch nicht an derselben Adresse, geladen wird, wird die Umsetzung für die `var`\-Adresse für den zweiten Prozess aktualisiert, und der Adressbereich des ersten Prozesses verweist auf die falsche Adresse.