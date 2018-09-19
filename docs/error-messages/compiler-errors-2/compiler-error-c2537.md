---
title: Compilerfehler C2537 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2537
dev_langs:
- C++
helpviewer_keywords:
- C2537
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65db4fa66d147cc46c1a6013d07048892dfa0800
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136022"
---
# <a name="compiler-error-c2537"></a>Compilerfehler C2537

"Spezifizierer": Unzulässige Angabe für Bindung

Mögliche Ursachen:

1. Der Bindungsspezifizierer wird nicht unterstützt. Nur der Bindungsspezifizierer "C" wird unterstützt.

1. "C"-Verknüpfung ist für mehr als eine Funktion in einem Satz von überladenen Funktionen angegeben. Dies ist nicht zulässig.

Im folgende Beispiel wird die C2537 generiert:

```
// C2537.cpp
// compile with: /c
extern "c" void func();   // C2537
extern "C" void func2();   // OK
```