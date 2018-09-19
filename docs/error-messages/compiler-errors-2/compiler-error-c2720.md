---
title: Compilerfehler C2720 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2720
dev_langs:
- C++
helpviewer_keywords:
- C2720
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c2d75c9847016102d4ae8609fb0a0a78726e4c67
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084015"
---
# <a name="compiler-error-c2720"></a>Compilerfehler C2720

> "*Bezeichner*': '*Spezifizierer*" Speicherklassenspezifizierer für Elemente unzulässig

Die Speicherklasse kann für Klassenmember außerhalb der Variablendeklaration verwendet werden. Um diesen Fehler zu beheben, entfernen Sie den nicht benötigten [Speicherklasse](../../cpp/storage-classes-cpp.md) -Bezeichner aus der Definition des Members außerhalb der Klassendeklaration.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2720 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C2720.cpp
struct S {
   static int i;
};
static S::i;   // C2720 - remove the unneeded 'static' to fix it
```