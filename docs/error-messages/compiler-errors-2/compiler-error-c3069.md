---
title: Compiler-Fehler C3069 generiert | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3069
dev_langs:
- C++
helpviewer_keywords:
- C3069
ms.assetid: ca94291b-2bb4-4e3f-9acf-534234b83513
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: 6cb151dcb6f96ec897eea5cea126ed23f68d147c
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3069"></a>Compilerfehler C3069
"Operator": Für den Enumerationstyp nicht zulässig  
  
 Ein Operator wird für CLR-Enumerationen nicht unterstützt.  Weitere Informationen finden Sie unter [Gewusst wie: definieren und Verarbeiten von Enumerationen in C++ / CLI](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3069 generiert:  
  
```  
// C3069.cpp  
// compile with: /clr  
enum struct E { e1 };  
enum F { f1 };  
  
int main() {  
   E e = E::e1;  
   bool tf;  
   tf = !e;   // C3069  
  
   // supported for native enums  
   F f = f1;  
   tf = !f;  
}  
```
