---
title: "Compilerfehler C2833 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2833"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2833"
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2833
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Operator 'Operator' ist kein bekannter Operator oder Typ  
  
 Dem Wort `operator` muss ein Operator folgen, der überschrieben werden soll, oder ein Typ, der konvertiert werden soll.  
  
 Eine Liste der Operatoren, die Sie in einem verwalteten Typ definieren können, finden Sie unter [Benutzerdefinierte Operatoren](../../dotnet/user-defined-operators-cpp-cli.md).  
  
 Im folgenden Beispiel wird C2833 generiert:  
  
```  
// C2833.cpp  
// compile with: /c  
class A {};  
  
void operator ::* ();   // C2833  
void operator :: ();   // OK  
```