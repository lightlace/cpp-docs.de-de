---
title: Compilerwarnung (Stufe 1) C4621
ms.date: 11/04/2016
f1_keywords:
- C4621
helpviewer_keywords:
- C4621
ms.assetid: 40931bd9-cb89-497e-86f0-cec9f016c63c
ms.openlocfilehash: d35c4143d5b90c7a6a49337931dad4ba73804f20
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555627"
---
# <a name="compiler-warning-level-1-c4621"></a>Compilerwarnung (Stufe 1) C4621

keine Postfix-Form des Operators"--" für Typ 'Typ', Präfix-Form gefunden.

Keine Postfix-Dekrementoperators für den angegebenen Typ definiert ist. Der Compiler hat den überladenen Präfixoperator verwendet.

Diese Warnung kann vermieden werden, indem Sie einen Postfix- `--` -Operator definieren. Erstellen Sie eine Version zwei Argumenten, der die `--` Operator wie unten dargestellt:

```
// C4621.cpp
// compile with: /W1
class A
{
public:
   A(int nData) : m_nData(nData)
   {
   }

   A operator--()
   {
      m_nData -= 1;
      return *this;
   }

   // A operator--(int)
   // {
   //    A tmp = *this;
   //    m_nData -= 1;
   //    return tmp;
   // }

private:
   int m_nData;
};

int main()
{
   A a(10);
   --a;
   a--;   // C4621
}
```