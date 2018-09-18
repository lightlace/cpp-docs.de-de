---
title: Compilerfehler C3628 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3628
dev_langs:
- C++
helpviewer_keywords:
- C3628
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a65dc33c5381b063c3adb01072e930075108649
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037371"
---
# <a name="compiler-error-c3628"></a>Compilerfehler C3628

'base Class': verwaltete oder WinRTclasses unterstützen nur öffentliche Vererbung

Es wurde versucht, mit einer verwalteten oder WinRT Klasse als eine [private](../../cpp/private-cpp.md) oder [geschützt](../../cpp/protected-cpp.md) Basisklasse. Eine verwaltete oder WinRT-Klasse kann nur verwendet werden, als eine Basisklasse mit [öffentliche](../../cpp/public-cpp.md) Zugriff.

Im folgenden Beispiel wird C3628 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C3628a.cpp
// compile with: /clr
ref class B {
};

ref class D : private B {   // C3628

// The following line resolves the error.
// ref class D : public B {
};

int main() {
}
```
