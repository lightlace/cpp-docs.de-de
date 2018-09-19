---
title: Auslassungszeichen- und Variadic-Vorlagen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: f20967d9-c967-4fd2-b902-2bb1d5ed87e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 509ff98082edfad8fc48b3e1eaf6c3d4b4e6ad48
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090476"
---
# <a name="ellipses-and-variadic-templates"></a>Auslassungszeichen- und Variadic-Vorlagen

In diesem Artikel wird gezeigt, wie die Auslassungspunkte (`...`) mit variadic Vorlagen von C++ verwendet werden. Das Auslassungszeichen hatte wird häufig in C und C++ verwendet. Hierzu gehören Variablenargumentlisten für Funktionen. Die `printf()`-Funktion der C-Laufzeitbibliothek ist eines der bekanntesten Beispiele.

Ein *Variadic-Vorlage* ist eine Klassen- oder Funktionsvorlage, die eine beliebige Anzahl von Argumenten unterstützt. Dieser Mechanismus ist für C++-Bibliotheksentwickler besonders nützlich, da Sie ihn auf Klassen- und Funktionsvorlagen anwenden können, und dadurch eine große Bandbreite typsicherer und nicht trivialer Funktionalität und Flexibilität bereitstellen können.

## <a name="syntax"></a>Syntax

Ein Auslassungszeichen wird auf zwei Arten von variadic-Vorlagen verwendet. Auf der linken Seite des Parameternamens, gibt es eine *parameterpaket*, und klicken Sie auf der rechten Seite des Parameternamens erweitert es die parameterpakete in separaten Namen.

Hier ist ein einfaches Beispiel *Variadic-Vorlagenklassen* definitionssyntax:

```cpp
template<typename... Arguments> class classname;
```

Sie können für Parameterpakete und Erweiterungen Leerstellen um die Auslassungszeichen entsprechend den jeweiligen Anforderungen, wie in den folgenden Beispielen dargestellt, hinzufügen:

```cpp
template<typename ...Arguments> class classname;
```

Oder:

```cpp
template<typename ... Arguments> class classname;
```

Beachten Sie, dass in diesem Artikel die Konvention verwendet wird, die im ersten Beispiel gezeigt wird (die Auslassungszeichen werden an `typename` angefügt).

In den obigen Beispielen *Argumente* ein parameterpaket. Die `classname`-Klasse kann eine variable Anzahl von Argumenten akzeptieren, wie in den folgenden Beispielen gezeigt.

```cpp
template<typename... Arguments> class vtclass;

vtclass< > vtinstance1;
vtclass<int> vtinstance2;
vtclass<float, bool> vtinstance3;
vtclass<long, std::vector<int>, std::string> vtinstance4;
```

Mit einer variadic-Vorlagenklassendefinition können Sie auch mindestens einen Parameter anfordern:

```cpp
template <typename First, typename... Rest> class classname;
```

Hier ist ein einfaches Beispiel *Variadic-Vorlagenfunktion* Syntax:

```cpp
template <typename... Arguments> returntype functionname(Arguments... args);
```

Die *Argumente* parameterpaket wird erweitert für die Verwendung, wie im nächsten Abschnitt gezeigt **Variadic-Vorlagen**.

Andere Formen der variadic-Vorlagenfunktionssyntax sind möglich, darunter diese Beispiele:

```cpp
template <typename... Arguments> returntype functionname(Arguments&... args);
template <typename... Arguments> returntype functionname(Arguments&&... args);
template <typename... Arguments> returntype functionname(Arguments*... args);
```

Bezeichner wie **const** sind ebenfalls zulässig:

```cpp
template <typename... Arguments> returntype functionname(const Arguments&... args);
```

Wie bei variadic-Vorlagenklassendefinitionen können Sie Funktionen ausführen, die mindestens einen Parameter erfordern:

```cpp
template <typename First, typename... Rest> returntype functionname(const First& first, const Rest&... args);
```

Variadic-Vorlagen verwenden den Operator `sizeof...()` (nicht verknüpft mit dem älteren `sizeof()`-Operator):

```cpp
template<typename... Arguments>
void tfunc(const Arguments&... args)
{
    constexpr auto numargs{ sizeof...(Arguments) };

    X xobj[numargs]; // array of some previously defined type X

    helper_func(xobj, args...);
}
```

## <a name="more-about-ellipsis-placement"></a>Weitere Informationen zur Platzierung von Auslassungszeichen

In diesem Artikel wurde bereits die Platzierung des Auslassungszeichens, mit der Parameterpakete und Erweiterungen definiert werden, wie folgt beschrieben: "Auf der linken Seite des Parameternamens zeigt es ein Parameterpaket an, und auf der rechten Seite des Parameternamens erweitert es die Parameterpakete in separaten Namen". Dies ist technisch gesehen richtig, kann jedoch bei der Übersetzung in Code verwirrend sein. Betrachten Sie das folgende Beispiel:

- In einer Vorlagen-Parameterliste (`template <parameter-list>`), `typename...` ein vorlagenparameterpaket führt.

- In einer Parameter-Declaration-Clause (`func(parameter-list)`), ein Auslassungszeichen "der obersten Ebene" führt ein funktionsparameterpaket und des Auslassungszeichens wichtig ist:

    ```cpp
    // v1 is NOT a function parameter pack:
    template <typename... Types> void func1(std::vector<Types...> v1);

    // v2 IS a function parameter pack:
    template <typename... Types> void func2(std::vector<Types>... v2);
    ```

- Wenn das Auslassungszeichen direkt nach dem Parameternamen angezeigt wird, haben Sie eine Parameterpaketerweiterung.

## <a name="example"></a>Beispiel

Eine gute Möglichkeit, den Funktionsmechanismus von variadic-Vorlagen zu veranschaulichen, ist dessen Verwendung in der Neuschreibung einiger Funktionen von `printf`:

```cpp
#include <iostream>

using namespace std;

void print() {
    cout << endl;
}

template <typename T> void print(const T& t) {
    cout << t << endl;
}

template <typename First, typename... Rest> void print(const First& first, const Rest&... rest) {
    cout << first << ", ";
    print(rest...); // recursive call using pack expansion syntax
}

int main()
{
    print(); // calls first overload, outputting only a newline
    print(1); // calls second overload

    // these call the third overload, the variadic template,
    // which uses recursion as needed.
    print(10, 20);
    print(100, 200, 300);
    print("first", 2, "third", 3.14159);
}
```

## <a name="output"></a>Ausgabe

```Output
1
10, 20
100, 200, 300
first, 2, third, 3.14159
```

> [!NOTE]
>  Die meisten Implementierungen, die Variadic-Vorlagenfunktionen enthalten verwenden, Rekursion irgendeiner Art, aber es ist etwas anders als herkömmliche Rekursion.  Herkömmliche Rekursion umfasst eine Funktion, die selbst mithilfe der gleichen Signatur aufruft. (Sie ist überladen oder vorlagenbasiert, aber dieselbe Signatur wird jedes Mal ausgewählt.) Variadic-Rekursion beinhaltet den Aufruf einer variadic-Funktionsvorlage, indem eine unterschiedliche (fast immer abnehmende) Anzahl von Argumenten verwendet und somit verhindert wird, dass sich die Signatur jedes Mal ändert. Eine "Basisfall" ist dennoch erforderlich, aber die Art der Rekursion ist anders.