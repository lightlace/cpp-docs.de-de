---
title: ".LIB-Dateien als Linkereingabe"
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
  - "VC.Project.VCLinkerTool.AdditionalDependencies"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".lib-Dateien"
  - "COFF-Dateien, Importbibliotheken"
  - "Standardbibliotheken [C++]"
  - "Standardbibliotheken [C++], Linkerausgabe"
  - "Standardwerte [C++], Bibliotheken"
  - "Importbibliotheken, Linkerdateien"
  - "Bibliotheken [C++], LIB-Dateien als Linkereingabe"
  - "Verknüpfen [C++], OMF-Bibliotheken"
  - "OMF-Bibliotheken"
ms.assetid: dc5d2b1c-2487-41fa-aa71-ad1e0647958b
caps.latest.revision: 15
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# .LIB-Dateien als Linkereingabe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**LINK** akzeptiert COFF\-Standardbibliotheken und COFF\-Importbibliotheken. Beide haben gewöhnlich die Dateierweiterung **.lib**.  Standardbibliotheken enthalten Objekte und werden durch das LIB\-Tool erstellt.  Importbibliotheken enthalten Informationen über Exporte in andere Programme und werden entweder durch **LINK** bei der Erstellung eines Programms, das Exporte enthält, oder durch das LIB\-Tool erstellt.  Weitere Informationen über die Verwendung von **LIB** zur Erstellung von Standard\- und Importbibliotheken finden Sie in der [LIB\-Referenz](../../build/reference/lib-reference.md).  Einzelheiten über die Verwendung von **LINK** zur Erstellung einer Importbibliothek finden Sie unter der Option [\/DLL](../../build/reference/dll-build-a-dll.md).  
  
 Eine Bibliothek wird für **LINK** entweder als Dateinamenargument oder als Standardbibliothek angegeben.  **LINK** löst externe Verweise auf, indem zuerst die in der Befehlszeile angegebenen Bibliotheken durchsucht werden, dann die mit der Option [\/DEFAULTLIB](../../build/reference/defaultlib-specify-default-library.md) festgelegten Standardbibliotheken und danach die in den OBJ\-Dateien benannten Standardbibliotheken.  Wenn zu dem Bibliotheksnamen ein Pfad angegeben ist, sucht **LINK** in diesem Verzeichnis nach der Bibliothek.  Wurde kein Pfad angegeben, sucht **LINK** zunächst in dem Verzeichnis, aus dem das Programm aufgerufen wurde, und dann in den Verzeichnissen, die in der LIB\-Umgebungsvariablen angegeben sind.  
  
### So fügen Sie LIB\-Dateien als Linker\-Eingabe in die Entwicklungsumgebung ein  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Eingabe**.  
  
4.  Bearbeiten Sie die Eigenschaft **Zusätzliche Abhängigkeiten**.  
  
### So fügen Sie LIB\-Dateien als Linker\-Eingabe programmgesteuert ein  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalDependencies*>.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie eine LIB\-Datei erstellt und verwendet wird:  
  
```  
// lib_link_input_1.cpp  
// compile with: /LD  
__declspec(dllexport) int Test() {  
   return 213;  
}  
```  
  
## Beispiel  
 und anschließend:  
  
```  
// lib_link_input_2.cpp  
// compile with: /EHsc lib_link_input_1.lib  
__declspec(dllimport) int Test();  
#include <iostream>  
int main() {  
   std::cout << Test() << std::endl;  
}  
```  
  
  **213**   
## Siehe auch  
 [LINK\-Eingabedateien](../../build/reference/link-input-files.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)