---
title: /Zc:twoPhase-(Zweiphasen-Namenssuche deaktivieren) | Microsoft Docs
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
ms.openlocfilehash: 5653959b25105f10ae98768217524dc0ff0cbe2a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389100"
---
# <a name="zctwophase--disable-two-phase-name-lookup"></a>/Zc:twoPhase-(Zweiphasen-Namenssuche deaktivieren)

Wenn die **/Zc:twoPhase-** angegeben wird, der Compiler analysiert und Klassen- und Funktionsvorlagen nicht konforme genauso wie in Versionen von Visual Studio vor Visual Studio 2017 Version 15.3 instanziiert. 

## <a name="syntax"></a>Syntax

> **/Zc:twoPhase-**

## <a name="remarks"></a>Hinweise

In Visual Studio 2017 Version 15,3 und höher standardmäßig verwendet der Compiler zweiphasigen Namenssuche für die namensauflösung für die Vorlage an. Wenn **/Zc:twoPhase-** angegeben ist, wird der Compiler auf das vorherige nicht konforme Klasse Vorlage und die Funktion Vorlage Namen auflösen und Ersetzung Verhalten zurückgesetzt.

Die **/Zc:twoPhase-** Option aus, um nicht konforme Verhalten zu aktivieren, wird nicht standardmäßig festgelegt. Die [/ liberalen-](permissive-standards-conformance.md) Option wird implizit die Konformität Compilerverhalten Zweiphasen-Suche, jedoch können sie mithilfe von außer Kraft gesetzt werden **/Zc:twoPhase-**.

Das Windows SDK-Headerdateien in 10.0.15063.0 (Ersteller-Update oder Redstone 2), Version und früheren Versionen funktionieren in Konformitätsmodus nicht ordnungsgemäß. Verwenden Sie **/Zc:twoPhase-** zum Kompilieren von Code für die SDK-Versionen, bei der Verwendung von Visual Studio 2017 Version 15.3 und höheren Versionen. Versionen des Windows SDK ab Version 10.0.15254.0 (Redstone 3 oder Herbst Ersteller Update) in Konformitätsmodus ordnungsgemäß funktioniert und erfordern keine der **/Zc:twoPhase-** Option.

Verwendung **/Zc:twoPhase-** Wenn Sie den Code ordnungsgemäß kompiliert das alte Verhalten erforderlich ist. Sollten Sie möglicherweise Aktualisierung des Codes, um den Standard zu entsprechen.

### <a name="compiler-behavior-under-zctwophase-"></a>Compilerverhalten unter /Zc:twoPhase-

In Versionen des Compilers vor Visual Studio 2017 Version 15.3 und wann **/Zc:twoPhase-** angegeben ist, verwendet der Compiler dieses Verhalten:

- Es analysiert nur die Vorlagendeklaration, die Klasse Head und der Basisklassenliste. Der Textkörper der Vorlage wird als ein Tokenstream erfasst. Keine Funktionsrümpfen, Initialisierer, Standardargumente oder Noexcept-Argumente werden analysiert. Die Klassenvorlage wird Pseudo-instanziiert auf eine vorläufige zu überprüfenden Datentyps an, dass die Deklarationen in der Klassenvorlage richtig sind. Betrachten Sie diese Klassenvorlage:

   ```cpp
   template <typename T> class Derived : public Base<T> { ... }
   ```

   Der Vorlagendeklaration `template <typename T`>, die Klasse Head `class Derived`, und der Liste der Basisklassen `public Base<T>` analysiert werden, aber der Textkörper der Vorlage wird als ein Tokenstream erfasst.

- Wenn eine Funktionsvorlage zu analysieren, analysiert der Compiler nur die Funktionssignatur. Hauptteil der Funktion wird nicht analysiert werden. Es wird stattdessen als eine Tokenstream erfasst.

Daher werden, wenn die Vorlage-Text Syntaxfehler enthält und nie die Vorlage instanziiert wird, nie die Fehler diagnostiziert.

Ein weiterer Effekt dieses Verhalten ist an der überladungsauflösung. Aufgrund der Art und Weise, die am Standort der Instanziierung der Tokenstream erweitert wird, Symbole, die nicht an die Vorlagendeklaration sichtbar waren möglicherweise zum Zeitpunkt der Instanziierung sichtbar und überladungsauflösung beteiligt. Dies kann zu Vorlagen führen, die basierend auf den Code, der nicht sichtbar war, wenn die Vorlage, entgegen der Standard definiert wurde-Verhalten ändern.

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

Beim Kompilieren unter **/Zc:twoPhase-**, dieses Programm druckt "der Aufruf aufgelöst zu Int". In Konformitätsmodus unter **/ liberalen-**, dieses Programm druckt "der Aufruf aufgelöst, als" void "*", da die zweite Überladung der `func` ist nicht sichtbar, wenn der Compiler die Vorlage auftritt.

