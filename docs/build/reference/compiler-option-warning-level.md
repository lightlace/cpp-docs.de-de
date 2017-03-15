---
title: "/w, /Wn, /WX, /Wall, /wln, /wdn, /wen, /won (Warnstufe)"
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
  - "VC.Project.VCCLCompilerTool.DisableSpecificWarnings"
  - "VC.Project.VCCLCompilerTool.WarningLevel"
  - "VC.Project.VCCLWCECompilerTool.DisableSpecificWarnings"
  - "VC.Project.VCCLCompilerTool.WarnAsError"
  - "VC.Project.VCCLWCECompilerTool.WarnAsError"
  - "/wx"
  - "VC.Project.VCCLWCECompilerTool.WarningLevel"
  - "/wall"
  - "VC.Project.VCCLCompilerTool.TreatSpecificWarningsAsErrors"
  - "/Wv"
  - "/w0"
  - "/w1"
  - "/w2"
  - "/w3"
  - "/w4"
  - "/wd"
  - "/we"
  - "/wo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/w (Compileroption)"
  - "/W0-Compileroption [C++]"
  - "/W1-Compileroption [C++]"
  - "/W2-Compileroption [C++]"
  - "/W3-Compileroption [C++]"
  - "/W4-Compileroption [C++]"
  - "/Wall (Compileroption) [C++]"
  - "/wd (Compileroption) [C++]"
  - "/we (Compileroption) [C++]"
  - "/wo (Compileroption) [C++]"
  - "/WX (Compileroption) [C++]"
  - "w (Compileroption) [C++]"
  - "-w (Compileroption) [C++]"
  - "W0-Compileroption [C++]"
  - "-W0-Compileroption [C++]"
  - "W1-Compileroption [C++]"
  - "-W1-Compileroption [C++]"
  - "W2-Compileroption [C++]"
  - "-W2-Compileroption [C++]"
  - "W3-Compileroption [C++]"
  - "-W3-Compileroption [C++]"
  - "W4-Compileroption [C++]"
  - "-W4-Compileroption [C++]"
  - "Wall (Compileroption) [C++]"
  - "-Wall (Compileroption) [C++]"
  - "Warnstufe-Compileroption"
  - "Warnungen, Als Fehler behandeln (Compileroption)"
  - "wd (Compileroption) [C++]"
  - "-wd (Compileroption) [C++]"
  - "we (Compileroption) [C++]"
  - "-we (Compileroption) [C++]"
  - "wo (Compileroption) [C++]"
  - "-wo (Compileroption) [C++]"
  - "WX (Compileroption) [C++]"
  - "-WX (Compileroption) [C++]"
ms.assetid: d6bc7bf5-c754-4879-909c-8e3a67e2629f
caps.latest.revision: 21
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# /w, /Wn, /WX, /Wall, /wln, /wdn, /wen, /won (Warnstufe)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt an, wie der Compiler Warnungen für eine angegebene Kompilierung generiert.  
  
## Syntax  
  
```  
/w  
/Wn  
/WX  
/Wall  
/wln  
/wdn  
/wen  
/won  
```  
  
## Hinweise  
 Die Optionen und die zugehörigen Argumente werden in der folgenden Tabelle beschrieben.  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|**\/w**|Deaktiviert alle Compilerwarnungen.|  
