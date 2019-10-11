---
title: Linkertoolfehler LNK2019
ms.date: 12/15/2017
f1_keywords:
- LNK2019
helpviewer_keywords:
- nochkclr.obj
- LNK2019
- _check_commonlanguageruntime_version
ms.openlocfilehash: 3c4e5578c7b0f496feb4d40933af624f462a31d2
ms.sourcegitcommit: 680a155cc44a38f88bb2b1c5a1ef6dcb7141c011
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "72252620"
---
# <a name="linker-tools-error-lnk2019"></a>Linkertoolfehler LNK2019

nicht aufgelöstes externes Symbol '*Symbol*' in Funktion '*Funktion*' referenziert

Der kompilierte Code für die *Funktion* erstellt einen Verweis oder einen aufrufbefehl, aber dieses Symbol ist in keiner der Bibliotheken oder Objektdateien definiert, die für den Linker *angegeben sind.*

Auf diese Fehlermeldung folgt ein schwerwiegender Fehler [Linkertoolfehler LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md). Sie müssen alle LNK2001-und LNK2019-Fehler beheben, um den Fehler Linkertoolfehler LNK1120 zu beheben.

## <a name="possible-causes"></a>Mögliche Ursachen

Es gibt viele Möglichkeiten, diesen Fehler zu erhalten, aber alle enthalten einen Verweis auf eine Funktion oder Variable, die der Linker nicht *Auflösen*kann, oder eine Definition für finden. Der Compiler kann erkennen, wenn ein Symbol nicht *deklariert*ist, aber nicht, wenn es nicht *definiert*ist, da sich die Definition in einer anderen Quelldatei oder Bibliothek befinden kann. Wenn auf ein Symbol verwiesen wird, aber nie definiert, generiert der Linker einen nicht aufgelösten externen symbolfehler.

Hier sind einige der häufigsten Probleme aufgeführt, die zum Fehler LNK2019 führen:

### <a name="the-object-file-or-library-that-contains-the-definition-of-the-symbol-is-not-linked"></a>Die Objektdatei oder-Bibliothek, die die Definition des Symbols enthält, ist nicht verknüpft.

Überprüfen Sie in Visual Studio, ob die Quelldatei, die die Definition enthält, als Teil des Projekts erstellt und verknüpft ist. Überprüfen Sie in der Befehlszeile, ob die Quelldatei, die die Definition enthält, kompiliert ist, und dass die resultierende Objektdatei in der Liste der zu verknüpfenden Dateien enthalten ist.

### <a name="the-declaration-of-the-symbol-is-not-spelled-the-same-as-the-definition-of-the-symbol"></a>Die Deklaration des Symbols ist nicht mit der Definition des Symbols identisch.

Überprüfen Sie, ob die korrekte Schreibweise und groß-und Kleinschreibung sowohl in der Deklaration als auch in der Definition verwendet wird und wo das Symbol verwendet oder aufgerufen

### <a name="a-function-is-used-but-the-type-or-number-of-the-parameters-do-not-match-the-function-definition"></a>Eine Funktion wird verwendet, aber der Typ oder die Anzahl der Parameter stimmt nicht mit der Funktionsdefinition.

Die Funktionsdeklaration muss mit die Definition übereinstimmen. Stellen Sie sicher, dass der Funktionsaufruf der Deklaration entspricht und dass die Deklaration mit der Definition übereinstimmt. Für Code, der Vorlagenfunktionen aufruft, sind auch entsprechende Deklarationen der Vorlagenfunktionen erforderlich, die dieselben Vorlagenparameter wie die Definition enthalten. Ein Beispiel für eine nicht übereinstimmende Vorlagen Deklaration finden Sie im Abschnitt "Sample LNK2019e. cpp" im Abschnitt "Beispiele".

### <a name="a-function-or-variable-is-declared-but-not-defined"></a>Eine Funktion oder Variable wurde deklariert, aber nicht definiert.

Dies bedeutet normalerweise, dass eine Deklaration in einer Header Datei vorhanden ist, aber keine übereinstimmende Definition implementiert wird. Für Memberfunktionen oder statische Datenmember muss die Implementierung die Klassenbereichsauswahl enthalten. Ein Beispiel finden Sie unter [Missing Function Body or Variable](../../error-messages/tool-errors/missing-function-body-or-variable.md).

