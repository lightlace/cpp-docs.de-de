---
title: "/vmb, /vmg (Darstellungsmethode)"
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
  - "/vmb"
  - "/vmg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/vmb (Compileroption) [C++]"
  - "/vmg (Compileroption) [C++]"
  - "Darstellungsmethode (Compileroptionen) [C++]"
  - "vmb (Compileroption) [C++]"
  - "-vmb (Compileroption) [C++]"
  - "vmg (Compileroption) [C++]"
  - "-vmg (Compileroption) [C++]"
ms.assetid: ecdb391c-7dab-40b1-916b-673d10889fd4
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# /vmb, /vmg (Darstellungsmethode)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Optionen legen fest, mit welcher Methode der Compiler die Zeiger auf Klassenmember darstellt.  
  
 Verwenden Sie **\/vmb**, wenn Sie immer eine Klasse definieren, bevor Sie einen Zeiger auf einen Member dieser Klasse deklarieren.  
  
 Verwenden Sie **\/vmg**, um einen Zeiger auf einen Member einer Klasse zu deklarieren, bevor Sie die Klasse definieren.  Diese Notwendigkeit kann entstehen, wenn Sie Member in zwei verschiedenen Klassen definieren, die aufeinander verweisen.  Bei solchen Klassen mit gegenseitigem Verweis muss auf eine Klasse verwiesen werden, bevor diese definiert wird.  
  
## Syntax  
  
```  
/vmb  
/vmg  
```  
  
## Hinweise  
 Sie können auch [pointers\_to\_members](../../preprocessor/pointers-to-members.md) oder [Vererbungsschlüsselwörter](../../cpp/inheritance-keywords.md) im Code verwenden, um eine Zeigerdarstellung festzulegen.  
  
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