---
title: "Compilerfehler C3131"
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
  - "C3131"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3131"
ms.assetid: 38f20fac-83c9-4cd9-b7b5-74ca8f650ea6
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3131
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das Projekt muss ein "module"\-Attribut mit der Eigenschaft "Name" besitzen  
  
 Das [module](../../windows/module-cpp.md)\-Attribut muss über einen Namensparameter verfügen.  
  
 Im folgenden Beispiel wird C3131 generiert:  
  
```  
// C3131.cpp  
[emitidl];  
[module];   // C3131  
// try the following line instead  
// [module (name="MyLib")];  
  
[public]  
typedef long int LongInt;  
```