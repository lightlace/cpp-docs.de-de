---
title: "/favor (Optimieren f&#252;r Besonderheiten der Architektur) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/favor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "-favor (Compileroption) [C++]"
  - "/favor (Compileroption) [C++]"
ms.assetid: ad264df2-e30f-4d68-8bd0-10d6bee71a2a
caps.latest.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 31
---
# /favor (Optimieren f&#252;r Besonderheiten der Architektur)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/favor:** `option` erstellt den Code, der für eine bestimmte Architektur oder für die Besonderheiten der MikroArchitekturen in AMD und in den Intel\-Architekturen optimiert ist.  
  
## Syntax  
  
```  
/favor:{blend | ATOM | AMD64 | INTEL64}  
```  
  
## Hinweise  
 **\/favor:blend**  
 \(x86 und x64\) erzeugt den Code, der für die Besonderheiten der MikroArchitekturen in AMD und in den Intel\-Architekturen optimiert ist.  Während **\/favor:blend** möglicherweise keine optimale Leistung gibt, die auf einen bestimmten Prozessor möglich ist, sie entworfen, um die optimale Leistung über einem Breitzeichen Spektrum von x86 und von x64\-Prozessoren zu geben.  Standardmäßig ist die **\/favor:blend** wirksam.  
  
 **\/favor:ATOM**  
 \(x86 und x64\) erzeugt den Code, der für die Besonderheiten der Prozessor Intel Atom und Prozessor\-Technologie Intel Centrino Atom optimiert ist.  Code, der möglicherweise wird generiert, indem **\/favor:ATOM** verwendet, auch Anweisungen Intel SSSE3, SSE3, SSE2\-Anweisungen und SSE für Intel\-Prozessoren erzeugt.  
  
 **\/favor:AMD64**  
 \(nur x64\) optimiert den generierten Code für Opteron AMD und Athlon\-Prozessoren, die 64\-Bit\-Erweiterungen unterstützen.  Die optimierte Code kann auf alle kompatiblen Plattformen x64\-Plattform ausgeführt werden.  Code, der möglicherweise wird generiert, indem **\/favor:AMD64** verwendet, ungültigere Leistung auf Intel\-Prozessoren verursacht, die Intel64 unterstützen.  
  
 **\/favor:INTEL64**  
 \(nur x64\) optimiert den generierten Code für Intel\-Prozessoren, die Intel64 unterstützen, das normalerweise bessere Leistung für diese Plattform führt.  Der resultierende Code können beliebige x64\-Plattform ausgeführt werden.  Code, der möglicherweise wird generiert mit **\/favor:INTEL64** ungültigere Leistung auf Opteron AMD und Athlon\-Prozessoren verursacht, die 64\-Bit\-Erweiterungen unterstützen.  
  
> [!NOTE]
>  Intel64\-Architektur war vorher als Extended Memory 64 Technology bekannt, und die entsprechende Compileroption war **\/favor:EM64T**.  
  
 Informationen darüber, wie [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] für die Architektur, finden Sie unter [x64\-Softwarekonventionen](../../build/x64-software-conventions.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Wählen Sie den Ordner **C\/C\+\+** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Befehlszeile** aus.  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)