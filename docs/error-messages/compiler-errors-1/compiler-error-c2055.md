---
title: "Compilerfehler C2055"
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
  - "C2055"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2055"
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2055
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Liste formaler Parameter erwartet, nicht Typenliste  
  
 Anstatt einer Liste formaler Parameter enthält eine Funktionsdefinition eine Parametertypenliste.  Bei ANSI C müssen formale Parameter benannt werden, sofern sie nicht vom Typ `void` sind oder Auslassungszeichen \(`...`\) darstellen.  
  
 Im folgenden Beispiel wird C2055 generiert:  
  
```  
// C2055.c  
// compile with: /c  
void func(int, char) {}  // C2055  
void func (int i, char c) {}   // OK  
```