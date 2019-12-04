---
title: Compilerfehler C2885
ms.date: 11/04/2016
f1_keywords:
- C2885
helpviewer_keywords:
- C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
ms.openlocfilehash: e60f3fff2ef61f4d6374072c05a2ad3e64a57031
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760927"
---
# <a name="compiler-error-c2885"></a>Compilerfehler C2885

"Class:: Identifier": keine gültige using-Deklaration im nicht Klassen Bereich.

Sie haben fälschlicherweise eine [using](../../cpp/using-declaration.md) -Deklaration verwendet.

## <a name="example"></a>Beispiel

Dieser Fehler kann als Ergebnis einer compilerübereinstimmungs-Arbeit generiert werden, die für Visual Studio 2005 durchgeführt wurde: Es ist nicht mehr zulässig, eine `using` Deklaration für einen nistyp zu haben. Sie müssen jeden Verweis, den Sie für den schsted Typ vornehmen, explizit qualifizieren, den Typ in einen Namespace einfügen oder eine typedef erstellen.

Im folgenden Beispiel wird C2885 generiert.

```cpp
// C2885.cpp
namespace MyNamespace {
   class X1 {};
}

struct MyStruct {
   struct X1 {
      int i;
   };
};

int main () {
   using MyStruct::X1;   // C2885

   // OK
   using MyNamespace::X1;
   X1 myX1;

   MyStruct::X1 X12;

   typedef MyStruct::X1 abc;
   abc X13;
   X13.i = 9;
}
```

## <a name="example"></a>Beispiel

Wenn Sie das `using`-Schlüsselwort mit einem Klassenmember verwenden, ist C++ es erforderlich, dass Sie dieses Element in einer anderen Klasse (einer abgeleiteten Klasse) definieren.

Im folgenden Beispiel wird C2885 generiert.

```cpp
// C2885_b.cpp
// compile with: /c
class A {
public:
   int i;
};

void z() {
   using A::i;   // C2885 not in a class
}

class B : public A {
public:
   using A::i;
};
```
