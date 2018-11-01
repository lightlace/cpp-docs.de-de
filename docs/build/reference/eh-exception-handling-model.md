---
title: /EH (Ausnahmebehandlungsmodell)
ms.date: 08/14/2018
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ExceptionHandling
- /eh
- VC.Project.VCCLCompilerTool.ExceptionHandling
helpviewer_keywords:
- exception handling, compiler model
- cl.exe compiler, exception handling
- EH compiler option [C++]
- -EH compiler option [C++]
- /EH compiler option [C++]
ms.assetid: 754b916f-d206-4472-b55a-b6f1b0f2cb4d
ms.openlocfilehash: f118f55ddaa4a2dbc8a4a3ad1e596ec461a2b078
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615058"
---
# <a name="eh-exception-handling-model"></a>/EH (Ausnahmebehandlungsmodell)

Gibt die Art der Ausnahmebehandlung an, die vom Compiler verwendet werden soll, gibt an, ob Ausnahmeprüfungen wegoptimiert werden sollen, und gibt an, ob C++-Objekte zerstört werden sollen, die sich aufgrund einer Ausnahme nicht mehr im Gültigkeitsbereich befinden. Wenn **/EH** nicht angegeben ist, der Compiler sowohl asynchrone strukturierte Ausnahmen als auch C++-Ausnahmen abfangen über Ihren Code ermöglicht, aber nicht zerstört C++-Objekte, die wegen einer asynchronen Ausnahme außerhalb des gültigen Bereichs zu wechseln.

## <a name="syntax"></a>Syntax

> **/ EH**{**s**|**eine**} [**c**] [**r**] [**-**]

## <a name="arguments"></a>Argumente

|||
|-|-|
**a**|Das Ausnahmebehandlungsmodell, die zwar beide asynchron abfängt (strukturierte) und synchrone (C++) Ausnahmen mithilfe c++ `catch(...)` Syntax.
**s**|Das Ausnahmebehandlungsmodell, die nur synchrone (C++)-Ausnahmen erfasst, und weist den Compiler an, wird davon ausgegangen, dass Funktionen als deklariert **Extern "C"** möglicherweise eine Ausnahme auslösen.
**c**|Bei Verwendung mit **s** (**/EHsc**) nur C++-Ausnahmen erfasst, und weist den Compiler an, wird davon ausgegangen, dass Funktionen als deklariert **Extern "C"** nie eine C++-Ausnahme auslösen. **/EHca** entspricht **/EHa**.
**r**|Weist den Compiler an, immer laufzeitbeendigungsprüfungen für alle generieren **"noexcept"** Funktionen. Standardmäßig sucht Common Language Runtime **"noexcept"** wegoptimiert werden, wenn der Compiler bestimmt die Funktion ruft nur nicht auslösende Funktionen.

## <a name="remarks"></a>Hinweise

