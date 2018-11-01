---
title: Literale (C++ / CLI und C++ / CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- literal
- literal_cpp
helpviewer_keywords:
- literal keyword [C++]
ms.assetid: 6b1a1f36-2e1d-4a23-8eb6-172f4f3c477f
ms.openlocfilehash: d58df1bb6a6ec1e53ee434cf60a8caf3d557eeb2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50521036"
---
# <a name="literal-ccli-and-ccx"></a>Literale (C++ / CLI und C++ / CX)

Eine Variable (Datenmember) markiert, als **literal** in einer **"/ CLR"** Kompilierung ist das systemeigene Äquivalent der ein **static Const** Variable.

## <a name="all-platforms"></a>Alle Plattformen

### <a name="remarks"></a>Hinweise

(Es gibt keine Hinweise für diese Sprachfunktion, die für alle Laufzeiten gültig sind.)

## <a name="windows-runtime"></a>Windows-Runtime

### <a name="remarks"></a>Hinweise

(Es gibt keine Hinweise für diese Sprachfunktion, die nur für Windows-Runtime gelten.)

### <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

## <a name="common-language-runtime"></a>Common Language Runtime

## <a name="remarks"></a>Hinweise

Ein Datenmember als markiert **literal** muss initialisiert werden, wenn Sie deklariert und der Wert muss eine ganzzahlige Konstante, Enumeration oder Zeichenfolgentyp. Eine benutzerdefinierte Konvertierung erforderlich die Konvertierung vom Typ des Initialisierungsausdrucks in den Typ des static const-Datenmembers nicht.

Für das literal Feld zur Laufzeit wird kein Arbeitsspeicher belegt werden; der Compiler fügt den Wert nur in den Metadaten für die Klasse.

Markiert eine Variable **static Const** werden nicht in den Metadaten für andere Compiler verfügbar.

Weitere Informationen finden Sie unter [statische](../cpp/storage-classes-cpp.md) und [const](../cpp/const-cpp.md).

**Literal** ist ein kontextbezogenes Schlüsselwort. Finden Sie unter [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md) für Weitere Informationen.

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt, dass eine **literal** Variable impliziert **statische**.

```cpp
// mcppv2_literal.cpp
// compile with: /clr
ref struct X {
   literal int i = 4;
};

int main() {
   int value = X::i;
}
```

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt die Auswirkungen der literalen in den Metadaten:

```cpp
// mcppv2_literal2.cpp
// compile with: /clr /LD
public ref struct A {
   literal int lit = 0;
   static const int sc = 1;
};
```

Beachten Sie den Unterschied in den Metadaten für `sc` und `lit`: die `modopt` Richtlinie gilt für `sc`, d. h. sie kann von anderen Compilern ignoriert werden.

```
.field public static int32 modopt([mscorlib]System.Runtime.CompilerServices.IsConst) sc = int32(0x0000000A)
```

```
.field public static literal int32 lit = int32(0x0000000A)
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird in c# verfasst verweist auf die Metadaten, die im vorherigen Beispiel erstellt und zeigt die Auswirkungen der **literal** und **static Const** Variablen:

```cs
// mcppv2_literal3.cs
// compile with: /reference:mcppv2_literal2.dll
// A C# program
class B {
   public static void Main() {
      // OK
      System.Console.WriteLine(A.lit);
      System.Console.WriteLine(A.sc);

      // C# does not enforce C++ const
      A.sc = 9;
      System.Console.WriteLine(A.sc);

      // C# enforces const for a literal
      A.lit = 9;   // CS0131

      // you can assign a C++ literal variable to a C# const variable
      const int i = A.lit;
      System.Console.WriteLine(i);

      // but you cannot assign a C++ static const variable
      // to a C# const variable
      const int j = A.sc;   // CS0133
      System.Console.WriteLine(j);
   }
}
```

## <a name="requirements"></a>Anforderungen

Compileroption: `/clr`

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für .NET und UWP](../windows/component-extensions-for-runtime-platforms.md)