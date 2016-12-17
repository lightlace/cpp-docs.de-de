---
title: "Compilerfehler C2688"
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
  - "C2688"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2688"
ms.assetid: 168c9e9d-8f65-4664-af86-db71d3e6ee46
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2688
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**"**   
 ***C2::fgrv* ": covariant\-Rückgaben mit mehrfacher oder virtueller Vererbung werden für varargs\-Funktionen nicht unterstützt.**  
  
 **Covariant**\-Rückgabetypen werden in Visual C\+\+ nicht unterstützt, wenn eine Funktion variable Argumente enthält.  
  
 Um diesen Fehler zu beheben, definieren Sie Funktionen entweder so, dass sie keine variablen Argumente verwenden, oder definieren die Rückgabewerte für alle virtuellen Funktionen identisch.  
  
 Im folgenden Beispiel wird C2688 generiert:  
  
```  
// C2688.cpp  
struct G1 {};  
struct G2 {};  
struct G3 : G1, G2 {};  
struct G4 {};  
struct G5 {};  
struct G6 : G4, G5 {};  
struct G7 : G3, G6 {};  
  
struct C1 {  
   virtual G4& fgrv(int,...);  
};  
  
struct C2 : C1 {  
   virtual G7& fgrv(int,...);   // C2688, does not return G4&  
};  
```