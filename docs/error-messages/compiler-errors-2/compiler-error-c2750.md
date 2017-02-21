---
title: "Compilerfehler C2750 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2750"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2750"
ms.assetid: 30450034-feb5-448c-9655-b8c5f3639695
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2750
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ': 'new' kann für den Referenztyp nicht verwendet werden. Verwenden Sie stattdessen 'gcnew'  
  
 Um eine Instanz eines CLR\-Typs zu erstellen, der veranlasst, dass die Instanz auf dem Heap der Garbage Collection abgelegt wird, muss [gcnew](../../windows/ref-new-gcnew-cpp-component-extensions.md) verwendet werden.  
  
 Im folgenden Beispiel wird C2750 generiert:  
  
```  
// C2750.cpp  
// compile with: /clr  
ref struct Y1 {};  
  
int main() {  
   Y1 ^ x = new Y1;   // C2750  
  
   // try the following line instead  
   Y1 ^ x2 = gcnew Y1;  
}  
```