*Abhängige Namen*, Namen, die von einem Vorlagenparameter abhängig sind, haben Suchverhalten, der auch unter unterscheidet **/Zc:twoPhase-**. Abhängige Namen im Konformitätsmodus nicht zum Zeitpunkt der Definition der Vorlage gebunden. Stattdessen werden diese Namen gesucht, wenn die Vorlage instanziiert wird. Für Funktionsaufrufe mit einem Funktionsnamen der abhängigen ist der Name der Satz von Funktionen gebunden, die zum Zeitpunkt der Aufruf in der Vorlagendefinition wie oben angezeigt werden. Auf dem Zeitpunkt der Definition der Vorlage und der Punkt, in dem die Vorlage instanziiert wird, werden zusätzliche Überladungen aus einer argumentbezogenen Suche hinzugefügt. Die beiden Phasen des Zweiphasen-Suche werden die Suche von nicht abhängigen Namen zum Zeitpunkt der Definition der Vorlagenfunktion und die Suche nach abhängigen Namen zum Zeitpunkt der Vorlageninstanziierung. Klicken Sie unter **/Zc:twoPhase-**, der Compiler keine einer argumentbezogenen Suche getrennt vom normalen, nicht qualifizierte Suche (d. h. nicht Zweiphasen-Suche), damit die Ergebnisse der Auflösung von funktionsüberladungen unterscheiden können.

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

Bei der Kompilierung ohne **/Zc:twoPhase-**, dies ausgibt

```Output
func(long)
NS::func(NS::S)
```

Beim Kompilieren mit **/Zc:twoPhase-**, dies ausgibt

```Output
func(int)
NS::func(NS::S)
```

In Konformitätsmodus unter **/ liberalen-**, den Aufruf `tfunc(1729)` löst in der `void func(long)` überladen, nicht `void func(int)` überladen, wie unter **/Zc:twoPhase-**, da der nicht qualifizierte `func(int)` nach der Definition der Vorlage deklariert und nicht durch einer argumentbezogenen Suche gefunden wurden. Aber `void func(S)` ist beteiligt einer argumentbezogenen Suche, damit es an die Überladung, legen Sie für den Aufruf hinzugefügt wird `tfunc(s)` , obwohl sie nach der Vorlagenfunktion deklariert ist.

### <a name="update-your-code-for-two-phase-conformance"></a>Aktualisieren Sie den Code für Zweiphasen-Konformität

Ältere Versionen des Compilers erfordern keine Schlüsselwörter `template` und `typename` überall im C++-Standard benötigt werden. Diese Schlüsselwörter sind in einigen Positionen erforderlich, um die Mehrdeutigkeit aufzulösen, wie der Compiler einen abhängigen Name während der ersten Phase der Suche analysieren soll. Zum Beispiel:

`T::Foo<a || b>(c);`

Ein übereinstimmenden Compiler analysiert `Foo` als Variable in den Bereich der `T`, d. h. dieser Code ist eine logische- oder einen Ausdruck mit `T::foo < a` wie der linke Operand und `b > (c)` als der Rechte Operand. Wenn Sie mit meinen `Foo` als Funktionsvorlage, müssen Sie angeben, dass dies durch Hinzufügen einer Vorlage ist die `template` Schlüsselwort:

`T::template Foo<a || b>(c);`

In Versionen vor Visual Studio 2017 Version 15.3 und wann **/Zc:twoPhase-** angegeben ist, wird der Compiler lässt dieser Code ohne die `template` Schlüsselwort und interpretiert ihn als Aufruf an eine Funktionsvorlage mit dem Argument `a || b`, da sie Vorlagen auf ein sehr eingeschränkter Weise analysiert. Der obige Code ist nicht in der ersten Phase überhaupt analysiert. In der zweiten Phase besteht genügend Kontext für die entsprechende `T::Foo` ist eine Vorlage anstatt einer Variablen, damit der Compiler nicht mithilfe des Schlüsselworts erzwingt.

Dieses Verhalten kann auch angezeigt werden, durch den Wegfall des Schlüsselworts `typename` vor dem Namen in den Funktionsrümpfen der Vorlage, Initialisierer Standardargumente und Noexcept-Argumente. Zum Beispiel:

```cpp
template<typename T>
typename T::TYPE func(typename T::TYPE*)
{
    /* typename */ T::TYPE i;
}
```

Wenn Sie nicht das Schlüsselwort verwenden `typename` im Hauptteil Funktion kompiliert diesen Code unter **/Zc:twoPhase-**, aber nicht unter **/ liberalen-**. Die `typename` Schlüsselwort ist erforderlich, um anzugeben, dass die `TYPE` richtet. Da der Text nicht unter analysiert wird **/Zc:twoPhase-**, der Compiler ab erfordern das Schlüsselwort. In **/ liberalen-** Konformitätsmodus, Code ohne die `typename` Schlüsselwort generiert Fehler. Migrieren von Code in Visual Studio 2017 Version 15.3 und darüber hinaus, fügen Sie der `typename` Schlüsselwort, in denen er fehlt.

Ebenso sollten Sie dieses Codebeispiel:

```cpp
template<typename T>
typename T::template X<T>::TYPE func(typename T::TYPE)
{
    typename T::/* template */ X<T>::TYPE i;
}
```

Klicken Sie unter **/Zc:twoPhase-** und in älteren Compilern, erfordert der Compiler nur die `template` für Zeile 2-Schlüsselwort. Standardmäßig, und in Konformitätsmodus, erfordert der Compiler jetzt auch die `template` -Schlüsselwort in Zeile 4 gibt an, dass `T::X<T>` ist eine Vorlage. Suchen Sie nach dem Code, der dieses Schlüsselwort fehlt, und geben Sie an, um den Code, der dem Standard zu gestalten.

Weitere Informationen über Konformitätsprobleme finden Sie unter [konformitätsverbesserungen in Visual Studio C++](../../cpp-conformance-improvements-2017.md) und [nicht standardmäßigem Verhalten](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Ändern der **Zusatzoptionen** Eigenschaft einschließen **/Zc:twoPhase-** und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)<br/>
