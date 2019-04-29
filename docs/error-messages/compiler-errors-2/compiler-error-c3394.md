---
title: Compilerfehler C3394
ms.date: 11/04/2016
f1_keywords:
- C3394
helpviewer_keywords:
- C3394
ms.assetid: 4e025d79-27ba-43c8-b0d9-839ecef98126
ms.openlocfilehash: 826084d375c69ca289a858a29a12ae16874c1fbd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328743"
---
# <a name="compiler-error-c3394"></a>Compilerfehler C3394

Syntaxfehler in Einschränkungsklausel: „identifier“ wurde gefunden, es wurde jedoch ein Typ erwartet.

Eine Einschränkung wurde nicht ordnungsgemäß formatiert.  Weitere Informationen finden Sie unter [Einschränkungen für generische Typparameter (C++ / CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3394 generiert:

```
// C3394.cpp
// compile with: /clr /c
ref class MyClass {};
ref class R {
   generic<typename T>
   where T : static   // C3394
   // try the following line instead
   // where T : MyClass
   void f() {}
};
```