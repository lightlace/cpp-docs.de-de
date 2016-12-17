---
title: "/MERGE (Abschnitte kombinieren)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "/merge"
  - "VC.Project.VCLinkerTool.MergeSections"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MERGE (Linkeroption)"
  - "MERGE (Linkeroption)"
  - "-MERGE (Linkeroption)"
  - "Abschnitte"
  - "Abschnitte, Kombinieren"
  - "Abschnitte, Benennen"
ms.assetid: 10fb20c2-0b3f-4c8d-98a8-f69aedf03d52
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# /MERGE (Abschnitte kombinieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MERGE:from=to  
```  
  
## Hinweise  
 Durch die Option **\/MERGE** wird der erste Abschnitt \(*from*\) mit dem zweiten \(*to*\) kombiniert und der sich ergebende Abschnitt mit *to* benannt.  Beispielsweise `/merge:.rdata=.text`.  
  
 Wenn der zweite Abschnitt nicht vorhanden ist, benennt **LINK** den Abschnitt *.rdata* in *.text* um.  
  
 Die Option **\/MERGE** wird für das Erstellen von VxDs und das Überschreiben der vom Compiler generierten Abschnittsnamen verwendet.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Erweitert**.  
  
4.  Ändern Sie die Eigenschaft **Abschnitte zusammenfügen**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergeSections*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)