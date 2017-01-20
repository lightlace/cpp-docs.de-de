---
title: "/Fe (Name der EXE-Datei)"
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
  - "/fe"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Fe (Compileroption) [C++]"
  - "Ausführbare Dateien, Umbenennen"
  - "Fe (Compileroption) [C++]"
  - "-Fe (Compileroption) [C++]"
  - "Datei umbenennen (Compileroption) [C++]"
ms.assetid: 49f594fd-5e94-45fe-a1bf-7c9f2abb6437
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# /Fe (Name der EXE-Datei)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit dieser Option werden ein Name und ein Verzeichnis für die vom Compiler erstellte EXE\-Datei oder DLL festgelegt.  
  
## Syntax  
  
```  
/Fepathname  
```  
  
## Hinweise  
 Ohne diese Option weist der Compiler der Datei einen Standardnamen zu, der sich aus dem Basisnamen der in der Befehlszeile zuerst angegebenen Quell\- oder Objektdatei und der entsprechenden Erweiterung \(.**exe** oder **.dll**\) zusammensetzt.  
  
 Bei Angabe der Option [\/c \(Kompilieren ohne Verknüpfen\)](../../build/reference/c-compile-without-linking.md) zum Kompilieren ohne Verknüpfen hat **\/Fe** keine Auswirkungen.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Allgemein**.  
  
4.  Ändern Sie die Eigenschaft **Ausgabedatei**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile*>.  
  
## Beispiel  
 Mit der nachfolgenden Befehlszeile werden alle C\-Quelldateien im aktuellen Verzeichnis kompiliert und verknüpft.  Die resultierende ausführbare Datei erhält den Namen **PROCESS.exe** und wird im Verzeichnis **C:\\BIN** erstellt.  
  
```  
CL /FeC:\BIN\PROCESS *.C  
```  
  
## Beispiel  
 Mit der folgenden Befehlszeile wird eine ausführbare Datei im Verzeichnis `C:\BIN` erstellt, die denselben Basisnamen wie die erste Quell\- oder Objektdatei hat:  
  
```  
CL /FeC:\BIN\ *.C  
```  
  
## Siehe auch  
 [\/F\-Optionen \(Ausgabedateioptionen\)](../../build/reference/output-file-f-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)