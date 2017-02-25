---
title: "Compilerfehler C2758 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2758"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2758"
ms.assetid: 1d273034-194c-4926-9869-142d1b219cbe
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2758
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member': Ein Member eines Verweistyps muss initialisiert werden  
  
 Der Compilerfehler C2758 wird ausgelöst, wenn der Konstruktor ein Member des Verweistyps in einer Initialisiererliste nicht initialisiert.  Der Compiler lässt das Member undefiniert.  Verweismembervariablen müssen initialisiert werden, wenn sie deklariert werden, oder sie müssen einen Wert in der Initialisierungsliste des Konstruktors erhalten.  
  
 Im folgenden Beispiel wird C2758 generiert:  
  
```  
// C2758.cpp  
// Compile by using: cl /W3 /c C2758.cpp  
struct A {  
   const int i;  
  
   A(int n) { };   // C2758  
   // try the following line instead  
   // A(int n) : i{n} {};  
};  
```