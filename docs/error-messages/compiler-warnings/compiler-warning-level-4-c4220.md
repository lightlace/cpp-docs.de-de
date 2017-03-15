---
title: "Compilerwarnung (Stufe 4) C4220 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4220"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4220"
ms.assetid: aba18868-825f-4763-9af6-3296406a80e4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 4) C4220
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Parameterliste mit Liste variabler Parameter verglichen  
  
 Bei Verwendung der Microsoft\-Standarderweiterungen \(**\/Ze**\) stimmt ein Funktionszeiger mit einem anderen Funktionszeiger überein, der über ähnliche, aber variable Argumente verfügt.  
  
## Beispiel  
  
```  
// C4220.c  
// compile with: /W4  
  
int ( *pFunc1) ( int a, ... );  
int ( *pFunc2) ( int a, int b);  
  
int main()  
{  
   if ( pFunc1 != pFunc2 ) {};  // C4220  
}  
```  
  
 Derartige Zeiger stimmen bei Einhaltung der ANSI\-Kompatibilität \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) nicht überein.