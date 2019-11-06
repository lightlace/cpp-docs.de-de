---
title: Compilerwarnung (Stufe 1) C4080
ms.date: 11/04/2016
f1_keywords:
- C4080
helpviewer_keywords:
- C4080
ms.assetid: 964fb3f4-b9fd-450b-aa23-35cece126172
ms.openlocfilehash: 5ecc50d4f967826cca691fae4f119c1dee2efef5
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626892"
---
# <a name="compiler-warning-level-1-c4080"></a>Compilerwarnung (Stufe 1) C4080

Bezeichner für Segmentnamen erwartet; "Symbol" gefunden

Der Name des Segments in [#pragma alloc_text](../../preprocessor/alloc-text.md) muss eine Zeichenfolge oder ein Bezeichner sein. Der Compiler ignoriert das Pragma, wenn kein gültiger Bezeichner gefunden wurde.

Im folgenden Beispiel wird C4080 generiert:

```cpp
// C4080.cpp
// compile with: /W1
extern "C" void func(void);

#pragma alloc_text()   // C4080

// try this line to resolve the warning
// #pragma alloc_text("mysection", func)

int main() {
}

void func(void) {
}
```