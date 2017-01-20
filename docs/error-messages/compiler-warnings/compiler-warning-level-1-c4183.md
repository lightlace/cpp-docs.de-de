---
title: "Compilerwarnung (Stufe 1) C4183"
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
  - "C4183"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4183"
ms.assetid: dc48312c-4b34-44dd-80ff-eb5f11d5ca47
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4183
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Rückgabetyp fehlt; Memberfunktion, die 'int' zurückgibt, wird angenommen  
  
 Die Inlinedefinition einer Memberfunktion in einer Klasse oder Struktur hat keinen Rückgabetyp.  Es wird angenommen, dass diese Memberfunktion den Standardrückgabetyp `int` hat.  
  
 Im folgenden Beispiel wird C4183 generiert:  
  
```  
// C4183.cpp  
// compile with: /W1 /c  
#pragma warning(disable : 4430)  
class MyClass1;  
class MyClass2 {  
   MyClass1() {};   // C4183  
};  
```