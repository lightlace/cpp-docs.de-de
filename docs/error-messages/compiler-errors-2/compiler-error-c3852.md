---
title: "Compilerfehler C3852"
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
  - "C3852"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3852"
ms.assetid: 194e5c5e-0dfb-414e-86db-791c11eb610c
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3852
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Member' vom Typ 'Typ': Aggregatsinitialisierung konnte diesen Member nicht initialisieren  
  
 Es wurde versucht, einem Datenmember, dem in einer Aggregatsinitialisierung keine Standardinitialisierung zugewiesen werden kann, eine Standardinitialisierung als Teil einer Aggregatsinitialisierung zuzuweisen.  
  
 In den folgenden Beispielen wird C3852 generiert:  
  
```  
// C3852.cpp  
struct S  
{  
   short s;  
};  
  
struct S1  
{  
   int i;  
   const S s;  
};  
  
struct S2  
{  
   int i;  
   char & rc;  
};  
  
int main()  
{  
   S1 s1 = { 1 };   // C3852 const member   
   // try the following line instead  
   // S1 s1 = { 1, 2 };  
  
   S2 s2 = { 2 };   // C3852 reference member  
   // try the following line instead  
   // char c = 'a';  
   S2 s2 = { 2, c };  
}  
```