---
title: "Compilerfehler C2427 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2427"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2427"
ms.assetid: a7d421af-6180-40b4-b7a6-9f3bc7dfaaf9
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2427
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse': In diesem Bereich kann die Klasse nicht definiert werden  
  
 Es wurde eine geschachtelte Klasse definiert, die jedoch ein Member einer Basisklasse und nicht die übergeordnete Klasse ist.  
  
 Im folgenden Beispiel wird C2427 generiert:  
  
```  
// C2427.cpp  
// compile with: /c  
template <class T>   
struct S {  
   struct Inner;   
};   
  
struct Y : S<int> {};   
  
struct Y::Inner {};   // C2427  
  
// OK  
template<typename T>  
struct S<T>::Inner {};  
```