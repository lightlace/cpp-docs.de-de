---
title: "-RTC (Laufzeitfehler-Überprüfungen) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /rtc
- VC.Project.VCCLCompilerTool.SmallerTypeCheck
- VC.Project.VCCLCompilerTool.UninitializedVariableCheck
- VC.Project.VCCLCompilerTool.StackFrameCheck
- VC.Project.VCCLCompilerTool.BasicRuntimeChecks
dev_langs:
- C++
helpviewer_keywords:
- /RTCs compiler option [C++]
- -RTC1 compiler option [C++]
- run-time errors, error checks
- -RTCu compiler option [C++]
- /RTC1 compiler option [C++]
- /RTCc compiler option [C++]
- /RTCu compiler option [C++]
- __MSVC_RUNTIME_CHECKS macro
- -RTCs compiler option [C++]
- RTCs compiler option
- RTC1 compiler option
- run-time errors, run-time checks
- run-time checks, /RTC option
- RTCu compiler option
- RTCc compiler option
- -RTCc compiler option [C++]
ms.assetid: 9702c558-412c-4004-acd5-80761f589368
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8699a96dcd7c04bc1b2707e964afb4b68068147e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="rtc-run-time-error-checks"></a>/RTC (Laufzeitfehlerüberprüfungen)
Zum Aktivieren und deaktivieren Sie die Laufzeitfehler-Überprüfungen-Funktion in Verbindung mit der [Runtime_checks](../../preprocessor/runtime-checks.md) Pragma.  
  
## <a name="syntax"></a>Syntax  
  
```  
/RTC1  
/RTCc  
/RTCs  
/RTCu  
```  
  
## <a name="arguments"></a>Argumente  
 `1`  
 Der entsprechende **/RTC**`su`.  
  
 `c`  
 Gibt an, wann ein Wert zugewiesen ist einem kleineren Datentyp und führt zu einem Datenverlust. Wenn ein Wert vom Typ z. B. `short 0x101` wird einer Variablen vom Typ zugewiesen `char`.  
  
 Diese Option gibt Situationen, in dem Sie möchten z. B. truncate gegebenenfalls die ersten acht Bits des, ein `int` zurückgegeben, als eine `char`. Da **/RTC** `c` verursacht einen Laufzeitfehler, wenn alle Informationen, die als Ergebnis der Zuweisung verloren geht, können Sie die Informationen, Sie einen Fehler zur Laufzeit als Ergebnis des zu vermeiden müssen, maskieren **/RTC** `c`. Zum Beispiel:  
  
```  
#include <crtdbg.h>  
  
char get8bits(int value, int position) {  
   _ASSERT(position < 32);  
   return (char)(value >> position);  
   // Try the following line instead:  
   // return (char)((value >> position) & 0xff);  
}  
  
int main() {  
   get8bits(12341235,3);  
}  
```  
  
 `s`  
 Ermöglicht das stack-Frame-Laufzeitfehler zur Überprüfung der wie folgt:  
  
-   Die Initialisierung der lokalen Variablen auf einen Wert ungleich NULL. Dadurch können Fehler zu identifizieren, die nicht angezeigt werden, wenn im Debugmodus ausgeführt wird. Es ist die Wahrscheinlichkeit, dass Stapelvariablen weiterhin mit 0 (null) in einem Debugbuild im Vergleich zu einem Releasebuild aufgrund von compileroptimierungen von Stapelvariablen in einem Releasebuild können größer. Sobald ein Programm einen Bereich von seinen Stapel verwendet, wird es vom Compiler nie auf 0 zurückgesetzt. Aus diesem Grund können nachfolgende, nicht initialisierte Stapelvariablen, die auftreten, verwenden Sie denselben Stapelbereich Werte, die überzählig sind, aus der vorherigen Verwendung dieser Stapelspeicher zu benötigen zurückgeben.  
  