### <a name="the-calling-convention-is-different-between-the-function-declaration-and-the-function-definition"></a>Die Aufruf Konvention unterscheidet sich zwischen der Funktionsdeklaration und der Funktionsdefinition.

Aufrufkonventionen ([__cdecl](../../cpp/cdecl.md), [__stdcall](../../cpp/stdcall.md), [__fastcall](../../cpp/fastcall.md)oder [__vectorcall](../../cpp/vectorcall.md)) werden als Teil des ergänzten Namens codiert. Stellen Sie sicher, dass die Aufrufkonvention identisch ist.

### <a name="a-symbol-is-defined-in-a-c-file-but-declared-without-using-extern-c-in-a-c-file"></a>Ein Symbol ist in einer C-Datei definiert, wurde aber ohne Verwendung von extern "C" C++ in einer Datei deklariert.

Symbole, die in einer in C kompilierten Datei definiert sind, besitzen andere ergänzte Namen als Symbole, die in einer C++-Datei deklariert werden, es sei denn, Sie verwenden einen [extern "C"](../../cpp/using-extern-to-specify-linkage.md) -Modifizierer. Stellen Sie sicher, dass die Deklaration der Kompilierungsverknüpfung für jedes Symbol entspricht. Auch wenn Sie ein Symbol in einer C++-Datei definieren, die von einem C-Programm verwendet wird, verwenden Sie `extern "C"` in der Definition.

### <a name="a-symbol-is-defined-as-static-and-then-later-referenced-outside-the-file"></a>Ein Symbol wird als statisch definiert und später außerhalb der Datei referenziert.

Anders als in C, verfügen [globale Konstanten](../../error-messages/tool-errors/global-constants-in-cpp.md) in C++ über eine `static` -Verknüpfung. Um diese Einschränkung zu umgehen, können Sie die `const` -Initialisierungen in eine Headerdatei einfügen und diesen Header anschließend in die CPP-Dateien einfügen, oder Sie deklarieren die Variable als nicht konstant und verwenden einen konstanten Verweis, um darauf zuzugreifen.

### <a name="a-static-member-of-a-class-is-not-defined"></a>Ein statischer Member einer Klasse ist nicht definiert.

Ein statischer Klassenmember muss eine eindeutige Definition aufweisen, da ansonsten ODR (One Definition Rule) verletzt wird. Ein statischer Klassenmember, der nicht inline definiert werden kann, muss anhand seines vollqualifizierten Namens in einer Quelldatei definiert werden. Wenn er überhaupt nicht definiert wird, generiert der Linker LNK2019.

### <a name="a-build-dependency-is-only-defined-as-a-project-dependency-in-the-solution"></a>Eine Buildabhängigkeit wird nur als Projekt Abhängigkeit in der Lösung definiert.

In früheren Versionen von Visual Studio war dieses Abhängigkeits Niveau ausreichend. Ab Visual Studio 2010 erfordert Visual Studio jedoch einen [Projekt-zu-Projekt-Verweis](/visualstudio/ide/managing-references-in-a-project). Wenn Ihr Projekt keinen Interprojektverweis enthält, wird dieser Linkerfehler möglicherweise angezeigt. Fügen Sie einen Interprojektverweis hinzu, um den Fehler zu beheben.

### <a name="an-entry-point-is-not-defined"></a>Ein Einstiegspunkt ist nicht definiert.

