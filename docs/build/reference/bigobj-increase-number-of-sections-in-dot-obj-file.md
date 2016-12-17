---
title: "/bigobj (Erh&#246;hen der Anzahl von Abschnitten in der OBJ-Datei)"
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
  - "/bigobj"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/bigobj (Compileroption) [C++]"
  - "bigobj (Compileroption) [C++]"
  - "-bigobj (Compileroption) [C++]"
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# /bigobj (Erh&#246;hen der Anzahl von Abschnitten in der OBJ-Datei)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Durch **\/bigobj** wird die Anzahl von Abschnitten erhöht, die in einer Objektdatei enthalten sein dürfen.  
  
## Syntax  
  
```  
/bigobj  
```  
  
## Hinweise  
 In der Standardeinstellung kann eine Objektdatei bis zu 65.536 \(2^16\) adressierbare Abschnitte enthalten.  Dabei spielt es keine Rolle, welche Zielplattform angegeben ist.  Durch **\/bigobj** wird diese Adressenkapazität auf 4.294.967.296 \(2^32\) erhöht.  
  
 Von den meisten Modulen werden keine OBJ\-Dateien erzeugt, die mehr als 65.536 Abschnitte enthalten.  Für computergenerierten Code oder Code, in dem häufig Gebrauch von Vorlagenbibliotheken gemacht wird, sind allerdings unter Umständen OBJ\-Dateien erforderlich, die mehr Abschnitte enthalten.  **\/bigobj** ist in Windows Store\-Projekten standardmäßig aktiviert, da der computergenerierte XAML\-Code viele Header enthält.  Wenn Sie diese Option in einem Windows Store\-App\-Projekt deaktivieren, ist es wahrscheinlich, dass der Compilerfehler C1128 auftritt.  
  
 Linker, die in früheren Versionen als Visual C\+\+ 2005 enthalten sind, können keine OBJ\-Dateien lesen, die mit **\/bigobj** generiert wurden.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)