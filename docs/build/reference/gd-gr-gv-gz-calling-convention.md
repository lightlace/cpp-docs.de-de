---
title: "/Gd, /Gr, /Gv, /Gz (Aufrufkonvention) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/gr"
  - "/Gv"
  - "/gz"
  - "/Gd"
  - "VC.Project.VCCLCompilerTool.CallingConvention"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gd (Compileroption) [C++]"
  - "/Gr (Compileroption) [C++]"
  - "/Gv-Compileroption [C++]"
  - "/Gz (Compileroption) [C++]"
  - "Gd (Compileroption) [C++]"
  - "-Gd (Compileroption) [C++]"
  - "Gr (Compileroption) [C++]"
  - "-Gr (Compileroption) [C++]"
  - "Gv-Compileroption [C++]"
  - "-Gv-Compileroption [C++]"
  - "Gz (Compileroption) [C++]"
  - "-Gz (Compileroption) [C++]"
ms.assetid: fd3110cb-2d77-49f2-99cf-a03f9ead00a3
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# /Gd, /Gr, /Gv, /Gz (Aufrufkonvention)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit diesen Optionen wird festgelegt, in welcher Reihenfolge die Funktionsargumente auf den Stapel verschoben werden, ob die aufrufende oder die aufgerufene Funktion die Argumente am Ende des Aufrufs aus dem Stapel entfernt, und welche Namensergänzungskonvention der Compiler zur Erkennung einzelner Funktionen verwendet.  
  
## Syntax  
  
```  
/Gd  
/Gr  
/Gv  
/Gz  
```  
  
## Hinweise  
 Die Standardeinstellung **\/Gd** legt für alle Funktionen die [\_\_cdecl](../../cpp/cdecl.md)\-Aufrufkonvention fest, mit Ausnahme von C\+\+\-Memberfunktionen und Funktionen, die als [\_\_stdcall](../../cpp/stdcall.md), [\_\_fastcall](../../cpp/fastcall.md) oder [\_\_vectorcall](../../cpp/vectorcall.md) gekennzeichnet sind.  
  
 **\/Gr** legt die `__fastcall`\-Aufrufkonvention für alle Funktionen mit Ausnahme von C\+\+\-Memberfunktionen, `main` benannten Funktionen und mit `__cdecl`, `__stdcall` oder `__vectorcall` gekennzeichneten Funktionen fest.  Alle `__fastcall`\-Funktionen müssen Prototypen haben.  Diese Aufrufkonvention ist nur in Compilern verfügbar, die auf x86 abzielen, und wird von Compilern ignoriert, die auf andere Architekturen abzielen.  
  
 **\/Gz** legt die `__stdcall`\-Aufrufkonvention für alle Funktionen mit Ausnahme von C\+\+\-Memberfunktionen, `main` benannten Funktionen und mit `__cdecl`, `__fastcall` oder `__vectorcall` gekennzeichneten Funktionen fest.  Alle `__stdcall`\-Funktionen müssen Prototypen haben.  Diese Aufrufkonvention ist nur in Compilern verfügbar, die auf x86 abzielen, und wird von Compilern ignoriert, die auf andere Architekturen abzielen.  
  
 **\/Gv** gibt die `__vectorcall` \- Aufrufkonvention für alle Funktionen an, außer C\+\+\-Memberfunktionen, Funktionen mit der Bezeichnung "main", Funktionen mit einer Liste variabler Argumente `vararg` oder Funktionen, die mit einem widersprüchlichen `__cdecl`, `__stdcall` oder  `__fastcall`\-Attribut markiert sind.  Diese Aufrufkonvention ist nur auf x86\- und x64\-Architekturen verfügbar, die "\/arch:SSE2" und höher unterstützen, und wird von Compilern ignoriert, die auf die ARM\-Architektur abzielen.  
  
 Funktionen, die eine variable Anzahl von Argumenten akzeptieren, müssen mit `__cdecl` gekennzeichnet sein.  
  
 **\/Gd**, **\/Gr**, **\/Gv** und **\/Gz** sind nicht mit [\/clr:safe](../../build/reference/clr-common-language-runtime-compilation.md) oder **\/clr:pure** kompatibel.  
  
> [!NOTE]
>  Für x86\-Prozessoren verwenden C\+\+\-Memberfunktionen standardmäßig [\_\_thiscall](../../cpp/thiscall.md).  
  
 Für alle Prozessoren verwendet eine Memberfunktion, die explizit als `__cdecl`, `__fastcall`, `__vectorcall` oder `__stdcall` gekennzeichnet ist, die angegebene Aufrufkonvention, wenn diese nicht auf dieser Architektur ignoriert wird.  Eine Memberfunktion, die eine variable Anzahl von Argumenten zulässt, verwendet immer die Aufrufkonvention `__cdecl`.  
  
 Diese Compileroptionen haben keine Auswirkungen auf die Namensergänzung von C\+\+\-Methoden und \-Funktionen.  Sofern sie nicht als `extern "C"` deklariert sind, kommt für C\+\+\-Methoden und \-Funktionen ein anderes Schema für Namensergänzungen zur Anwendung.  Weitere Informationen finden Sie unter [Ergänzte Namen](../../build/reference/decorated-names.md).  
  
 Weitere Informationen zu Aufrufkonventionen finden Sie unter [Aufrufkonventionen](../../cpp/calling-conventions.md).  
  
