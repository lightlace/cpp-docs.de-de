---
title: Compilerfehler C3467 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3467
dev_langs:
- C++
helpviewer_keywords:
- C3467
ms.assetid: e2b844d0-4920-412f-99fd-cd8051c4aa41
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e14104c0fe67ce371f2faf5debb4a07f0c938856
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3467"></a>Compilerfehler C3467
'typ': Dieser Typ wurde bereits weitergeleitet.  
  
 Der Compiler hat mehr als eine Vorwärts-Typdeklaration für den gleichen Typ gefunden. Es ist nur eine Deklaration pro Typ zulässig.  
  
 Weitere Informationen finden Sie unter [Typweiterleitung (C + c++ / CLI)](../../windows/type-forwarding-cpp-cli.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Komponente erstellt:  
  
```  
// C3467.cpp  
// compile with: /LD /clr  
public ref class R {};  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3467 generiert:  
  
```  
// C3467_b.cpp  
// compile with: /clr /c  
#using "C3467.dll"  
[ assembly:TypeForwardedTo(R::typeid) ];  
[ assembly:TypeForwardedTo(R::typeid) ];   // C3467  
```
