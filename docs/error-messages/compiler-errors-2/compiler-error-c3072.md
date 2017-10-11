---
title: Compilerfehler C3072 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3072
dev_langs:
- C++
helpviewer_keywords:
- C3072
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3334edd6f297a61ca62a5fe5a0f8b6cddfef7f80
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3072"></a>Compilerfehler C3072
Operator "Operator" kann nicht mit einer Instanz einer Verweisklasse angewendet werden  
  
 Verwenden Sie die unären "`operator` " Operator, um eine Instanz einer Verweisklasse in einen Handletyp konvertieren  
  
 Ein CLR-Typ erfordert CLR-Operatoren, keine systemeigenen (oder Standard-)-Operatoren.  Weitere Informationen finden Sie unter [Verweisoperator nachverfolgen](../../windows/tracking-reference-operator-cpp-component-extensions.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3072 generiert.  
  
```  
// C3072.cpp  
// compile with: /clr  
ref class R {};  
  
int main() {  
   R r1;  
   R^ r2 = &r1;   // C3072  
   R^ r3 = %r1;   // OK  
}  
```
