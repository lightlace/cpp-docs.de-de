---
title: "/Fm (Name der Zuordnungsdatei)"
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
  - "/fm"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Fm (Compileroption) [C++]"
  - "Dateien [C++], Erstellen einer Zuordnung"
  - "Fm (Compileroption) [C++]"
  - "-Fm (Compileroption) [C++]"
  - "Zuordnungsdateien [C++], Erstellen des Linkers"
ms.assetid: 8154448a-93a7-4546-8e4c-5c44d0aff45d
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# /Fm (Name der Zuordnungsdatei)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Option weist den Linker an, eine Zuordnungsdatei mit einer Liste von Segmenten in derselben Reihenfolge zu erstellen wie in der entsprechenden EXE\-Datei oder DLL.  
  
## Syntax  
  
```  
/Fmpathname  
```  
  
## Hinweise  
 Standardmäßig erhält die MAP\-Datei den Basisnamen der entsprechenden C\- oder C\+\+\-Quelldatei mit der Erweiterung **.map**.  
  
 Die Angabe von **\/Fm** hat die dieselbe Wirkung wie die Angabe der [\/MAP \(Zuordnungsdatei generieren\)](../../build/reference/map-generate-mapfile.md)\-Linkeroption.  
  
 Bei der Angabe von [\/c \(Kompilieren ohne Verknüpfen\)](../../build/reference/c-compile-without-linking.md) zum Unterdrücken der Verknüpfung hat **\/Fm** keine Auswirkungen.  
  
 Globale Symbole in einer MAP\-Datei haben gewöhnlich einen oder mehrere führende Unterstriche, weil der Compiler am Anfang von Variablennamen einen Unterstrich einfügt.  Viele der globalen Symbole in einer MAP\-Datei werden intern vom Compiler und den Standardbibliotheken verwendet.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [\/F\-Optionen \(Ausgabedateioptionen\)](../../build/reference/output-file-f-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)