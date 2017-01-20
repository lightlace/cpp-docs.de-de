---
title: "Compilerwarnung (Stufe 3) C4534"
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
  - "c4534"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4534"
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 3) C4534
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Konstruktor' ist kein Standardkonstruktor für Klasse 'Klasse' aufgrund des Standardarguments  
  
 Eine nicht verwaltete Klasse kann einen Konstruktor mit Parametern aufweisen, die über Standardwerte verfügen. Dieser Konstruktor wird dann vom Compiler als Standardkonstruktor verwendet.  Eine mit dem Schlüsselwort `value` gekennzeichnete Klasse verwendet keinen Konstruktor als Standardkonstruktor, dessen Parameter über Standardwerte verfügen.  
  
 Weitere Informationen finden Sie unter [Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird C4534 generiert:  
  
```  
// C4534.cpp  
// compile with: /W3 /clr /WX  
value class MyClass {  
public:  
   int ii;  
   MyClass(int i = 9) {   // C4534, will not be the default constructor  
      i++;  
   }  
};  
  
int main() {  
   MyClass ^ xx = gcnew MyClass;  
   xx->ii = 0;  
}  
```