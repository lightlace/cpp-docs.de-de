---
title: "/arch (x64) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: ecda22bf-5bed-43f4-99fb-88aedd83d9d8
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /arch (x64)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt die Architektur für die Codegenerierung auf x64 an.  Siehe auch [\/arch \(x86\)](../../build/reference/arch-x86.md) und [\/arch \(ARM\)](../../build/reference/arch-arm.md).  
  
## Syntax  
  
```  
/arch:[AVX|AVX2]  
```  
  
## Argumente  
 **\/arch:AVX**  
 Aktiviert die Verwendung von Intel Advanced Vector Extensions\-Anweisungen.  
  
 **\/arch:AVX2**  
 Aktiviert die Verwendung von Intel Advanced Vector Extensions 2\-Anweisungen.  
  
## Hinweise  
 **\/arch** wirkt sich nur auf die Codegenerierung für systemeigene Funktionen aus.  Wenn Sie Kompilierungsvorgänge mit [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) ausführen, hat **\/arch** keine Auswirkungen auf die Codegenerierung für verwaltete Funktionen.  
  
 Es wird das `__AVX__`\-Präprozessorsymbol verwendet, wenn die **\/arch:AVX**\-Compileroption angegeben wird.  Es wird das `__AVX2__`\-Präprozessorsymbol verwendet, wenn die **\/arch:AVX2**\-Compileroption angegeben wird.  Weitere Informationen finden Sie unter [Vordefinierte Makros](../../preprocessor/predefined-macros.md).  Die Option **\/arch:AVX2** wurde in Visual Studio 2013 Update 2 Version 12.0.34567.1 eingeführt.  
  
### So legen Sie die \/arch:AVX\- oder \/arch:AVX2\-Compileroption in Visual Studio fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** für das Projekt.  Weitere Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Wählen Sie den Ordner **Konfigurationseigenschaften**, **C\/C\+\+** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Codegenerierung** aus.  
  
4.  Wählen Sie im Dropdown\-Feld **Erweitertes Anweisungsset aktivieren Advanced Vector Extensions \(\/arch:AVX\)** oder **Advanced Vector Extensions 2 \(\/arch:\/AVX2\)** aus.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet*>.  
  
## Siehe auch  
 [\/arch \(Minimale CPU\-Architektur\)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)