|**\/W** `n`|Gibt die Ebene der Warnung, vom Compiler generiert werden an.  Gültige Warnstufen für `n` liegen zwischen 0 und 4:<br /><br /> -   Bei Stufe 0 werden alle Warnungen deaktiviert.<br />-   Bei Stufe 1 werden schwere Warnungen angezeigt.  Ebene 1 ist die Standardeinstellung.<br />-   Ebene 2 werden alle Warnungen der Stufe 1 und Warnungen an, die weniger stark als 1. Ebene sind.<br />-   Ebene 3 werden alle Warnungen der Stufe 2 und weitere Warnungen an, die den Produktionszwecken empfohlen werden.<br />-   Ebene 4 werden alle Warnungen der Stufe 3 und informative Warnungen erläutert.  Es wird empfohlen, dass Sie diese Option verwenden, Fussel ähnliche Warnungen nur bereitstellen.  Für ein neues Projekt, kann es empfehlenswert, `/W4` in allen Kompilationen zu verwenden; Dies stellt die wenigsten möglichen Hart\-zuSuchencodefehler sicher.|  
|**\/Wall**|Zeigt alle \/W4\- Warnungen und andere Warnungen an, die nicht in \/W4 \- für Beispiel, Warnungen enthalten sind, die standardmäßig deaktiviert sind.  Siehe [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md).|  
|**\/WX**|Behandelt alle Compilerwarnungen als Fehler.  Bei einem neuen Projekt ist es möglicherweise ratsam, **\/WX** in allen Kompilierungen zu verwenden: Die Beachtung aller Warnmeldungen minimiert die Anzahl der schwer zu findenden Codefehler.<br /><br /> Der Linker besitzt auch eine **\/WX** \- Option.  Weitere Informationen finden Sie unter [\/WX \(Linkerwarnungen als Fehler behandeln\)](../../build/reference/wx-treat-linker-warnings-as-errors.md).|  
|**\/w** `ln`|Gibt die Stufe einer bestimmten Warnmeldung an.  Der erste Parameter legt die Warnstufe fest \(entspricht **\/W**`n`\), der zweite Parameter ist die Nummer der Warnmeldung.<br /><br /> So sorgt z. B. die Option `/w14326` dafür, dass C4326 als Warnmeldung der Stufe 1 generiert wird.|  
|**\/wd** `n`|Deaktiviert die Compilerwarnung, die in `n` angegeben wird.<br /><br /> Die Option `/wd4326` deaktiviert beispielsweise die Warnung C4326.|  
|**\/we** `n`|Behandelt als Fehler die Compilerwarnung, die in `n` angegeben wird.<br /><br /> `/we4326` markiert z. B. Warnung Nr. C4326 als Fehler.|  
|**\/wo** `n`|Meldet den Fehler nur einmal für die Compilerwarnung, die in `n` angegeben wird.<br /><br /> Beispielsweise bewirkt `/wo4326` Warnung C4326, nur einmal ausgegeben werden.|  
  
 Wenn Sie erstellen einen vorkompilierten Header \([\/Yc \(Datei der vorkompilierten Header erstellen\)](../../build/reference/yc-create-precompiled-header-file.md)\) mit einer der Optionen **\/w** verwenden, führt jede mit der vorkompilierten Headerdatei \([\/Yu \(Vorkompilierte Headerdatei verwenden\)](../../build/reference/yu-use-precompiled-header-file.md)\) denen die gleichen **\/w** Optionen sein wirksam erneut.  Sie können **\/w** überschreiben, die in der vorkompilierten Headers festgelegt, indem Sie eine andere Option **\/w** in der Befehlszeile verwenden.  
  
 Pragmadirektiven im Quellcode werden von der **\/w**\-Option nicht beeinflusst.  
  
 Sie können [warning](../../preprocessor/warning.md) verwenden, um die Ebene der Warnung zu steuern, die zur Kompilierzeit ausgegeben wird.  
  
 [Buildfehlerdokumentation](../../error-messages/compiler-errors-1/c-cpp-build-errors.md) beschreibt die Warnungen und Warnstufen und gibt an, warum bestimmte Anweisungen möglicherweise nicht kompiliert, wie Sie möchten.  
  
### So die Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Wählen Sie **C\/C\+\+** aus.  
  
3.  Auf der Eigenschaftenseite **Allgemein** ändern Sie den **Warnstufe** oder die Eigenschaften **Warnungen als Fehler behandeln**.  
  
4.  Auf der Eigenschaftenseite **Erweitert** ändern Sie die Eigenschaft **Bestimmte Warnungen deaktivieren**.  
  
5.  Für die übrigen Optionen auf der Eigenschaftenseite **Befehlszeile**, geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### So die Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarningLevel*>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarnAsError*>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableSpecificWarnings*> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)