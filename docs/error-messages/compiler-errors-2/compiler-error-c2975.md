---
title: Compilerfehler C2975 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2975
dev_langs:
- C++
helpviewer_keywords:
- C2975
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f779ec2623b6b07f61c1e8347304288d0bcfe96a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2975"></a>Compilerfehler C2975

> "*Argument*': Ungültiges Vorlagenargument für '*Typ*", Kompilierzeit konstanter Ausdruck erwartet

Das Vorlagenargument entspricht nicht der Vorlagendeklaration; Ein konstanter Ausdruck sollte in die spitzen Klammern angezeigt werden. Variablen werden als tatsächliche Vorlagenargumente nicht zulässig. Überprüfen Sie die Vorlagendefinition, um die richtigen Typen zu ermitteln.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2975 generiert und zeigt außerdem die richtige Verwendung:

```cpp
// C2975.cpp
template<int I>
class X {};

int main() {
   int i = 4, j = 2;
   X<i + j> x1;   // C2975
   X<6> x2;   // OK
}
```

C2975 tritt auch bei Verwendung von &#95; &#95; LINE #95; &#95; als eine Kompilierzeitkonstante mit [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md). Eine Lösung wäre die Kompilierung mit [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) anstelle von **/Zi**.

```cpp
// C2975b.cpp
// compile with: /ZI
// processor: x86
template<long line>
void test(void) {}

int main() {
   test<__LINE__>();   // C2975
}
```