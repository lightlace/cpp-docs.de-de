---
title: Compilerwarnung (Stufe 4) C4204 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4204
dev_langs:
- C++
helpviewer_keywords:
- C4204
ms.assetid: 298d2880-6737-448e-b711-15572d540200
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a803c81ea0f2fd6ce4b5a8f26eb626e89a32a9b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293217"
---
# <a name="compiler-warning-level-4-c4204"></a>Compilerwarnung (Stufe 4) C4204
nicht dem Standard entsprechende Erweiterung: aggregierter Initialisierer für nicht-Konstante  
  
 Mit Microsoft-Erweiterungen (/ Ze) können Sie Aggregattypen (Arrays, Strukturen, Unions und Klassen) mit den Werten initialisieren, die nicht Konstanten sind.  
  
## <a name="example"></a>Beispiel  
  
```  
// C4204.c  
// compile with: /W4  
int func1()  
{  
   return 0;  
}  
struct S1  
{  
   int i;  
};  
  
int main()  
{  
   struct S1 s1 = { func1() };   // C4204  
   return s1.i;  
}  
```  
  
 Solche Initialisierungen sind ungültig, ANSI-Kompatibilität (["/ Za"](../../build/reference/za-ze-disable-language-extensions.md)).