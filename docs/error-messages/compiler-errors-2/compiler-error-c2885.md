---
title: Compilerfehler C2885 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2885
dev_langs:
- C++
helpviewer_keywords:
- C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cf47d830980b9fb93481f575e3e3a806ce8bbf68
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035694"
---
# <a name="compiler-error-c2885"></a>Compilerfehler C2885

'class:: Identifier': keine gültige using-Deklaration im Gültigkeitsbereich einer nicht-Klasse

Sie verwendet eine [mit](../../cpp/using-declaration.md) Deklaration nicht ordnungsgemäß.

## <a name="example"></a>Beispiel

Dieser Fehler kann infolge einer konformitätsverbesserung für Compiler, die für Visual C++ 2005 durchgeführt wurde generiert werden: Es ist nicht mehr gültig ist, damit eine `using` Deklaration auf einen geschachtelten Typ müssen Sie explizit jeden Verweis, die Sie, um den geschachtelten Typ, und fügen Sie den Typ in einen Namen vornehmen qualifizieren Speicherplatz, oder erstellen Sie eine Typedef.

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