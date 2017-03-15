---
title: "/TLBID (Ressourcen-ID f&#252;r TypeLib festlegen) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/tlbid"
  - "VC.Project.VCLinkerTool.TypeLibraryResourceID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".tlb-Dateien, Angeben der Ressourcen-ID"
  - "/TLBID (Linkeroption)"
  - "TLB-Dateien, Angeben der Ressourcen-ID"
  - "TLBID (Linkeroption)"
  - "-TLBID (Linkeroption)"
  - "Typbibliotheken, Angeben der Ressourcen-ID"
ms.assetid: 434b28a2-4656-4d52-ac82-8b18bf486fb2
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /TLBID (Ressourcen-ID f&#252;r TypeLib festlegen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/TLBID:id  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `id`  
 ein benutzerdefinierter Wert für eine vom Linker erstellte Typbibliothek.  Die Standardressourcen\-ID \(1\) wird dadurch überschrieben.  
  
## Hinweise  
 Beim Kompilieren eines Programms, das Attribute verwendet, erstellt der Linker eine Typbibliothek.  Der Linker weist der Typbibliothek die Ressourcen\-ID 1 zu.  
  
 Wenn diese Ressourcen\-ID einen Konflikt mit einer der vorhandenen Ressourcen hervorruft, können Sie mithilfe von **\/TLBID** eine andere ID festlegen.  Der für `id` gültige Wertebereich umfasst Zahlen von 1 bis 65535.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Eingebettete IDL**.  
  
4.  Ändern Sie die Eigenschaft **TypeLib\-Ressourcen\-ID**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryResourceID*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)