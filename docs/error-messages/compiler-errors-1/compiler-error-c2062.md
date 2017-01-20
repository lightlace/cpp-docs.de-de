---
title: "Compilerfehler C2062"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2062"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2062"
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2062
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ'\-Typ unerwartet  
  
 Der Compiler hat keinen Typnamen erwartet.  
  
 Im folgenden Beispiel wird C2062 generiert:  
  
```  
// C2062.cpp  
// compile with: /c  
struct A {  : int l; };   // C2062  
struct B { private: int l; };   // OK  
```  
  
 C2062 kann auch auftreten, wenn der Compiler nicht definierte Typen in der Parameterliste eines Konstruktor findet.  Wenn der Compiler einen nicht definierten \(falsch geschriebenen\) Typ entdeckt, wird der Konstruktor als Ausdruck interpretiert und C2062 ausgegeben.  Um den Fehler zu beheben, verwenden Sie ausschließlich definierte Typen in der Parameterliste eines Konstruktors.