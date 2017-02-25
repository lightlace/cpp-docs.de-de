---
title: "Compilerfehler C2492 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2492"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2492"
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
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