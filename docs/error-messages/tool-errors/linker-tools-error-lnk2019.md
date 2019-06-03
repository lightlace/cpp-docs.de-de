---
title: Linkertoolfehler LNK2019
ms.date: 12/15/2017
f1_keywords:
- LNK2019
helpviewer_keywords:
- nochkclr.obj
- LNK2019
- _check_commonlanguageruntime_version
ms.openlocfilehash: eb28ff3673c054b8ac1876d8ba736ceddfa5fd1a
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66449611"
---
# <a name="linker-tools-error-lnk2019"></a>Linkertoolfehler LNK2019

nicht aufgelöstes externes Symbol "*Symbol*"verwiesen wird, in der Funktion"*Funktion*"

Der kompilierte Code für *Funktion* stellt einen Verweis oder einen Aufruf von *Symbol*, aber dieses Symbol ist nicht definiert, in die Bibliotheken oder Objektdateien, die dem Linker angegeben.

Diese Fehlermeldung folgt Schwerwiegender Fehler [LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md). Sie müssen alle LNK2001 und LNK2019 Fehler zum Beheben von Fehler LNK1120 beheben.

## <a name="possible-causes"></a>Mögliche Ursachen

Es gibt viele Möglichkeiten, um diesen Fehler zu erhalten, aber alle umfassen einen Verweis auf eine Funktion oder Variable, die der Linker kann nicht *beheben*, oder suchen Sie eine Definition für. Der Compiler erkennen, wenn ein Symbol nicht *deklariert*, aber nicht bei nicht *definiert*, weil die Definition in einer anderen Quelldatei oder eine Bibliothek sein kann. Wenn ein Symbol ist bezeichnet, aber nicht definiert, generiert der Linker einen Fehler nicht aufgelöstes externes Symbol.

Hier sind einige der häufigsten Probleme aufgeführt, die zum Fehler LNK2019 führen:

### <a name="the-object-file-or-library-that-contains-the-definition-of-the-symbol-is-not-linked"></a>Die Objektdatei oder eine Bibliothek mit der Definition des Symbols ist nicht verknüpft.

In Visual Studio stellen Sie sicher, dass die Quelldatei mit der Definition erstellt und als Teil Ihres Projekts verknüpft ist. Stellen Sie sicher, dass die Quelldatei mit der Definition kompiliert wird, und dass die resultierende Objektdatei in der Liste der Dateien auf den link enthalten ist, in der Befehlszeile.

### <a name="the-declaration-of-the-symbol-is-not-spelled-the-same-as-the-definition-of-the-symbol"></a>Die Deklaration des Symbols ist nicht identisch mit der Definition des Symbols geschrieben

Überprüfen Sie die richtige Schreibweise und Groß-/Kleinschreibung wird in der Deklaration und Definition verwendet, und ganz egal, wo das Symbol wird verwendet oder aufgerufen wird.

### <a name="a-function-is-used-but-the-type-or-number-of-the-parameters-do-not-match-the-function-definition"></a>Eine Funktion wird verwendet, aber die Art und Anzahl der Parameter stimmen nicht überein die Funktionsdefinition

Die Funktionsdeklaration muss mit die Definition übereinstimmen. Stellen Sie sicher, dass der Funktionsaufruf der Deklaration entspricht und dass die Deklaration mit der Definition übereinstimmt. Für Code, der Vorlagenfunktionen aufruft, sind auch entsprechende Deklarationen der Vorlagenfunktionen erforderlich, die dieselben Vorlagenparameter wie die Definition enthalten. Ein Beispiel für eine Vorlage Deklaration Nichtübereinstimmung finden Sie unter Beispiel LNK2019e.cpp im Abschnitt "Beispiele".

### <a name="a-function-or-variable-is-declared-but-not-defined"></a>Eine Funktion oder Variable wurde deklariert, aber nicht definiert

Dies bedeutet in der Regel eine Deklaration, die in einer Headerdatei vorhanden ist, aber keine entsprechende Definition implementiert wurde. Für Memberfunktionen oder statische Datenmember muss die Implementierung die Klassenbereichsauswahl enthalten. Ein Beispiel finden Sie unter [Missing Function Body or Variable](../../error-messages/tool-errors/missing-function-body-or-variable.md).

### <a name="the-calling-convention-is-different-between-the-function-declaration-and-the-function-definition"></a>Die Aufrufkonvention unterscheidet sich zwischen der Deklaration und Definition der Funktion

Aufrufkonventionen ([__cdecl](../../cpp/cdecl.md), [__stdcall](../../cpp/stdcall.md), [__fastcall](../../cpp/fastcall.md)oder [__vectorcall](../../cpp/vectorcall.md)) werden als Teil des ergänzten Namens codiert. Stellen Sie sicher, dass die Aufrufkonvention identisch ist.

