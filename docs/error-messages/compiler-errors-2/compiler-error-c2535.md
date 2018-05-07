---
title: Compilerfehler C2535 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2535
dev_langs:
- C++
helpviewer_keywords:
- C2535
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1dc791cd7782cc758aa51b0c61d87a79570c13c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2535"></a>Compilerfehler C2535
'Bezeichner' : Memberfunktion bereits definiert oder deklariert  
  
 Dieser Fehler kann auftreten, wenn dieselbe Liste formaler Parameter in mehr als einer Funktionsdefinition oder -deklaration einer überladenen Funktion verwendet wird.  
  
 Wenn C2535 durch die Dispose-Funktion verursacht wird, finden Sie unter [Destruktoren und Finalizer](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) für Weitere Informationen.  
  
 Informationen zum Kompilieren eines ATL-Projekts finden Sie im Knowledge Base-Artikel Q241852 (nur auf Englisch verfügbar).  
  
 Im folgenden Beispiel wird C2535 generiert:  
  
```  
// C2535.cpp  
// compile with: /c  
class C {  
public:  
   void func();   // forward declaration  
   void func() {}   // C2535  
};  
```