---
title: Compiler-Fehler C2634 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2634
dev_langs:
- C++
helpviewer_keywords:
- C2634
ms.assetid: 58c8f2db-ac95-4a81-9355-ef3cfb0ba7b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 728bbb1a90a4c9d8095b1be1faf054fdec47bd9a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229369"
---
# <a name="compiler-error-c2634"></a>Compiler-Fehler C2634 generiert
' & Class:: Member ': Zeiger auf Verweismember ist nicht zulässig  
  
 Ein Zeiger auf einen Verweismember deklariert ist.  
  
 Im folgende Beispiel wird C2634 generiert:  
  
```  
// C2634.cpp  
int mem;  
struct S {  
   S() : rf(mem) { }  
   int &rf;  
};  
int (S::*pdm) = &S::rf;   // C2634  
```