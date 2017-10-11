---
title: Compilerfehler C3288 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3288
dev_langs:
- C++
helpviewer_keywords:
- C3288
ms.assetid: ed08a540-9751-46e1-9cbe-c51d6a49ffab
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9030ad9f46a36a1879d1c0f4f97b772e893b37ab
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3288"></a>Compilerfehler C3288
'Typ': unzulässige Dereferenzierung eines Handletyps  
  
 Der Compiler hat eine ungültige Dereferenzierung eines Handletyps erkannt. Sie können einen Handletyp dereferenzieren und einen Verweis zuweisen. Weitere Informationen finden Sie unter [Verweisoperator nachverfolgen](../../windows/tracking-reference-operator-cpp-component-extensions.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3288 generiert.  
  
```  
// C3288.cpp  
// compile with: /clr  
ref class R {};  
int main() {  
   *(System::Object^) nullptr;   // C3288  
  
// OK  
   (System::Object^) nullptr;   // OK  
   R^ r;  
   R% pr = *r;  
}  
```
