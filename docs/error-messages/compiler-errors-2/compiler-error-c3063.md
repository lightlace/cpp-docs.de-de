---
title: Compilerfehler C3063 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3063
dev_langs:
- C++
helpviewer_keywords:
- C3063
ms.assetid: 0ecf6f1f-e4a7-487a-9fd5-79d8ac470001
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 26d30e56c3e694b39f583b29d8bd378b6dcaee0f
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3063"></a>Compilerfehler C3063
Operator "Operator": alle Operanden müssen den gleichen Enumerationstyp aufweisen  
  
Bei Verwendung von Operatoren für Enumeratoren müssen beide Operanden des Enumerationstyps sein. Weitere Informationen finden Sie unter [wie: definieren und Verarbeiten von Enumerationen in c++ / CLI](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md).  
  
## <a name="example"></a>Beispiel  
Im folgende Beispiel wird C3063 generiert und gezeigt, wie sie diesen Fehler beheben:  
  
```  
// C3063.cpp  
// compile with: /clr  
enum class E { a, b } e, mask;  
int main() {  
   if ( ( e & mask ) != 0 ) ;   // C3063 no operator!= (E, int)  
  
   if ( ( e & mask ) != E() )   // OK  
      ;  
}  
```
