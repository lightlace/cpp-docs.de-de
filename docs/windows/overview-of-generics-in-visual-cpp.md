---
title: Übersicht über Generika in C++ / CLI
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- generics [C++], about generics
- default initializers [C++]
- type parameters [C++]
- constructed types
- type arguments [C++]
- constructed types, open [C++]
- open constructed types [C++]
- constructed types, closed [C++]
ms.assetid: 21f10637-0fce-4916-b925-6c86a126d3aa
ms.openlocfilehash: 1105025ebebdfcbce723505747f6677674c04334
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50655168"
---
# <a name="overview-of-generics-in-ccli"></a>Übersicht über Generika in C++ / CLI

Generika sind parametrisierte Typen, die von der common Language Runtime unterstützt werden. Ein parametrisierter Typ ist ein Typ, der mit einem unbekannten Typ-Parameter definiert ist, die angegeben wird, wenn die generische verwendet wird.

## <a name="why-generics"></a>Warum Generika?

C++ unterstützt, und beide Vorlagen und Generika unterstützt parametrisierte Typen um typisierte Auflistungsklassen zu erstellen. Allerdings bieten Vorlagen während der Kompilierung Parametrisierung. Sie können nicht auf eine Assembly, die eine Vorlagendefinition enthalten verweisen und erstellen neue spezialisierungen der Vorlage. Nach der Kompilierung, sieht eine spezialisierte Vorlage einer anderen Klasse oder Methode. Im Gegensatz dazu werden als ein parametrisierter Typ, die bekanntermaßen von der Laufzeit einem parametrisierten Typ Generika in MSIL ausgegeben; Quellcode, der eine Assembly mit einem generischen Typ verweist, kann spezialisierungen des generischen Typs erstellen. Weitere Informationen zu den Vergleich der standardmäßigen C++-Vorlagen und Generika, finden Sie unter [Generika und Vorlagen (C++ / CLI)](../windows/generics-and-templates-visual-cpp.md).

## <a name="generic-functions-and-types"></a>Generische Funktionen und Typen

Klassentypen, können solange sie verwaltete Datentypen sind generisch sein. Ein Beispiel hierfür ist möglicherweise eine `List` Klasse. Der Typ eines Objekts in der Liste, wäre der Type-Parameter. Wenn nötig, eine `List` -Klasse für viele verschiedene Arten von Objekten, die vor Generika, die Sie verwendet haben eine `List` akzeptiert `System::Object` als Elementtyp. Aber, ein Objekt (einschließlich Objekte des falschen Typs) in der Liste verwendet werden können. Eine solche Liste würde eine nicht typisierte Sammlungsklasse aufgerufen werden. Im besten Fall könnten Sie den Typ zur Laufzeit überprüfen und löst eine Ausnahme. Oder Sie haben eine Vorlage, die seine generische Qualität, die nach der Kompilierung in eine Assembly verloren gehen würde verwendet. Consumer Ihrer Assembly konnte eigene spezialisierungen der Vorlage nicht erstellt werden. Generika ermöglichen Ihnen die typisierte Auflistungsklassen, z. B. Erstellung `List<int>` (ausgesprochen "List of Int") und `List<double>` ("List Double-Wert") dem einen Fehler während der Kompilierung generieren würden, würden Sie versuchen, einen Typ zu platzieren, die die Auflistung wurde nicht dafür ausgelegt, die in den typisierten akzeptieren Auflistung. Darüber hinaus bleibt dieser Typen generische, wenn sie kompiliert werden.

Eine Beschreibung der Syntax von generischen Klassen finden Sie im [generische Klassen (C++ / CLI)](../windows/generic-classes-cpp-cli.md). Einen neuen Namespace, <xref:System.Collections.Generic>, führt eine Reihe von parametrisierten Sammlungstypen, z.B. <xref:System.Collections.Generic.Dictionary%602>, <xref:System.Collections.Generic.List%601> und <xref:System.Collections.Generic.LinkedList%601>.

