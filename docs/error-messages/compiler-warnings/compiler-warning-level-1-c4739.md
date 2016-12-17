---
title: "Compilerwarnung (Stufe 1) C4739"
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
  - "C4739"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4739"
ms.assetid: 600873b3-7c85-4cd4-944e-cd8e01bfcbb0
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4739
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Für den Verweis auf die Variable 'var' ist nicht genügend Speicherplatz vorhanden.  
  
 Ein Wert wurde einer Variablen zugewiesen, aber der Wert ist größer als die Größe der Variablen. Der Arbeitsspeicher wird über den Speicherbereich der Variablen hinaus beschrieben, wodurch ein Datenverlust möglich ist.  
  
 Weisen Sie einen Wert nur einer Variablen zu, deren Größe den Wert aufnehmen kann, um diese Warnung zu vermeiden.  
  
 Im folgenden Beispiel wird C4739 generiert.  
  
```  
// C4739.cpp // compile with: /RTCs /Zi /W1 /c char *pc; int main() { char c; *(int *)&c = 1;   // C4739 // OK *(char *)&c = 1; }  
```