---
title: "/DYNAMICBASE (Address Space Layout Randomization verwenden) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.RandomizedBaseAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DYNAMICBASE (Linkeroption)"
  - "DYNAMICBASE (Linkeroption)"
  - "-DYNAMICBASE (Linkeroption)"
ms.assetid: 6c0ced8e-fe9c-4b63-b956-eb8a55fbceb2
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /DYNAMICBASE (Address Space Layout Randomization verwenden)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt an, ob ein ausführbares Abbild generiert werden soll, für das zur Ladezeit mit der ASLR \(Address Space Layout Randomization\)\-Funktion von [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] nach dem Zufallsprinzip ein Rebase\-Vorgang ausgeführt werden kann.  
  
## Syntax  
  
```  
/DYNAMICBASE[:NO]  
```  
  
## Hinweise  
 Standardmäßig ist \/DYNAMICBASE aktiviert.  
  
 Mit dieser Option wird der Header einer ausführbaren Datei geändert, um anzugeben, ob für die Anwendung zur Ladezeit nach dem Zufallsprinzip ein Rebase\-Vorgang ausgeführt werden soll.  
  
 Die Adressbereichslayouterstellung einer zufälligen Verteilung wird auf [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] unterstützt.  
  
### So legen Sie diese Linkeroption in Visual Studio fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Weitere Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften**.  
  
3.  Erweitern Sie den Knoten **Linker**.  
  
4.  Wählen Sie die Eigenschaftenseite **Erweitert** aus.  
  
5.  Ändern Sie die Eigenschaft **Zufällige Basisadresse**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RandomizedBaseAddress*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)