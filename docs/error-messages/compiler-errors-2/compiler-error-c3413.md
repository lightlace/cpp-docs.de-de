---
title: Compilerfehler C3413 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3413
dev_langs:
- C++
helpviewer_keywords:
- C3413
ms.assetid: de6c9b05-c373-4bd8-8cb0-12c2cd2e5674
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1403c65b0eac3879cbbcd612b077d4b4b3937b49
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3413"></a>Compilerfehler C3413
'name': Ungültige explizite Instanziierung  
  
 Der Compiler hat eine explizite Instanziierung in einem ungültigen Format erkannt.  
  
 Im folgenden Beispiel wird C3413 generiert:  
  
```  
// C3413.cpp  
template  
class MyClass {};   // C3413  
```  
  
 Mögliche Lösung:  
  
```  
// C3413b.cpp  
// compile with: /c  
template <class T>  
class MyClass {};  
  
template <>  
class MyClass<int> {};  
```
