---
title: /Zc:twoPhase-(Zweiphasen-Namenssuche deaktivieren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- twoPhase
- /Zc:twoPhase
- VC.Project.VCCLCompilerTool.EnforceTypeConversionRules
dev_langs:
- C++
helpviewer_keywords:
- twoPhase
- disable two-phase name lookup
- /Zc:twoPhase
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30647ab07984c393b10d7c0fb74d0e2be35cdf26
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723293"
---
# <a name="zctwophase--disable-two-phase-name-lookup"></a>/Zc:twoPhase-(Zweiphasen-Namenssuche deaktivieren)

Wenn die **/Zc:twoPhase-** angegeben wurde, wird der Compiler analysiert und Klassen- und Funktionsvorlagen nicht konforme genauso wie Versionen von Visual Studio vor Visual Studio 2017 Version 15.3 instanziiert.

## <a name="syntax"></a>Syntax

> **/Zc:twoPhase-**

## <a name="remarks"></a>Hinweise

In Visual Studio 2017 Version 15.3 und höher standardmäßig verwendet der Compiler Zweiphasen-Namenssuche für die namensauflösung für die Vorlage an. Wenn **/Zc:twoPhase-** angegeben ist, wird der Compiler setzt das vorherige nicht konforme Klasse Vorlage und die Funktion Vorlage Namen auflösen und-Ersetzung Verhalten.

Die **/Zc:twoPhase-** Option aus, um nicht konforme Verhalten zu aktivieren, wird standardmäßig nicht festgelegt. Die [/ PERMISSIVE--](permissive-standards-conformance.md) implizit Optionssätze konforme Verhalten des Zweiphasen-Lookup-Compilers, aber sie kann überschrieben werden, mithilfe von **/Zc:twoPhase-**.

Die Windows SDK-Header-Dateien in Version 10.0.15063.0 (Creators Update oder Redstone 2) und frühere Versionen funktionieren nicht ordnungsgemäß im Standards-Modus. Verwenden Sie **/Zc:twoPhase-** zum Kompilieren von Code für die SDK-Versionen, bei der Verwendung von Visual Studio 2017 Version 15.3 und höher. Versionen des Windows SDK ab Version 10.0.15254.0 (Redstone 3 oder Fall Creators Update) funktionieren ordnungsgemäß in Übereinstimmung mit Standards-Modus und erfordern keine der **/Zc:twoPhase-** Option.

Verwendung **/Zc:twoPhase-** Wenn Ihr Code ordnungsgemäß kompiliert das alte Verhalten erforderlich ist. Sollten Sie die Aktualisierung des Codes, um den Standard zu entsprechen.

### <a name="compiler-behavior-under-zctwophase-"></a>Compilerverhalten unter/Zc: twophase-

In Versionen des Compilers vor Visual Studio 2017 Version 15.3 und wann **/Zc:twoPhase-** angegeben ist, verwendet der Compiler dieses Verhalten:

- Nur der Vorlagendeklaration des Klassenhead und der Basisklassenliste analysiert. Der Vorlagentext wird als token-Stream erfasst. Keine funktionsrümpfe, Initialisierer, Standardargumente oder Noexcept-Argumente werden analysiert. Die Klassenvorlage ist unechte instanziiertes auf eine vorläufige zu überprüfenden Datentyps an, dass die Deklarationen in der Klassenvorlage richtig sind. Betrachten Sie diese Klassenvorlage ein:

   ```cpp
   template <typename T> class Derived : public Base<T> { ... }
   ```

   Der Vorlagendeklaration `template <typename T`>, des Klassenhead `class Derived`, und der Liste der Basisklasse `public Base<T>` werden analysiert, aber als token-Stream Vorlagentext aufgezeichnet wird.

- Bei der Analyse einer Funktionsvorlage, analysiert der Compiler nur die Funktionssignatur. Hauptteil der Funktion wird nicht analysiert werden. Stattdessen wird es als token-Stream erfasst.

Daher werden Wenn Vorlagentext Syntaxfehler und nie die Vorlage instanziiert wird, nie die Fehler diagnostiziert.

Eine weitere Auswirkung dieses Verhalten ist an der überladungsauflösung. Aufgrund der Art und Weise, die am Standort der Instanziierung der Tokenstream erweitert wird, Symbole, die nicht unter der Vorlagendeklaration sichtbar waren möglicherweise zum Zeitpunkt der Instanziierung sichtbar und überladungsauflösung beteiligt. Dies kann zu Vorlagen führen, die Verhalten basierend auf den Code, der nicht sichtbar war, wenn die Vorlage, im Gegensatz zu den Standard definiert wurde ändern.

Betrachten Sie beispielsweise folgenden Code:

```cpp
#include <cstdio>

void func(void*) { std::puts("The call resolves to void*") ;}

template<typename T> void g(T x)
{
    func(0);
}

void func(int) { std::puts("The call resolves to int"); }

int main()
{
    g(3.14);
}
```

Beim Kompilieren unter **/Zc:twoPhase-**, dieses Programm druckt "in ganzzahligen Typ löst der Aufruf auf". In Übereinstimmung mit Standards-Modus unter **/ PERMISSIVE--**, dieses Programm druckt "löst der Aufruf, Void *", da die zweite Überladung der `func` ist nicht sichtbar, wenn der Compiler die Vorlage erkennt.

*Abhängige Namen*, Namen, die von einem Vorlagenparameter abhängig sind aufweisen, der auch unter anderen ist das Suchverhalten **/Zc:twoPhase-**. In Übereinstimmung mit Standards-Modus werden abhängige Namen nicht zum Zeitpunkt der Definition von der Vorlage gebunden. Stattdessen werden diese Namen gesucht, wenn die Vorlage instanziiert wird. Für Funktionsaufrufe mit dem Funktionsnamen der abhängigen ist der Name der Satz von Funktionen gebunden, die zum Zeitpunkt des Aufrufs in der Vorlagendefinition wie oben angezeigt werden. Auf dem Zeitpunkt der Definition der Vorlage und dem Zeitpunkt der, in dem die Vorlage instanziiert wird, werden zusätzliche Überladungen von argumentbezogenen Suche hinzugefügt. Die beiden Phasen des Zweiphasen-Suche gibt die Suche nach nicht abhängigen Namen zum Zeitpunkt der Template-Definition und die Suche nach abhängigen Namen zum Zeitpunkt der Vorlageninstanziierung. Klicken Sie unter **/Zc:twoPhase-**, der Compiler keine argumentbezogenen Suche separat aus normalen, nicht qualifizierte Suche (d. h. es nicht zwei-Phasen-Suche), damit die Ergebnisse der Auflösung von funktionsüberladungen abweichen können.

Hier ist ein weiteres Beispiel:

```cpp
// zctwophase1.cpp
// Compile by using
// cl /EHsc /W4 /permissive- zctwophase1.cpp
// cl /EHsc /W4 /permissive- /Zc:twoPhase- zctwophase1.cpp

#include <cstdio>

void func(long) { std::puts("func(long)"); }

template <typename T> void tfunc(T t) {
    func(t);
}

void func(int) { std::puts("func(int)"); }

namespace NS {
    struct S {};
    void func(S) { std::puts("NS::func(NS::S)"); }
}

int main() {
    tfunc(1729);
    NS::S s;
    tfunc(s);
}
```

Bei der Kompilierung ohne **/Zc:twoPhase-**, dies druckt

```Output
func(long)
NS::func(NS::S)
```

Bei der Kompilierung mit **/Zc:twoPhase-**, dies druckt

```Output
func(int)
NS::func(NS::S)
```

In Übereinstimmung mit Standards-Modus unter **/ PERMISSIVE--**, den Aufruf `tfunc(1729)` löst in der `void func(long)` überladen, nicht `void func(int)` überladen auf **/Zc:twoPhase-**, da der nicht qualifizierte `func(int)` nach der Definition der Vorlage deklariert und nicht durch argumentbezogenen Suche gefunden wurden. Aber `void func(S)` ist beteiligt argumentbezogenen Suche, damit sie die Überladung, legen Sie für den Aufruf hinzugefügt wird `tfunc(s)` , obwohl sie nach der Vorlagenfunktion deklariert wurde.

### <a name="update-your-code-for-two-phase-conformance"></a>Aktualisieren Sie den Code für die Zweiphasen-Konformität

Ältere Versionen des Compilers erfordern keine Schlüsselwörter `template` und `typename` überall auf der C++-Standard erfordert diese. Diese Schlüsselwörter werden in einige Positionen benötigt, um zu unterscheiden, wie der Compiler einen abhängigen Name während der ersten Phase der Suche analysieren soll. Zum Beispiel:

`T::Foo<a || b>(c);`

Ein konforme Compiler analysiert `Foo` als Variable in den Bereich der `T`, d. h. dieser Code ist eine logische- oder einen Ausdruck mit `T::foo < a` wie der linke Operand und `b > (c)` als der Rechte Operand. Wenn Sie mit meinen `Foo` als Funktionsvorlage, müssen Sie angeben, dass dies durch das Hinzufügen einer Vorlage ist die `template` Schlüsselwort:

`T::template Foo<a || b>(c);`

In Versionen vor Visual Studio 2017 Version 15.3 und wann **/Zc:twoPhase-** angegeben ist, wird der Compiler kann diesen Code ohne die `template` Schlüsselwort und interpretiert ihn als Aufruf an eine Funktionsvorlage, die mit einem Argument von `a || b`, da sie die Vorlagen in einer sehr begrenzten Weise analysiert. Der obige Code ist nicht in der ersten Phase überhaupt analysiert. In der zweiten Phase wird es genügend Kontext an, die Sie informieren `T::Foo` ist eine Variable, statt eine Vorlage, damit der Compiler die Verwendung des Schlüsselworts nicht erzwingt.

Dieses Verhalten kann auch anzeigen, indem das Schlüsselwort eliminieren `typename` vor dem Namen in der Vorlage funktionsrümpfe, Initialisierer, Standardargumente und Noexcept-Argumente. Zum Beispiel:

```cpp
template<typename T>
typename T::TYPE func(typename T::TYPE*)
{
    /* typename */ T::TYPE i;
}
```

Wenn Sie nicht das Schlüsselwort verwenden `typename` im Hauptteil Funktion dieser Code kompiliert wird, klicken Sie unter **/Zc:twoPhase-**, aber nicht unter **/ PERMISSIVE--**. Die `typename` Schlüsselwort ist erforderlich, um anzugeben, dass die `TYPE` richtet. Da der Text nicht, klicken Sie unter analysiert wird **/Zc:twoPhase-**, den Compiler ist nicht erforderlich, das Schlüsselwort. In **/ PERMISSIVE--** Konformitätsmodus, Code ohne die `typename` Schlüsselwort generiert Fehler. Migrieren Ihres Codes zu Visual Studio 2017 Version 15.3 und höher, fügen Sie der `typename` Schlüsselwort, es nicht vorhanden ist.

Ebenso sollten Sie in diesem Codebeispiel wird ein:

```cpp
template<typename T>
typename T::template X<T>::TYPE func(typename T::TYPE)
{
    typename T::/* template */ X<T>::TYPE i;
}
```

Klicken Sie unter **/Zc:twoPhase-** und in älteren Compilern, erfordert der Compiler nur die `template` -Schlüsselwort in Zeile 2. Standardmäßig, und in Übereinstimmung mit Standards-Modus, erfordert der Compiler jetzt auch die `template` Schlüsselwort in Zeile 4 gibt an, dass `T::X<T>` ist eine Vorlage. Suchen Sie nach Code, der dieses Schlüsselwort nicht vorhanden ist, und geben Sie an, um den Code, der dem Standard entsprechen zu gestalten.

Weitere Informationen über Konformitätsprobleme finden Sie unter [C++-konformitätsverbesserungen in Visual Studio](../../cpp-conformance-improvements-2017.md) und [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Ändern der **zusätzliche Optionen** Eigenschaft sollen **/Zc:twoPhase-** und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)<br/>
