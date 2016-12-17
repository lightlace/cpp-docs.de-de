---
title: "/Wp64 (Nach 64-Bit-Portabilit&#228;tsproblemen suchen)"
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
  - "VC.Project.VCCLWCECompilerTool.Detect64BitPortabilityProblems"
  - "VC.Project.VCCLCompilerTool.Detect64BitPortabilityProblems"
  - "/wp64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Wp64 (Compileroption) [C++]"
  - "64-Bit-Compiler [C++], Suchen nach Portabilitätsproblemen"
  - "Wp64 (Compileroption) [C++]"
  - "-Wp64 (Compileroption) [C++]"
ms.assetid: 331ae5aa-e627-4d03-8f63-dd2c2d76dadd
caps.latest.revision: 21
caps.handback.revision: "21"
ms.author: "corob"
manager: "ghogen"
---
# /Wp64 (Nach 64-Bit-Portabilit&#228;tsproblemen suchen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Compileroption ist veraltet. In Versionen von Visual Studio vor Visual Studio 2013 werden dadurch 64\-Bit\-Portabilitätsprobleme für Typen ermittelt, die mit dem Schlüsselwort [\_\_w64](../../cpp/w64.md) markiert sind.  
  
## Syntax  
  
```  
/Wp64  
```  
  
## Hinweise  
 In Versionen von Visual Studio vor Visual Studio 2013, ist die **\/Wp64**\-Compileroption im Visual C\+\+\-Compiler \(32 Bit\) standardmäßig deaktiviert und der Visual C\+\+\-Compiler \(64 Bit\) standardmäßig aktiviert.  
  
> [!IMPORTANT]
>  Die [\/Wp64](../../build/reference/wp64-detect-64-bit-portability-issues.md) Compileroption und das [\_\_w64](../../cpp/w64.md)\-Schlüsselwort sind in Visual Studio 2010 und Visual Studio 2012 veraltet und werden ab Visual Studio 2013 nicht mehr unterstützt. Wenn Sie ein Projekt konvertieren, das diesen Schalter verwendet, wird der Schalter während der Konvertierung nicht migriert. Um diese Option in Visual Studio 2010 oder Visual Studio 2012 zu verwenden, müssen Sie den Compilerschalter unter **Zusätzliche Optionen** im Befehlszeilenabschnitt der Projekteigenschaften eingeben. Wenn Sie die **\/Wp64**\-Compileroption in der Befehlszeile verwenden, gibt der Compiler eine Befehlszeilenwarnung D9002 aus. Verwenden Sie statt dieser Option und dieses Schlüsselworts zum Ermitteln von 64\-Bit\-Portabilitätsproblemen einen Visual C\+\+\-Compiler, der für eine 64\-Bit\-Plattform konzipiert ist, und geben Sie die [\/W4](../../build/reference/compiler-option-warning-level.md)\-Option an. Weitere Informationen finden Sie unter [Konfigurieren von Programmen für 64\-Bit](../../build/configuring-programs-for-64-bit-visual-cpp.md).  
  
 Variablen der folgenden Typen werden auf einem 32\-Bit\-Betriebssystem getestet, als ob sie auf einem 64\-Bit\-Betriebssystem verwendet würden:  
  
-   int  
  
-   long  
  
-   pointer  
  
 Wenn Sie die Anwendung regelmäßig mit einem 64\-Bit\-Compiler kompilieren, können Sie **\/Wp64** in den 32\-Bit\-Kompilierungen einfach deaktivieren, da der 64\-Bit\-Compiler alle Probleme erkennt. Weitere Informationen zum Abzielen auf ein Windows\-64\-Bit\-Betriebssystem finden Sie unter [Konfigurieren von Programmen für 64\-Bit](../../build/configuring-programs-for-64-bit-visual-cpp.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  
  
     Weitere Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Ändern Sie das Feld **Zusätzliche Optionen** so, dass **\/Wp64** eingeschlossen ist.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Detect64BitPortabilityProblems*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Konfigurieren von Programmen für 64\-Bit](../../build/configuring-programs-for-64-bit-visual-cpp.md)