## \_\_cdecl\-Besonderheiten  
 Auf x86\-Prozessoren werden alle Funktionsargumente auf dem Stapel von rechts nach links übergeben.  Auf ARM\- und x64\-Architekturen werden einige Argumente nach Register übergeben und der Rest wird auf dem Stapel von rechts nach links übergeben.  Die Aufrufroutine ruft die Argumente vom Stapel auf.  
  
 Für C verwendet die `__cdecl`\-Benennungskonvention den Funktionsnamen mit einem führenden Unterstrich \(`_`\); Groß\-\/Kleinbuchstaben werden nicht umgewandelt.  Sofern sie nicht als `extern "C"` deklariert sind, kommt für C\+\+\-Funktionen ein anderes Schema für Namensergänzungen zur Anwendung.  Weitere Informationen finden Sie unter [Ergänzte Namen](../../build/reference/decorated-names.md).  
  
## \_\_fastcall\-Besonderheiten  
 Einige der Argumente einer `__fastcall`\-Funktion werden an Register übergeben \(für x86\-Prozessoren, ECX und EDX\), der Rest wird von rechts nach links auf den Stapel verschoben.  Die aufgerufene Routine nimmt diese Argumente vor ihrem Rücksprung vom Stapel auf.  **\/Gr** verringert gewöhnlich die Ausführungszeit.  
  
> [!NOTE]
>  Seien Sie vorsichtig, wenn Sie die `__fastcall`\-Aufrufkonvention für eine in Inlineassemblysprache geschriebene Funktion verwenden.  Es kann zu Konflikten zwischen Ihrer Verwendung von Registern und deren Verwendung durch den Compiler kommen.  
  
 Für C verwendet die `__fastcall`\-Benennungskonvention den Funktionsnamen, mit einem führenden `@`\-Zeichen, gefolgt von der Größe der Funktionsargumente in Byte.  Groß\-\/Kleinbuchstaben werden nicht umgewandelt.  Der Compiler verwendet für die Benennungskonvention diese Vorlage:  
  
```c  
@function_name@number  
```  
  
 Mit der Benennungskonvention `__fastcall` sollten Sie die standardmäßigen Includedateien verwenden.  Andernfalls erhalten Sie nicht aufgelöste externe Verweise.  
  
## \_\_stdcall\-Besonderheiten  
 Die Argumente einer `__stdcall`\-Funktion werden von rechts nach links auf dem Stapel abgelegt, und die aufgerufene Funktion nimmt diese Argumente vor ihrer Rücksetzung vom Stapel.  
  
 Für C verwendet die `__stdcall`\-Benennungskonvention den Funktionsnamen mit führendem Unterstrich \(`_`\), gefolgt von einem @\-Zeichen und der Größe der Funktionsargumente in Byte.  Groß\-\/Kleinbuchstaben werden nicht umgewandelt.  Der Compiler verwendet für die Benennungskonvention diese Vorlage:  
  
```c  
_functionname@number  
```  
  
## \_\_vectorcall\-Besonderheiten  
 Die ganzzahligen Argumente einer `__vectorcall`\-Funktion werden nach Wert übergeben, wobei bis zu zwei \(auf x86\) oder vier \(x64\) Ganzzahlregister und bis zu sechs XMM\-Register für Gleitkomma\- und Vektorwerte verwendet werden. Der Rest wird auf dem Stapel von rechts nach links übergeben.  Die aufgerufene Funktion bereinigt den Stapel vor dem Zurückgeben.  Vektor\- und Gleitkomma\-Rückgabewerte werden in XMM0 zurückgegeben.  
  
 Für C verwendet die `__vectorcall`\-Benennungskonvention den Funktionsnamen, gefolgt von zwei @\-Zeichen und der Größe der Funktionsargumente in Byte.  Groß\-\/Kleinbuchstaben werden nicht umgewandelt.  Der Compiler verwendet für die Benennungskonvention diese Vorlage:  
  
```c  
functionname@@number  
```  
  
### To set this compiler option in the Visual Studio development environment  
  
1.  Open the project's **Property Pages** dialog box.  For details, see [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Select the **C\/C\+\+** folder.  
  
3.  Select the **Advanced** property page.  
  
4.  Modify the **Calling Convention** property.  
  
### To set this compiler option programmatically  
  
-   See <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CallingConvention*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)