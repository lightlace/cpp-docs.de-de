---
title: "Compilerfehler C2492"
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
  - "C2492"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2492"
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2492
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Variable': 'thread'\-Daten dürfen keine DLL\-Schnittstelle haben  
  
 Die Variable wurde mit dem [thread](../../cpp/thread.md)\-Attribut und mit der DLL\-Schnittstelle deklariert.  Die Adresse der `thread`\-Variablen ist jedoch erst zur Laufzeit bekannt und kann somit nicht mit einem DLL\-Import oder \-Export verknüpft werden.  
  
 Im folgenden Beispiel wird C2492 generiert:  
  
```  
// C2492.cpp  
// compile with: /c  
class C {  
public:  
   char   ch;  
};  
  
__declspec(dllexport) __declspec(thread) C c_1;   // C2492  
__declspec(thread) C c_1;   // OK  
```