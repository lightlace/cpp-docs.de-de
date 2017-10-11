---
title: Compilerfehler C2529 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2529
dev_langs:
- C++
helpviewer_keywords:
- C2529
ms.assetid: 73a99e55-b91e-488d-9b72-cc80faaeb436
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7c0a693af458818b8c5ac44e160272d8b15fa5f5
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2529"></a>Compilerfehler C2529
'Name': Verweis auf Verweis ist nicht zulässig  
  
 Dieser Fehler kann möglicherweise behoben werden, indem mithilfe der Zeigersyntax und das Deklarieren eines Verweises auf einen Zeiger.  
  
 Im folgende Beispiel wird C2529 generiert:  
  
```  
// C2529.cpp  
// compile with: /c  
int i;  
int &ri = i;  
int &(&rri) = ri;   // C2529  
```
