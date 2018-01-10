---
title: Compilerfehler C3063 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3063
dev_langs: C++
helpviewer_keywords: C3063
ms.assetid: 0ecf6f1f-e4a7-487a-9fd5-79d8ac470001
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 764cebae9e95992ba3d5ffa1773af4802c489392
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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