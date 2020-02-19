---
title: Attribute inC++
ms.date: 05/06/2019
ms.assetid: 748340d9-8abf-4940-b0a0-91b6156a3ff8
ms.openlocfilehash: b3ed21b033c0e606d02d3aa845f09f72118a3c5e
ms.sourcegitcommit: 7bea0420d0e476287641edeb33a9d5689a98cb98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/17/2020
ms.locfileid: "77416074"
---
# <a name="attributes-in-c"></a>Attribute inC++

Der C++ Standard definiert einen Satz von Attributen und ermöglicht compileranbietern auch das Definieren Ihrer eigenen Attribute (innerhalb eines herstellerspezifischen Namespace). Compiler müssen jedoch nur die im Standard definierten Attribute erkennen.

In einigen Fällen überlappen sich Standard Attribute mit compilerspezifischen declspec-Parametern. In Visual C++können Sie das `[[deprecated]]`-Attribut verwenden, anstatt `declspec(deprecated)` zu verwenden, und das-Attribut wird von jedem entsprechenden Compiler erkannt. Für alle anderen declspec-Parameter, wie z. b. DllImport und dllexport, gibt es noch kein Attribut äquivalent, sodass Sie weiterhin die declspec-Syntax verwenden müssen. Attribute wirken sich nicht auf das Typsystem aus und ändern die Bedeutung eines Programms nicht. Compiler ignorieren Attributwerte, die Sie nicht erkennen.

**Visual Studio 2017 Version 15,3 und** höher (verfügbar mit [/Std: c++ 17](../build/reference/std-specify-language-standard-version.md)): im Bereich einer Attribut Liste können Sie den Namespace für alle Namen mit einem einzelnen **mithilfe** von Introduction angeben:

```cpp
void g() {
    [[using rpr: kernel, target(cpu,gpu)]] // equivalent to [[ rpr::kernel, rpr::target(cpu,gpu) ]]
    do task();
}
```

## <a name="c-standard-attributes"></a>C++Standard Attribute

In c++ 11 bieten Attribute eine standardisierte Möglichkeit zum Kommentieren von C++ Konstrukten (einschließlich, aber nicht beschränkt auf Klassen, Funktionen, Variablen und Blöcke) mit zusätzlichen Informationen, die möglicherweise Hersteller spezifisch sind. Ein Compiler kann diese Informationen zum Generieren von Informationsmeldungen oder zum Anwenden spezieller Logik beim Kompilieren des attributierten Codes verwenden. Der Compiler ignoriert alle Attribute, die nicht erkannt werden. Dies bedeutet, dass Sie mit dieser Syntax keine eigenen benutzerdefinierten Attribute definieren können. Attribute werden durch doppelte eckige Klammern eingeschlossen:

```cpp
[[deprecated]]
void Foo(int);
```

Attribute stellen eine standardisierte Alternative zu herstellerspezifischen Erweiterungen, z. b. #pragma Direktiven, __declspec ( C++) (Visual &#95; &#95;)&#95; &#95; oder Attribut (GNU) dar. Für die meisten Zwecke müssen Sie jedoch weiterhin die herstellerspezifischen Konstrukte verwenden. Der Standard gibt derzeit die folgenden Attribute an, die ein konformer Compiler erkennen sollte:

- `[[noreturn]]` gibt an, dass eine Funktion niemals zurückgibt. Das heißt, es wird immer eine Ausnahme ausgelöst. Der Compiler kann seine Kompilierungs Regeln für `[[noreturn]]` Entitäten anpassen.

- `[[carries_dependency]]` gibt an, dass die Funktion die Reihenfolge der Daten Abhängigkeit in Bezug auf die Thread Synchronisierung weitergibt. Das-Attribut kann auf einen oder mehrere Parameter angewendet werden, um anzugeben, dass das übergebenen Argument eine Abhängigkeit in den Funktions Rumpf enthält. Das-Attribut kann auf die Funktion selbst angewendet werden, um anzugeben, dass der Rückgabewert eine Abhängigkeit von der Funktion enthält. Der Compiler kann diese Informationen verwenden, um effizienteren Code zu generieren.

