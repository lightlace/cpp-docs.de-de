---
title: "/Ge (Stapel&#252;berpr&#252;fungen aktivieren)"
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
  - "/ge"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Ge (Compileroption) [C++]"
  - "Aktivieren der Stapelüberprüfungen"
  - "Ge (Compileroption) [C++]"
  - "-Ge (Compileroption) [C++]"
  - "Stapelüberprüfungsaufrufe"
  - "Stapelüberprüfungen"
  - "Stapel, Stapelüberprüfungen"
ms.assetid: 4b54deae-4e3c-4bfa-95f3-ba23590f7258
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# /Ge (Stapel&#252;berpr&#252;fungen aktivieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Option aktiviert die Stapelüberprüfung für jeden Funktionsaufruf, der Speicherplatz für lokale Variablen erfordert.  
  
## Syntax  
  
```  
/Ge  
```  
  
## Hinweise  
 Dieser Mechanismus ist sinnvoll, wenn Sie die Funktionalität der Stapelüberprüfung neu schreiben.  Es wird empfohlen, die Option [\/Gh \(\_penter\-Hookfunktion aktivieren\)](../../build/reference/gh-enable-penter-hook-function.md) zu verwenden, statt die Stapelüberprüfungen neu zu schreiben.  
  
 [\/Gs \(Stapel\-Überprüfungsaufrufe kontrollieren\)](../../build/reference/gs-control-stack-checking-calls.md) hat dieselbe Wirkung.  
  
 **\/Ge** ist veraltet. Der Compiler generiert die Stapelprüfung.  Weitere Informationen finden Sie unter [Deprecated Compiler Options in Visual C\+\+ 2005](assetId:///aa59fce3-50b8-4f66-9aeb-ce09a7a84cce).  
  
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