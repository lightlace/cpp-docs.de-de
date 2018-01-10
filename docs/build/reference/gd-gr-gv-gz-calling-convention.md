---
title: -Gd - Gr, / - Gv, - Gz (Aufrufkonvention) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /gr
- /Gv
- /gz
- /Gd
- VC.Project.VCCLCompilerTool.CallingConvention
dev_langs: C++
helpviewer_keywords:
- -Gd compiler option [C++]
- -Gv compiler option [C++]
- /Gv compiler option [C++]
- -Gr compiler option [C++]
- Gd compiler option [C++]
- Gr compiler option [C++]
- /Gz compiler option [C++]
- -Gz compiler option [C++]
- /Gd compiler option [C++]
- Gz compiler option [C++]
- Gv compiler option [C++]
- /Gr compiler option [C++]
ms.assetid: fd3110cb-2d77-49f2-99cf-a03f9ead00a3
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 26e88abf30c0f67fe5b104d560c40dd2adc57752
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="gd-gr-gv-gz-calling-convention"></a>/Gd, /Gr, /Gv, /Gz (Aufrufkonvention)
Mit diesen Optionen wird festgelegt, in welcher Reihenfolge die Funktionsargumente auf den Stapel verschoben werden, ob die aufrufende oder die aufgerufene Funktion die Argumente am Ende des Aufrufs aus dem Stapel entfernt, und welche Namensergänzungskonvention der Compiler zur Erkennung einzelner Funktionen verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Gd  
/Gr  
/Gv  
/Gz  
```  
  
## <a name="remarks"></a>Hinweise  
 **/ GD**, in der Standardeinstellung gibt die [__cdecl](../../cpp/cdecl.md) -Aufrufkonvention für alle Funktionen mit Ausnahme von C++-Memberfunktionen, Funktionen und Funktionen, die markiert sind [__stdcall](../../cpp/stdcall.md), [__ Fastcall](../../cpp/fastcall.md), oder [__vectorcall](../../cpp/vectorcall.md).  
  
 **/ Gr** gibt an, die `__fastcall` -Aufrufkonvention für alle Funktionen mit Ausnahme von C++-Memberfunktionen, Funktionen namens `main`, Funktionen, die markiert sind und `__cdecl`, `__stdcall`, oder `__vectorcall`. Alle `__fastcall` -Funktionen müssen Prototypen aufweisen. Diese Aufrufkonvention ist nur in Compilern verfügbar, die auf x86 abzielen, und wird von Compilern ignoriert, die auf andere Architekturen abzielen.  
  
 **/ GZ** gibt an, die `__stdcall` -Aufrufkonvention für alle Funktionen mit Ausnahme von C++-Memberfunktionen, Funktionen namens `main`, Funktionen, die markiert sind und `__cdecl`, `__fastcall`, oder `__vectorcall`. Alle `__stdcall` -Funktionen müssen Prototypen aufweisen. Diese Aufrufkonvention ist nur in Compilern verfügbar, die auf x86 abzielen, und wird von Compilern ignoriert, die auf andere Architekturen abzielen.  
  
 **/ GV** gibt an, die `__vectorcall` -Aufrufkonvention für alle Funktionen mit Ausnahme von C++-Memberfunktionen, Funktionen benannte Main, Funktionen mit einer `vararg` Variablenargumentliste oder Funktionen, die mit einem widersprüchlichen markiert sind `__cdecl`, `__stdcall`, oder `__fastcall` Attribut. Diese Aufrufkonvention ist nur auf x86- und x64-Architekturen verfügbar, die „/arch:SSE2“ und höher unterstützen, und wird von Compilern ignoriert, die auf die ARM-Architektur abzielen.  
  
 Funktionen, die eine variable Anzahl von Argumenten akzeptieren, müssen mit `__cdecl` gekennzeichnet sein.  
  
 **/ GD**, **/Gr**, **/GV** und **/GZ** sind nicht kompatibel mit [/CLR: safe](../../build/reference/clr-common-language-runtime-compilation.md) oder   **/CLR: pure**. Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet.  
  
> [!NOTE]
>  Standardmäßig für X86 Prozessoren, die C++-Memberfunktionen verwenden [__thiscall](../../cpp/thiscall.md).  
  
 Für alle Prozessoren verwendet eine Memberfunktion, die explizit als `__cdecl`, `__fastcall`, `__vectorcall` oder `__stdcall` gekennzeichnet ist, die angegebene Aufrufkonvention, wenn diese nicht auf dieser Architektur ignoriert wird. Eine Memberfunktion, die eine variable Anzahl von Argumenten zulässt, verwendet immer die Aufrufkonvention `__cdecl`.  
  
 Diese Compileroptionen haben keine Auswirkungen auf die Namensergänzung von C++-Methoden und -Funktionen. Sofern sie nicht als `extern "C"` deklariert sind, kommt für C++-Methoden und -Funktionen ein anderes Schema für Namensergänzungen zur Anwendung. Weitere Informationen finden Sie unter [ergänzte Namen](../../build/reference/decorated-names.md).  
  
 Weitere Informationen über Aufrufkonventionen finden Sie unter [Aufrufkonventionen](../../cpp/calling-conventions.md).  
  
## <a name="cdecl-specifics"></a>__cdecl-Besonderheiten  
 Auf x86-Prozessoren werden alle Funktionsargumente auf dem Stapel von rechts nach links übergeben. Auf ARM- und x64-Architekturen werden einige Argumente nach Register übergeben und der Rest wird auf dem Stapel von rechts nach links übergeben. Die Aufrufroutine ruft die Argumente vom Stapel auf.  
  
 Für C verwendet die `__cdecl`-Benennungskonvention den Funktionsnamen mit einem führenden Unterstrich (`_`); Groß-/Kleinbuchstaben werden nicht umgewandelt. Sofern sie nicht als `extern "C"` deklariert sind, kommt für C++-Funktionen ein anderes Schema für Namensergänzungen zur Anwendung. Weitere Informationen finden Sie unter [ergänzte Namen](../../build/reference/decorated-names.md).  
  
## <a name="fastcall-specifics"></a>__fastcall-Besonderheiten  
 Einige der Argumente einer `__fastcall`-Funktion werden an Register übergeben (für x86-Prozessoren, ECX und EDX), der Rest wird von rechts nach links auf den Stapel verschoben. Die aufgerufene Routine nimmt diese Argumente vor ihrem Rücksprung vom Stapel auf. In der Regel **/Gr** verringert die Ausführungszeit.  
  
> [!NOTE]
>  Seien Sie vorsichtig, wenn Sie die `__fastcall`-Aufrufkonvention für eine in Inlineassemblysprache geschriebene Funktion verwenden. Es kann zu Konflikten zwischen Ihrer Verwendung von Registern und deren Verwendung durch den Compiler kommen.  
  
 Für C verwendet die `__fastcall`-Benennungskonvention den Funktionsnamen, mit einem führenden `@`-Zeichen, gefolgt von der Größe der Funktionsargumente in Byte. Groß-/Kleinbuchstaben werden nicht umgewandelt. Der Compiler verwendet für die Benennungskonvention diese Vorlage:  
  
```  
@function_name@number  
```  
  
 Mit der Benennungskonvention `__fastcall` sollten Sie die standardmäßigen Includedateien verwenden. Andernfalls erhalten Sie nicht aufgelöste externe Verweise.  
  
## <a name="stdcall-specifics"></a>__stdcall-Besonderheiten  
 Die Argumente einer `__stdcall`-Funktion werden von rechts nach links auf dem Stapel abgelegt, und die aufgerufene Funktion nimmt diese Argumente vor ihrer Rücksetzung vom Stapel.  
  
 Für C verwendet die `__stdcall`-Benennungskonvention den Funktionsnamen mit führendem Unterstrich (`_`), gefolgt von einem @-Zeichen und der Größe der Funktionsargumente in Byte. Groß-/Kleinbuchstaben werden nicht umgewandelt. Der Compiler verwendet für die Benennungskonvention diese Vorlage:  
  
```  
_functionname@number  
```  
  
## <a name="vectorcall-specifics"></a>__vectorcall-Besonderheiten  
 Die ganzzahligen Argumente einer `__vectorcall`-Funktion werden nach Wert übergeben, wobei bis zu zwei (auf x86) oder vier (x64) Ganzzahlregister und bis zu sechs XMM-Register für Gleitkomma- und Vektorwerte verwendet werden. Der Rest wird auf dem Stapel von rechts nach links übergeben. Die aufgerufene Funktion bereinigt den Stapel vor dem Zurückgeben. Vektor- und Gleitkomma-Rückgabewerte werden in XMM0 zurückgegeben.  
  
 Für C verwendet die `__vectorcall`-Benennungskonvention den Funktionsnamen, gefolgt von zwei @-Zeichen und der Größe der Funktionsargumente in Byte. Groß-/Kleinbuchstaben werden nicht umgewandelt. Der Compiler verwendet für die Benennungskonvention diese Vorlage:  
  
```  
functionname@@number  
```  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **C/C++-** Ordner.  
  
3.  Wählen Sie die **erweitert** Eigenschaftenseite.  
  
4.  Ändern der **Aufrufkonvention** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CallingConvention%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)