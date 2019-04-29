---
title: Compilerwarnung C4394
ms.date: 11/04/2016
f1_keywords:
- C4394
helpviewer_keywords:
- C4394
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
ms.openlocfilehash: 00c9e139e920473590389c05f076a7cd91a4fb8d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311474"
---
# <a name="compiler-warning-c4394"></a>Compilerwarnung C4394

'Funktion': Ein anwendungsdomänenspezifisches Symbol sollte nicht mit __declspec(dllexport) markiert werden

Eine Funktion mit markiert die [Appdomain](../../cpp/appdomain.md) `__declspec` Modifizierer wird zu MSIL kompiliert (nicht zu systemeigen), und Exporttabellen ([exportieren](../../windows/export.md) `__declspec` Modifizierer) werden für verwaltete Funktionen nicht unterstützt.

Sie können eine verwaltete Funktion mit öffentlicher Zugriffsmöglichkeit deklarieren. Weitere Informationen finden Sie unter [geben Sichtbarkeit](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) und [membersichtbarkeit](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility).

C4394 wird immer als Fehler ausgegeben.  Sie können diese Warnung mit Deaktivieren der `#pragma warning` oder **/WD**; finden Sie unter [Warnung](../../preprocessor/warning.md) oder  [ /w, / W0, / W1, / W2, / w3, / W4, / W1, / W2, / w3, / W4, / Wall, / WD, / we, / wo, / WV, / WX (Warnstufe)](../../build/reference/compiler-option-warning-level.md)für Weitere Informationen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4394 generiert.

```
// C4394.cpp
// compile with: /clr /c
__declspec(dllexport) __declspec(appdomain) int g1 = 0;   // C4394
__declspec(dllexport) int g2 = 0;   // OK
```