---
title: Compilerwarnung (Stufe 1) C4407 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4407
dev_langs:
- C++
helpviewer_keywords:
- C4407
ms.assetid: 32bc2c21-363a-4bb8-b486-725faeaededc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cbc02c32463703f658cef1d5756926311d89b193
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4407"></a>Compilerwarnung (Stufe 1) C4407
eine Umwandlung zwischen verschiedenen Zeiger auf Member-Darstellungen, möglicherweise Compiler fehlerhaftem Code generieren  
  
 Eine falsche Umwandlung wurde erkannt.  
  
 C4407 kann aufgrund einer konformitätsverbesserung für Compiler generiert werden, die in Visual C++ 2005 erstellt wurde. Pointer-to-Member erfordert jetzt ein qualifizierter Name und Address-of-Operators (&).  
  
 C4407 kann auftreten, wenn Sie eine zwischen einem mehrere Vererbung Pointer-to-Member auf eine einfache Vererbung Pointer-to-Member Umwandlung. In einigen Fällen kann dies funktioniert, aber in einigen Fällen ist dies nicht möglich, da die einfache Vererbung Pointer-to-Member-Darstellung ausreichend Informationen enthalten, nicht. Beim Kompilieren mit der **/VMM** hilfreich sein (Weitere Informationen finden Sie unter [/VMM, / VMs, vmv (immer allgemeiner Zweck)](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)). Sie können auch versuchen, Ihre Basisklassen Neuanordnen; der Compiler ist einen Datenverlust bei der Konvertierung erkennen, da an einem Offset ungleich NULL aus dem abgeleiteten Basisklasse ist.  
  
 Im folgenden Beispiel wird C4407 generiert:  
  
```  
// C4407.cpp  
// compile with: /W1 /c  
struct C1 {};  
struct C2 {};  
struct C3 : C1, C2 {};  
  
typedef void(C3::*PMF_C3)();  
typedef void(C2::*PMF_C2)();  
  
PMF_C2 f1(PMF_C3 pmf) {  
   return (PMF_C2)pmf;   // C4407, change type of cast,  
   // or reverse base class inheritance of C3 (i.e. : C2, C1)  
}  
```