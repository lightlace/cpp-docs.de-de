---
title: Compilerfehler C2101 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2101
dev_langs:
- C++
helpviewer_keywords:
- C2101
ms.assetid: 42f0136f-8cc1-4f2b-be1c-721ec9278e66
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 035b0d70a75652edb5ba01357076ba9942acdfae
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2101"></a>Compilerfehler C2101
"&" auf Konstante  
  
 Der address-of-Operator ( `&` ) muss einen l-Wert als Operanden haben.  
  
 Im folgenden Beispiel wird C2101 generiert:  
  
```  
// C2101.cpp  
int main() {  
   char test;  
   test = &'a';   // C2101  
   test = 'a';   // OK  
}  
```
