---
title: Compilerfehler C2781
ms.date: 11/04/2016
f1_keywords:
- C2781
helpviewer_keywords:
- C2781
ms.assetid: f29b9963-f55b-427c-8db6-50f37713df5a
ms.openlocfilehash: be665d86cf230c364f522fd1ad74cd5a124ac9de
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558963"
---
# <a name="compiler-error-c2781"></a>Compilerfehler C2781

'Declaration': erwartet zumindest value1-Argument - Wert2 unterstützt

Eine Funktionsvorlage mit einer Liste variabler Parameter weist zu wenige Argumente auf.

Im folgende Beispiel wird die C2781 generiert:

```
// C2781.cpp
template<typename T>
void f(T, T, ...){}

int main() {
   f(1);   // C2781

   // try the following line instead
   f(1,1);
}
```