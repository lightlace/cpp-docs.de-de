---
title: Compilerwarnung (Stufe 1) C4584 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4584
dev_langs:
- C++
helpviewer_keywords:
- C4584
ms.assetid: ad86582f-cb8c-4d21-8c4c-a6c800059e25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9db97bf35034f7ca628f860924bfb9a1fccc942f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036253"
---
# <a name="compiler-warning-level-1-c4584"></a>Compilerwarnung (Stufe 1) C4584

'Klasse1': Base-Klasse 'Klasse2' ist bereits eine Basisklasse von "class3"

Die Klasse, die Sie definiert erbt von zwei Klassen, von denen aus den anderen erbt. Zum Beispiel:

```
// C4584.cpp
// compile with: /W1 /LD
class A {
};

class B : public A {
};

class C : public A, public B { // C4584
};
```

In diesem Fall würde eine Warnung für Klasse C ausgegeben werden, weil es erbt sowohl von Klasse A und B, die auch von Klasse a erbt-Klasse Diese Warnung dient als Erinnerung, Sie die Verwendung von Membern, die von diesen Basisklassen vollständig qualifizieren müssen oder aufgrund der Mehrdeutigkeit bezüglich der, die Klassenmember Sie finden ein Compilerfehler generiert werden.