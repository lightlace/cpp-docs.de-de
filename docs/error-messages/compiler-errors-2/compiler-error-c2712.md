---
title: Compiler-Fehler C2712 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2712
dev_langs:
- C++
helpviewer_keywords:
- C2712
ms.assetid: f7d4ffcc-7ed2-459b-8067-a728ce647071
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 89b7d0ad3c7e175db1525c2f3fb8407240ce943c
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2712"></a>Compiler-Fehler C2712
__try kann nicht in Funktionen verwendet werden, die eine Objektentladung benötigen  
  
 Fehler C2712 kann auftreten, wenn Sie [/EHsc](../../build/reference/eh-exception-handling-model.md), und eine Funktion mit strukturierter Ausnahmebehandlung auch Objekte, die Entladung (Zerstörung) benötigen.  
  
 Folgende Lösungen sind möglich:  
  
-   Verschieben Sie Code, der SEH benötigt, zu einer anderen Funktion.  
  
-   Schreiben Sie Funktionen, die SEH verwenden, neu, um die Verwendung von lokalen Variablen und Parameter, die über Destruktoren verfügen, zu vermeiden. Verwenden Sie SEH nicht in Konstruktoren oder Destruktoren  
  
-   Kompilieren ohne /EHsc  
  
 Fehler C2712 kann auch auftreten, wenn Sie eine Methode deklariert mithilfe von Aufrufen der [__event](../../cpp/event.md) Schlüsselwort. Da das Ereignis möglicherweise in einer Multithreadumgebung verwendet wird, generiert der Compiler Code, die Bearbeitung des zugrunde liegenden Ereignisobjekts verhindert, und schließt den generierten Code dann in eine SEH- [Try-finally-Anweisung](../../cpp/try-finally-statement.md). Folglich wird Fehler C2712 auftreten, wenn Sie die Ereignismethode aufrufen und ein Argument, dessen Typ einen Destruktor enthält, als Wert übergeben. Eine Lösung besteht in diesem Fall darin, das Argument als konstanten Verweis zu übergeben.  
  
## <a name="example"></a>Beispiel  
 C2712 kann auch auftreten, wenn Sie die Kompilierung mit **/CLR: pure** , und deklarieren Sie ein statisches Array von Zeigern auf Funktionen in einem `__try` Block. Ein statischer Member erfordert, dass der Compiler dynamische Initialisierung unter **/CLR: pure**, wodurch eine C++-Ausnahmebehandlung impliziert. Eine C++-Ausnahmebehandlung ist jedoch in einem `__try`-Block nicht zulässig.  
  
 Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 veraltet sind.  
  
 Im folgenden Beispiel wird C2712 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2712.cpp  
// compile with: /clr:pure /c  
struct S1 {  
   static int smf();  
   void fnc();  
};  
  
void S1::fnc() {  
   __try {  
      static int (*array_1[])() = {smf,};   // C2712  
  
      // OK  
      static int (*array_2[2])();  
      array_2[0] = smf;  
    }  
    __except(0) {}  
}  
```
