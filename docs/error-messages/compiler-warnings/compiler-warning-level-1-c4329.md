---
title: "Compilerwarnung (Stufe 1) C4329 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4329"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4329"
ms.assetid: 4316f51a-2c56-4b3f-831e-65d24b83b65c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4329
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_\_declspec\(align\(\)\) wird für enum ignoriert  
  
 Das Schlüsselwort [align](../../cpp/align-cpp.md) des [\_\_declspec](../../cpp/declspec.md)\-Modifizierers kann für `enum` nicht verwendet werden.  Im folgenden Beispiel wird C4329 generiert:  
  
```  
// C4329.cpp  
// compile with: /W1 /LD  
enum __declspec(align(256)) TestEnum {   // C4329  
   TESTVAL1,  
   TESTVAL2,  
   TESTVAL3  
};  
__declspec(align(256)) enum TestEnum1;  
```