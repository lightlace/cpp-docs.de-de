---
title: "Linkertoolwarnung LNK4102"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4102"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4102"
ms.assetid: bfd1b17e-05c7-4bc2-80d6-2888b1a425b2
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolwarnung LNK4102
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Export des Löschdestruktors 'Name'; Abbild kann möglicherweise nicht fehlerfrei ausgeführt werden  
  
 Das Programm hat versucht, einen Löschdestruktor zu exportieren.  Der resultierende Löschvorgang kann sich über eine DLL\-Grenze hinaus auswirken, z. B. derart, dass ein Prozess Arbeitsspeicher freigeben kann, der ihm nicht zugeordnet wurde.  Stellen Sie sicher, dass das angegebene Symbol weder in der DEF\-Datei aufgelistet ist, noch als Argument der Option **\/IMPORT** oder **\/EXPORT** in der Linkerbefehlszeile angegeben ist.  
  
 Wenn Sie die C\-Laufzeitbibliothek neu erstellen, können Sie diese Meldung ignorieren.