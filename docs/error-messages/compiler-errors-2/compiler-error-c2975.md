---
title: Compilerfehler C2975 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2975
dev_langs:
- C++
helpviewer_keywords:
- C2975
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 53cb020dc0d456f10b7cfbae82a16b2ebe5fda6b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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

C2975 tritt auch bei Verwendung von &#95; &#95;Zeile&#95; &#95; als eine Kompilierzeitkonstante mit [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md). Eine Lösung wäre die Kompilierung mit [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) anstelle von **/Zi**.

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