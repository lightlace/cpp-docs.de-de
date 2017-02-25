---
title: "Compilerfehler C3156 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3156"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3156"
ms.assetid: 1876da78-b94e-4af7-9795-28f72b209b3e
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C3156
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': Sie können nicht über eine lokale Definition eines verwalteten oder WinRT\-Typs verfügen  
  
 Eine Funktion kann weder die Definition noch die Deklaration einer verwalteten oder WinRT\-Klasse, \-Struktur oder \-Oberfläche enthalten.  
  
## Beispiel  
 Im folgenden Beispiel wird C3156 generiert:  
  
```  
// C3156.cpp  
// compile with: /clr /c  
void f() {  
   ref class X {};   // C3156  
   ref class Y;   // C3156  
}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C3156 generiert:  
  
```  
// C3156_b.cpp  
// compile with: /clr:oldSyntax /c  
void f() {  
   __gc class X {};   // C3156  
   __gc class Y;   // C3156  
}  
```