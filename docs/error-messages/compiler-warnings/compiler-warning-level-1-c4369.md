---
title: "Compilerwarnung (Stufe 1) C4369 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4369"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4369"
ms.assetid: ade87e84-36be-4e00-be99-2930af848feb
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
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