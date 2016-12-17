---
title: "Compilerwarnung (Stufe 1) C4369"
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
  - "C4369"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4369"
ms.assetid: ade87e84-36be-4e00-be99-2930af848feb
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4369
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Enumerator':  Enumerator 'Wert'\-Wert kann nicht als 'Typ' dargestellt werden, Wert ist 'new\_value'  
  
 Ein Enumerator wurde größer berechnet als der größte Wert für den angegebenen zugrunde liegenden Typ.  Hierdurch wurde ein Überlauf verursacht, und der Compiler hat den Enumeratorwert in den kleinstmöglichen Wert für den Typ umgewandelt.  
  
## Beispiel  
 Im folgenden Beispiel wird C4369 generiert.  
  
```  
// C4369.cpp  
// compile with: /W1  
int main() {  
   enum Color: char { red = 0x7e, green, blue };   // C4369  
   enum Color2: char { red2 = 0x7d, green2, blue2};   // OK  
}  
```