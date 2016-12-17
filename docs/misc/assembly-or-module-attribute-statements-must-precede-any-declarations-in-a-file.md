---
title: "Assembly- oder Modulattributanweisungen m&#252;ssen vor allen Deklarationen in einer Datei stehen."
ms.custom: na
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc30637"
  - "bc30637"
helpviewer_keywords: 
  - "BC30637"
ms.assetid: 80242581-fa8a-4903-9395-6f7ad1610231
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "shoag"
manager: "wpickett"
---
# Assembly- oder Modulattributanweisungen m&#252;ssen vor allen Deklarationen in einer Datei stehen.
Globale Attribute müssen am Anfang einer Quelldatei deklariert werden, nach den `Option` und `Imports`\-Anweisungen, aber vor allen anderen Anweisungen.  
  
 **Fehler\-ID:** BC30637  
  
### So beheben Sie diesen Fehler  
  
1.  Setzen Sie globale Attribute, wie z. B. `<Module:>` und `<Assembly:>` an den Anfang der Quelldatei.  
  
## Siehe auch  
 [NICHT IM BUILD: Attribute in Visual Basic](assetId:///620bfc0e-4582-4c8b-8432-ebc5c3dccc22)   
 [NICHT IM BUILD: Globale Attribute in Visual Basic](assetId:///253a32d8-1531-4504-b687-088554ab71d2)