Sowohl-Instanz und Memberfunktionen von statischen Klassen, Delegaten und globale Funktionen können auch generisch sein. Generische Funktionen können erforderlich sein, wenn Funktionsparameter eines unbekannten Typs sind oder wenn die Funktion selbst mit generischen Typen arbeiten muss. In vielen Fällen, in denen `System::Object` verwendet wurde in der Vergangenheit als Parameter für ein Unbekannter Objekttyp ein generischer Typparameter kann verwendet werden stattdessen mehr als typsicherer Code ermöglicht. Zum Zeitpunkt der Kompilierung würde jeder Versuch, einen Typ übergeben, das die Funktion nicht für entworfen wurde als Fehler gekennzeichnet. Mithilfe von `System::Object` als Funktionsparameter, die unbeabsichtigte Übergabe eines Objekts, dass die Funktion für den Umgang mit unbeabsichtigte würde nicht erkannt, und Sie müssten unbekannten Objekttyps auf einen bestimmten Typ in den Funktionstext umgewandelt, und berücksichtigen die Möglichkeit, eine InvalidCastException-Ausnahme. Mit einer generischen würde Code, es wird versucht, ein Objekt an die Funktion übergeben zu einen Typenkonflikt, damit der Hauptteil der Funktion gewährleistet ist, um den richtigen Typ zu erhalten.

Die gleichen Vorteile gelten für Auflistungsklassen zu Generika erstellt. Auflistungsklassen, die in der Vergangenheit verwenden `System::Object` zum Speichern der Elemente in einer Auflistung. Einfügen von Objekten eines Typs, der die Auflistung nicht für entworfen wurde wurde zum Zeitpunkt der Kompilierung und oft auch nicht, wenn die Objekte eingefügt wurden, nicht gekennzeichnet. In der Regel wird ein Objekt zu einem anderen Typ umgewandelt werden, wenn es in der Auflistung zugegriffen wurde. Nur, wenn die Umwandlung Fehler wird vom unerwartete Typ erkannt werden. Generika löst dieses Problem zur Kompilierungszeit durch die Erkennung von Code, der einen Typ, die nicht übereinstimmen eingefügt (oder implizit in konvertieren) der Typparameter der generischen Auflistung.

Eine Beschreibung der Syntax, finden Sie unter [generische Funktionen (C++ / CLI)](../windows/generic-functions-cpp-cli.md).

## <a name="terminology-used-with-generics"></a>Mit Generika-Terminologie

### <a name="type-parameters"></a>Typparameter

Eine generische Deklaration enthält eine oder mehrere unbekannte Typen genannt *Typparameter*. Typparameter sind ein Name zugewiesen, das für den Typ innerhalb des Texts der generischen Deklaration steht. Der Typparameter wird als ein Typ innerhalb des Texts der generischen Deklaration verwendet. Die generische Deklaration für `List<T>` enthält den Typparameter "t".

### <a name="type-arguments"></a>Typargumente

Die *Typargument* ist der tatsächliche Typ anstelle des Typparameters verwendet werden, wenn die generische für einen bestimmten Typ oder Typen spezialisiert ist. Z. B. **Int** ist das Typargument in `List<int>`. Werttypen und Typen von Handles sind die einzigen Typen, die als ein generisches Typargument zulässig.

### <a name="constructed-type"></a>Konstruierter Typ

Aus einem generischen Typ erstellter Typ wird als bezeichnet ein *konstruierter Typ*. Ein Typ, der nicht vollständig angegeben, wie z. B. `List<T>` ist ein *konstruierten Typs öffnen*; einen Typ vollständig angegeben, wie z. B. `List<double>,` ist eine *geschlossener konstruierten Typ* oder *spezialisierte Typ* . Offene konstruierte Typen können in der Definition der andere generische Typen oder Methoden verwendet werden und dürfen nicht vollständig angegeben werden, bis der einschließenden generischen selbst angegeben ist. Folgendes ist beispielsweise eine Verwendung eines offenen konstruierten Typs als Basisklasse für einen generischen:

