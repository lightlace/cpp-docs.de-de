---
title: Compilerfehler Fehler C2088 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2088
dev_langs:
- C++
helpviewer_keywords:
- C2088
ms.assetid: b93f7094-185b-423d-8bb9-507cd757dbf5
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a8c99d25995baf6285fe77761c7a054a0512bdfc
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2088"></a>Compilerfehler Fehler C2088
'Operator': Unzulässiger für "Klassenschlüssel"  
  
 Der Operator wurde für die Struktur oder Union nicht definiert. Dieser Fehler gilt nur für C#-Code.  
  
 Im folgende Beispiel wird dreimal C2088 generiert:  
  
```  
// C2088.c  
struct S {  
   int m_i;   
} s;  
  
int main() {  
   int i = s * 1;   // C2088  
   struct S s2 = +s;   // C2088  
   s++;   // C2088  
}  
```
