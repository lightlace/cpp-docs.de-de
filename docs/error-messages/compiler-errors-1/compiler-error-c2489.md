---
title: Compilerfehler C2489 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2489
dev_langs:
- C++
helpviewer_keywords:
- C2489
ms.assetid: 67d8cd98-db7e-4f7f-86b4-4af7bc89ec8b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 633a15cfdc05ec2691570b5ecdd91eaf8af9ca78
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021381"
---
# <a name="compiler-error-c2489"></a>Compilerfehler C2489

"Bezeichner": Initialisierte automatische oder Registervariable im Gültigkeitsbereich der Funktion in "naked"-Funktion nicht zulässig

Weitere Informationen finden Sie unter [naked](../../cpp/naked-cpp.md).

Im folgende Beispiel wird die C2489 generiert:

```
// C2489.cpp
// processor: x86
__declspec( naked ) int func() {
   int i = 1;   // C2489
   register int j = 1;   // C2489
}
```