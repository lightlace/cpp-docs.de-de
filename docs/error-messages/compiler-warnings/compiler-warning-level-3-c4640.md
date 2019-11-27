---
title: Compilerwarnung (Stufe 3) C4640
ms.date: 11/04/2016
f1_keywords:
- C4640
helpviewer_keywords:
- C4640
ms.assetid: f76871f6-e436-4c35-9793-d2f22f7e1c7f
ms.openlocfilehash: 1bd983f1fcc4248910c5eeafd4dea30106083d05
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2019
ms.locfileid: "74189108"
---
# <a name="compiler-warning-level-3-c4640"></a>Compilerwarnung (Stufe 3) C4640

' instance ': die Konstruktion des lokalen statischen Objekts ist nicht Thread sicher.

Eine statische Instanz eines Objekts ist nicht Thread sicher.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Im folgenden Beispiel wird C4640 generiert:

```cpp
// C4640.cpp
// compile with: /W3
#pragma warning(default:4640)

class X {
public:
   X() {
   }
};

void f() {
   static X aX;   // C4640
}

int main() {
   f();
}
```