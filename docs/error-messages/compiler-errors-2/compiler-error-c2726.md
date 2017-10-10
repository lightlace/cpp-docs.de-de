---
title: Compilerfehler Fehler C2726 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2726
dev_langs:
- C++
helpviewer_keywords:
- C2726
ms.assetid: f0191bb7-c175-450b-bf09-a3213db96d09
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f97067f71927491072f303bc872616640bae3367
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2726"></a>Compilerfehler Fehler C2726
"gcnew" kann nur zum Erstellen eines Objekts mit verwaltetem oder WinRT-Typ verwendet werden.  
  
 Sie können keine Instanz eines systemeigenen Typs auf dem Heap der Garbage Collection erstellen.  
  
 Im folgenden Beispiel wird C2726 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2726.cpp  
// compile with: /clr  
using namespace System;  
class U {};  
ref class V {};  
value class W {};  
  
int main() {  
   U* pU = gcnew U;    // C2726  
   U* pU2 = new U;   // OK  
   V^ p2 = gcnew V;   // OK  
   W p3;   // OK  
  
}  
```  

