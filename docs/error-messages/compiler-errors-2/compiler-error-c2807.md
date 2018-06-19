---
title: Compilerfehler C2807 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2807
dev_langs:
- C++
helpviewer_keywords:
- C2807
ms.assetid: bd7a207a-f379-4de6-8ee8-c7cab78b3480
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 538cdfe6ce8c199a213077e26c16fce65e55b9b4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33237015"
---
# <a name="compiler-error-c2807"></a>Compilerfehler C2807
der zweite formale Parameter für die postfix-'Operator Operator' muss 'Int' sein.  
  
 Der zweite Parameter für ein Postfix-Operator hat den falschen Typ.  
  
 Im folgende Beispiel wird C2807 generiert:  
  
```  
// C2807.cpp  
// compile with: /c  
class X {  
public:  
   X operator++ ( X );   // C2807 nonvoid parameter  
   X operator++ ( int );   // OK, int parameter  
};  
```