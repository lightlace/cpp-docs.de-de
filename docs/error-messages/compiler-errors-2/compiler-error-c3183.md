---
title: "Compilerfehler C3183"
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
  - "C3183"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3183"
ms.assetid: dbd0f020-c739-43c9-947e-9ce21537331b
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3183
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine unbenannte Klasse, Struktur oder Union kann nicht innerhalb des verwalteten oder WinRT\-Typs „type“ definiert werden.  
  
 Ein Typ, der in einen verwalteten oder WinR\-Typ eingebettet ist, muss benannt werden.  
  
 Im folgenden Beispiel wird C3183 generiert:  
  
```  
// C3183a.cpp  
// compile with: /clr /c  
ref class Test  
{  
   ref class  
   {  // C3183, delete class or name it  
      int a;  
      int b;  
   };  
};  
```  
  
 Im folgenden Beispiel wird C3183 generiert:  
  
```  
// C3183b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__gc class Test  
{  
   __gc class  
   {  // C3183, delete class or name it  
      int a;  
      int b;  
   };  
};  
  
int main()  
{  
}  
```