Der Anwendungscode muss einen geeigneten Einstiegspunkt definieren: `main` oder `wmain` für Konsolen Anwendungen, `WinMain` oder `wWinMain` für Windows-Anwendungen. Weitere Informationen finden Sie unter [main: Programmstart @ no__t-0 oder [WinMain-Funktion](/windows/win32/api/winbase/nf-winbase-winmain). Wenn Sie einen benutzerdefinierten Einstiegspunkt verwenden möchten, geben Sie die Linkeroption [/Entry (Einstiegspunkt Symbol)](../../build/reference/entry-entry-point-symbol.md) an. 

### <a name="you-build-a-console-application-by-using-settings-for-a-windows-application"></a>Sie erstellen eine Konsolenanwendung mithilfe von Einstellungen für eine Windows-Anwendung.

Wenn die Fehlermeldung dem nicht aufgelösten **externen Symbol ähnelt, auf das in der** *function_name*-Funktion verwiesen wird, verknüpfen Sie diese mithilfe von **/Subsystem: Console** anstelle von **/Subsystem: Windows**. Weitere Informationen zu dieser Einstellung und Anweisungen zum Festlegen dieser Eigenschaft in Visual Studio finden Sie unter [/SUBSYSTEM (Specify Subsystem)](../../build/reference/subsystem-specify-subsystem.md).

### <a name="you-attempt-to-link-64-bit-libraries-to-32-bit-code-or-32-bit-libraries-to-64-bit-code"></a>Sie versuchen, 64-Bit-Bibliotheken mit 32-Bit-Code oder 32-Bit-Bibliotheken in 64-Bit-Code zu verknüpfen.

Bibliotheken und Objektdateien, die mit dem Code verknüpft sind, müssen für die gleiche Architektur wie der Code kompiliert werden. Vergewissern Sie sich, dass die Bibliotheken, auf die Ihr Projekt verweist, für dieselbe Architektur wie das Projekt kompiliert werden. Stellen Sie sicher, dass die vom Linker verwendete Pfad Option " [/LIBPATH](../../build/reference/libpath-additional-libpath.md) " oder " **zusätzliche Bibliotheks Verzeichnisse** " auf Bibliotheken verweist, die für die richtige Architektur erstellt wurden.

### <a name="you-use-different-compiler-options-for-function-inlining-in-different-source-files"></a>Sie verwenden verschiedene Compileroptionen für Inline Funktionen in verschiedenen Quelldateien.

Durch die Verwendung von Inlinefunktionen, die in CPP-Dateien definiert sind, und die Kombination von Inlinecompileroptionen für Funktionen in anderen Quelldateien kann LNK2019 verursacht werden. Weitere Informationen finden Sie unter [Function Inlining Problems](../../error-messages/tool-errors/function-inlining-problems.md).

### <a name="you-use-automatic-variables-outside-their-scope"></a>Sie verwenden automatische Variablen außerhalb ihres Bereichs.

Automatische Variablen (mit Funktionsgültigkeitsbereich) können nur im Rahmen dieser Funktion verwendet werden. Diese Variablen können nicht `extern` deklariert und in anderen Quelldateien verwendet werden. Ein Beispiel finden Sie unter [Automatic (Function Scope) Variables](../../error-messages/tool-errors/automatic-function-scope-variables.md).

### <a name="you-call-instrinsic-functions-or-pass-argument-types-to-intrinsic-functions-that-are-not-supported-on-your-target-architecture"></a>Sie können instreinsic-Funktionen oder Argument Typen an intrinsische Funktionen übergeben, die von der Zielarchitektur nicht unterstützt werden.

Wenn Sie beispielsweise eine intrinsische AVX2-Funktion verwenden, aber nicht die Compileroption [/ARCH:AVX2](../../build/reference/arch-x86.md) angeben, nimmt der Compiler an, dass es sich bei der intrinsischen um eine externe Funktion handelt. Anstelle einer Inlineanweisung generiert der Compiler einen Aufruf an ein externes Symbol mit demselben Namen wie die intrinsische Funktion. Wenn der Linker versucht, die Definition dieser fehlende Funktion zu finden, wird LNK2019 generiert. Stellen Sie sicher, dass Sie nur intrinsische Funktionen und Typen verwenden, die von der Zielarchitektur unterstützt werden.

### <a name="you-mix-code-that-uses-native-wchar_t-with-code-that-doesnt"></a>Sie mischen Code, der Native WCHAR @ no__t-0t mit Code verwendet, der nicht

C++die sprach Konformität, die in Visual Studio 2005 durchgeführt wurde, hat standardmäßig einen systemeigenen Typ `wchar_t` erstellt. Sie müssen die [/Zc: wchar_t-Compileroption](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) verwenden, um Code zu generieren, der mit Bibliothek-und Objektdateien kompatibel ist, die mit früheren Versionen von Visual Studio kompiliert wurden. Wenn nicht alle Dateien mit denselben **/Zc: WCHAR @ no__t-1T-** Einstellungen kompiliert wurden, werden Typverweise möglicherweise nicht in kompatible Typen aufgelöst. Überprüfen Sie, ob `wchar_t` -Typen in allen Bibliotheks- und Objektdateien kompatibel sind. Aktualisieren Sie hierzu entweder die verwendeten Typen, oder verwenden Sie beim Kompilieren konsistente **/Zc:wchar_t** -Einstellungen.

## <a name="third-party-library-issues-and-vcpkg"></a>Drittanbieter-Bibliotheks Probleme und vcpkg

Wenn dieser Fehler angezeigt wird, wenn Sie versuchen, eine Bibliothek eines Drittanbieters als Teil Ihres Builds zu konfigurieren, sollten Sie die Verwendung von [vcpkg](../../vcpkg.md), dem visuellen C++ Paket-Manager, zum Installieren und Erstellen der Bibliothek in Erwägung gezogen. Vcpkg unterstützt eine große und wachsende [Liste von Bibliotheken von Drittanbietern](https://github.com/Microsoft/vcpkg/tree/master/ports)und legt alle Konfigurations Eigenschaften und Abhängigkeiten, die für erfolgreiche Builds erforderlich sind, als Teil des Projekts fest. Weitere Informationen finden Sie im zugehörigen [visuellen C++ Blog](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/) Beitrag.

## <a name="diagnosis-tools"></a>Diagnosetools

Es kann schwierig sein festzustellen, warum der Linker eine bestimmte Symboldefinition nicht finden kann. Häufig besteht das Problem darin, dass Sie den Code, der die Definition enthält, nicht in Ihren Build einbezogen haben oder dass Buildoptionen verschiedene ergänzte Namen für externe Symbole erstellt haben. Es gibt mehrere Tools und Optionen, mit denen Sie einen Fehler LNK2019 diagnostizieren können.

- Mithilfe der Linkeroption [/VERBOSE](../../build/reference/verbose-print-progress-messages.md) können Sie ermitteln, auf welche Dateien der Linker verweist. Damit können Sie überprüfen, ob die Datei mit der Definition des Symbols in Ihrem Build enthalten ist.

- Mithilfe der Optionen [/Exports](../../build/reference/dash-exports.md) und [/Symbols](../../build/reference/symbols.md) des **DUMPBIN** -Hilfsprogramms können Sie ermitteln, welche Symbole in den dll-und Objekt-oder Bibliotheksdateien definiert sind. Stellen Sie sicher, dass die exportierten ergänzten Namen den ergänzten Namen entsprechen, die vom Linker gesucht werden.

- Das Hilfsprogramm **undname** kann Ihnen das entsprechende nicht ergänzte externe Symbol für einen ergänzten Namen anzeigen.

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

Im folgenden finden Sie ein weiteres Beispiel, in dem eine Variable und eine Funktion als `extern` deklariert sind, aber keine Definition bereitgestellt wird:

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

Wenn `i` und `g` in einer der Dateien, die im Build enthalten sind, definiert sind, generiert der Linker LNK2019. Sie können die Fehler beheben, indem Sie die Quellcodedatei mit den Definitionen in die Kompilierung einbeziehen. Alternativ können Sie obj-oder LIB-Dateien, die die Definitionen enthalten, an den Linker übergeben.

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

### <a name="inconsistent-wchar_t-type-definitions"></a>Inkonsistente wchar_t-Typdefinitionen

In diesem Beispiel wird eine DLL mit einem Export erstellt, der `WCHAR` verwendet, der in `wchar_t` aufgelöst wird.

```cpp
// LNK2019g.cpp
// compile with: cl /EHsc /LD LNK2019g.cpp
#include "windows.h"
// WCHAR resolves to wchar_t
__declspec(dllexport) void func(WCHAR*) {}
```

Im nächsten Beispiel wird die dll im vorherigen Beispiel verwendet, und LNK2019 wird generiert, da die Typen Ganzzahl ohne Vorzeichen Short * und WCHAR @ no__t-0 nicht identisch sind.

```cpp
// LNK2019h.cpp
// compile by using: cl /EHsc LNK2019h LNK2019g.lib
// LNK2019 expected
__declspec(dllimport) void func(unsigned short*);

int main() {
   func(0);
}
```

Um diesen Fehler zu beheben, ändern Sie `unsigned short` in `wchar_t` oder `WCHAR`, oder kompilieren Sie "LNK2019g. cpp mithilfe von **/Zc: wchar_t-** .

## <a name="additional-resources"></a>Zusätzliche Ressourcen

Weitere Informationen zu möglichen Ursachen und Lösungen für LNK2001 finden Sie in der Stack Overflow Frage, [was ein nicht definierter Verweis/nicht aufgelöstes externes Symbol ist, und wie kann ich das Problem beheben?](https://stackoverflow.com/q/12573816/2002113).

