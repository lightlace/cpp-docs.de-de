---
title: Compilerfehler C3153
ms.date: 11/04/2016
f1_keywords:
- C3153
helpviewer_keywords:
- C3153
ms.assetid: d775d97e-2480-484f-81f1-88406b10f947
ms.openlocfilehash: 54fa7de8eb3df8d4b3695544c5285cc202275492
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745915"
---
# <a name="compiler-error-c3153"></a>Compilerfehler C3153

' Schnittstelle ': Sie können keine Instanz einer Schnittstelle erstellen.

Eine Schnittstelle kann nicht instanziiert werden. Um die Member einer Schnittstelle zu verwenden, leiten Sie eine Klasse von der-Schnittstelle ab, implementieren Sie die Schnittstellenmember, und verwenden Sie dann die-Member.

Im folgenden Beispiel wird C3153 generiert:

```cpp
// C3153.cpp
// compile with: /clr
interface class A {
};

int main() {
   A^ a = gcnew A;   // C3153
}
```
