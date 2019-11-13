---
title: Compilerwarnung (Stufe 1) C4684
ms.date: 11/04/2016
f1_keywords:
- C4684
helpviewer_keywords:
- C4684
ms.assetid: e95f1a83-2784-4b05-ae94-12148e056e26
ms.openlocfilehash: f6ce86cc297a6529d58573f3e7d906f51771013b
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052517"
---
# <a name="compiler-warning-level-1-c4684"></a>Compilerwarnung (Stufe 1) C4684

' Attribut ': Warnung! das Attribut kann eine ungültige Codegenerierung verursachen: Verwendung mit Vorsicht.

Sie haben ein Attribut verwendet, das nicht häufig verwendet werden sollte.

Im folgenden Beispiel wird C4684 generiert:

```cpp
// C4684.cpp
// compile with: /W1 /LD
[module(name="xx")]; // C4684 expected
[no_injected_text];
```