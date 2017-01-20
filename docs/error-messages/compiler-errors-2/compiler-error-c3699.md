---
title: "Compilerfehler C3699"
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
  - "C3699"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3699"
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3699
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operator': Diese Dereferenzierung kann nicht für den Typ 'Typ' verwendet werden  
  
 Es wurde versucht, eine Dereferenzierung zu verwenden, die für `type` nicht zulässig ist.  
  
## Beispiel  
 Im folgenden Beispiel wird C3699 generiert.  
  
```  
// C3699.cpp  
// compile with: /clr /c  
using namespace System;  
int main() {  
   String * s;   // C3699  
   // try the following line instead  
   // String ^ s2;  
}  
```  
  
## Beispiel  
 Eine triviale Eigenschaft kann nicht über einen Referenztyp verfügen.  Weitere Informationen finden Sie unter [property](../../windows/property-cpp-component-extensions.md).  Im folgenden Beispiel wird C3699 generiert.  
  
```  
// C3699_b.cpp  
// compile with: /clr /c  
ref struct C {  
   property System::String % x;   // C3699  
   property System::String ^ y;   // OK  
};  
```  
  
## Beispiel  
 Das Äquivalent einer "Zeiger auf Zeiger"\-Syntax ist ein Handle auf einen Nachverfolgungsverweis.  Im folgenden Beispiel wird C3699 generiert.  
  
```  
// C3699_c.cpp  
// compile with: /clr /c  
using namespace System;  
void Test(String ^^ i);   // C3699  
void Test2(String ^% i);  
```