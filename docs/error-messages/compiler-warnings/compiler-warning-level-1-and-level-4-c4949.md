---
title: "Compilerwarnung (Stufe 1 und Stufe 4) C4949 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4949"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4949"
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 1 und Stufe 4) C4949
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pragmas 'verwaltetet' und 'nicht verwaltet' sind nur bei der Kompilierung mit '\/clr\[:Option\]' von Bedeutung  
  
 [Verwaltete](../../preprocessor/managed-unmanaged.md) und nicht verwalteten Pragmas werden vom Compiler ignoriert, wenn der Quellcode nicht mit [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) kompiliert wird.  Diese Warnung dient zu Informationszwecken.  
  
 Im folgenden Beispiel wird C4949 generiert:  
  
```  
// C4949.cpp  
// compile with: /LD /W1  
#pragma managed   // C4949  
```  
  
 Wenn **\#pragma unmanaged** ohne **\/clr** verwendet wird, ist C4949 eine Warnmeldung der Stufe 4.  
  
 Im folgenden Beispiel wird C4949 generiert:  
  
```  
// C4949b.cpp  
// compile with: /LD /W4  
#pragma unmanaged   // C4949  
```