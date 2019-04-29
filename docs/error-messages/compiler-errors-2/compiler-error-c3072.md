---
title: Compilerfehler C3072
ms.date: 11/04/2016
f1_keywords:
- C3072
helpviewer_keywords:
- C3072
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
ms.openlocfilehash: 2b76fa91d739e9cc89251aaf56aa9b196e62a68d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406729"
---
# <a name="compiler-error-c3072"></a>Compilerfehler C3072

Operator 'Operator' kann nicht auf eine Instanz einer Verweisklasse angewendet werden

Verwenden Sie die unären '`operator` ' Operator, um eine Instanz einer Verweisklasse in einen Handletyp zu konvertieren

Ein CLR-Typ ist erforderlich, CLR-Operatoren, keine systemeigenen (oder Standard-)-Operatoren.  Weitere Informationen finden Sie unter [Verweisoperator nachverfolgung](../../extensions/tracking-reference-operator-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3072 generiert.

```
// C3072.cpp
// compile with: /clr
ref class R {};

int main() {
   R r1;
   R^ r2 = &r1;   // C3072
   R^ r3 = %r1;   // OK
}
```