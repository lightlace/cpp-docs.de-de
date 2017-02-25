---
title: "Compilerfehler C2862 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2862"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2862"
ms.assetid: c04d8499-b799-48a1-9fb4-7902a0b0ac8e
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2862
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Schnittstelle': Eine Schnittstelle kann nur öffentliche Member besitzen  
  
 Auf geschützte und private Member kann nur von anderen Memberfunktionen aus zugegriffen werden.  Derartige Member sind in einer Schnittstelle nicht von Nutzen, da die Schnittstelle u. U. keine Implementierungen für ihre Member bereitstellt.  
  
 Im folgenden Beispiel wird C2862 generiert:  
  
```  
// C2862.cpp  
// compile with: /c  
#include <unknwn.h>  
  
[object, uuid="60719E20-EF37-11D1-978D-0000F805D73B"]  
__interface IMyInterface {  
   HRESULT mf1(void);   // OK  
protected:  
   HRESULT mf2(int *b);   // C2862  
private:  
   HRESULT mf3(int *c);   // C2862  
};  
```