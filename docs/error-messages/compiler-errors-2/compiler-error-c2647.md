---
title: Compiler-Fehler C2647 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2647
dev_langs:
- C++
helpviewer_keywords:
- C2647
ms.assetid: 1034589e-bc3e-41a6-831f-2a1a4b8a2500
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ca5de79746876a60cc9a64c4bf8f91e468b4d379
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2647"></a>Compiler-Fehler C2647 generiert
'Operator': 'Typ1' in 'Typ2' kann nicht dereferenziert werden.  
  
 Der linke Operand des einen Zeiger auf Member-Operator ( `->*` oder `.*` ) kann nicht implizit in einen Typ im Zusammenhang mit der rechten Operator konvertiert werden.  
  
 Im folgende Beispiel wird C2647 generiert:  
  
```  
// C2647.cpp  
class C {};  
class D {};  
  
int main() {  
   D d, *pd;  
   C c, *pc = 0;  
   int C::*pmc = 0;  
   pd->*pmc = 0;   // C2647  
   d.*pmc = 0;   // C2647  
  
   // OK  
   pc->*pmc = 0;  
   c.*pmc = 0;  
}  
```