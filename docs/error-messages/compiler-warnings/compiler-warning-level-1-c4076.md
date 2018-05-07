---
title: Compilerwarnung (Stufe 1) C4076 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4076
dev_langs:
- C++
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1cfa28469e099dbf2b6bd43213073c304d0b2894
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4076"></a>Compilerwarnung (Stufe 1) C4076
"Typmodifizierer": Kann nicht mit Typ "Typname" verwendet werden  
  
 Ein Typmodifizierer kann unabhängig davon, ob er **signed** oder `unsigned`ist, nicht mit einem Typ verwendet werden, der nicht ganzzahlig ist. ***Typmodifizierer*** wird ignoriert.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4076 generiert:  
  
```  
// C4076.cpp  
// compile with: /W1 /LD  
unsigned double x;   // C4076  
```