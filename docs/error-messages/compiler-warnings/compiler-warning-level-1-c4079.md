---
title: "Compilerwarnung (Stufe 1) C4079 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4079"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4079"
ms.assetid: 549759f0-e168-47e9-8c9a-de93ac843689
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4079
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

unerwartetes Token 'token'  
  
 In einer Pragmaargumentliste tritt ein unerwartetes Trennzeichentoken auf.  Der Rest des Pragmas wurde ignoriert.  
  
 Im folgenden Beispiel wird C4079 generiert:  
  
```  
// C4079.cpp  
// compile with: /W1  
#pragma warning(disable : 4081)  
#pragma pack(c,16)   // C4079  
  
int main() {  
}  
```