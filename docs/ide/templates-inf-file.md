---
title: "INF-Vorlagendatei"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Benutzerdefinierte Assistenten, Vorlagendateien"
ms.assetid: 93d60d27-2402-4dc8-a829-e97417ccea49
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# INF-Vorlagendatei
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Templates.inf** ist eine Textdatei mit einer Liste von Vorlagen, die für das Projekt gerendert werden müssen.  
  
 Da **Templates.inf** selbst eine [Vorlagendatei](../ide/template-files.md) ist, können Sie Direktiven verwenden um anzugeben, welche Dateien in Abhängigkeit der vom Benutzer ausgewählten Optionen in ein Projekt eingeschlossen werden sollen.  Eine Liste der Direktiven, die Sie in dieser Datei verwenden können, finden Sie unter [Vorlagendirektiven](../ide/template-directives.md).  
  
## Beispiel  
  
```  
Template1.txt  
Template2.txt  
  [!if TYPE_A]  
TemplateOptionA.h  
TemplateOptionA.cpp  
  [!else]  
TemplateOptionB.h  
TemplateOptionB.cpp  
  [!endif]  
```  
  
 Durch **CreateCustomInfFile** wird **Templates.inf** in einer temporären Textdatei gerendert, die nach der Verarbeitung der Dateien gelöscht werden muss.  
  
## Beispiel  
  
```  
var InfFile = CreateCustomInfFile();  
AddFilesToProject(selProj, strProjectName, InfFile);  
InfFile.Delete();  
```  
  
 Weitere Informationen finden Sie unter [JScript\-Datei](../ide/jscript-file.md).  
  
## Siehe auch  
 [Für den Assistenten erstellte Dateien](../ide/files-created-for-your-wizard.md)   
 [Benutzerdefinierter Assistent](../ide/custom-wizard.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)