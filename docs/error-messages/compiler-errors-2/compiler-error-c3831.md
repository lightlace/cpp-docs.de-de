---
title: Compilerfehler C3831 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3831
dev_langs:
- C++
helpviewer_keywords:
- C3831
ms.assetid: a125d8dc-b75a-4ea0-b6c7-fe7b119dba25
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 27b330e82c952bd02de7499e8dffe548acfe819c
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3831"></a>Compilerfehler C3831
'Member': 'Class' sind keine festen Datenmember oder eine Memberfunktion, die einen festen Zeiger zurückgibt  
  
 [Pin_ptr (C + c++ / CLI)](../../windows/pin-ptr-cpp-cli.md) wurde falsch verwendet.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3831 generiert:  
  
```  
// C3831a.cpp  
// compile with: /clr  
ref class Y  
{  
public:  
   int i;  
};  
  
ref class X  
{  
   pin_ptr<int> mbr_Y;   // C3831  
   int^ mbr_Y2;   // OK  
};  
  
int main() {  
   Y y;  
   pin_ptr<int> p = &y.i;  
}  
```  

