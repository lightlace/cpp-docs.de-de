---
title: "Compilerfehler C2652 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2652"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2652"
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2652
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Unzulässiger Kopierkonstruktor: erster Parameter darf nicht 'Bezeichner' sein  
  
 Der erste Parameter im Kopierkonstruktor ist vom selben Typ wie die Klasse, Struktur oder Union, für die er definiert wurde.  Als erster Parameter kann zwar ein Verweis auf den Typ, nicht aber der Typ selbst aufgenommen werden.  
  
 Im folgenden Beispiel wird C2651 generiert:  
  
```  
// C2652.cpp  
// compile with: /c  
class A {  
   A( A );   // C2652 takes an A  
};  
class B {  
   B( B& );   // OK, reference to B  
};  
```