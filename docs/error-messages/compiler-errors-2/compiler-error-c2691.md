---
title: Compilerfehler C2691
ms.date: 11/04/2016
f1_keywords:
- C2691
helpviewer_keywords:
- C2691
ms.assetid: 6925f8f3-ea60-4909-91e6-b781492c645d
ms.openlocfilehash: 34287b785532394d33e94e37e7a6a9955d935f14
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360191"
---
# <a name="compiler-error-c2691"></a>Compilerfehler C2691

"Datentyp": eine verwaltete oder WinRTarray darf nicht diesen Elementtyp aufweisen

Der Typ eines verwalteten oder WinRT-Arrayelements kann ein Werttyp oder Verweistyp sein.

Im folgenden Beispiel wird C2691 generiert:

```
// C2691a.cpp
// compile with: /clr
class A {};

int main() {
   array<A>^ a1 = gcnew array<A>(20);   // C2691
   array<int>^ a2 = gcnew array<int>(20);   // value type OK
}
```
