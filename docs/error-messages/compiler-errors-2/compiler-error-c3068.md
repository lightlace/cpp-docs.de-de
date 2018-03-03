---
title: Compilerfehler C3068 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3068
dev_langs:
- C++
helpviewer_keywords:
- C3068
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 448a0b9e9c626523c08a0bd30ab285ef2c29312c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3068"></a>Compilerfehler C3068
'Funktion': eine naked-Funktion kann keine Objekte enthalten, die Entladung erforderlich wäre, wenn eine C++-Ausnahme aufgetreten ist.  
  
 Der Compiler konnte nicht zum Ausführen der stapelentladung auf eine [naked](../../cpp/naked-cpp.md) -Funktion, die eine Ausnahme ausgelöst hat, weil ein temporäres Objekt, in der Funktion und die C++-Ausnahmebehandlung erstellt wurde ([/EHsc /](../../build/reference/eh-exception-handling-model.md)) angegeben wurde.  
  
 Führen Sie mindestens eine der folgenden Schritte aus, um diesen Fehler zu beheben:  
  
-   Nicht mit/EHsc / kompiliert.  
  
-   Markieren Sie die Funktion als nicht `naked`.  
  
-   Erstellen Sie ein temporäres Objekt nicht in der Funktion.  
  
 Wenn eine Funktion ein temporäres Objekt auf dem Stapel erstellt, wenn die Funktion eine Ausnahme auslöst, und C++-Ausnahmebehandlung aktiviert ist, wird der Compiler bereinigt den Stapel, wenn eine Ausnahme ausgelöst wird.  
  
 Wenn eine Ausnahme ausgelöst wird, vom Compiler Code, mit dem Namen von Prolog generierte und Epilog nicht in eine naked-Funktion vorhanden sind, werden für eine Funktion ausgeführt.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3068 generiert:  
  
```  
// C3068.cpp  
// compile with: /EHsc  
// processor: x86  
class A {  
public:  
   A(){}  
   ~A(){}  
};  
  
void b(A){}  
  
__declspec(naked) void c() {  
   b(A());   // C3068   
};  
```