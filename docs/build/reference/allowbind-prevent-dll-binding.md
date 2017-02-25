---
title: "/ALLOWBIND (DLL-Bindung verhindern) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.PreventDLLBinding"
  - "/allowbind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ALLOWBIND (Linkeroption)"
  - "ALLOWBIND (Linkeroption)"
  - "-ALLOWBIND (Linkeroption)"
  - "Binden von DLLs"
  - "DLLs [C++], Verhindern von Bindungen"
  - "Verhindern von DLL-Bindungen"
ms.assetid: 30e37e24-12e4-407e-988a-39d357403598
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /ALLOWBIND (DLL-Bindung verhindern)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ALLOWBIND[:NO]  
```  
  
## Hinweise  
 \/ALLOWBIND:NO legt ein Bit im Header einer DLL fest, das Bind.exe darauf hinweist, dass das Image nicht gebunden werden darf.  Möglicherweise möchten Sie nicht, dass eine DLL gebunden wird, wenn sie digital signiert wurde \(das Binden macht die Signatur ungültig\).  
  
 Sie können eine vorhandene DLL für die \/ALLOWBIND\-Funktionalität mit der Option [\/ALLOWBIND](../../build/reference/allowbind.md) des EDITBIN\-Hilfsprogramms bearbeiten.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie **Konfigurationseigenschaften**, **Linker**, und wählen Sie **Befehlszeile** aus.  
  
3.  Geben `/ALLOWBIND:NO` in **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)   
 [BindImage\-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms679278.aspx)   
 [BindImageEx\-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms679279.aspx)