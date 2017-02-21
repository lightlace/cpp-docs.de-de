---
title: "Compilerfehler C2679 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2679"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2679"
ms.assetid: 1a5f9d00-9190-4aa6-bc72-949f68ec136f
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2679
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

binärer 'Operator' : Es konnte kein Operator gefunden werden, der einen rechtsseitigen Operanden vom Typ 'Typ' akzeptiert \(oder keine geeignete Konvertierung möglich\)  
  
 Um den Operator zu verwenden, müssen Sie ihn für den angegebenen Typ überladen oder eine Konvertierung in einen Typ definieren, für den der Operator definiert ist.  
  
 Im folgenden Beispiel wird C2679 generiert:  
  
```  
// C2679.cpp  
class C {  
public:  
   C();   // no constructor with an int argument  
} c;  
  
class D {  
public:  
   D(int) {}  
   D(){}  
} d;  
  
int main() {  
   c = 10;   // C2679  
   d = 10;   // OK  
}  
```