---
title: abstract (C++ / CLI und C++ / CX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- abstract
- abstract_cpp
dev_langs:
- C++
helpviewer_keywords:
- abstract keyword [C++]
ms.assetid: cbae3408-0378-4ac8-b70d-c016b381a6d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 78a5b42de6b0ac54d060bb6369566aa446863289
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2018
ms.locfileid: "49328193"
---
# <a name="abstract--ccli-and-ccx"></a>abstract (C++ / CLI und C++ / CX)

Die **abstrakte** -Schlüsselwort deklariert entweder:

- Ein Typ kann als Basistyp verwendet werden, aber der Typ selbst kann nicht instanziiert werden.

- Eine Typmemberfunktion kann nur in einem abgeleiteten Typ definiert werden.

## <a name="all-platforms"></a>Alle Plattformen

### <a name="syntax"></a>Syntax

*Klassendeklaration* *-Klassenbezeichner* **abstrakte {}**

**virtuelle** *Rückgabetyp* *Member-Funktion-Identifier* **abstrakt)**

### <a name="remarks"></a>Hinweise

Die erste Beispielsyntax deklariert eine Klasse als abstrakt. Die *-Klassendeklaration* Komponente kann entweder eine native C++-Deklaration sein (**Klasse** oder **Struktur**), oder eine C++-erweiterungsdeklaration (**Verweisklasse** oder **Referenzstruktur**) Wenn die `/ZW` oder `/clr` -Compileroption angegeben ist.

Die zweite Beispielsyntax deklariert eine virtuelle Memberfunktion als abstrakt. Das Deklarieren einer Funktion als abstrakt ist mit dem Deklarieren als rein virtuelle Funktion identisch. Das Deklarieren einer Memberfunktion als abstrakt bewirkt, dass auch die einschließende Klasse als abstrakt deklariert wird.

Die **abstrakte** Schlüsselwort in systemeigenem und plattformspezifischem Code unterstützt wird; d. h., kompiliert werden kann, mit oder ohne die `/ZW` oder `/clr` -Compileroption.

Sie können zur Kompilierzeit erkennen, wenn ein Typ abstrakt ist mit ist der `__is_abstract(type)` Typeigenschaft. Weitere Informationen finden Sie unter [Compilerunterstützung für Typmerkmale](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).

Die **abstrakte** -Schlüsselwort ist ein kontextbezogener Überschreibungsspezifizierer. Weitere Informationen zu kontextbezogenen Schlüsselwörtern finden Sie unter [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md). Weitere Informationen zu überschreibungsspezifizierern finden Sie unter [wie: Deklarieren Sie Überschreibungsspezifizierer in nativen Kompilierungen](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).

## <a name="windows-runtime"></a>Windows-Runtime

Weitere Informationen finden Sie unter [Verweisklassen und Strukturen](../cppcx/ref-classes-and-structs-c-cx.md).

### <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

## <a name="common-language-runtime"></a>Common Language Runtime

### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`

### <a name="examples"></a>Beispiele

Im folgenden Codebeispiel wird einen Fehler generiert, da Klasse `X` RuntimeCompatibility **abstrakte**.

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

Das folgende Codebeispiel generiert einen Fehler, da es sich um eine systemeigene Klasse instanziiert, die markiert ist **abstrakte**. Dieser Fehler tritt mit und ohne Compileroption `/clr` auf.

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

Im folgenden Codebeispiel wird einen Fehler generiert, da Funktion `f` enthält eine Definition, aber ist als **abstrakte**. Die letzte Anweisung im Beispiel zeigt, dass das Deklarieren einer abstrakten virtuellen Funktion dem Deklarieren einer rein virtuellen Funktion entspricht.

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

[Komponentenerweiterungen für .NET- und UWP](../windows/component-extensions-for-runtime-platforms.md)
