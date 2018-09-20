---
title: Zeichenfolgenliteral | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- string literals
- strings [C++], string literals
ms.assetid: 6d1fc3f8-0d58-4d68-9678-16b4f6dc4766
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 41f1996cd4f4caf24ac08d09b05e636cb09f7eed
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415264"
---
# <a name="string-literal"></a>Zeichenfolgenliterale

Die Behandlung von Zeichenfolgenliteralen wurde von Managed Extensions für C++ in Visual C++ geändert.

In Managed Extensions for C++-Sprachentwurf, wurde eine verwaltete Zeichenfolge, die Literale angegeben, durch das Zeichenfolgenliteral mit voranstellen einer `S`. Zum Beispiel:

```
String *ps1 = "hello";
String *ps2 = S"goodbye";
```

Die Leistung zwischen den zwei Initialisierungen erweist sich nicht trivialen, wie die folgenden CIL Darstellung wird veranschaulicht, wie durch **Ildasm**:

```
// String *ps1 = "hello";
ldsflda    valuetype $ArrayType$0xd61117dd
     modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier)
     '?A0xbdde7aca.unnamed-global-0'

newobj instance void [mscorlib]System.String::.ctor(int8*)
stloc.0

// String *ps2 = S"goodbye";
ldstr      "goodbye"
stloc.0
```

Das ist bemerkenswerten einsparungen für nur merken (oder Learning), ein Zeichenfolgenliteral-Präfix mit einem `S`. In der neuen Syntax wird die Behandlung von Zeichenfolgenliteralen transparent, erfolgt durch den Kontext der Verwendung bestimmt. Die `S` muss nicht mehr angegeben werden.

Was geschieht in Fällen, in denen wir explizit müssen, den Compiler eine Interpretation oder einer anderen? In diesen Fällen wenden wir eine explizite Umwandlung. Zum Beispiel:

```
f( safe_cast<String^>("ABC") );
```

Darüber hinaus das Zeichenfolgenliteral jetzt entspricht einem `String` mit einer standardkonvertierung, anstatt eine einfache Konvertierung. Obwohl dies nicht klingen mag, wie viel die Auflösung der überladene Funktion ändert die enthalten eine `String` und `const char*` als konkurrierende formale Parameter. Die Lösung, die einmal aufgelöst wurde eine `const char*` Instanz jetzt als mehrdeutig markiert wird. Zum Beispiel:

```
ref struct R {
   void f(const char*);
   void f(String^);
};

int main () {
   R r;
   // old syntax: f( const char* );
   // new syntax: error: ambiguous
   r.f("ABC"); 
}
```

Warum gibt es einen Unterschied? Seit mehr als eine Instanz, die mit dem Namen `f` vorhanden ist innerhalb des Programms, die dies erfordert die Funktion Überladung Auflösungsalgorithmus auf den Aufruf angewendet werden. Die formale Auflösung einer überladenen Funktion umfasst drei Schritte.

1. Die Auflistung der möglichen Funktionen. Die kandidatenfunktionen sind diese Methoden innerhalb des Bereichs, die den Namen der aufgerufenen Funktion lexikalisch entsprechen. Z. B. seit `f()` wird aufgerufen, durch eine Instanz der `R`, werden alle Funktionen mit dem Namen `f` , sind nicht Mitglied der `R` (oder seiner Hierarchie Basisklasse) sind nicht geeignete Funktionen. In unserem Beispiel gibt es zwei mögliche Funktionen. Hierbei handelt es sich um die zwei Memberfunktionen der `R` mit dem Namen `f`. Während dieser Phase schlägt ein Aufruf in die Candidate-Funktion leer ist.

1. Der Satz der geeignete Funktionen aus den möglichen Funktionen. Eine sinnvolle Funktion ist eine, die mit den Argumenten im Aufruf angegebenen angesichts der Anzahl von Argumenten und ihre Typen aufgerufen werden kann. In unserem Beispiel sind beide kandidatenfunktionen auch geeignete Funktionen. Ein Aufruf fehlschlägt in dieser Phase, wenn sinnvolle Funktion leer ist.

1. Wählen Sie die Funktion, die die beste Übereinstimmung des Aufrufs darstellt. Dazu ordnen die Konvertierungen angewendet, um die Argumente für den Typ der kleinstmögliche Funktionsparameter zu transformieren. Dies ist verhältnismäßig einfach mit einer einzelnen Parameter-Funktion. Es wird etwas komplexer, wenn mehrere Parameter vorhanden sind. Ein Aufruf fehlschlägt in dieser Phase, liegt keine bestmögliche Entsprechung gefunden. D.h., wenn die Konvertierungen, die zum Transformieren des Typs des tatsächlichen Arguments in den Typ des formalen Parameters gleich gut geeignet sind. Der Aufruf wird als mehrdeutig gekennzeichnet.

