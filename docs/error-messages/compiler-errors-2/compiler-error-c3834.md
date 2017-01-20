---
title: "Compilerfehler C3834"
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
  - "C3834"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3834"
ms.assetid: 059e0dc4-300b-4e74-b6c2-41a57831fe2a
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3834
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unzulässige explizite Umwandlung zu einem festen Zeiger. Verwenden Sie eine fixierte lokale Variable.  
  
 Explizite Typumwandlungen in einen festen Zeiger sind nicht zulässig.  
  
## Beispiel  
 Im folgenden Beispiel wird C3834 generiert.  
  
```  
// C3834.cpp  
// compile with: /clr  
int main() {  
   int x = 33;  
  
   pin_ptr<int> p = safe_cast<pin_ptr<int> >(&x);   // C3834  
   pin_ptr<int> p2 = &x;   // OK  
}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C3834 generiert.  
  
```  
// C3834_b.cpp  
// compile with: /clr:oldSyntax  
using namespace System;  
  
int main() {  
   const __wchar_t * pS = reinterpret_cast<const __wchar_t __pin*>(S"hello");   // C3834  
  
   // OK   
   // declare a pinning variable  
   String __pin* ppin = S"Hello";  
  
   // cast pinning variable to unmanaged type  
   const __wchar_t * pS2 = reinterpret_cast<__wchar_t*>(ppin);     
  
   pS2 += 6;  
}  
```