- `[[deprecated]]` **Visual Studio 2015 und höher:** gibt an, dass eine Funktion nicht für die Verwendung vorgesehen ist und in zukünftigen Versionen einer Bibliotheks Schnittstelle möglicherweise nicht vorhanden ist. Der Compiler kann dies verwenden, um eine Informations Meldung zu generieren, wenn der Client Code versucht, die Funktion aufzurufen. Kann auf die Deklaration einer Klasse, einen Typedef-Namen, eine Variable, einen nicht statischen Datenmember, eine Funktion, einen Namespace, eine Enumeration, einen Enumerator oder eine Vorlagen Spezialisierung angewendet werden.

- `[[fallthrough]]` **Visual Studio 2017 und höher:** (verfügbar mit [/Std: c++ 17](../build/reference/std-specify-language-standard-version.md)) das `[[fallthrough]]`-Attribut kann im Kontext von [Switch](switch-statement-cpp.md) -Anweisungen als Hinweis für den Compiler verwendet werden (oder jeder, der den Code liest), der für das Ausweich Verhalten vorgesehen ist. Der Microsoft C++ -Compiler warnt derzeit nicht bei einem FallThrough-Verhalten, sodass dieses Attribut keine Auswirkung auf das Compilerverhalten hat.

- `[[nodiscard]]` **Visual Studio 2017 Version 15,3 und höher:** (verfügbar mit [/Std: c++ 17](../build/reference/std-specify-language-standard-version.md)) gibt an, dass der Rückgabewert einer Funktion nicht verworfen werden soll. Löst die Warnung C4834 aus, wie im folgenden Beispiel gezeigt:

    ```cpp
    [[nodiscard]]
    int foo(int i) { return i * i; }

    int main()
    {
        foo(42); //warning C4834: discarding return value of function with 'nodiscard' attribute
        return 0;
    }
    ```

- `[[maybe_unused]]` **Visual Studio 2017 Version 15,3 und höher:** (verfügbar mit [/Std: c++ 17](../build/reference/std-specify-language-standard-version.md)) gibt an, dass eine Variable, eine Funktion, eine Klasse, eine typedef, ein nicht statisches Datenmember, eine Enumeration oder eine Vorlagen Spezialisierung absichtlich nicht verwendet werden kann. Der Compiler warnt nicht, wenn eine Entität, die als `[[maybe_unused]]` gekennzeichnet ist, nicht verwendet wird. Eine Entität, die ohne das-Attribut deklariert wird, kann später mit dem-Attribut und umgekehrt erneut deklariert werden. Eine Entität wird als gekennzeichnet betrachtet, nachdem die erste markierte Deklaration analysiert wurde, und für die restliche Übersetzung der aktuellen Übersetzungseinheit.

## <a name="microsoft-specific-attributes"></a>Microsoft-spezifische Attribute

- `[[gsl::suppress(rules)]]` dieses Microsoft-spezifische Attribut wird zum Unterdrücken von Warnungen von Checker verwendet, die [gsl-Regeln (Guidelines Support Library)](https://github.com/Microsoft/GSL) im Code erzwingen. Sehen Sie sich beispielsweise den folgenden Code Ausschnitt an:

    ```cpp
    int main()
    {
        int arr[10]; // GSL warning C26494 will be fired
        int* p = arr; // GSL warning C26485 will be fired
        [[gsl::suppress(bounds.1)]] // This attribute suppresses Bounds rule #1
        {
            int* q = p + 1; // GSL warning C26481 suppressed
            p = q--; // GSL warning C26481 suppressed
        }
    }
    ```

  Im Beispiel werden folgende Warnungen ausgelöst:

  - 26494 (Typregel 5: Initialisieren Sie immer ein Objekt.)

  - 26485 (Begrenzungen Regel 3: kein Array zu Zeiger Verfall.)

  - 26481 (Begrenzungen-Regel 1: Verwenden Sie keine Zeigerarithmetik. Verwenden Sie stattdessen span.)

  Die ersten beiden Warnungen werden ausgelöst, wenn Sie diesen Code mit dem Code Analysetool cppcorecheck kompilieren, das installiert und aktiviert ist. Die dritte Warnung wird jedoch aufgrund des-Attributs nicht ausgelöst. Sie können das gesamte Begrenzungen-Profil unterdrücken, indem Sie [[gsl:: Unterdrückung (Begrenzungen)]] schreiben, ohne eine bestimmte Regel Nummer einzuschließen. Die C++ grundlegenden Richtlinien sollen Ihnen helfen, besseren und sichereren Code zu schreiben. Mit dem Attribut "unterdrücken" können Sie die Warnungen auf einfache Weise deaktivieren, wenn Sie nicht gewünscht werden.
  