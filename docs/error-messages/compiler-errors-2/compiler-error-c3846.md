---
title: Compilerfehler C3846
ms.date: 11/04/2016
f1_keywords:
- C3846
helpviewer_keywords:
- C3846
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
ms.openlocfilehash: 788f03e4364404ad5c30b7edcba8b743c7f201ad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651216"
---
# <a name="compiler-error-c3846"></a>Compilerfehler C3846

'Symbol': Symbol aus "assembly2" kann nicht importiert: 'Symbol' wurde bereits von einer anderen Assembly 'assembly1' importiert

Ein Symbol konnte nicht aus einer referenzierten Assembly importiert werden, weil sie zuvor aus einer referenzierten Assembly importiert wurde.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3846 generiert:

```
// C3846a.cpp
// compile with: /LD /clr
public ref struct G
{
};
```

Und kompilieren Sie diese:

```
// C3846b.cpp
// compile with: /clr
#using "c3846a.dll"
#using "c3846a.obj"   // C3846

int main()
{
}
```
