---
title: "/MD, /MT, /LD (Laufzeitbibliothek verwenden) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/ld"
  - "/mt"
  - "VC.Project.VCCLWCECompilerTool.RuntimeLibrary"
  - "VC.Project.VCCLCompilerTool.RuntimeLibrary"
  - "/md"
  - "/ml"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LD (Compileroption) [C++]"
  - "/MD (Compileroption) [C++]"
  - "/MDd-Compileroption [C++]"
  - "/MT (Compileroption) [C++]"
  - "/MTd-Compileroption [C++]"
  - "_STATIC_CPPLIB-Symbol"
  - "DLLs [C++], Compileroptionen"
  - "LD (Compileroption) [C++]"
  - "-LD (Compileroption) [C++]"
  - "LIBC.lib"
  - "LIBCD.lib"
  - "LIBCMT.lib"
  - "LIBCMTD.lib"
  - "MD (Compileroption) [C++]"
  - "-MD (Compileroption) [C++]"
  - "MDd-Compileroption [C++]"
  - "-MDd-Compileroption [C++]"
  - "MSVCRT.lib"
  - "MSVCRTD.lib"
  - "MT (Compileroption) [C++]"
  - "-MT (Compileroption) [C++]"
  - "MTd-Compileroption [C++]"
  - "-MTd-Compileroption [C++]"
  - "multithread (Compileroption)"
  - "Threading [C++], multithread (Compileroption)"
ms.assetid: cf7ed652-dc3a-49b3-aab9-ad60e5395579
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# /MD, /MT, /LD (Laufzeitbibliothek verwenden)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zeigt an, ob es sich bei einem Multithread\-Modul um eine DLL handelt, und gibt Veröffentlichungs\- oder Debugversionen der Laufzeitbibliothek an.  
  
## Syntax  
  
```  
/MD[d]  
/MT[d]  
/LD[d]  
```  
  
## Hinweise  
  
|Option|Beschreibung|  
|------------|------------------|  
|**\/MD**|Bewirkt, dass die Anwendung die DLL\-spezifische und Multithreaded\-Version der Laufzeitbibliothek verwendet.  Definiert `_MT` und `_DLL` und veranlasst, dass der Compiler den Bibliotheksnamen "MSVCRT.lib" in der OBJ\-Datei positioniert.<br /><br /> Mit dieser Option kompilierte Anwendungen werden statisch mit der Bibliothek "MSVCRT.lib" verknüpft.  Diese Bibliothek stellt eine Codeschicht bereit, die dem Linker ermöglicht, externe Verweise aufzulösen.  Der tatsächlich ausgeführte Code ist in der Datei MSVCR*versionnumber*.DLL, enthalten. Diese Datei muss zur Laufzeit für die mit "MSVCRT.LIB" verknüpften Anwendungen verfügbar sein.|  
|**\/MDd**|Definiert `_DEBUG`, `_MT` und `_DLL` und veranlasst, dass die Anwendung die DLL\-spezifische und Multithreaded\-Version der Laufzeitbibliothek verwendet.  Außerdem wird verursacht, dass der Compiler den Bibliotheksnamen "MSVCRTD.lib" in der .obj\-Datei positioniert.|  
|**\/MT**|Bewirkt, dass die Anwendung die statische Multithreaded\-Version der Laufzeitbibliothek verwendet.  Definiert `_MT` und bewirkt, dass der Compiler den Bibliotheksnamen "LIBCMT.LIB" in der OBJ\-Datei ablegt, sodass diese Bibliothek vom Linker zum Auflösen externer Symbole verwendet wird.|  
|**\/MTd**|Definiert `_DEBUG` und `_MT`.  Diese Option führt auch dazu, dass der Compiler den Bibliotheksnamen "LIBCMTD.lib" in der .obj\-Datei positioniert, sodass der Linker "LIBCMTD.lib" für das Auflösen externer Symbole verwendet.|  
|**\/LD**|Erstellt eine DLL.<br /><br /> Übergibt die Option **\/DLL** an den Linker.  Der Linker sucht nach einer `DllMain`\-Funktion, die jedoch nicht unbedingt erforderlich ist.  Wenn Sie keine `DllMain`\-Funktion schreiben, fügt der Linker eine `DllMain`\-Funktion ein, die TRUE zurückgibt.<br /><br /> Verknüpft den DLL\-Startcode.<br /><br /> Erstellt eine Importbibliothek \(LIB\), wenn in der Befehlszeile keine Exportdatei \(EXP\) angegeben wurde.  Sie verknüpfen die Importbibliothek mit Anwendungen, die die DLL aufrufen.<br /><br /> Interpretiert [\/Fe \(Name der EXE\-Datei\)](../../build/reference/fe-name-exe-file.md) als Benennung einer DLL anstelle einer EXE\-Datei.  Der Name des Programms lautet standardmäßig *basename*.dll und nicht *basename*.exe.<br /><br /> Impliziert **\/MT**, sofern Sie nicht explizit **\/MD** angeben.|  
|**\/LDd**|Erstellt eine Debug\-DLL.  Definiert `_MT` und `_DEBUG`.|  
  
 Weitere Informationen zu C\-Laufzeitbibliotheken finden Sie unter [CRT\-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md). An dieser Stelle erfahren Sie auch, welche Bibliotheken beim Kompilieren mit [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md) verwendet werden.  
  
 Alle an einen bestimmten Aufruf des Linkers übergebenen Module müssen mit derselben Compileroption für die Laufzeitbibliothek kompiliert werden \(**\/MD**, **\/MT**, **\/LD**\).  
  
 Weitere Informationen über die Verwendung der Debugversionen von Laufzeitbibliotheken finden Sie unter [C\-Laufzeitbibliotheksverweis](../../c-runtime-library/c-run-time-library-reference.md).  
  
 Auch im Knowledge Base\-Artikel Q140584 wird beschrieben, wie die passende C\-Laufzeitbibliothek auszuwählen ist.  
  
 Weitere Informationen über DLLs finden Sie unter [DLLs in Visual C\+\+](../../build/dlls-in-visual-cpp.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Erweitern Sie den Ordner **C\/C\+\+**.  
  
3.  Wählen Sie die Eigenschaftenseite **Codegenerierung** aus.  
  
4.  Ändern Sie die Eigenschaft **Laufzeitbibliothek**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeLibrary*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)