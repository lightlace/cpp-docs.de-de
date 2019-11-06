---
title: Compilerwarnung (Stufe 1) C4003
ms.date: 11/04/2016
f1_keywords:
- C4003
helpviewer_keywords:
- C4003
ms.assetid: 0ed1c285-4428-4c90-8131-86897e31f115
ms.openlocfilehash: 4adbffe3220060ee9d43f01cf94628f85d3991cc
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627383"
---
# <a name="compiler-warning-level-1-c4003"></a>Compilerwarnung (Stufe 1) C4003

Nicht genügend tatsächliche Parameter für das Makro 'identifier'

Die Anzahl der formalen Parameter in der Makro Definition überschreitet die Anzahl der tatsächlichen Parameter im Makro. Die Makro Erweiterung ersetzt leeren Text für die fehlenden Parameter.

Im folgenden Beispiel wird C4003 generiert:

```cpp
// C4003.cpp
// compile with: /WX
#define test(a,b) (a+b)

int main()
{
   int a = 1;
   int b = 2;
   a = test(b);   // C4003
   // try..
   a = test(a,b);
}
```