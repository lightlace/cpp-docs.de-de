---
title: "/GZ (Laufzeitfehler&#252;berpr&#252;fung f&#252;r Stapelrahmen aktivieren)"
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
  - "/gz"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gz (Compileroption) [C++]"
  - "Debugbuilds, Abfangen von Releasebuildfehlern"
  - "Gz (Compileroption) [C++]"
  - "-Gz (Compileroption) [C++]"
  - "Releasebuildfehler"
ms.assetid: b3efeeff-d5e3-4057-91c9-f6fc73d0270c
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# /GZ (Laufzeitfehler&#252;berpr&#252;fung f&#252;r Stapelrahmen aktivieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Führt die gleichen Operationen wie die [\/RTC \(Laufzeitfehlerüberprüfungen\)](../../build/reference/rtc-run-time-error-checks.md)\-Option aus.  Veraltet.  
  
## Syntax  
  
```  
/GZ  
```  
  
## Hinweise  
 **\/GZ** ist nur zur Verwendung in einem nicht optimierten \([\/Od \(Deaktivieren \(Debuggen\)\)](../../build/reference/od-disable-debug.md)\) Build geeignet.  
  
 **\/GZ** ist veraltet. Verwenden Sie stattdessen [\/RTC \(Laufzeitfehlerüberprüfungen\)](../../build/reference/rtc-run-time-error-checks.md).  Weitere Informationen finden Sie unter [Deprecated Compiler Options in Visual C\+\+ 2005](assetId:///aa59fce3-50b8-4f66-9aeb-ce09a7a84cce).  
  
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