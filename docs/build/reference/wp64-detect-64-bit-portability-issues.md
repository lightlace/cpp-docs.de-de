---
title: "-Wp64 (nach 64-Bit-Portabilitätsproblemen suchen) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.Detect64BitPortabilityProblems
- VC.Project.VCCLCompilerTool.Detect64BitPortabilityProblems
- /wp64
dev_langs:
- C++
helpviewer_keywords:
- 64-bit compiler [C++], detecting portability problems
- /Wp64 compiler option [C++]
- -Wp64 compiler option [C++]
- Wp64 compiler option [C++]
ms.assetid: 331ae5aa-e627-4d03-8f63-dd2c2d76dadd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 59784b713ce1c40cb9b946bc885827fb7141772f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="wp64-detect-64-bit-portability-issues"></a>/Wp64 (Nach 64-Bit-Portabilitätsproblemen suchen)

Diese Compileroption ist veraltet. In Versionen von Visual Studio vor Visual Studio 2013 werden dadurch 64-Bit-Portabilitätsprobleme für Typen ermittelt, die mit dem Schlüsselwort [__w64](../../cpp/w64.md) markiert sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Wp64  
```  
  
## <a name="remarks"></a>Hinweise  

In Versionen vor Visual Studio 2013, Visual Studio standardmäßig die **/Wp64** Compileroption ist deaktiviert, in der Visual C++-Compiler, die 32-Bit-X86 erstellt Code, und auf in Visual C++-Compiler, die 64-Bit-X64 erstellt Code.  
  
> [!IMPORTANT]
>  Die [/Wp64](../../build/reference/wp64-detect-64-bit-portability-issues.md) Compileroption und das [__w64](../../cpp/w64.md) -Schlüsselwort sind in Visual Studio 2010 und Visual Studio 2012 veraltet und werden ab Visual Studio 2013 nicht mehr unterstützt. Wenn Sie ein Projekt konvertieren, das diesen Schalter verwendet, wird der Schalter während der Konvertierung nicht migriert. Um diese Option in Visual Studio 2010 oder Visual Studio 2012 zu verwenden, müssen Sie den Compilerschalter unter **Zusätzliche Optionen** im **Befehlszeilenabschnitt** der Projekteigenschaften eingeben. Wenn Sie die **/Wp64** -Compileroption in der Befehlszeile verwenden, gibt der Compiler eine Befehlszeilenwarnung D9002 aus. Verwenden Sie statt dieser Option und dieses Schlüsselworts zum Ermitteln von 64-Bit-Portabilitätsproblemen einen Visual C++-Compiler, der für eine 64-Bit-Plattform konzipiert ist, und geben Sie die [/W4](../../build/reference/compiler-option-warning-level.md) -Option an. Weitere Informationen finden Sie unter [Konfigurieren von Visual C++ für die 64-Bit-X64 Ziele](../../build/configuring-programs-for-64-bit-visual-cpp.md).  
  
Variablen der folgenden Typen werden auf einem 32-Bit-Betriebssystem getestet, als ob sie auf einem 64-Bit-Betriebssystem verwendet würden:  
  
-   int  
  
-   long  
  
-   pointer  
  
 Wenn Sie die Anwendung regelmäßig mit einem Compiler, die 64-Bit-X64 builds kompilieren Code, Sie können nur deaktivieren, **/Wp64** in den 32-Bit-Kompilierungen, da der 64-Bit-Compiler alle Probleme erkennt. Weitere Informationen zum abzielen auf ein Windows-64-Bit-Betriebssystem finden Sie unter [Konfigurieren von Visual C++ für die 64-Bit-X64 Ziele](../../build/configuring-programs-for-64-bit-visual-cpp.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  
  
     Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Ändern Sie das Feld **Zusätzliche Optionen** so, dass **/Wp64**eingeschlossen ist.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Detect64BitPortabilityProblems%2A>.  
  
## <a name="see-also"></a>Siehe auch  

[Compileroptionen](../../build/reference/compiler-options.md)   
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
[Konfigurieren von Visual C++ für 64-Bit-x64-Ziele](../../build/configuring-programs-for-64-bit-visual-cpp.md)