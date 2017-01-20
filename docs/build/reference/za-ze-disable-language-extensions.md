---
title: "/Za, /Ze (Spracherweiterungen deaktivieren)"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.DisableLanguageExtensions"
  - "/za"
  - "/ze"
  - "VC.Project.VCCLCompilerTool.DisableLanguageExtensions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Za (Compileroption) [C++]"
  - "/Ze (Compileroption) [C++]"
  - "Spracherweiterungen deaktivieren (Compileroption)"
  - "Aktivieren der Spracherweiterungen"
  - "Spracherweiterungen"
  - "Spracherweiterungen, Deaktivieren im Compiler"
  - "Za (Compileroption) [C++]"
  - "-Za (Compileroption) [C++]"
  - "Ze (Compileroption) [C++]"
  - "-Ze (Compileroption) [C++]"
ms.assetid: 65e49258-7161-4289-a176-7c5c0656b1a2
caps.latest.revision: 18
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# /Za, /Ze (Spracherweiterungen deaktivieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **\/Za**\-Compileroption gibt einen Fehler für Sprachkonstrukte aus, die weder mit ANSI C noch mit ANSI C\+\+ kompatibel sind.  Die **\/Ze**\-Compileroption, die der Standard ist, aktiviert Microsoft\-Erweiterungen.  
  
## Syntax  
  
```  
/Za  
/Ze  
```  
  
## Hinweise  
  
> [!NOTE]
>  Die **\/Ze**\-Option ist veraltet.  Weitere Informationen finden Sie unter [Deprecated Compiler Options in Visual C\+\+ 2005](assetId:///aa59fce3-50b8-4f66-9aeb-ce09a7a84cce).  
  
 Der [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]\-Compiler bietet eine Reihe von Features, die über den ANSI C\- und den ANSI C\+\+\-Standard hinausgehen.  Diese Funktionen werden allgemein als Microsoft\-Erweiterungen für C und C\+\+ bezeichnet.  Diese Erweiterungen sind verfügbar, wenn die **\/Ze**\-Option angegeben ist. Sie sind nicht verfügbar, wenn die **\/Za**\-Option angegeben ist.  Weitere Informationen finden Sie unter [Microsoft\-Erweiterungen für C und C\+\+](../../build/reference/microsoft-extensions-to-c-and-cpp.md).  
  
 Deaktivieren Sie die Spracherweiterungen, wenn Sie die Absicht haben, Ihr Programm in andere Umgebungen zu portieren.  Der Compiler behandelt erweiterte Schlüsselwörter als einfache Bezeichner, deaktiviert die anderen Microsoft\-Erweiterungen und definiert automatisch das vordefinierte Makro `__STDC__` für C\-Programme.  
  
 Weitere mit **\/Za** verwendete Compileroptionen können sich darauf auswirken, wie der Compiler die ANSI\-Konformität sicherstellt.  Zum Beispiel führen **\/Za** und [\/fp \(Festlegen des Gleitkommaverhaltens\)](../../build/reference/fp-specify-floating-point-behavior.md) möglicherweise zu unerwartetem Verhalten.  
  
 Unter [\/Zc](../../build/reference/zc-conformance.md)\-Compileroption finden Sie Möglichkeiten zum Erzwingen von Standardverhalten mit **\/Za**.  
  
 Weitere Informationen zur Konformität mit [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] finden Sie unter [Kompatibilitäts\- und Konformitätsprobleme in Visual C\+\+](../../misc/compatibility-and-compliance-issues-in-visual-cpp.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Sprache**.  
  
4.  Ändern Sie die Eigenschaft **Spracherweiterungen deaktivieren**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableLanguageExtensions*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)