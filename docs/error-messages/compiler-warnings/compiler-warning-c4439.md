---
title: Compilerwarnung C4439
ms.date: 11/04/2016
f1_keywords:
- C4439
helpviewer_keywords:
- C4439
ms.assetid: 9449958f-f407-4824-829b-9e092f2af97d
ms.openlocfilehash: 7cab2e55fca640438051fbb79ac933e83d5f3cbb
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73623654"
---
# <a name="compiler-warning-c4439"></a>Compilerwarnung C4439

"Function": eine Funktionsdefinition mit einem verwalteten Typ in der Signatur muss eine __clrcall-Aufruf Konvention aufweisen.

Der Compiler hat implizit eine Aufruf Konvention durch [__clrcall](../../cpp/clrcall.md)ersetzt. Entfernen Sie die `__cdecl` oder `__stdcall` Aufruf Konvention, um diese Warnung zu beheben.

C4439 wird immer als Fehler ausgegeben. Sie können diese Warnung mit dem `#pragma warning` oder **/WD**deaktivieren. Weitere Informationen finden Sie unter [Warning](../../preprocessor/warning.md) or [/w,/W0,/W1,/W2,/w3,/W4,/W1,/W2,/w3,/W4,/Wall,/WD,/We,/wo,/WV,/WX (Warnstufe)](../../build/reference/compiler-option-warning-level.md) .

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4439 generiert.

```cpp
// C4439.cpp
// compile with: /clr
void __stdcall f( System::String^ arg ) {}   // C4439
void __clrcall f2( System::String^ arg ) {}   // OK
void f3( System::String^ arg ) {}   // OK
```