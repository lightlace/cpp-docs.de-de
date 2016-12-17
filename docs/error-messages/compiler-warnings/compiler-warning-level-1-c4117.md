---
title: "Compilerwarnung (Stufe 1) C4117"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C4117"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4117"
ms.assetid: c45aa281-4cc1-4dfd-bd32-bd7a60ddd577
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4117
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Makroname 'Name' ist reserviert. 'Befehl' wird ignoriert.  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Versuchen Sie, ein vordefiniertes Makro zu definieren bzw. dessen Definition aufzuheben.  
  
2.  Versuchen Sie, den **defined**\-Präprozessoroperator zu definieren bzw. dessen Definition aufzuheben.  
  
 Im folgenden Beispiel wird C4117 generiert:  
  
```  
// C4117.cpp // compile with: /W1 #define __FILE__ test         // C4117. __FILE__ is a predefined macro #define ValidMacroName test   // ok int main() { }  
```