---
title: Compilerfehler C2528 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2528
dev_langs:
- C++
helpviewer_keywords:
- C2528
ms.assetid: 2ea9d583-67a8-4b16-b35f-a50eeffc03c4
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: df8179dbf51f329d12420593f187aad37d76564e
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2528"></a>Compilerfehler C2528
'Name': Zeiger auf Verweis ist nicht zulässig  
  
 Einen Zeiger auf einen Verweis nicht deklariert werden. Die Variable vor dem Deklarieren eines Zeigers, dereferenziert werden.  
  
 Im folgende Beispiel wird C2528 generiert:  
  
```  
// C2528.cpp  
int i;  
int &ir = i;  
int & (*irptr) = ir;    // C2528  
```
