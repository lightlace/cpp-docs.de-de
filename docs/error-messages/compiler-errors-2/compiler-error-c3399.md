---
title: Compilerfehler C3399
ms.date: 11/04/2016
f1_keywords:
- C3399
helpviewer_keywords:
- C3399
ms.assetid: 306ad199-d150-4f6c-bcf1-24a7948b93be
ms.openlocfilehash: e400c181f987a83588f8aedc63ecdedb82be310f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568677"
---
# <a name="compiler-error-c3399"></a>Compilerfehler C3399

'Typ': Beim Erstellen einer Instanz eines generischen Parameters können Argumente nicht bereitgestellt werden.

Wenn Sie die `gcnew()` -Einschränkung angeben, geben Sie auch an, dass der Einschränkungstyp über einen parameterlosen Konstruktor verfügt. Aus diesem Grund tritt bei dem Versuch ein Fehler auf, diesen Typ zu instanziieren und einen Parameter zu übergeben.

Finden Sie unter [Einschränkungen für generische Typparameter (C++ / CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md) für Weitere Informationen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3399 generiert:

```
// C3399.cpp
// compile with: /clr /c
generic <class T>
where T : gcnew()
void f() {
   T t = gcnew T(1);   // C3399
   T t2 = gcnew T();   // OK
}
```