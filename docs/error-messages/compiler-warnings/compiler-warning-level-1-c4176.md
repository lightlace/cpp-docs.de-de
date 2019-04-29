---
title: Compilerwarnung (Stufe 1) C4176
ms.date: 11/04/2016
f1_keywords:
- C4176
helpviewer_keywords:
- C4176
ms.assetid: cfffb934-219a-4a63-9df6-ba54405bf766
ms.openlocfilehash: 44f2dea9b5f0afb5b97867f9137f420ad92c388a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391750"
---
# <a name="compiler-warning-level-1-c4176"></a>Compilerwarnung (Stufe 1) C4176

"Subcomponent": Unbekannte Unterkomponente bei #pragma component browser.

#pragma **component** enthält eine ungültige Unterkomponente. Um Verweise auf einen bestimmten Namen auszuschließen, müssen Sie die Option **references** vor dem Namen verwenden.

## <a name="example"></a>Beispiel

```
// C4176.cpp
// compile with: /W1 /LD
#pragma component(browser, off, i)  // C4176
#pragma component(browser, off, references, i) // ok
```