In Managed Extensions die Auflösung des Aufrufs aufgerufen, die `const char*` Instanz als beste Übereinstimmung. In der neuen Syntax, die entsprechend erforderlichen Konvertierung `"abc"` zu `const char*` und `String^` entsprechen nun – d. h., gleich gut geeignet – und damit der Aufruf als fehlerhaft -, d. h. gekennzeichnet ist als mehrdeutig.

Dies führt uns zwei Fragen:

- Was ist, dass der Typ des tatsächlichen Arguments `"abc"`?

- Was ist der Algorithmus, um zu bestimmen, wann eine typkonvertierung besser als eine andere ist?

Der Typ des Zeichenfolgenliterals `"abc"` ist `const char[4]` – berücksichtigen Sie, dass ein impliziter null abschließende Zeichen am Ende jeder Zeichenfolge literal.

Der Algorithmus, um zu bestimmen, wenn eine typkonvertierung ist besser als eine andere umfasst die möglichen typkonvertierungen in einer Hierarchie platziert werden soll. Hier ist meine Kenntnisse dieser Hierarchie – alle diese Konvertierungen natürlich sind implizit. Verwenden eine explizite Umwandlungsnotation überschreibt die Hierarchie, die ähnlich wie die Klammern überschreibt die üblichen Operatorrangfolge eines Ausdrucks.

1. Eine genaue Übereinstimmung empfiehlt. Es überrascht, dass für ein Argument, das eine genaue Übereinstimmung wird, muss nicht exakt mit den Parametertyp übereinstimmen; Es muss einfach nahe genug sein. Dies ist der Schlüssel zum Verständnis, was passiert in diesem Beispiel wird und wie die Sprache geändert hat.

1. Eine heraufstufung ist besser als eine standardkonvertierung. Z. B. Höherstufen einer `short int` auf eine `int` ist besser als die Konvertierung ein `int` in eine `double`.

1. Eine standardkonvertierung ist besser als ein Boxing-Konvertierung. Zum Beispiel die Konvertierung einer `int` in eine `double` ist besser, Boxing eine `int` in einer `Object`.

1. Eine Boxingkonvertierung ist besser als eine implizite Konvertierung von benutzerdefinierten. Boxing z. B. eine `int` in eine `Object` ist besser als die Anwendung eines Konvertierungsoperators, der eine `SmallInt` value-Klasse.

1. Eine implizite Konvertierung von benutzerdefinierten ist überhaupt keine Konvertierung besser. Eine implizite Konvertierung von benutzerdefinierten ist der letzte vor dem Fehler (mit dem Nachteil, dass die formale Signatur ein Parameterarray oder mit den Auslassungspunkten, an dieser Position enthalten kann).

Also, was bedeutet es zu sagen, dass eine exakte Übereinstimmung unbedingt genau eine Übereinstimmung ist? Z. B. `const char[4]` stimmt nicht genau überein, entweder `const char*` oder `String^`, und noch die Mehrdeutigkeit in unserem Beispiel befindet sich zwischen zwei in Konflikt stehende genaue Übereinstimmungen!

Eine genaue Übereinstimmung, während des Vorgangs, einer umfasst eine Reihe von trivialen Konvertierungen an. Es gibt vier triviale Konvertierungen unter ISO C++-, die angewendet werden können und immer noch als genaue Übereinstimmung zu qualifizieren. Drei werden als Lvalue-Transformationen bezeichnet. Ein vierter Typ wird eine qualifikationskonvertierung aufgerufen. Die drei Lvalue-Transformationen werden als besser genaue Übereinstimmung als erfordern eine qualifikationskonvertierung behandelt.

Eine Form der Transformation für das l-Wert ist der systemeigene Array zu Zeiger-Konvertierung. Dies kommt bei der Zuordnung von einem `const char[4]` zu `const char*`. Aus diesem Grund wird die Übereinstimmung der `f("abc")` zu `f(const char*)` eine exakte Übereinstimmung. In der früheren Berufsleben unserer Sprache war dies die beste Übereinstimmung in der Tat.

Für der Compiler so kennzeichnen Sie den Aufruf als mehrdeutig ist, erfordert daher, dass die Konvertierung von einer `const char[4]` auf eine `String^` auch sein, eine genaue Übereinstimmung über eine triviale Konvertierung. Dies ist die Änderung, die in der neuen Sprachversion eingeführt wurde. Und aus diesem Grund ist der Aufruf jetzt gekennzeichnet wird als mehrdeutig.

## <a name="see-also"></a>Siehe auch

[Allgemeine Sprachänderungen (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)<br/>
[String](../windows/string-cpp-component-extensions.md)