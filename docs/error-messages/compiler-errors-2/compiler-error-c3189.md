---
title: "Compilerfehler C3189"
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
  - "C3189"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3189"
ms.assetid: b254de79-931e-4a59-a9f4-1c690d90ca5e
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3189
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'typeidtype \<abstrakter Deklarator\>': diese Syntax wird nicht mehr, Verwendung ::typeid stattdessen unterstützt  
  
 Es wurde ein veraltetes [typeid](../../windows/typeid-cpp-component-extensions.md)\-Format verwendet, verwenden Sie das neue Format.  
  
 Im folgenden Beispiel wird C3189 generiert:  
  
```  
// C3189.cpp  
// compile with: /clr  
int main() {  
   System::Type^ t  = typeid<System::Object>;   // C3189  
   System::Type^ t2  = System::Object::typeid;   // OK  
}  
```