---
title: "/U, /u (Symboldefinitionen aufheben)"
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
  - "VC.Project.VCCLCompilerTool.UndefinePreprocessorDefinitions"
  - "VC.Project.VCCLWCECompilerTool.UndefinePreprocessorDefinitions"
  - "VC.Project.VCCLCompilerTool.UndefineAllPreprocessorDefinitions"
  - "/u"
  - "VC.Project.VCCLWCECompilerTool.UndefineAllPreprocessorDefinitions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/U (Compileroption) [C++]"
  - "U (Compileroption) [C++]"
  - "-U (Compileroption) [C++]"
  - "Symboldefinitionen aufheben (Compileroption)"
ms.assetid: 7bc0474f-6d1f-419b-807d-0d8816763b2a
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# /U, /u (Symboldefinitionen aufheben)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **\/U**\-Compileroption hebt die Definition des angegebenen Präprozessorsymbols auf.  Die **\/u**\-Compileroption hebt die Definition der Microsoft\-spezifischen Symbole auf, die der Compiler definiert.  
  
## Syntax  
  
```  
/U[ ]symbol  
/u  
```  
  
## Argumente  
 `symbol`  
 Das Präprozessorsymbol, dessen Definition aufgehoben werden soll.  
  
## Hinweise  
 Mit den Optionen **\/U** und **\/u** können keine Symboldefinitionen aufgehoben werden, die mit der **\#define**\-Direktive erstellt wurden.  
  
 Mit der **\/U**\-Option kann eine Symboldefinition aufgehoben werden, die zuvor mit der Option **\/D** definiert wurde.  
  
 Standardmäßig definiert der Compiler die folgenden Microsoft\-spezifischen Symbole.  
  
|Symbol|Funktion|  
|------------|--------------|  
|\_CHAR\_UNSIGNED|Standardmäßig unsigned char.  Definiert, wenn die [\/J](../../build/reference/j-default-char-type-is-unsigned.md)\-Option angegeben wird.|  
|\_CPPRTTI|Definiert für Code, der mit der [\/GR](../../build/reference/gr-enable-run-time-type-information.md)\-Option kompiliert wurde.|  
|\_CPPUNWIND|Definiert für Code, der mit der [\/EHsc](../../build/reference/eh-exception-handling-model.md)\-Option kompiliert wurde.|  
|\_DLL|Definiert, wenn die [\/MD](../../build/reference/md-mt-ld-use-run-time-library.md)\-Option angegeben wird.|  
|\_M\_IX86|Standardmäßig für x86\-Ziele auf 600 festgelegt.|  
|\_MSC\_VER|Weitere Informationen finden Sie unter [Vordefinierte Makros](../../preprocessor/predefined-macros.md).|  
|\_WIN32|Definiert für WIN32\-Anwendungen.  Immer definiert.|  
|\_MT|Definiert, wenn die Option [\/MD oder \/MT](../../build/reference/md-mt-ld-use-run-time-library.md) angegeben wird.|  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Erweitert**.  
  
4.  Ändern Sie die Eigenschaften **Präprozessordefinitionen aufheben** oder **Alle Präprozessordefinitionen aufheben**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefineAllPreprocessorDefinitions*> oder <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefinePreprocessorDefinitions*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [\/J \(Standardmäßig "unsigned char"\)](../../build/reference/j-default-char-type-is-unsigned.md)   
 [\/GR \(Laufzeit\-Typeninformation aktivieren\)](../../build/reference/gr-enable-run-time-type-information.md)   
 [\/EH \(Ausnahmebehandlungsmodell\)](../../build/reference/eh-exception-handling-model.md)   
 [\/MD, \/MT, \/LD \(Laufzeitbibliothek verwenden\)](../../build/reference/md-mt-ld-use-run-time-library.md)