```cpp
// generics_overview.cpp
// compile with: /clr /c
generic <typename T>

ref class List {};

generic <typename T>

ref class Queue : public List<T> {};
```

### <a name="constraint"></a>Constraint

Eine Einschränkung ist eine Einschränkung für die Typen, die als Typparameter verwendet werden kann. Beispielsweise kann eine bestimmte generische Klasse akzeptieren nur Klassen, die von einer bestimmten Klasse erben, oder implementieren eine angegebene Schnittstelle. Weitere Informationen finden Sie unter [Einschränkungen für generische Typparameter (C++ / CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="reference-types-and-value-types"></a>Verweistypen und Werttypen

Handles und Werttypen können als Typargumente verwendet werden. In der generischen Methodendefinition, in denen beide Typen verwendet werden kann, ist die Syntax, die von Verweistypen. Z. B. die `->` Operator wird verwendet, um die Member des Typs des Typparameters zugreifen, und zwar unabhängig davon, ob der Typ, der schließlich verwendet ein Verweistyp oder ein Werttyp ist. Wenn ein Werttyp als Typargument verwendet wird, generiert die Laufzeit Code, der die Werttypen direkt ohne boxing von Werttypen verwendet.

Wenn einen Verweistyp als ein generisches Typargument verwenden möchten, verwenden Sie die Handle-Syntax. Wenn einen Werttyp als ein generisches Typargument verwenden möchten, verwenden Sie den Namen des Typs direkt.

```cpp
// generics_overview_2.cpp
// compile with: /clr
generic <typename T>

ref class GenericType {};
ref class ReferenceType {};

value struct ValueType {};

int main() {
    GenericType<ReferenceType^> x;
    GenericType<ValueType> y;
}
```

## <a name="type-parameters"></a>Typparameter

Der Typparameter in einer generischen Klasse werden wie andere Bezeichner behandelt. Da der Typ nicht bekannt ist, gibt es jedoch Einschränkungen für deren Verwendung. Sie können nicht z. B. Member und Methoden der Klasse von Type-Parameter verwenden, es sei denn, der der Typparameter bekannt ist, dass diese Elemente unterstützen. Für den Zugriff auf einen Member mithilfe der Type-Parameter müssen Sie den Typ mit dem Element um Einschränkungsliste des Typparameters, also hinzufügen.

```cpp
// generics_overview_3.cpp
// compile with: /clr
interface class I {
   void f1();
   void f2();
};

ref struct R : public I {
   virtual void f1() {}
   virtual void f2() {}
   virtual void f3() {}
};

generic <typename T>
where T : I
void f(T t) {
   t->f1();
   t->f2();
   safe_cast<R^>(t)->f3();
}

int main() {
   f(gcnew R());
}
```

Diese Einschränkungen gelten auch Operatoren. Ein uneingeschränkte generischen Typparameter können nicht die `==` und `!=` Operatoren zum Vergleichen von zwei Instanzen des Typparameters, für den Fall, dass der Typ dieser Operatoren nicht unterstützt. Diese Überprüfungen werden für Generika erforderlich sind, aber nicht für Vorlagen, da Generika zur Laufzeit mit einer beliebigen Klasse spezialisiert werden können, erfüllt die Einschränkungen, wird er zu spät für die Verwendung von ungültigen Elementen zu überprüfen.

Eine Standardinstanz des Typparameters kann erstellt werden, mithilfe der `()` Operator. Zum Beispiel:

`T t = T();`

wo `T` ein Parameter vom Typ in der Definition einer generischen Klasse oder Methode ist, initialisiert die Variable auf den Standardwert zurück. Wenn `T` ist eine Verweisklasse, es wird ein null-Zeiger; sein, wenn `T` eine Wertklasse ist, wird das Objekt ist 0 (null) initialisiert. Dies wird als bezeichnet ein *Standard-Initialisierer*.

## <a name="see-also"></a>Siehe auch

[Generika](../windows/generics-cpp-component-extensions.md)