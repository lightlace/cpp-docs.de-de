---
title: "/OUT (Ausgabedateiname)"
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
  - "VC.Project.VCLinkerTool.OutputFile"
  - "/out"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/OUT (C++-Linkeroption)"
  - "Linker [C++], Ausgabedateien"
  - "OUT (Linkeroption)"
  - "-OUT (Linkeroption)"
  - "Ausgabedateien, name (Linkeroption)"
ms.assetid: 976210a4-e51f-4cfb-af5e-c16344455834
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# /OUT (Ausgabedateiname)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/OUT:filename  
```  
  
## Hinweise  
 Hierbei ist:  
  
 *filename*  
 ein benutzerdefinierter Name für die Ausgabedatei.  Er wird anstelle des Standardnamens verwendet.  
  
## Hinweise  
 Die \/OUT\-Option überschreibt den Standardnamen und den Standardspeicherort des Programms, das der Linker erstellt.  
  
 Standardmäßig bildet der Linker den Dateinamen aus dem Basisnamen der zuerst angegebenen OBJ\-Datei und aus der entsprechenden Erweiterung \(**.exe** oder **.dll**\).  
  
 Mit dieser Option wird der Standardbasisname für eine MAP\-Datei oder eine Importbibliothek gebildet.  Ausführliche Informationen finden Sie unter [\/MAP \(Zuordnungsdatei generieren\)](../../build/reference/map-generate-mapfile.md) und [\/IMPLIB \(Name der Importbibliothek\)](../../build/reference/implib-name-import-library.md).  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Allgemein**.  
  
4.  Ändern Sie die Eigenschaft **Ausgabedatei**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)