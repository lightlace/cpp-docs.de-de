---
title: Compilerfehler C3731 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3731
dev_langs:
- C++
helpviewer_keywords:
- C3731
ms.assetid: 45f89fcd-464c-4bc8-8a42-edcb5416d26c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b7b87b59fa7a3e3695da88b5ddb30a84837f6e60
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275303"
---
# <a name="compiler-error-c3731"></a>Compilerfehler C3731
Inkompatible Ereignis "Funktion1" und der Handler "Funktion2"; Ereignisquelle und Ereignishandler müssen vom selben Typ sein.  
  
 Die Ereignisquelle und einen Ereignisempfänger müssen denselben Typ haben (z. B. `native` im Vergleich zu `com` Typen). Um diesen Fehler zu beheben, stellen Sie die Typen von der Ereignisquelle und Ereignishandler.  
  
 Im folgende Beispiel wird C3731 generiert:  
  
```  
// C3731.cpp  
// compile with: /clr  
#using <mscorlib.dll>  
[event_source(native)]  
struct A {  
   __event void MyEvent();  
};  
  
[event_receiver(managed)]  
// try the following line instead  
// [event_receiver(native)]  
struct B {  
   void func();  
   B(A a) {  
      __hook(&A::MyEvent, &a, &B::func);   // C3731  
   }  
};  
  
int main() {  
}  
```