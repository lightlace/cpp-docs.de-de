---
title: Compilerfehler Fehler C2050 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2050
dev_langs:
- C++
helpviewer_keywords:
- C2050
ms.assetid: 66aaed7d-00db-4ce1-a9d6-4447c1cf07ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 70e8f66742cc08880bbcd7c93441d98eb1b9ca4a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2050"></a>Compilerfehler Fehler C2050
nicht ganzzahlige Schalterausdruck  
  
 Die `switch` Ausdruck ausgewertet wird, auf einen nicht ganzzahligen Wert. Verwenden Sie nur ganzzahlige Werte in Switch-Anweisungen, um den Fehler zu beheben.  
  
 Im folgenden Beispiel wird C2050 generiert:  
  
```  
// C2050.cpp  
int main() {  
   int a = 1;  
   switch ("a") {   // C2050  
      case 1:  
         a = 0;  
      default:  
         a = 2;  
   }  
}  
```  
  
 Mögliche Lösung:  
  
```  
// C2050b.cpp  
int main() {  
   int a = 1;  
   switch (a) {  
      case 1:  
         a = 0;  
      default:  
         a = 2;  
   }  
}  
```