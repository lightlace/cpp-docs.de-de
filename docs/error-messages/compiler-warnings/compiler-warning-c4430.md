---
title: Compilerwarnung C4430 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4430
dev_langs:
- C++
helpviewer_keywords:
- C4430
ms.assetid: 12efbfff-aa58-4a86-a7d6-2c6a12d01dd3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 311c75ed1fcacdf8b40f096a759d669c9331c2ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-c4430"></a>Compilerwarnung C4430
Fehlender Typspezifizierer - int wird angenommen. Hinweis: C++ unterstützt keine Standard-int  
  
 Dieser Fehler kann infolge einer konformitätsverbesserung für Visual C++ 2005 erstellt wurde, die generiert werden: alle Deklarationen müssen den Typ explizit angeben Int wird nicht mehr angenommen.  
  
 C4430 wird immer als Fehler ausgegeben.  Sie können diese Warnung mit Deaktivieren der `#pragma warning` oder **/WD**; finden Sie unter [Warnung](../../preprocessor/warning.md) oder  [ /w, / W0, /W1, /W2, /W3, / W4, /w1, /w2, /w3, / W4, / Wall, / WD, / we, /, wo WV, / WX (Warnstufe)](../../build/reference/compiler-option-warning-level.md)für Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4430 generiert.  
  
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