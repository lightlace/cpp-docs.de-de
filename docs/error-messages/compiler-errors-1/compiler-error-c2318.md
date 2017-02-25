---
title: "Compilerfehler C2318 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2318"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2318"
ms.assetid: 169e30b9-df78-46cb-90bf-576ad3c32fd4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2318
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kein try\-Block mit diesem catch\-Handler verbunden  
  
 Es ist ein `catch`\-Handler definiert, vor diesem ist aber kein `try`\-Block angegeben.  
  
 Im folgenden Beispiel wird C2318 generiert:  
  
```  
// C2318.cpp // compile with: /EHsc #include <eh.h> int main() { // no try block catch( int ) {}   // C2318 }  
```  
  
 Mögliche Lösung:  
  
```  
// C2318b.cpp // compile with: /EHsc #include <eh.h> int main() { try{} catch( int ) {} }  
```