---
title: "Compilerfehler C3254 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3254"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3254"
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C3254
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'explizite Überschreibung' : Die Klasse enthält die explizite Überschreibung 'Überschreiben', wird jedoch nicht von einer Schnittstelle abgeleitet, die die Funktionsdeklaration enthält  
  
 Wenn Sie eine Methode [explizit überschreiben](../../cpp/explicit-overrides-cpp.md), muss die Klasse, in der die Überschreibung enthalten ist, direkt oder indirekt von dem Typ ableiten, der die zu überschreibende Funktion enthält.  
  
 Im folgenden Beispiel wird C3254 generiert:  
  
```  
// C3254.cpp  
__interface I  
{  
   void f();  
};  
  
__interface I1 : I  
{  
};  
  
struct A /* : I1 */  
{  
   void I1::f()  
   {   // C3254, uncomment : I1 to resolve this C3254  
   }  
};  
  
int main()  
{  
}  
```