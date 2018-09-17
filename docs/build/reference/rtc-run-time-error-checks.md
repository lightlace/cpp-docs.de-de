---
title: -RTC (Laufzeitfehler-Überprüfungen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29fd7e3ec71b38aec187f60548ce7cededd01c2b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709399"
---
# <a name="rtc-run-time-error-checks"></a>/RTC (Laufzeitfehlerüberprüfungen)

Zum Aktivieren und deaktivieren die Run-Time-Funktion für laufzeitfehlerüberprüfungen in Verbindung mit der [Runtime_checks](../../preprocessor/runtime-checks.md) Pragma.

## <a name="syntax"></a>Syntax

```
/RTC1
/RTCc
/RTCs
/RTCu
```

## <a name="arguments"></a>Argumente

**1**<br/>
Der entsprechende **/RTC**`su`.

**c**<br/>
Zeigt an, dass ein Wert zugewiesen wird einem kleineren Datentyp, und führt zu einem Datenverlust. Wenn ein Wert vom Typ beispielsweise `short 0x101` eine Variable des Typs zugewiesen wird `char`.

Diese Option gibt Situationen, in denen Sie beabsichtigen abschneiden, z. B. Wenn Sie möchten, dass die ersten acht Bits, eine `int` als eine `char`. Da **/RTC** `c` verursacht einen Laufzeitfehler, wenn als Ergebnis der Zuweisung keine Informationen verloren gehen, können Sie die Informationen, die Sie einen Laufzeitfehler aufgrund vermeiden müssen maskieren **/RTC** `c`. Zum Beispiel:

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

**s**<br/>
Ermöglicht das stack-Frame-Laufzeitfehler überprüfen, wie folgt:

- Initialisierung von lokalen Variablen einen Wert ungleich NULL. Dadurch können Fehler zu identifizieren, die bei der Ausführung im Debugmodus nicht angezeigt werden. Es ist wahrscheinlicher, dass Stapelvariablen weiterhin 0 (null) in einem Debugbuild im Vergleich zu einem Releasebuild, aufgrund von compileroptimierungen von Stapelvariablen in einem Releasebuild werden. Nachdem ein Programm einen Bereich von seinen Stapel verwendet, wird es vom Compiler nicht auf 0 zurückgesetzt. Aus diesem Grund können nachfolgende, nicht initialisierte Stapelvariablen, die auftreten, verwenden Sie denselben Stapelbereich Werte, die überzählig sind, aus der vorherigen Verwendung dieser Stapelspeicher zu benötigen zurückgeben.

- Erkennung von Überläufen und Unterläufe von lokalen Variablen, z. B. Arrays. **/ RTC** `s` Überläufe wird nicht erkannt werden, beim Zugriff auf Speicher, der vom Compiler Füllzeichen innerhalb einer Struktur ergibt. Füllzeichen können mithilfe von [ausrichten](../../cpp/align-cpp.md), [/Zp (Strukturmemberausrichtung)](../../build/reference/zp-struct-member-alignment.md), oder [Pack](../../preprocessor/pack.md), oder wenn Sie so, dass der Compiler Füllzeichen hinzufügen muss Strukturelemente geordnet.

- Stack-Zeiger-Überprüfung wird der Stack Zeiger eine Beschädigung erkennt. Stack Beschädigung kann durch einen Aufruf Konvention Konflikt verursacht werden. Beispielsweise verwenden einen Funktionszeiger, Sie Aufrufen einer Funktion in einer DLL, die als exportiert wird [__stdcall](../../cpp/stdcall.md) , aber Sie deklarieren den Zeiger an die Funktion als [__cdecl](../../cpp/cdecl.md).

**n**<br/>
Meldet, wenn eine Variable wurde ohne Initialisierung verwendet wird. Z. B. eine Anweisung, die generiert `C4701` möglicherweise einen Fehler zur Laufzeit generiert **/RTC**`u`. Jede Anweisung, [Compilerwarnung (Stufe 1 und Stufe 4) C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md) generiert einen Laufzeitfehler unter **/RTC**`u`.

Beachten Sie jedoch, das folgende Codefragment:

```cpp
int a, *b, c;
if ( 1 )
b = &a;
c = a;  // No run-time error with /RTCu
```

Wenn eine Variable initialisiert wurden kann, es nicht gemeldet werden zur Laufzeit **/RTC**`u`. Z. B. nach dem eine Variable mit einem Alias versehen, über einen Zeiger ist, der Compiler nicht die Variable und Melden von nicht initialisierten verwendet. Aktiviert ist, können Sie eine Variable initialisieren, durch das Übernehmen der Adresse. Die & Operator funktioniert wie einen Zuweisungsoperator in dieser Situation.

## <a name="remarks"></a>Hinweise

Laufzeitfehler-Überprüfungen sind eine Möglichkeit, um Probleme in Ihrem ausgeführten Code zu ermitteln. Weitere Informationen finden Sie unter [Vorgehensweise: verwenden systemeigene Laufzeitüberprüfungen](/visualstudio/debugger/how-to-use-native-run-time-checks).

Wenn Sie das Programm in der Befehlszeile, die mit einer der Kompilieren der **/RTC** Compileroptionen, treten bei allen [optimieren](../../preprocessor/optimize.md) Anweisungen in Ihrem Code im Hintergrund fehl. Dies ist da fehlerprüfung zur Laufzeit in einem Releasebuild (optimiert) ungültig sind.

Verwenden Sie **/RTC** für Entwicklungsbuilds; **/RTC** sollte nicht für eine Verkaufsversion verwendet werden. **/ RTC** kann nicht verwendet werden, mit compileroptimierungen ([/o-Optionen (Code optimieren)](../../build/reference/o-options-optimize-code.md)). Ein Programm-Images erstellt, mit **/RTC** ist etwas größer und etwas langsamer als ein Bild mit erstellten **/Od** (bis zu 5 % langsamer als ein **/Od** erstellen).

Die Präprozessordirektive __MSVC_RUNTIME_CHECKS wird definiert werden, wenn Sie eine beliebige **/RTC** Option oder [/GZ](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die **Codegenerierung** Eigenschaftenseite.

1. Ändern Sie eine oder beide der folgenden Eigenschaften: **vollständige Laufzeitüberprüfungen** oder **kleinere Typüberprüfung**.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe die Eigenschaften <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BasicRuntimeChecks%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.SmallerTypeCheck%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[Gewusst wie: Verwenden von nativen Laufzeitprüfungen](/visualstudio/debugger/how-to-use-native-run-time-checks)