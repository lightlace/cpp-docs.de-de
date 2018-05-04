---
title: C++-Standard Attribute | Microsoft Docs
ms.custom: ''
ms.date: 03/28/2017
ms.topic: language-reference
ms.assetid: 748340d9-8abf-4940-b0a0-91b6156a3ff8
ms.openlocfilehash: 7bd7fd4e01fb210069f4dbae42a671e4dd9c64c9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="attributes-in-c"></a>Attribute in C++

Der C++-Standard definiert einen Satz von Attributen und können auch compileranbietern Definieren eigener Attribute (in einem anbieterspezifischen Namespace), aber der Compiler sind erforderlich, um nur die Attribute, die im Standard definiert zu erkennen.

In einigen Fällen nicht überlappen Standardattributen compilerspezifisch Declspec-Parameter. In Visual C++ können Sie die `[[deprecated]]` Attribut anstatt `declspec(deprecated)` und das Attribut wird von einem Compiler konform erkannt werden. Für alle anderen Declspec Parametern wie Dllimport und Dllexport gibt es noch keine Attribut Entsprechung so fortgesetzt werden muss, um Declspec-Syntax verwenden. Attribute wirken sich nicht auf das Typsystem und die Bedeutung eines Programms nicht ändern. Compiler ignorieren Attributwerte, die sie nicht kennen.

**Visual Studio 2017 15,3 und höher** (verfügbar mit [/std:c ++ 17](../build/reference/std-specify-language-standard-version.md)): Sie können den Namespace für alle Namen mit einem einzelnen angeben, im Rahmen einer Attributliste `using` Introducer:

```cpp
void g() {
    [[using rpr: kernel, target(cpu,gpu)]] // equivalent to [[ rpr::kernel, rpr::target(cpu,gpu) ]]
    do task();
}
```

## <a name="c-standard-attributes"></a>C++-Standard-Attribute

In C ++ 11 Geben Sie Attribute eine standardisierte Verfahren zum C++-Konstrukte (einschließlich aber nicht beschränkt auf Klassen, Funktionen, Variablen und Blöcke) mit zusätzlichen Informationen zu versehen, die nicht unbedingt herstellerspezifischen. Ein Compiler kann diese Informationen zum Generieren von informationsmeldungen oder spezielle Logik angewendet, beim Kompilieren des Codes attributierte verwenden. Der Compiler ignoriert alle Attribute, die er nicht erkennt, was bedeutet, dass Sie eigene benutzerdefinierte Attribute, die mithilfe dieser Syntax definieren können. Attribute werden durch doppelte eckige Klammern eingeschlossen:

```cpp
[[deprecated]]
void Foo(int);
```

Attribute, die eine standardisierte Alternative zu herstellerspezifischen Erweiterungen wie z. B. #pragma-Direktiven, __declspec() (Visual C++) darstellen oder &#95; &#95;Attribut&#95; &#95; (GNU). Allerdings müssen Sie dennoch die anbieterspezifische-Konstrukte für die meisten Zwecke zu verwenden. Der Standard gibt derzeit die folgenden Attribute, die ein übereinstimmenden Compiler erkennen soll:

- `[[noreturn]]` Gibt an, dass eine Funktion nie zurück. mit anderen Worten löst immer eine Ausnahme aus. Der Compiler kann die kompilierungsregeln für anpassen `[[noreturn]]` Entitäten.

- `[[carries_dependency]]` Gibt an, dass die Funktion datenabhängigkeits-Reihenfolge in Bezug auf die Threadsynchronisierung weitergibt. Das Attribut kann auf einen oder mehrere Parameter, um anzugeben, dass das übergebene Argument eine Abhängigkeit in den Funktionstext führt angewendet werden. Das Attribut kann für die Funktion selbst, um anzugeben, dass der Rückgabewert eine Abhängigkeit Rücksprung aus der Funktion führt angewendet werden. Dieser Informationen können Compiler um effizienter Code zu generieren.

