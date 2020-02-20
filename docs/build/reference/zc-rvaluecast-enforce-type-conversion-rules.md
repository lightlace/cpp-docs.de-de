---
title: /Zc:rvalueCast (Typkonvertierungsregeln erzwingen)
ms.date: 02/18/2020
f1_keywords:
- rvaluecast
- /Zc:rvalueCast
- VC.Project.VCCLCompilerTool.EnforceTypeConversionRules
helpviewer_keywords:
- -Zc compiler options (C++)
- rvaluecast
- Enforce type conversion rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 7825277d-e565-4c48-b0fb-76ac0b0c6e38
ms.openlocfilehash: ac74192cad8a62e4c82b480038e727b114362cdd
ms.sourcegitcommit: b9aaaebe6e7dc5a18fe26f73cc7cf5fce09262c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77504573"
---
# <a name="zcrvaluecast-enforce-type-conversion-rules"></a>/Zc:rvalueCast (Typkonvertierungsregeln erzwingen)

Wenn die **`/Zc:rvalueCast`** -Option angegeben ist, identifiziert der Compiler einen Rvalue-Verweistyp als Ergebnis eines Umwandlungs Vorgangs ordnungsgemäß. Das Verhalten entspricht dem Standard c++ 11. Wenn die Option nicht angegeben wird, ist das Compilerverhalten mit dem in Visual Studio 2012 identisch.

## <a name="syntax"></a>Syntax

> **`/Zc:rvalueCast`**\
> **`/Zc:rvalueCast-`**

## <a name="remarks"></a>Hinweise

Wenn **`/Zc:rvalueCast`** angegeben wird, befolgt der Compiler den Abschnitt 5,4 des c++ 11-Standards und behandelt nur Umwandlungs Ausdrücke, die zu nicht Verweis Typen und Umwandlungs Ausdrücken führen, die zu Rvalue-verweisen auf nicht Funktionstypen als Rvalue-Typen führen. Standardmäßig ist oder, wenn **`/Zc:rvalueCast-`** angegeben wird, der Compiler nicht kompatibel und behandelt alle Cast Ausdrücke, die zu Rvalue-verweisen führen, als Rvalues. Aus Gründen der Übereinstimmung und um Fehler bei der Verwendung von Umwandlungen zu vermeiden, empfiehlt es sich, **`/Zc:rvalueCast`** zu verwenden.

Standardmäßig ist **`/Zc:rvalueCast`** deaktiviert ( **`/Zc:rvalueCast-`** ). Diese Option wird von der [/permissive-](permissive-standards-conformance.md) -Compileroption implizit festgelegt, Sie kann jedoch mit **`/Zc:rvalueCast-`** überschrieben werden.

Verwenden Sie **`/Zc:rvalueCast`** , wenn Sie einen Umwandlungs Ausdruck als Argument an eine Funktion übergeben, die einen Rvalue-Verweistyp annimmt. Das Standardverhalten verursacht Compilerfehler [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) , wenn der Compiler den Typ des Umwandlungs Ausdrucks falsch bestimmt. Dieses Beispiel zeigt einen Compilerfehler im korrekten Code, wenn **`/Zc:rvalueCast`** nicht angegeben ist:

```cpp
// Test of /Zc:rvalueCast
// compile by using:
// cl /c /Zc:rvalueCast- make_thing.cpp
// cl /c /Zc:rvalueCast make_thing.cpp

#include <utility>

template <typename T>
struct Thing {
   // Construct a Thing by using two rvalue reference parameters
   Thing(T&& t1, T&& t2)
      : thing1(t1), thing2(t2) {}

   T& thing1;
   T& thing2;
};

// Create a Thing, using move semantics if possible
template <typename T>
Thing<T> make_thing(T&& t1, T&& t2)
{
   return (Thing<T>(std::forward<T>(t1), std::forward<T>(t2)));
}

struct Test1 {
   long a;
   long b;

   Thing<long> test() {
      // Use identity casts to create rvalues as arguments
      return make_thing(static_cast<long>(a), static_cast<long>(b));
   }
};
```

Das standardmäßige Compilerverhalten meldet möglicherweise keinen Fehler C2102, wenn dies angemessen ist. In diesem Beispiel meldet der Compiler keinen Fehler, wenn die Adresse eines von einer Identitäts Umwandlung erstellten Rvalue-Werts angenommen wird, wenn **`/Zc:rvalueCast`** nicht angegeben ist:

```cpp
int main() {
   int a = 1;
   int *p = &a;   // Okay, take address of lvalue
                  // Identity cast creates rvalue from lvalue;
   p = &(int)a;   // problem: should cause C2102: '&' requires l-value
}
```

Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Wählen Sie die **Eigenschaften Seite Konfigurations Eigenschaften** > **C++ C/**  > **Sprache** aus.

1. Legen Sie die Eigenschaft **Typkonvertierungs Regeln erzwingen** auf **`/Zc:rvalueCast`** oder **`/Zc:rvalueCast-`** fest. Wählen Sie **OK** oder **anwenden** aus, um die Änderungen zu speichern.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](zc-conformance.md)
