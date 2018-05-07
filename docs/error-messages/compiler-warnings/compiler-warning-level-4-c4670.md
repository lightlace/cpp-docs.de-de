---
title: Compilerwarnung (Stufe 4) C4670 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4670
dev_langs:
- C++
helpviewer_keywords:
- C4670
ms.assetid: e172b134-b1fb-4dfe-8e9d-209ea08b73c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9bec30fff715984073aa3061979fff11923f0bf8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4670"></a>Compilerwarnung (Stufe 4) C4670
'bezeichner': Auf diese Basisklasse kann nicht zugegriffen werden.  
  
 Auf die angegebene Klasse eines Objekts, das in einem **try** -Block ausgelöst werden soll, kann nicht zugegriffen werden. Das Objekt kann nicht instanziiert werden, wenn es ausgelöst wird. Überprüfen Sie, ob die Basisklasse mit dem richtigen Zugriffsspezifizierer geerbt wird.  
  
 Im folgenden Beispiel wird C4670 generiert.  
  
```  
// C4670.cpp  
// compile with: /EHsc /W4  
class A  
{  
};  
  
class B : /* public */ A  
{  
} b;   // inherits A with private access by default  
  
int main()  
{  
    try  
    {  
       throw b;   // C4670  
    }  
    catch( B )  
    {  
    }  
}  
```