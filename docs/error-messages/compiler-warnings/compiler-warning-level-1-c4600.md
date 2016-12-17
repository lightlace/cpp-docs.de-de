---
title: "Compilerwarnung (Stufe 1) C4600"
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
  - "C4600"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4600"
ms.assetid: f023a2a1-7fc4-463f-a434-dc93fcd3f4e9
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4600
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma 'Makroname': es wurde eine gültige nicht leere Zeichenfolge erwartet  
  
 Sie können keine leere Zeichenfolge angeben, wenn Sie einen Makronamen mit [pop\_macro](../../preprocessor/pop-macro.md) auslesen oder mit [push\_macro](../../preprocessor/push-macro.md) ablegen.  
  
 Im folgenden Beispiel wird C4600 generiert:  
  
```  
// C4600.cpp  
// compile with: /W1  
int main()  
{  
   #pragma push_macro("")   // C4600 passing an empty string  
}  
```