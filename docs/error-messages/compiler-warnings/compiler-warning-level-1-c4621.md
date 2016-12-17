---
title: "Compilerwarnung (Stufe 1) C4621"
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
  - "C4621"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4621"
ms.assetid: 40931bd9-cb89-497e-86f0-cec9f016c63c
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4621
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Keine Postfix\-Form für 'Operator \-\-' für den Typ 'Typ' gefunden, Präfix\-Form wird verwendet  
  
 Für den angegebenen Typ wurde kein Postfix\-Dekrementoperator definiert.  Der Compiler hat stattdessen den überladenen Operator Präfix verwendet.  
  
 Diese Warnung kann durch die Definition eines Operators Postfix `--` vermieden werden.  Erstellen Sie eine aus zwei Argumenten bestehende Version des Operators `--`, wie im Folgenden dargestellt:  
  
```  
// C4621.cpp  
// compile with: /W1  
class A  
{  
public:  
   A(int nData) : m_nData(nData)  
   {  
   }  
  
   A operator--()  
   {  
      m_nData -= 1;  
      return *this;  
   }  
  
   // A operator--(int)  
   // {  
   //    A tmp = *this;  
   //    m_nData -= 1;  
   //    return tmp;  
   // }  
  
private:  
   int m_nData;  
};  
  
int main()  
{  
   A a(10);  
   --a;  
   a--;   // C4621  
}  
```