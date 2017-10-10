---
title: Compilerfehler C2141 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2141
dev_langs:
- C++
helpviewer_keywords:
- C2141
ms.assetid: 10cf770f-0500-4220-ac90-a863b7ea5fe6
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 641e8cec02ced5bb61f60932fb90a2dc2c4afea0
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2141"></a>Compilerfehler C2141
Überlauf der Array-Größe  
  
 Ein Array überschreitet das Limit von 2GB. Reduzieren Sie die Größe des Arrays.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2141 generiert.  
  
```  
// C2141.cpp  
// processor: IPF  
class A {  
   short m_n;  
};  
  
int main()  
{  
   A* pA = (A*)(-1);  
   pA = new A[0x8000000000000001];   // C2141  
  
   A* pA2 = (A*)(-1);  
   pA2 = new A[0x80000000000000F];   // OK  
}  
```