- `[[deprecated]]` **Visual Studio 2015 und höher:** gibt an, dass eine Funktion nicht vorgesehen ist, verwendet werden, und möglicherweise nicht vorhanden in zukünftigen Versionen von einer Schnittstelle der Bibliothek. Der Compiler kann dies verwenden, um eine informationsmeldung zu generieren, wenn Clientcode versucht die Funktion aufgerufen. Kann auf die Deklaration einer Klasse, eine Typedef-Name, eine Variable, einen nicht statischen Datenmember, eine Funktion, einen Namespace, eine Enumeration, einen Enumerator oder eine Spezialisierung einer Klassenvorlage angewendet werden.  

- `[[fallthrough]]` **Visual Studio 2017 und höher:** (verfügbar mit [/std:c ++ 17](../build/reference/std-specify-language-standard-version.md)) der `[[fallthrough]]` Attribut kann verwendet werden, im Kontext des [wechseln](switch-statement-cpp.md) Anweisungen als Hinweis für den Compiler (oder ein anderer Nutzer lesen der Code), die das Verhalten Fallthrough vorgesehen ist. Visual C++-Compiler warnt derzeit nicht auf Fallthrough Verhalten, damit dieses Attribut keine Compilerverhalten Auswirkungen hat.

- `[[nodiscard]]` **Visual Studio 2017 15,3 und höher:** (verfügbar mit [/std:c ++ 17](../build/reference/std-specify-language-standard-version.md)) gibt an, dass der Rückgabewert einer Funktion nicht verworfen werden soll. Löst Warnung C4834, wie im folgenden Beispiel gezeigt:

   ```cpp
   [[nodiscard]]
   int foo(int i) { return i * i; }

   int main()
   {
       foo(42); //warning C4834: discarding return value of function with 'nodiscard' attribute
       return 0;
   }
   ```

- `[[maybe_unused]]` **Visual Studio 2017 15,3 und höher:** (verfügbar mit [/std:c ++ 17](../build/reference/std-specify-language-standard-version.md)) gibt an, dass eine Variable, Funktion, Klasse, Typedef, nicht statischen Datenmember, Enum oder Spezialisierung einer Klassenvorlage absichtlich nicht verwendet werden kann. Der Compiler warnt nicht, wenn eine Entität markiert `[[maybe_unused]]` wird nicht verwendet. Eine Entität, die ohne das Attribut deklariert ist kann später mit dem Attribut und umgekehrt erneut deklariert werden. Eine Entität wird gekennzeichnet, die nach der Analyse der ersten Deklaration, die markiert ist, für den Rest der Übersetzung von der aktuellen Übersetzungseinheit betrachtet.

## <a name="microsoft-specific-attributes"></a>Microsoft-spezifische Attribute

- `[[gsl::suppress(rules)]]` Dieses Microsoft-spezifische-Attribut wird verwendet, für das Unterdrücken von Warnungen von Prüfer, die erzwingen [Richtlinien Support Library (GSL)](https://github.com/Microsoft/GSL) Regeln im Code. Betrachten Sie beispielsweise diesen Codeausschnitt:

    ```cpp
    void main()
    {
        int arr[10]; // GSL warning 26494 will be fired
        int* p = arr; // GSL warning 26485 will be fired
        [[gsl::suppress(bounds.1)]] // This attribute suppresses Bounds rule #1
        {
            int* q = p + 1; // GSL warning 26481 suppressed
            p = q--; // GSL warning 26481 suppressed
        }
    }
    ```

   Im Beispiel löst diese Warnungen aus:

   - 26494 (Typ Regel 5: immer ein Objekt initialisiert werden.)

   - 26485 (Grenzen Regel 3: kein Array, Zeiger Decay.)

   - 26481 (Grenzen Regel 1: Verwenden Sie keine Zeigerarithmetik. Stattdessen Sie Spanne.)

   Die ersten beiden Warnungen ausgelöst werden, wenn Sie mit der CppCoreCheck Codeanalysetool installiert und aktiviert diesen Code kompilieren. Aber die dritte Warnung wird nicht ausgelöst, weil das Attribut. Sie können das gesamte Grenzen Profil unterdrücken, indem Sie [gsl::suppress(bounds)] schreiben, ohne eine bestimmte Regel Zahl. Die C++-Core-Richtlinien dienen lassen sich besser und sicherer Code zu schreiben. Das Attribut unterdrücken erleichtert die Warnungen deaktivieren, wenn sie nicht erwünscht sind.
