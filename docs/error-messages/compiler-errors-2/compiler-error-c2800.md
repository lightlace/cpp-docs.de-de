---
title: "Compilerfehler C2800"
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
  - "C2800"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2800"
ms.assetid: a2f1a590-9fe6-44cb-ad09-b4505ef47c6a
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2800
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operator Operator' kann nicht überladen werden  
  
 Die folgenden Operatoren können nicht überladen werden: Klassenmemberzugriff \(`.`\), Memberzeiger \(`.*`\), Bereichsauflösung \(`::`\), bedingter Ausdruck \(`? :`\) und `sizeof`.  
  
 Im folgenden Beispiel wird C2800 generiert:  
  
```  
// C2800.cpp  
// compile with: /c  
class C {  
   operator:: ();   // C2800  
};  
```