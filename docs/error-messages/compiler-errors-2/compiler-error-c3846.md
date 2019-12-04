---
title: Compilerfehler C3846
ms.date: 11/04/2016
f1_keywords:
- C3846
helpviewer_keywords:
- C3846
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
ms.openlocfilehash: a4c51ccfc724cf8309044812b287677f0f1a2ff0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754900"
---
# <a name="compiler-error-c3846"></a>Compilerfehler C3846

' Symbol ': das Symbol kann nicht aus ' Assembly2 ' importiert werden: da ' Symbol ' bereits aus einer anderen Assembly ' Assembly1 ' importiert wurde.

Ein Symbol konnte nicht aus einer referenzierten Assembly importiert werden, da es zuvor aus einer Assembly importiert wurde, auf die verwiesen wird.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3846 generiert:

```cpp
// C3846a.cpp
// compile with: /LD /clr
public ref struct G
{
};
```

Und kompilieren Sie dann Folgendes:

```cpp
// C3846b.cpp
// compile with: /clr
#using "c3846a.dll"
#using "c3846a.obj"   // C3846

int main()
{
}
```