### <a name="a-symbol-is-defined-in-a-c-file-but-declared-without-using-extern-c-in-a-c-file"></a>Ein Symbol ist in einer C-Datei definiert, aber ohne Verwendung von Extern "C" in einer C++-Datei deklariert

Symbole, die in einer in C kompilierten Datei definiert sind, besitzen andere ergänzte Namen als Symbole, die in einer C++-Datei deklariert werden, es sei denn, Sie verwenden einen [extern "C"](../../cpp/using-extern-to-specify-linkage.md) -Modifizierer. Stellen Sie sicher, dass die Deklaration der Kompilierungsverknüpfung für jedes Symbol entspricht. Auch wenn Sie ein Symbol in einer C++-Datei definieren, die von einem C-Programm verwendet wird, verwenden Sie `extern "C"` in der Definition.

### <a name="a-symbol-is-defined-as-static-and-then-later-referenced-outside-the-file"></a>Ein Symbol als statisch definiert ist, und klicken Sie dann später außerhalb der Datei referenziert

Anders als in C, verfügen [globale Konstanten](../../error-messages/tool-errors/global-constants-in-cpp.md) in C++ über eine `static` -Verknüpfung. Um diese Einschränkung zu umgehen, können Sie die `const` -Initialisierungen in eine Headerdatei einfügen und diesen Header anschließend in die CPP-Dateien einfügen, oder Sie deklarieren die Variable als nicht konstant und verwenden einen konstanten Verweis, um darauf zuzugreifen.

### <a name="a-static-member-of-a-class-is-not-defined"></a>Ein statischer Member einer Klasse ist nicht definiert.

Ein statischer Klassenmember muss eine eindeutige Definition aufweisen, da ansonsten ODR (One Definition Rule) verletzt wird. Ein statischer Klassenmember, der nicht inline definiert werden kann, muss anhand seines vollqualifizierten Namens in einer Quelldatei definiert werden. Wenn er überhaupt nicht definiert wird, generiert der Linker LNK2019.

### <a name="a-build-dependency-is-only-defined-as-a-project-dependency-in-the-solution"></a>Eine Buildabhängigkeit wird nur als projektabhängigkeit in der Projektmappe definiert.

In früheren Versionen von Visual Studio war diese Ebene der Abhängigkeit ausreichend. Ab Visual Studio 2010, Visual Studio erfordert jedoch eine [Projekt-zu-Projekt-Verweis](/visualstudio/ide/managing-references-in-a-project). Wenn Ihr Projekt keinen Interprojektverweis enthält, wird dieser Linkerfehler möglicherweise angezeigt. Fügen Sie einen Interprojektverweis hinzu, um den Fehler zu beheben.

### <a name="you-build-a-console-application-by-using-settings-for-a-windows-application"></a>Sie erstellen eine Konsolenanwendung anhand von Einstellungen für eine Windows-Anwendung

Wenn die Fehlermeldung ähnelt **nicht aufgelöstes externes Symbol WinMain in Funktion referenced** *Function_name*, verknüpfen Sie über **Subsystem: Console** statt **Native**. Weitere Informationen zu dieser Einstellung und Anweisungen zum Festlegen dieser Eigenschaft in Visual Studio finden Sie unter [/SUBSYSTEM (Specify Subsystem)](../../build/reference/subsystem-specify-subsystem.md).

### <a name="you-attempt-to-link-64-bit-libraries-to-32-bit-code-or-32-bit-libraries-to-64-bit-code"></a>Sie versuchen, die 64-Bit-Bibliotheken mit 32-Bit-Code oder 32-Bit-Bibliotheken für 64-Bit-Code zu verknüpfen.

Bibliotheken und Objektdateien verknüpft werden, um Ihren Code müssen für die gleiche Architektur wie Ihren Code kompiliert werden. Überprüfen Sie, ob die Bibliotheken, die Ihre Projektverweise auf die gleiche Architektur wie das Projekt kompiliert werden. Stellen Sie sicher, dass die [/LIBPATH](../../build/reference/libpath-additional-libpath.md) oder **Zusätzliche Bibliotheksverzeichnisse** Pfadoption, die durch die Linker-verweist auf Bibliotheken, die für die richtige Architektur verwendet.

### <a name="you-use-different-compiler-options-for-function-inlining-in-different-source-files"></a>Sie verwenden verschiedene Compileroptionen für Inlinefunktionen in anderen Quelldateien

Durch die Verwendung von Inlinefunktionen, die in CPP-Dateien definiert sind, und die Kombination von Inlinecompileroptionen für Funktionen in anderen Quelldateien kann LNK2019 verursacht werden. Weitere Informationen finden Sie unter [Function Inlining Problems](../../error-messages/tool-errors/function-inlining-problems.md).

