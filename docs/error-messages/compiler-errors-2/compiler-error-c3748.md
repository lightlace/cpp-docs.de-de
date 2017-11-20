---
title: Compilerfehler C3748 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3748
dev_langs:
- C++
helpviewer_keywords:
- C3748
ms.assetid: 6fe71a0a-dd93-4ce6-9729-b9616360cf34
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 678fdb112114e7e6fa8aff148af488a17952fa47
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3748"></a>Compilerfehler C3748
'Schnittstelle': verwaltete Schnittstellen können keine Ereignisse auslösen  
  
 Die [__event](../../cpp/event.md) Schlüsselwort kann nicht innerhalb einer Schnittstelle verwendet werden.  
  
 Im folgende Beispiel wird C3748 generiert:  
  
```  
// C3748.cpp  
__interface I {  
// try the following line instead  
// struct I {  
   __event void f();   // C3748  
};  
  
int main() {  
}  
```