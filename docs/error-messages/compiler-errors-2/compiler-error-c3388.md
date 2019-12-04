---
title: Compilerfehler C3388
ms.date: 11/04/2016
f1_keywords:
- C3388
helpviewer_keywords:
- C3388
ms.assetid: 34336545-ed13-4d81-ab5f-f869799fe4c2
ms.openlocfilehash: bb2a847c24b2a0b7829008793f311459e76587f4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758345"
---
# <a name="compiler-error-c3388"></a>Compilerfehler C3388

"Typ": nicht als Einschränkung zulässig, "Verweisklasse" wird angenommen, um mit dem Analysieren fortzufahren

Eine Einschränkung wurde für einen generischen Typ angegeben, die Einschränkung wurde jedoch nicht ordnungsgemäß festgelegt. Weitere Informationen finden Sie [unter Einschränkungen fürC++generische Typparameter (/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) .

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3388 generiert.

```cpp
// C3388.cpp
// compile with: /clr /c
interface class AA {};

generic <class T>
where T : interface class   // C3388
ref class C {};

// OK
generic <class T>
where T : AA
ref class D {};
```
