---
title: Compilerwarnung (Stufe 1) C4369
ms.date: 11/04/2016
f1_keywords:
- C4369
helpviewer_keywords:
- C4369
ms.assetid: ade87e84-36be-4e00-be99-2930af848feb
ms.openlocfilehash: 617cb2cc3774b288581a3868125ced19b28ba45a
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966508"
---
# <a name="compiler-warning-level-1-c4369"></a>Compilerwarnung (Stufe 1) C4369

' Enumerator ': der Enumeratorwert ' value ' kann nicht als ' type ' dargestellt werden, der Wert ist ' new_value '.

Ein Enumerator wurde so berechnet, dass er größer als der größte Wert für den angegebenen zugrunde liegenden Typ ist.  Dies verursachte einen Überlauf, und der Compiler hat den Enumeratorwert auf den niedrigsten möglichen Wert für den Typ umschließen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4369 generiert.

```cpp
// C4369.cpp
// compile with: /W1
int main() {
   enum Color: char { red = 0x7e, green, blue };   // C4369
   enum Color2: char { red2 = 0x7d, green2, blue2};   // OK
}
```