Die Compileroption **/EHa** unterstützt die asynchrone strukturierte Ausnahmebehandlung (Structured Exception Handling, SEH) mit der systemeigenen C++-Klausel `catch(...)` . Zur Implementierung von SEH ohne Angabe von **/EHa**, können Sie die **__try**, **__except**, und **__finally** Syntax. SEH wird zwar von Windows und Visual C++ unterstützt, trotzdem ist die Verwendung der ISO-Standard-C++-Ausnahmebehandlung (**/EHs** oder **/EHsc**) empfehlenswert, da Code damit besser portierbar und flexibler ist. Dennoch in vorhandenem Code oder für bestimmte Arten von Programmen – z. B. in Code, der zur Unterstützung der common Language Runtime kompiliert ([/CLR (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md)) – Sie können es erforderlich sein, die SEH verwenden. Weitere Informationen finden Sie unter [Structured Exception Handling (C/C++)](../../cpp/structured-exception-handling-c-cpp.md).

Die Angabe von **/EHa** und der Versuch, alle Ausnahmen mit `catch(...)` zu behandeln, kann riskant sein. Da asynchrone Ausnahmen größtenteils nicht behebbar sind, gelten sie als schwerwiegende Ausnahmen. Wenn Sie sie abfangen und den Prozess anschließend fortsetzen, können Beschädigungen und Fehler auftreten, die schwer zu finden und zu beheben sind.

Wenn Sie **/EHs** oder **/EHsc**verwenden, werden durch die `catch(...)` -Klausel keine asynchronen strukturierten Ausnahmen abgefangen. Zugriffverletzungen und verwaltete <xref:System.Exception?displayProperty=fullName> -Ausnahmen werden nicht abgefangen, und beim Erzeugen von asynchronen Ausnahmen werden Objekte im Gültigkeitsbereich nicht beschädigt, auch dann nicht, wenn die asynchrone Ausnahme behandelt wird.

Bei Verwendung von **/EHa**, das Bild möglicherweise ein größeres und weniger leistungsfähiges kann ausgeführt werden, da der Compiler nicht optimiert ist eine **versuchen** so aggressiv blockiert. Außerdem bewirkt es ein Verlassen in Ausnahmefiltern, die automatisch die Destruktoren aller lokalen Objekte aufrufen, und zwar selbst dann, wenn der Compiler keinen Code feststellt, der eine C++-Ausnahme auslösen kann. Dies ermöglicht sichere Stapelentladungen für asynchrone Ausnahmen sowie für C++-Ausnahmen. Bei Verwendung von **/EHs**, nimmt der Compiler an, dass Ausnahmen nur auftreten können, auf eine **auslösen** Anweisung oder auf ein Funktionsaufruf. Damit kann der Compiler Code für die Lebensdauerverfolgung vieler nicht entladbarer Objekte entfernen, wodurch sich die Codegröße u. U. deutlich reduziert.

Es wird empfohlen, dass Sie keine Objekte, die mit Verknüpfung **/EHa** zusammen mit der Objekte, die mit **/EHs** oder **/EHsc** im selben ausführbaren Modul. Wenn Sie eine asynchrone Ausnahme behandeln müssen, indem Sie **/EHa** an einer beliebigen Position innerhalb des Moduls verwenden, kompilieren Sie mithilfe von **/EHa** den gesamten Code im Modul. Können Sie strukturierte ausnahmebehandlungssyntax im selben Modul wie Code, der kompiliert wird **/EHs**, jedoch nicht möglich, die SEH-Syntax mit **versuchen**, **auslösen**, und **catch** in derselben Funktion.

Verwendung **/EHa** sollten Sie eine Ausnahme abfangen, die durch eine Aktion, anders als ausgelöst wird eine **auslösen**. Im nachfolgenden Beispiel wird eine strukturierte Ausnahme generiert und abgefangen:

```cpp
// compiler_options_EHA.cpp
// compile with: /EHa
#include <iostream>
#include <excpt.h>
using namespace std;

void fail() {   // generates SE and attempts to catch it using catch(...)
   try {
      int i = 0, j = 1;
      j /= i;   // This will throw a SE (divide by zero).
      printf("%d", j);
   }
   catch(...) {   // catch block will only be executed under /EHa
      cout<<"Caught an exception in catch(...)."<<endl;
   }
}

int main() {
   __try {
      fail();
   }

   // __except will only catch an exception here
   __except(EXCEPTION_EXECUTE_HANDLER) {
      // if the exception was not caught by the catch(...) inside fail()
      cout << "An exception was caught in __except." << endl;
   }
}
```

Für die **/EHc** -Option muss **/EHs** oder **/EHa** angegeben sein. Die **"/ CLR"** Option impliziert **/EHa** (d. h. **"/ CLR"** **/EHa** ist redundant). Der Compiler generiert einen Fehler aus, wenn **/EHs** oder **/EHsc** wird verwendet, nach dem **"/ CLR"**. Optimierungen haben auf dieses Verhalten keinen Einfluss. Wenn die Ausnahme abgefangen wird, werden vom Compiler die Klassendestruktoren für die Objekte aufgerufen, die sich in demselben Gültigkeitsbereich wie die Ausnahme befinden. Wenn eine Ausnahme nicht abgefangen wird, werden diese Destruktoren nicht ausgeführt.

Weitere Informationen über Beschränkungen für die Ausnahmebehandlung unter **/clr**finden Sie unter [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md).

Die Option kann mit dem Symbol **-** deaktiviert werden. Z. B. **/EHsc-** als interpretiert **/EHs** **EHc-** entspricht **/EHs**.

Die **/EHr** -Compileroption erzwingt laufzeitbeendigungsprüfungen in allen Funktionen, die eine **"noexcept"** Attribut. Standardmäßig können Laufzeitprüfungen wegoptimiert werden, wenn das Compiler-Back-End feststellt, dass eine Funktion nur *nicht auslösende* Funktionen aufruft. Nicht auslösende Funktionen sind alle Funktionen, die ein Attribut haben, das angibt, dass keine Ausnahmen ausgelöst werden können. Hierzu gehören Funktionen, die markiert **"noexcept"**, `throw()`, `__declspec(nothrow)`, und wann **/EHc** angegeben wird, **Extern "C"** Funktionen. Zu den nicht auslösenden Funktionen gehört auch jede Funktion, für die der Compiler durch Prüfung ermittelt hat, dass sie nicht auslösend ist. Sie können die Standardeinstellung explizit mit **/EHr-** festlegen.

Das Attribut für nicht auslösend bedingt jedoch keine Garantie, dass von einer Funktion keine Ausnahmen ausgelöst werden können. Im Gegensatz zu das Verhalten einer **"noexcept"** -Funktion, die Visual C++-Compiler betrachtet eine Ausnahme, die von einer Funktion deklariert, mit `throw()`, `__declspec(nothrow)`, oder **Extern "C"** als nicht definiert Verhalten. Funktionen, für die diese drei Deklarationsattribute verwendet werden, erzwingen keine Laufzeitbeendigungsprüfungen für Ausnahmen. Können Sie die **/EHr** können Sie dies erkennen können zu nicht definiertem Verhalten, durch den Compiler an, laufzeitprüfungen für nicht behandelte Ausnahmen zu generieren, Erzwingen einer **"noexcept"** Funktion.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie **Konfigurationseigenschaften** > **C/C++-** > **Codegenerierung**.

1. Ändern Sie die Eigenschaft **C++-Ausnahmen aktivieren** .

   Oder legen Sie den Wert für **C++-Ausnahmen aktivieren** auf **Nein**fest, und fügen Sie dann auf der Eigenschaftenseite **Befehlszeile** im Feld **Zusätzliche Optionen** die Compileroption hinzu.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExceptionHandling%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[Fehler- und Ausnahmebehandlung](../../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[Ausnahmespezifikationen (throw)](../../cpp/exception-specifications-throw-cpp.md)<br/>
[Strukturierte Ausnahmebehandlung (C/C++)](../../cpp/structured-exception-handling-c-cpp.md)
