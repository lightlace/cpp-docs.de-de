---
title: Compilerwarnung C4394 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4394
dev_langs:
- C++
helpviewer_keywords:
- C4394
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 05535621443770a2b414f1c4312efbc46e6be858
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276220"
---
# <a name="compiler-warning-c4394"></a>Compilerwarnung C4394
'Funktion': Ein anwendungsdomänenspezifisches Symbol sollte nicht mit __declspec(dllexport) markiert werden  
  
 Eine Funktion mit markiert die [Appdomain](../../cpp/appdomain.md) `__declspec` Modifizierer ist zu MSIL kompiliert (nicht zu systemeigen), und Exporttabellen ([exportieren](../../windows/export.md) `__declspec` Modifizierer) werden für verwaltete Funktionen nicht unterstützt.  
  
 Sie können eine verwaltete Funktion mit öffentlicher Zugriffsmöglichkeit deklarieren. Weitere Informationen finden Sie unter [geben Sichtbarkeit](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) und [membersichtbarkeit](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility).  
  
 C4394 wird immer als Fehler ausgegeben.  Sie können diese Warnung mit Deaktivieren der `#pragma warning` oder **/WD**; finden Sie unter [Warnung](../../preprocessor/warning.md) oder  [ /w, / W0, /W1, /W2, /W3, / W4, /w1, /w2, /w3, / W4, / Wall, / WD, / we, /, wo WV, / WX (Warnstufe)](../../build/reference/compiler-option-warning-level.md)für Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4394 generiert.  
  
```  
// C4394.cpp  
// compile with: /clr /c  
__declspec(dllexport) __declspec(appdomain) int g1 = 0;   // C4394  
__declspec(dllexport) int g2 = 0;   // OK  
```