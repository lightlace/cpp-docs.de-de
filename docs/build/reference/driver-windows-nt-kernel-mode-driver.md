---
title: "/DRIVER (Treiber f&#252;r den Kernelmodus von Windows&#160;NT) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.driver"
  - "/driver"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DRIVER (Linkeroption)"
  - "DRIVER (Linkeroption)"
  - "-DRIVER (Linkeroption)"
  - "Kernelmodustreiber"
ms.assetid: aeee8e28-5d97-40f5-ba16-9f370fe8a1b8
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /DRIVER (Treiber f&#252;r den Kernelmodus von Windows&#160;NT)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DRIVER[:UPONLY | :WDM]  
```  
  
## Hinweise  
 Verwenden Sie die \/DRIVER\-Linkeroption, um einen Windows NT\-Kernelmodustreiber zu erstellen.  
  
 **\/DRIVER:UPONLY** veranlasst den Linker dazu, das **IMAGE\_FILE\_UP\_SYSTEM\_ONLY**\-Bit zu den Merkmalen im Ausgabeheader hinzuzufügen, um festzulegen, dass es sich um einen Uniprozessor\-Treiber \(UP\) handelt.  Das Betriebssystem lädt keinen UP\-Treiber auf einem Multiprozessorsystem \(MP\).  
  
 **\/DRIVER:WDM** veranlasst den Linker, das **IMAGE\_DLLCHARACTERISTICS\_WDM\_DRIVER**\-Bit im DllCharacteristics\-Feld des optionalen Headers festzulegen.  
  
 Wenn **\/DRIVER** nicht angegeben wird, werden diese Bits nicht vom Linker festgelegt.  
  
 Wenn **\/DRIVER** angegeben wird:  
  
-   ist \/FIXED:NO gültig \([\/FIXED \(Feste Basisadresse\)](../../build/reference/fixed-fixed-base-address.md)\).  
  
-   Die Erweiterung der Ausgabedatei lautet .sys.  Verwenden **\/OUT**, um den Standarddateinamen und die Erweiterung \([\/OUT \(Ausgabedateiname\)](../../build/reference/out-output-file-name.md)\) zu ändern.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **System**.  
  
4.  Ändern Sie die Eigenschaft **Treiber**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe `P:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.driver`.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)