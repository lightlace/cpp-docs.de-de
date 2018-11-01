---
title: Compilerfehler C3072
ms.date: 11/04/2016
f1_keywords:
- C3072
helpviewer_keywords:
- C3072
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
ms.openlocfilehash: 34b5cff9191814b2a16a42d9e234bab09f29c117
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490024"
---
# <a name="compiler-error-c3072"></a>Compilerfehler C3072

Operator 'Operator' kann nicht auf eine Instanz einer Verweisklasse angewendet werden

Verwenden Sie die unären '`operator` ' Operator, um eine Instanz einer Verweisklasse in einen Handletyp zu konvertieren

Ein CLR-Typ ist erforderlich, CLR-Operatoren, keine systemeigenen (oder Standard-)-Operatoren.  Weitere Informationen finden Sie unter [Verweisoperator nachverfolgung](../../windows/tracking-reference-operator-cpp-component-extensions.md).

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