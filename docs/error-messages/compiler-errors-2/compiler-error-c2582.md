---
title: Compilerfehler C2582 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2582
dev_langs:
- C++
helpviewer_keywords:
- C2582
ms.assetid: ee1b9378-8bcd-4792-b87e-6d7a466d29ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc8a926297f9b0762c629f031da6e12cbe528e87
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2582"></a>Compilerfehler C2582
' Funktion ' ist in "Type" nicht verfügbar  
  
 Es wurde versucht, ein Objekt zuweisen, die nicht über einen Zuweisungsoperator verfügt.  
  
 Im folgende Beispiel wird C2582 generiert:  
  
```  
// C2582.cpp  
// compile with: /clr  
using namespace System;  
  
struct N {};  
ref struct O {};  
ref struct R {  
   property O prop;   // C2582  
   property O ^ prop2;   // OK  
};  
  
int main() {  
   String ^ st1 = gcnew String("");  
   ^st1 = gcnew String("");   // C2582  
   st1 = "xxx";   // OK  
}  
```