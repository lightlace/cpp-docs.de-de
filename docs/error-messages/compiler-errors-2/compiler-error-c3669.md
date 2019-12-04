---
title: Compilerfehler C3669
ms.date: 11/04/2016
f1_keywords:
- C3669
helpviewer_keywords:
- C3669
ms.assetid: be9c7ae4-e96f-47ab-922a-39a3537d5ca6
ms.openlocfilehash: 560f4e8ef39e265f20d3c119858ff06b463d9841
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758137"
---
# <a name="compiler-error-c3669"></a>Compilerfehler C3669

"Member": der Überschreibungsspezifizierer "override" ist für statische Element Funktionen oder Konstruktoren nicht zulässig.

Eine außer Kraft Setzung wurde falsch angegeben. Weitere Informationen finden Sie unter [explizite über](../../extensions/explicit-overrides-cpp-component-extensions.md)schreibungen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3669 generiert.

```cpp
// C3669.cpp
// compile with: /clr
public ref struct R {
   R() override {}   // C3669
};
```
