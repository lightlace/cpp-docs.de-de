---
title: "/MACHINE (Zielplattform angeben) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.TargetMachine"
  - "/machine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MACHINE (Linkeroption)"
  - "MACHINE (Linkeroption)"
  - "-MACHINE (Linkeroption)"
  - "Zuordnungsdateien, Erstellen des Linkers"
  - "Zielplattform"
ms.assetid: 8d41bf4b-7e53-4ab9-9085-d852b08d31c2
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /MACHINE (Zielplattform angeben)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MACHINE:{ARM|EBC|X64|X86}  
```  
  
## Hinweise  
 Die \/MACHINE\-Option gibt die Zielplattform für das Programm an.  
  
 Normalerweise müssen Sie die \/MACHINE\-Option nicht angeben.  LINK leitet den Computertyp aus den OBJ\-Dateien ab.  Unter gewissen Umständen kann LINK den Computertyp jedoch nicht ermitteln und gibt dann den [Linkertoolfehler LNK1113](../../error-messages/tool-errors/linker-tools-error-lnk1113.md) aus.  Geben Sie "\/MACHINE" an, wenn ein solcher Fehler auftritt.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Erweitert**.  
  
4.  Ändern Sie die Eigenschaft **Zielcomputer**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TargetMachine*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)