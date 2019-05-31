---
title: abstract  (C++/CLI und C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- abstract
- abstract_cpp
helpviewer_keywords:
- abstract keyword [C++]
ms.assetid: cbae3408-0378-4ac8-b70d-c016b381a6d5
ms.openlocfilehash: d5060f1a0950b9b2ac2638b99ff157983944a3bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "65516165"
---
# <a name="abstract--ccli-and-ccx"></a>abstract  (C++/CLI und C++/CX)

Das **abstract**-Schlüsselwort nimmt eine der folgenden Deklarationen vor:

- Ein Typ kann als Basistyp verwendet werden, aber der Typ selbst kann nicht instanziiert werden.

- Eine Typmemberfunktion kann nur in einem abgeleiteten Typ definiert werden.

## <a name="all-platforms"></a>Alle Plattformen

### <a name="syntax"></a>Syntax

*Klassendeklaration* *Klassenbezeichner* **abstract {}**

**virtual** *Rückgabetyp* *Memberfunktionsbezeichner* **() abstract ;**

### <a name="remarks"></a>Anmerkungen

Die erste Beispielsyntax deklariert eine Klasse als abstrakt. Die *Klassendeklaration*-Komponente kann entweder eine native C++-Deklaration (**Klasse** oder **Struktur**) oder eine C++-Erweiterungsdeklaration (**Referenzklasse** oder **Referenzstruktur**) sein, wenn die Compileroption `/ZW` oder `/clr` angegeben wird.

Die zweite Beispielsyntax deklariert eine virtuelle Memberfunktion als abstrakt. Das Deklarieren einer Funktion als abstrakt ist mit dem Deklarieren als rein virtuelle Funktion identisch. Das Deklarieren einer Memberfunktion als abstrakt bewirkt, dass auch die einschließende Klasse als abstrakt deklariert wird.

Das **abstract**-Schlüsselwort wird in nativem und plattformspezifischem Code unterstützt, d.h. es kann mit oder ohne Compileroption `/ZW` oder `/clr` kompiliert werden.

Sie können mit der `__is_abstract(type)`-Typeigenschaft zum Zeitpunkt der Kompilierung ermitteln, ob ein Typ abstrakt ist. Weitere Informationen finden Sie unter [Compilerunterstützung für Typmerkmale](compiler-support-for-type-traits-cpp-component-extensions.md).

Das **abstract**-Schlüsselwort ist ein kontextbezogener Überschreibungsspezifizierer. Weitere Informationen zu kontextbezogenen Schlüsselwörtern finden Sie unter [Kontextbezogene Schlüsselwörter](context-sensitive-keywords-cpp-component-extensions.md). Weitere Informationen zu Überschreibungsspezifizierern finden Sie unter [Vorgehensweise: Deklarieren von Überschreibungsspezifizierern in nativen Kompilierungen](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).

## <a name="windows-runtime"></a>Windows-Runtime

Weitere Informationen finden Sie unter [Referenzklassen und -strukturen](../cppcx/ref-classes-and-structs-c-cx.md).

### <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

## <a name="common-language-runtime"></a>Common Language Runtime

### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`

### <a name="examples"></a>Beispiele

Das folgende Codebeispiel generiert einen Fehler, da Klasse `X` als **abstract** gekennzeichnet ist.

```cpp
// abstract_keyword.cpp
// compile with: /clr
ref class X abstract {
public:
   virtual void f() {}
};

int main() {
   X ^ MyX = gcnew X;   // C3622
}
```

Das folgende Codebeispiel generiert einen Fehler, da es eine native Klasse instanziiert, die als **abstract** gekennzeichnet ist. Dieser Fehler tritt mit und ohne Compileroption `/clr` auf.

```cpp
// abstract_keyword_2.cpp
class X abstract {
public:
   virtual void f() {}
};

int main() {
   X * MyX = new X; // C3622: 'X': a class declared as 'abstract'
                    // cannot be instantiated. See declaration of 'X'}
```

Das folgende Codebeispiel generiert einen Fehler, da Funktion `f` eine Definition enthält, aber als **abstract** gekennzeichnet ist. Die letzte Anweisung im Beispiel zeigt, dass das Deklarieren einer abstrakten virtuellen Funktion dem Deklarieren einer rein virtuellen Funktion entspricht.

```cpp
// abstract_keyword_3.cpp
// compile with: /clr
ref class X {
public:
   virtual void f() abstract {}   // C3634
   virtual void g() = 0 {}   // C3634
};
```

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für .NET und UWP](component-extensions-for-runtime-platforms.md)
