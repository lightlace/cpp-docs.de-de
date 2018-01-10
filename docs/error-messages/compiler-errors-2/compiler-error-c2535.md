---
title: Compilerfehler C2535 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2535
dev_langs: C++
helpviewer_keywords: C2535
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2cdcd4aa00f0b96e0995e7589a8bbe4d1b990c74
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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