---
title: Compilerfehler C2208 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2208
dev_langs:
- C++
helpviewer_keywords:
- C2208
ms.assetid: 9ae704bc-bf70-45f1-8e47-0470f21edd4e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 24377d17735fc63e9dc0541dfd9fb432eb0e0cda
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2208"></a>Compilerfehler C2208
'Typ': keine Member definiert diesen Typ verwenden  
  
 Ein Bezeichner, die in einen Typnamen aufgelöst ist, in der Deklaration eines aggregieren, aber der Compiler kann ein Element nicht deklariert werden.  
  
 Im folgende Beispiel wird C2208 generiert:  
  
```  
// C2208.cpp  
class C {  
   C;   // C2208  
   C(){}   // OK  
};  
```