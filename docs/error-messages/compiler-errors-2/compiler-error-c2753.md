---
title: Compilerfehler C2753 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2753
dev_langs:
- C++
helpviewer_keywords:
- C2753
ms.assetid: 92bfeeac-524a-4a8e-9a4f-fb8269055826
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 722176744dc614e54d7b25ffd75be679ef9e63dc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060584"
---
# <a name="compiler-error-c2753"></a>Compilerfehler C2753

"*Vorlage*": teilweiser Spezialisierung darf nicht mit der Argumentliste für die primäre Vorlage übereinstimmen

Wenn die Vorlagenargumentliste die Parameterliste entspricht, behandelt der Compiler ihn als die gleiche Vorlage an. Definieren die gleiche Vorlage zweimal ist nicht zulässig.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2753 generiert und zeigt, wie Sie diesen Fehler beheben:

```cpp
// C2753.cpp
// compile with: cl /c C2753.cpp
template<class T>
struct A {};

template<class T>
struct A<T> {};   // C2753
// try the following line instead
// struct A<int> {};

template<class T, class U, class V, class W, class X>
struct B {};
```