---
title: Compilerfehler C3669
ms.date: 11/04/2016
f1_keywords:
- C3669
helpviewer_keywords:
- C3669
ms.assetid: be9c7ae4-e96f-47ab-922a-39a3537d5ca6
ms.openlocfilehash: c2e92fec7c3faeda80bf7f0be3caa33e5d78295b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50550279"
---
# <a name="compiler-error-c3669"></a>Compilerfehler C3669

'Member': Der Überschreibungsspezifizierer "override" ist für statische Memberfunktionen oder Konstruktoren nicht zulässig

Eine Überschreibung wurde falsch angegeben. Weitere Informationen finden Sie unter [explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3669 generiert.

```
// C3669.cpp
// compile with: /clr
public ref struct R {
   R() override {}   // C3669
};
```