---
title: Compilerfehler C3072 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3072
dev_langs:
- C++
helpviewer_keywords:
- C3072
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a36eaaf12cf9f8909455847036f670f6fc0cd40b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047511"
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