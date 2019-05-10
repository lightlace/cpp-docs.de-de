---
title: Compilerfehler C2885
ms.date: 11/04/2016
f1_keywords:
- C2885
helpviewer_keywords:
- C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
ms.openlocfilehash: ff5e770052301e95f694d3712f95b82732c2faba
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447702"
---
# <a name="compiler-error-c2885"></a>Compilerfehler C2885

'class:: Identifier': keine gültige using-Deklaration im Gültigkeitsbereich einer nicht-Klasse

Sie verwendet eine [mit](../../cpp/using-declaration.md) Deklaration nicht ordnungsgemäß.

## <a name="example"></a>Beispiel

Dieser Fehler kann infolge einer konformitätsverbesserung für Compiler, die für Visual Studio 2005 durchgeführt wurde generiert werden: Es ist nicht mehr gültig ist, damit eine `using` Deklaration auf einen geschachtelten Typ müssen Sie explizit jeden Verweis, die Sie, um den geschachtelten Typ, der den Typ in ein n einfügen vornehmen qualifizieren Amespace, oder erstellen Sie eine Typedef.

Im folgende Beispiel wird die C2885 generiert.

```
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

Bei Verwendung der `using` Schlüsselwort mit einem Klassenmember, C++ erfordert, dass Sie dieses Element in einer anderen Klasse (in einer abgeleiteten Klasse) zu definieren.

Im folgende Beispiel wird die C2885 generiert.

```
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