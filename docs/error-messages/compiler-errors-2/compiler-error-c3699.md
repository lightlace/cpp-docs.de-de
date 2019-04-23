---
title: Compilerfehler C3699
ms.date: 11/04/2016
f1_keywords:
- C3699
helpviewer_keywords:
- C3699
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
ms.openlocfilehash: 93058d34ca9a17ab175a55a7bc7b953d369e65c5
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59779452"
---
# <a name="compiler-error-c3699"></a>Compilerfehler C3699

'Operator': Diese Dereferenzierung für Typ 'Typ' können keine

Es wurde versucht, Dereferenzierung zu verwenden, die für nicht zulässig ist `type`.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3699 generiert.

```
// C3699.cpp
// compile with: /clr /c
using namespace System;
int main() {
   String * s;   // C3699
   // try the following line instead
   // String ^ s2;
}
```

## <a name="example"></a>Beispiel

Eine triviale Eigenschaft kann nicht Verweistyp aufweisen. Weitere Informationen finden Sie unter [property](../../extensions/property-cpp-component-extensions.md) . Im folgende Beispiel wird die C3699 generiert.

```
// C3699_b.cpp
// compile with: /clr /c
ref struct C {
   property System::String % x;   // C3699
   property System::String ^ y;   // OK
};
```

## <a name="example"></a>Beispiel

Das Äquivalent einer "Zeiger auf einen Zeiger"-Syntax ist ein Handle für ein Nachverfolgungsverweis an. Im folgende Beispiel wird die C3699 generiert.

```
// C3699_c.cpp
// compile with: /clr /c
using namespace System;
void Test(String ^^ i);   // C3699
void Test2(String ^% i);
```