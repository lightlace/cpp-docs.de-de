---
title: Compilerfehler C2381 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2381
dev_langs:
- C++
helpviewer_keywords:
- C2381
ms.assetid: cc765f67-64ac-406f-93ef-ae7d548d58d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7bd5f5edcf95144333524c41b803c24b728a621f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2381"></a>Compilerfehler C2381
'Funktion': Neudefinition; __declspec(noreturn) unterscheidet sich  
  
 Eine Funktion wurde deklariert, und klicken Sie dann definiert, aber die Definition verwendet die [Noreturn](../../cpp/noreturn.md) `__declspec` Modifizierer. Die Verwendung von `noreturn` Neudefinition der Funktion, die Deklaration und Definition für die Verwendung von zustimmen müssen `noreturn`.  
  
 Im folgende Beispiel wird C2381 generiert:  
  
```  
// C2381.cpp  
// compile with: /c  
void f1();  
void __declspec(noreturn) f1() {}   // C2381  
void __declspec(noreturn) f2() {}   // OK  
```