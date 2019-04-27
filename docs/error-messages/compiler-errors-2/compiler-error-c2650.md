---
title: Compilerfehler C2650
ms.date: 11/04/2016
f1_keywords:
- C2650
helpviewer_keywords:
- C2650
ms.assetid: 49a8ac6e-aa6d-4616-917c-a3cfcdbad5a4
ms.openlocfilehash: c7cbc12bff4e00613032a9d28b5be7533dce9612
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152558"
---
# <a name="compiler-error-c2650"></a>Compilerfehler C2650

'Operator': eine virtuelle Funktion nicht möglich

Ein `new` oder `delete` Operator deklariert ist `virtual`. Diese Operatoren sind `static` Member-Funktionen und kann nicht `virtual`.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2650 generiert:

```
// C2650.cpp
// compile with: /c
class A {
   virtual void* operator new( unsigned int );   // C2650
   // try the following line instead
   // void* operator new( unsigned int );
};
```