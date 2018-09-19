---
title: Compilerfehler C3699 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3699
dev_langs:
- C++
helpviewer_keywords:
- C3699
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 64e5a5bb98f9e8a6950bbb279c026f167a2ee92e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46107709"
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

Eine triviale Eigenschaft kann nicht Verweistyp aufweisen. Weitere Informationen finden Sie unter [property](../../windows/property-cpp-component-extensions.md) . Im folgende Beispiel wird die C3699 generiert.

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