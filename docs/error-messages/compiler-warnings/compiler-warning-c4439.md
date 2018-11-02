---
title: Compilerwarnung C4439
ms.date: 11/04/2016
f1_keywords:
- C4439
helpviewer_keywords:
- C4439
ms.assetid: 9449958f-f407-4824-829b-9e092f2af97d
ms.openlocfilehash: d604c234b9445a7e5304118124620f0057f30975
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541738"
---
# <a name="compiler-warning-c4439"></a>Compilerwarnung C4439

'Funktion': Funktionsdefinition mit einem verwalteten Typ in der Signatur muss eine __clrcall-Aufrufkonvention aufweisen

Der Compiler implizit ersetzt eine Aufrufkonvention mit [__clrcall](../../cpp/clrcall.md). Um diese Warnung zu beheben, entfernen die `__cdecl` oder `__stdcall` Aufrufkonvention.

C4439 wird immer als Fehler ausgegeben. Sie können diese Warnung mit Deaktivieren der `#pragma warning` oder **/WD**; finden Sie unter [Warnung](../../preprocessor/warning.md) oder  [ /w, / W0, / W1, / W2, / w3, / W4, / W1, / W2, / w3, / W4, / Wall, / WD, / we, / wo, / WV, / WX (Warnstufe)](../../build/reference/compiler-option-warning-level.md)für Weitere Informationen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4439 generiert.

```
// C4439.cpp
// compile with: /clr
void __stdcall f( System::String^ arg ) {}   // C4439
void __clrcall f2( System::String^ arg ) {}   // OK
void f3( System::String^ arg ) {}   // OK
```