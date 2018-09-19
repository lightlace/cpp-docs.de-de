---
title: Compilerfehler C2868 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2868
dev_langs:
- C++
helpviewer_keywords:
- C2868
ms.assetid: 6ff5837b-e66d-44d1-9d17-80af35e08d08
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2de22b34f9dc564ef89d7776af86718af70d51eb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037865"
---
# <a name="compiler-error-c2868"></a>Compilerfehler C2868

> "*Bezeichner*": Unzulässige Syntax für using-Deklaration; vollständiger Name erwartet

Ein [using-Deklaration](../../cpp/using-declaration.md) erfordert eine *qualifizierten Namen*, einen Bereichsoperator (`::`) getrennte Sequenz mit Namespace, Klasse oder eines Enumerationswerts-Namen, die mit den Namen des Bezeichners endet. Ein einzelnes Bereichsauflösungsoperator kann verwendet werden, um einen Namen aus dem globalen Namespace einzuführen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2868 generiert und zeigt auch die richtige Verwendung:

```cpp
// C2868.cpp
class X {
public:
   int i;
};

class Y : X {
public:
   using X::i;   // OK
};

int main() {
   using X;   // C2868
}
```