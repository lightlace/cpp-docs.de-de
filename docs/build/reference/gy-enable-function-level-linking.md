---
title: "/Gy (Funktionslevel-Linking aktivieren)"
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
  - "VC.Project.VCCLCompilerTool.EnableFunctionLevelLinking"
  - "/gy"
  - "VC.Project.VCCLWCECompilerTool.EnableFunctionLevelLinking"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gy (Compileroption) [C++]"
  - "COMDAT-Funktion"
  - "Aktivieren der Verknüpfung auf Funktionsebene (Compileroption) [C++]"
  - "Gy (Compileroption) [C++]"
  - "-Gy (Compileroption) [C++]"
  - "Paketfunktionen"
ms.assetid: 0d3cf14c-ed7d-4ad3-b4b6-104e56f61046
caps.latest.revision: 17
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# /Gy (Funktionslevel-Linking aktivieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ermöglicht dem Compiler, einzelne Funktionen in Form von kompilierten Funktionen \(COMDATs\) zu kompilieren.  
  
## Syntax  
  
```  
/Gy[-]  
```  
  
## Hinweise  
 Der Linker erfordert, dass Funktionen separat als COMDATs zusammengepackt werden, um einzelne Funktionen in einer DLL oder einer EXE\-Datei ausschließen oder anordnen zu können.  
  
 Mit der [\/OPT \(Optimierungen\)](../../build/reference/opt-optimizations.md)\-Linkeroption können Sie nicht referenzierte Paketfunktionen aus der EXE\-Datei ausschließen.  
  
 Mit der [\/ORDER \(Reihenfolge von Funktionen festlegen\)](../../build/reference/order-put-functions-in-order.md)\-Linkeroption können Sie Paketfunktionen in einer angegebenen Reihenfolge in der EXE\-Datei ablegen.  
  
 Inlinefunktionen werden immer zu Paketfunktionen zusammengepackt, wenn sie als Aufrufe instanziiert werden \(beispielsweise wenn Inlining deaktiviert oder eine Funktionsadresse verwendet wird\).  Außerdem werden C\+\+\-Memberfunktionen, die innerhalb der Klassendeklaration definiert sind, automatisch zusammengepackt, andere Funktionen jedoch nicht. Die Auswahl dieser Option ist erforderlich, um sie als Paketfunktionen zu kompilieren.  
  
> [!NOTE]
>  Die zum Bearbeiten und Fortsetzen des Vorgangs verwendete [\/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)\-Option legt automatisch die **\/Gy**\-Option fest.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Codegenerierung**.  
  
4.  Ändern Sie die Eigenschaft **Funktionslevel\-Linking aktivieren**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)