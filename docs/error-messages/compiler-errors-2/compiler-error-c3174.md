---
title: "Compilerfehler C3174"
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
  - "C3174"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3174"
ms.assetid: fe6b3b5a-8196-485f-a45f-0b2e51df4086
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3174
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das Modulattribut wurde nicht angegeben  
  
 Von einem Programm, das Visual C\+\+\-Attribute verwendet, wurde zusätzlich kein [module](../../windows/module-cpp.md)\-Attribut verwendet. Diese Bedingung gilt für alle Programme, die Attribute verwenden.  
  
 Im folgenden Beispiel wird C3174 generiert:  
  
```  
// C3174.cpp  
// C3174 expected  
// uncomment the following line to resolve this C3174  
// [module(name="x")];  
[export]  
struct S  
{  
   int i;  
};  
  
int main()  
{  
}  
```