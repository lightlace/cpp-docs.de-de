---
title: Compilerfehler C3063 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3063
dev_langs:
- C++
helpviewer_keywords:
- C3063
ms.assetid: 0ecf6f1f-e4a7-487a-9fd5-79d8ac470001
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 68809002b2c895387cd10d33615ec9d6c7a6b861
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33248979"
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