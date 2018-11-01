---
title: Compilerfehler C3290
ms.date: 11/04/2016
f1_keywords:
- C3290
helpviewer_keywords:
- C3290
ms.assetid: 0baf684b-1143-4953-ac99-a2fa267d8017
ms.openlocfilehash: d82d3272563f7a5af5de399a2f7fff621500e612
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490479"
---
# <a name="compiler-error-c3290"></a>Compilerfehler C3290

"Typ": Eine trivial-Eigenschaft darf keinen Referenztyp aufweisen.

Eine Eigenschaft wurde falsch deklariert. Wenn Sie eine triviale Eigenschaft deklarieren, erstellt der Compiler eine Variable, die von der Eigenschaft aktualisiert wird, und es ist nicht möglich, eine Nachverfolgungsverweisvariable in einer Klasse zu verwenden.

Finden Sie unter [Eigenschaft](../../windows/property-cpp-component-extensions.md) und [Verweisoperator nachverfolgung](../../windows/tracking-reference-operator-cpp-component-extensions.md) für Weitere Informationen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3290 generiert.

```
// C3290.cpp
// compile with: /clr /c
ref struct R {};

ref struct X {
   R^ mr;

   property R % y;   // C3290
   property R ^ x;   // OK

   // OK
   property R% prop {
      R% get() {
         return *mr;
      }

      void set(R%) {}
   }
};

int main() {
   X x;
   R% xp = x.prop;
}
```