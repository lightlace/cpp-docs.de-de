---
title: Compilerfehler C3068 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3068
dev_langs:
- C++
helpviewer_keywords:
- C3068
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f378a60c79defed4fb1738515ca5b65b2851056
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33256554"
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