### <a name="you-use-automatic-variables-outside-their-scope"></a>Sie verwenden automatische Variablen außerhalb ihres Bereichs

Automatische Variablen (mit Funktionsgültigkeitsbereich) können nur im Rahmen dieser Funktion verwendet werden. Diese Variablen können nicht `extern` deklariert und in anderen Quelldateien verwendet werden. Ein Beispiel finden Sie unter [Automatic (Function Scope) Variables](../../error-messages/tool-errors/automatic-function-scope-variables.md).

### <a name="you-call-instrinsic-functions-or-pass-argument-types-to-intrinsic-functions-that-are-not-supported-on-your-target-architecture"></a>Sie rufen intrinsische Funktionen, oder übergeben Argumenttypen an intrinsische Funktionen, die auf der Zielarchitektur nicht unterstützt werden

Wenn Sie beispielsweise eine intrinsische AVX2-Funktion verwenden, aber nicht die Compileroption [/ARCH:AVX2](../../build/reference/arch-x86.md) angeben, nimmt der Compiler an, dass es sich bei der intrinsischen um eine externe Funktion handelt. Anstelle einer Inlineanweisung generiert der Compiler einen Aufruf an ein externes Symbol mit demselben Namen wie die intrinsische Funktion. Wenn der Linker versucht, die Definition dieser fehlende Funktion zu finden, wird LNK2019 generiert. Stellen Sie sicher, dass Sie nur intrinsische Funktionen und Typen verwenden, die von der Zielarchitektur unterstützt werden.

### <a name="you-mix-code-that-uses-native-wchart-with-code-that-doesnt"></a>Sie kombinieren Code, der systemeigenen Wchar verwendet\_t mit Code, der nicht

C++konformitätsverbesserung der Sprache, die in Visual Studio 2005 vorgenommene durchgeführt wurde `wchar_t` standardmäßig ein systemeigener Typ. Verwenden Sie die [/Zc:](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) Compileroption zum Generieren von Code mit Bibliotheks- und Objektdateien, kompiliert mit früheren Versionen von Visual Studio kompatibel. Wenn nicht alle Dateien mit der gleichen kompiliert wurden **/Zc:wchar\_t** Einstellungen Typenverweise möglicherweise nicht in kompatible Typen aufgelöst. Überprüfen Sie, ob `wchar_t` -Typen in allen Bibliotheks- und Objektdateien kompatibel sind. Aktualisieren Sie hierzu entweder die verwendeten Typen, oder verwenden Sie beim Kompilieren konsistente **/Zc:wchar_t** -Einstellungen.

## <a name="third-party-library-issues-and-vcpkg"></a>Bibliotheken von Drittanbietern Probleme und Vcpkg

