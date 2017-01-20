---
title: "Compilerfehler C3156"
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
  - "C3156"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3156"
ms.assetid: 1876da78-b94e-4af7-9795-28f72b209b3e
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
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