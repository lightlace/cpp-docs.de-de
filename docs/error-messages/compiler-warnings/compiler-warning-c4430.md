---
title: Compilerwarnung C4430
ms.date: 11/04/2016
f1_keywords:
- C4430
helpviewer_keywords:
- C4430
ms.assetid: 12efbfff-aa58-4a86-a7d6-2c6a12d01dd3
ms.openlocfilehash: 661b687373d6c72b9f40a05d1406bc89ce332133
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73623704"
---
# <a name="compiler-warning-c4430"></a>Compilerwarnung C4430

Fehlender Typspezifizierer - int wird angenommen. Hinweis: C++ "default-int" wird von nicht unterstützt

Dieser Fehler kann als Ergebnis einer compilerübereinstimmungs-Arbeit generiert werden, die für Visual Studio 2005 durchgeführt wurde: alle Deklarationen müssen explizit den Typ angeben. "int" wird nicht mehr angenommen.

C4430 wird immer als Fehler ausgegeben.  Sie können diese Warnung mit dem `#pragma warning` oder **/WD**deaktivieren. Weitere Informationen finden Sie unter [Warning](../../preprocessor/warning.md) or [/w,/W0,/W1,/W2,/w3,/W4,/W1,/W2,/w3,/W4,/Wall,/WD,/We,/wo,/WV,/WX (Warnstufe)](../../build/reference/compiler-option-warning-level.md) .

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4430 generiert.

```cpp
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