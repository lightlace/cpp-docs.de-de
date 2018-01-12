---
title: "-favor (optimieren für Besonderheiten der Architektur) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /favor
dev_langs: C++
helpviewer_keywords:
- -favor compiler option [C++]
- /favor compiler option [C++]
ms.assetid: ad264df2-e30f-4d68-8bd0-10d6bee71a2a
caps.latest.revision: "31"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4f9ec5882cb1535f089250bc467c795263132d35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="favor-optimize-for-architecture-specifics"></a>/favor (Optimieren für Besonderheiten der Architektur)
**/ favor:** `option` erzeugt Code, der für eine bestimmte Architektur oder für spezifische Merkmale der Mikroarchitekturen von-der AMD und der Intel-Architekturen optimiert ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
/favor:{blend | ATOM | AMD64 | INTEL64}  
```  
  
## <a name="remarks"></a>Hinweise  
 **/ favor: Blend**  
 (X86- und X64) erzeugt Code, der für spezifische Merkmale der Mikroarchitekturen von-der AMD und der Intel-Architekturen optimiert ist. Während **/favor: Blend** erzielen möglicherweise nicht die optimale Leistung möglich für einen bestimmten Prozessor, es bietet die beste Leistung über eine Breite Palette von X86- und X64 Prozessoren. Standardmäßig **/favor: Blend** wirksam wird.  
  
 **/favor:Atom**  
 (X86- und X64) erzeugt Code, der für die Einzelheiten der Intel Atom-Prozessor und Intel Centrino Atom-Prozessor-Technologie optimiert ist. Mithilfe von generierten Code **/favor:ATOM** auch Intel SSSE3, SSE3 SSE2 und SSE-Anweisungen für Intel-Prozessoren erzeugen.  
  
 **/favor:AMD64**  
 (nur X64) optimiert den generierten Code für die AMD Opteron und Athlon-Prozessoren, die 64-Bit-Erweiterungen unterstützen. Der optimierte Code kann auf alle X64 kompatible Plattformen ausgeführt. Mithilfe von generierten Code **/favor:AMD64** möglicherweise schlechter Leistung auf Intel-Prozessoren, die Intel64 unterstützen.  
  
 **/favor:Intel64**  
 (nur X64) optimiert den generierten Code für Intel-Prozessoren, die Intel64, zu unterstützen, die in der Regel eine bessere Leistung für diese Plattform ergibt. Der resultierende Code kann auf alle X64 ausführen Plattform. Mit generierten Code **/favor:INTEL64** möglicherweise schlechter Leistung AMD Opteron und Athlon-Prozessoren, die 64-Bit-Erweiterungen unterstützen.  
  
> [!NOTE]
>  Intel64-Architektur wurde zuvor als Extended Memory 64 Technology bezeichnet, und die entsprechende Compileroption wurde **/favor:EM64T**.  
  
 Informationen über das Programm für die [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] -Architektur finden Sie unter [X64 Softwarekonventionen](../../build/x64-software-conventions.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **C/C++-** Ordner.  
  
3.  Wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
4.  Geben Sie die Compileroption "in der **Zusatzoptionen** Feld.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)