-   Erkennung von Überläufen und Unterläufe von lokalen Variablen, z. B. Arrays. **/ RTC** `s` Überläufe beim Zugriff auf Speicher, die vom Compiler Füllzeichen innerhalb einer Struktur nicht erkennt. Auffüllung mit auftreten [ausrichten](../../cpp/align-cpp.md), [/Zp (Ausrichten des Strukturmembers)](../../build/reference/zp-struct-member-alignment.md), oder [Pack](../../preprocessor/pack.md), oder wenn die Struktur Zeichenfolgenelemente so, dass der Compiler Füllzeichen hinzufügen muss.  
  
-   Der Stapel zeigerbeschädigung erkennt Zeiger Überprüfung des Stapels. Stack-zeigerbeschädigung kann durch eine aufrufende Konvention nicht übereinstimmende verursacht werden. Beispielsweise über einen Funktionszeiger, Sie rufen eine Funktion in einer DLL, die als exportiert wird [__stdcall](../../cpp/stdcall.md) , aber Sie deklarieren den Zeiger an die Funktion als [__cdecl](../../cpp/cdecl.md).  
  
 `u`  
 Gibt an, wann eine Variable verwendet wird, wurde ohne Initialisierung. Angenommen, eine Anweisung, die generiert `C4701` möglicherweise einen Laufzeitfehler unter generiert **/RTC**`u`. Jede Anweisung, [Compilerwarnung (Stufe 1 und Stufe 4) C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md) generiert einen Laufzeitfehler unter **/RTC**`u`.  
  
 Jedoch sollten Sie das folgende Codefragment:  
  
```cpp  
int a, *b, c;  
if ( 1 )  
b = &a;  
c = a;  // No run-time error with /RTCu  
```  
  
 Wenn eine Variable initialisiert wurden konnte, es wird nicht gemeldet zur Laufzeit durch **/RTC**`u`. Beispielsweise nach der eine Variable als Alias durch einen Zeiger handelt, der Compiler nicht die Variable und Melden von nicht initialisierten verwendet. Aktiviert ist, können Sie eine Variable initialisieren, durch das Übernehmen der Adresse. Der &-Operator funktioniert wie einen Zuweisungsoperator in dieser Situation.  
  
## <a name="remarks"></a>Hinweise  
 Laufzeitfehler-Überprüfungen sind eine Möglichkeit, Probleme im ausgeführten Code zu suchen. Weitere Informationen finden Sie unter [Vorgehensweise: verwenden Native Run-Time Checks](/visualstudio/debugger/how-to-use-native-run-time-checks).  
  
 Wenn Sie das Programm mithilfe der Befehlszeile kompilieren der **/RTC** Compileroptionen, treten bei allen [optimieren](../../preprocessor/optimize.md) Anweisungen in Ihrem Code werden ohne Meldung fehl. Dies ist, da der fehlerprüfung zur Laufzeit in einem Releasebuild (optimiert) ungültig sind.  
  
 Verwenden Sie **/RTC** für Entwicklungsbuilds; **/RTC** sollte nicht für eine Verkaufsversion verwendet werden. **/ RTC** kann nicht verwendet werden, mit compileroptimierungen ([/o-Optionen (Code optimieren)](../../build/reference/o-options-optimize-code.md)). Programm-Abbilds mit **/RTC** ist etwas größer und etwas langsamer als ein Bild mit erstellten **/Od** (bis zu 5 Prozent langsamer als ein **/Od** erstellen).  
  
 __MSVC_RUNTIME_CHECKS-Präprozessordirektive wird definiert, wenn Sie eine beliebige **/RTC** Option oder [/GZ](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die **Codegenerierung** Eigenschaftenseite.  
  
4.  Ändern Sie eine oder beide der folgenden Eigenschaften: **vollständige Laufzeitüberprüfungen** oder **kleinere Typüberprüfung**.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe die Eigenschaften <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BasicRuntimeChecks%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.SmallerTypeCheck%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Gewusst wie: Verwenden von nativen Laufzeitprüfungen](/visualstudio/debugger/how-to-use-native-run-time-checks)