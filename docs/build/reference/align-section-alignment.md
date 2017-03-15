---
title: "/ALIGN (Abschnittsausrichtung) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.Alignment"
  - "/align"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ALIGN (Linkeroption)"
  - "ALIGN (Linkeroption)"
  - "-ALIGN (Linkeroption)"
  - "Abschnittsausrichtung"
  - "Abschnitte"
  - "Abschnitte, Angeben der Ausrichtung"
ms.assetid: f2f8ac24-e90e-4bea-8205-f2960a3b1740
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /ALIGN (Abschnittsausrichtung)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ALIGN[:number]  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `number`  
 Der Ausrichtungswert.  
  
## Hinweise  
 Die \/ALIGN\-Option gibt die Ausrichtung der einzelnen Abschnitten im linearen Adressbereich des Programms an.  Das number\-Argument wird in Bytes angegeben und muss ein Wert hoch zwei sein.  Die Standardeinstellung lautet 4 KB \(4096\).  Der Linker gibt eine Warnmeldung aus, wenn sich aus der Ausrichtung ein ungültiges Abbild ergibt.  
  
 Sie sollten die Ausrichtung nur beim Programmieren einer Anwendung, z. B. eines Gerätetreibers, ändern.  
  
 Die Ausrichtung eines bestimmten Abschnitts lässt sich mit dem Ausrichtungsparameter der Option [\/SECTION](../../build/reference/section-specify-section-attributes.md) ändern.  
  
 Der angegebene Ausrichtungswert darf nicht kleiner als die größte Abschnittsausrichtung sein.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Option im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)