---
title: "/MAP (Zuordnungsdatei generieren) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/map"
  - "VC.Project.VCLinkerTool.MapFileName"
  - "VC.Project.VCLinkerTool.GenerateMapFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MAP (Linkeroption)"
  - "Zuordnungsdatei generieren (Linkeroption)"
  - "MAP (Linkeroption)"
  - "-MAP (Linkeroption)"
  - "mapfile (Linkeroption)"
  - "Zuordnungsdateien, Erstellen des Linkers"
  - "Zuordnungsdateien, Informationen über das zu verknüpfende Programm"
  - "Zuordnungsdateien, Angeben des Dateinamens"
ms.assetid: 9ccce53d-4e36-43da-87b0-7603ddfdea63
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /MAP (Zuordnungsdatei generieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MAP[:filename]  
```  
  
## Hinweise  
 Hierbei ist:  
  
 *filename*  
 ein benutzerdefinierter Name für die Map\-Datei.  Er wird anstelle des Standardnamens verwendet.  
  
## Hinweise  
 Die \/MAP\-Option weist den Linker an, eine Zuordnungsdatei zu erstellen.  
  
 Der Linker gibt der MAP\-Datei standardmäßig den Basisnamen des Programms mit der Erweiterung **.map**.  Der optionale *Dateiname* ermöglicht das Überschreiben des Standardnamens einer MAP\-Datei.  
  
 Eine MAP\-Datei ist eine Textdatei, die die folgenden Informationen über das zu verknüpfende Programm enthält:  
  
-   Den Modulnamen, der dem Basisnamen der Datei entspricht  
  
-   Der Timestamp aus dem Header der Programmdatei \(nicht aus dem Dateisystem\)  
  
-   Eine Liste von Gruppen im Programm, mit Angabe der Startadresse \(als *section*:*offset*\), der Länge, des Gruppennamens und der Klasse für jede Gruppe  
  
-   Eine Liste der öffentlichen Symbole, mit Angabe der jeweiligen Adresse \(als *section*:*offset*\), dem jeweiligen Symbolnamen, der Adresse im linearen Adressraum und der OBJ\-Datei, in der das Symbol definiert ist  
  
-   Den Einstiegspunkt \(als *section*:*offset*\)  
  
 Die Option [\/MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md) gibt weitere Informationen an, die in der MAP\-Datei mit enthalten werden sollen.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Debuggen**.  
  
4.  Ändern Sie die Eigenschaft **Zuordnungsdatei generieren**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Weitere Informationen finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateMapFile*> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapFileName*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)