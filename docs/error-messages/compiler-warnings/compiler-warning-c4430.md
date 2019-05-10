---
title: Compilerwarnung C4430
ms.date: 11/04/2016
f1_keywords:
- C4430
helpviewer_keywords:
- C4430
ms.assetid: 12efbfff-aa58-4a86-a7d6-2c6a12d01dd3
ms.openlocfilehash: fe765fa49b9aa11667e1eac4a9cfed54bb84fd8f
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447863"
---
# <a name="compiler-warning-c4430"></a>Compilerwarnung C4430

Fehlender Typspezifizierer - int wird angenommen. Hinweis: C++ unterstützt nicht die Standard-int

Dieser Fehler kann infolge einer konformitätsverbesserung für Compiler, die für Visual Studio 2005 durchgeführt wurde generiert werden: alle Deklarationen müssen explizit den Typ angeben Int wird nicht mehr angenommen.

C4430 wird immer als Fehler ausgegeben.  Sie können diese Warnung mit Deaktivieren der `#pragma warning` oder **/WD**; finden Sie unter [Warnung](../../preprocessor/warning.md) oder  [ /w, / W0, / W1, / W2, / w3, / W4, / W1, / W2, / w3, / W4, / Wall, / WD, / we, / wo, / WV, / WX (Warnstufe)](../../build/reference/compiler-option-warning-level.md)für Weitere Informationen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4430 generiert.

```
// C4430.cpp
// compile with: /c
struct CMyClass {
   CUndeclared m_myClass;  // C4430
   int m_myClass;  // OK
};

typedef struct {
   POINT();   // C4430
   // try the following line instead
   // int POINT();
   unsigned x;
   unsigned y;
} POINT;
```