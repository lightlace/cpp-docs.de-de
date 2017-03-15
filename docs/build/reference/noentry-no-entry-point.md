---
title: "/NOENTRY (Kein Einstiegspunkt) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.ResourceOnlyDLL"
  - "/noentry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/NOENTRY-Linkeroption [C++]"
  - "DLLs [C++], Erstellen"
  - "Einstiegspunkte [C++], Linker festlegen"
  - "NOENTRY (Linkeroption)"
  - "-NOENTRY (Linkeroption)"
  - "Nur-Ressourcen-DLLs [C++], Erstellen"
ms.assetid: 0214dd41-35ad-43ab-b892-e636e038621a
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /NOENTRY (Kein Einstiegspunkt)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/NOENTRY  
```  
  
## Hinweise  
 Die Option\/NOENTRY ist erforderlich für das Erstellen einer reinen Ressourcen\-DLL, die keinen ausführbaren Code enthält.  Weitere Informationen finden Sie unter [Erstellen einer DLL als reine Ressource](../../build/creating-a-resource-only-dll.md).  
  
 Sie können mit dieser Option verhindern, dass LINK einen Verweis auf `_main` in die DLL einbindet.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie den Ordner **Linker** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Erweitert** aus.  
  
4.  Ändern Sie die Eigenschaft **Kein Einstiegspunkt**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ResourceOnlyDLL*>.  
  
## Siehe auch  
 [Erstellen einer DLL als reine Ressource](../../build/creating-a-resource-only-dll.md)   
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)