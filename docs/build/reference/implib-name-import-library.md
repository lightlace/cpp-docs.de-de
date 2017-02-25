---
title: "/IMPLIB (Name der Importbibliothek) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/implib"
  - "VC.Project.VCLinkerTool.ImportLIbrary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/IMPLIB (Linkeroption)"
  - "IMPLIB (Linkeroption)"
  - "-IMPLIB (Linkeroption)"
  - "Importbibliotheken, Überschreiben des Standardnamens"
ms.assetid: fe8f71ab-7055-41b5-8ef8-2b97cfa4a432
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /IMPLIB (Name der Importbibliothek)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/IMPLIB:filename  
```  
  
## Hinweise  
 Hierbei ist:  
  
 *filename*  
 ein benutzerdefinierter Name für die Importbibliothek.  Er wird anstelle des Standardnamens verwendet.  
  
## Hinweise  
 Mit der Option **\/IMPLIB** wird der Standardname für die Importbibliothek, die **LINK** bei der Erstellung eines Programms mit Exporten erstellt, überschrieben.  Der Standardname wird aus dem Basisnamen der Hauptausgabedatei und der Erweiterung **.lib** zusammengesetzt.  Ein Programm enthält Exporte, wenn einer oder mehrere der folgenden Punkte angegeben wurden:  
  
-   Das [\_\_declspec\(dllexport\)](../../cpp/dllexport-dllimport.md)\-Schlüsselwort im Quellcode  
  
-   Eine [EXPORTS](../../build/reference/exports.md)\-Anweisung in einer DEF\-Datei  
  
-   Eine [\/EXPORT](../../build/reference/export-exports-a-function.md)\-Spezifikation in einem **LINK**\-Befehl  
  
 **LINK** berücksichtigt **\/IMPLIB** nicht, wenn keine Importbibliothek erstellt wird.  Dies ist dann der Fall, wenn **LINK** keine Importbibliothek erstellt.  Wenn im Buildvorgang eine Exportdatei verwendet wird, nimmt **LINK** an, dass bereits eine Importbibliothek vorhanden ist und erstellt somit keine weitere Bibliothek.  Weitere Informationen über Importbibliotheken und Exportdateien finden Sie unter [LIB\-Referenz](../../build/reference/lib-reference.md).  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Erweitert**.  
  
4.  Ändern Sie die Eigenschaft **Bibliothek importieren**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ImportLibrary*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)