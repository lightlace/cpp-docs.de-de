---
title: "/FC (Vollst&#228;ndiger Pfad der Quellcodedatei in Diagnostik) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.UseFullPaths"
  - "/FC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FC (Compileroption) [C++]"
  - "-FC (Compileroption) [C++]"
ms.assetid: 1f11414e-cb42-421b-be68-9d369aab036b
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /FC (Vollst&#228;ndiger Pfad der Quellcodedatei in Diagnostik)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Veranlasst den Compiler, während der Diagnostik den vollständigen Pfad der übergebenen Quellcodedateien anzuzeigen.  
  
## Syntax  
  
```  
/FC  
```  
  
## Hinweise  
 Betrachten Sie das folgende Codebeispiel:  
  
```  
// compiler_option_FC.cpp  
int main( ) {  
   int i   // C2143  
}  
```  
  
 Ohne **\/FC** würde ein Diagnosetext ähnlich dem Folgenden generiert werden:  
  
-   compiler\_option\_FC.cpp\(5\) : Fehler C2143: Syntaxfehler : ';' fehlt vor '}'  
  
 Mit **\/FC** würde ein Diagnosetext ähnlich dem Folgenden generiert werden:  
  
-   c:\\test\\compiler\_option\_FC.cpp\(5\) : Fehler C2143: Syntaxfehler : ';' fehlt vor '}'  
  
 **\/FC** ist auch erforderlich, wenn bei Verwendung des Makros \_\_FILE\_\_ der vollständige Pfad eines Dateinamens angezeigt werden soll.  Weitere Informationen zu \_\_FILE\_\_ finden Sie unter [Vordefinierte Makros](../../preprocessor/predefined-macros.md).  
  
 Die **\/FC**\-Option wird von **\/ZI** impliziert.  Weitere Informationen zu **\/ZI** finden Sie unter [\/Z7, \/Zi, \/ZI \(Debuginformationsformat\)](../../build/reference/z7-zi-zi-debug-information-format.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften**.  
  
3.  Erweitern Sie den Knoten **C\/C\+\+**.  
  
4.  Wählen Sie die Eigenschaftenseite **Erweitert** aus.  
  
5.  Ändern Sie die Eigenschaft **Vollständige Pfade verwenden**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UseFullPaths*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)