Wenn dieser Fehler angezeigt wird, wenn Sie eine Drittanbieter-Bibliothek als Teil Ihres Builds konfigurieren möchten, sollten Sie [Vcpkg](../../vcpkg.md), im Visual C++ Paket-Manager zum Installieren und erstellen Sie die Bibliothek. Vcpkg unterstützt eine große und wachsende [Liste der Drittanbieter-Bibliotheken](https://github.com/Microsoft/vcpkg/tree/master/ports), und legt alle Eigenschaften und Abhängigkeiten, die als Teil des Projekts für erfolgreiche Builds erforderlich sind. Weitere Informationen finden Sie im zugehörigen [Visual C++-Blog](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/) Posten.

## <a name="diagnosis-tools"></a>Diagnosetools

Es kann schwierig sein festzustellen, warum der Linker eine bestimmte Symboldefinition nicht finden kann. Häufig ist das Problem, dass Sie enthalten nicht den Code, der die in Ihrem Build-Definition enthält, oder Build erstellte Optionen andere Namen für externe Symbole ergänzte. Es gibt mehrere Tools und Optionen, mit denen Sie einen Fehler LNK2019 diagnostizieren können.

- Mithilfe der Linkeroption [/VERBOSE](../../build/reference/verbose-print-progress-messages.md) können Sie ermitteln, auf welche Dateien der Linker verweist. Damit können Sie überprüfen, ob die Datei mit der Definition des Symbols in Ihrem Build enthalten ist.

- Die [/EXPORTS](../../build/reference/dash-exports.md) und [& gt; SYMBOLE](../../build/reference/symbols.md) Optionen auf der die **DUMPBIN** Dienstprogramm können Sie ermitteln, welche Symbole in den DLL- und Objekt- oder Bibliotheksdateien definiert sind. Stellen Sie sicher, dass die exportierten ergänzten Namen den ergänzten Namen entsprechen, die vom Linker gesucht werden.

- Die **UNDNAME** Dienstprogramm können Sie das entsprechende nicht ergänzte externe Symbol für einen ergänzten Namen anzeigen.

## <a name="examples"></a>Beispiele

Hier sind einige Beispiele für Code aufgeführt, der einen Fehler LNK2019 verursacht, sowie Informationen zur Behebung des Fehlers.

### <a name="a-symbol-is-declared-but-not-defined"></a>Ein Symbol wurde deklariert, aber nicht definiert

In diesem Beispiel wird eine externe Variable deklariert, aber nicht definiert:

```cpp
// LNK2019.cpp
// Compile by using: cl /EHsc /W4 LNK2019.cpp
// LNK2019 expected
extern char B[100];   // B is not available to the linker
int main() {
   B[0] = ' ';   // LNK2019
}
```

Ein weiteres Beispiel, in dem eine Variable und eine Funktion als deklariert `extern` jedoch wird keine Definition bereitgestellt:

```cpp
// LNK2019c.cpp
// Compile by using: cl /EHsc LNK2019c.cpp
// LNK2019 expected
extern int i;
extern void g();
void f() {
   i++;
   g();
}
int main() {}
```

Es sei denn, `i` und `g` definiert sind in einer der Dateien im Build enthalten ist, generiert der Linker LNK2019. Sie können die Fehler beheben, indem Sie die Quellcodedatei mit den Definitionen in die Kompilierung einbeziehen. Alternativ können Sie OBJ- oder LIB-Dateien, die die Definitionen für den Linker enthalten übergeben.

### <a name="a-static-data-member-is-declared-but-not-defined"></a>Ein statischer Datenmember wurde deklariert, aber nicht definiert

LNK2019 kann auch auftreten, wenn ein statischer Datenmember deklariert, aber nicht definiert wurde. Im folgenden Beispiel wird LNK2019 generiert und gezeigt, wie Sie diesen Fehler beheben.

```cpp
// LNK2019b.cpp
// Compile by using: cl /EHsc LNK2019b.cpp
// LNK2019 expected
struct C {
   static int s;
};

// Uncomment the following line to fix the error.
// int C::s;

int main() {
   C c;
   C::s = 1;
}
```

### <a name="declaration-parameters-do-not-match-definition"></a>Deklarationsparameter stimmen nicht mit Definition überein

Code, der Vorlagenfunktionen aufruft, muss übereinstimmende Deklarationen von Vorlagenfunktionen aufweisen. Deklarationen müssen dieselben Vorlagenparameter wie die Definition enthalten. Das folgende Beispiel generiert LNK2019 für einen benutzerdefinierten Operator und zeigt, wie Sie diesen Fehler beheben.

```cpp
// LNK2019e.cpp
// compile by using: cl /EHsc LNK2019e.cpp
// LNK2019 expected
#include <iostream>
using namespace std;

template<class T> class
Test {
   // The operator<< declaration does not match the definition below:
   friend ostream& operator<<(ostream&, Test&);
   // To fix, replace the line above with the following:
   // template<typename T> friend ostream& operator<<(ostream&, Test<T>&);
};

template<typename T>
ostream& operator<<(ostream& os, Test<T>& tt) {
   return os;
}

int main() {
   Test<int> t;
   cout << "Test: " << t << endl;   // LNK2019 unresolved external
}
```

### <a name="inconsistent-wchart-type-definitions"></a>Inkonsistente wchar_t-Typdefinitionen

Dieses Beispiel erstellt eine DLL, die einen Export verfügt, verwendet `WCHAR`, dieser wird in aufgelöst `wchar_t`.

```cpp
// LNK2019g.cpp
// compile with: cl /EHsc /LD LNK2019g.cpp
#include "windows.h"
// WCHAR resolves to wchar_t
__declspec(dllexport) void func(WCHAR*) {}
```

Im folgenden Beispiel wird die DLL aus dem vorherigen Beispiel verwendet und LNK2019 generiert, da die Typen ohne, Short * und WCHAR Vorzeichen\* stimmen nicht überein.

```cpp
// LNK2019h.cpp
// compile by using: cl /EHsc LNK2019h LNK2019g.lib
// LNK2019 expected
__declspec(dllimport) void func(unsigned short*);

int main() {
   func(0);
}
```

Um diesen Fehler zu beheben, ändern `unsigned short` zu `wchar_t` oder `WCHAR`, oder Kompilieren Sie "LNK2019g.cpp" über **/Zc:** .

## <a name="additional-resources"></a>Zusätzliche Ressourcen

Weitere Informationen zu möglichen Ursachen und Lösungen für LNK2001 finden Sie unter der Stack Overflow-Frage [Was ist ein Fehler für undefined Reference/unresolved external Symbol, und wie behebe ich es?](https://stackoverflow.com/q/12573816/2002113).

