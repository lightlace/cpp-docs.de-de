---
title: "Compilerfehler C3507 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3507"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3507"
ms.assetid: 75f89767-f6f9-40f6-9820-81a49e09abdf
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C3507
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine ProgID darf maximal 39 Zeichen 'id' haben. Es dürfen keine Satzzeichen außer '.' enthalten sein, und das erste Zeichen darf keine Ziffer sein  
  
 Das [progid](../../windows/progid.md)\-Attribut unterliegt Beschränkungen bezüglich der Werte, die es enthalten kann.  
  
 Im folgenden Beispiel wird C3507 generiert:  
  
```  
// C3507.cpp  
[module(name="x")];  
[  
coclass,  
progid("0123456789012345678901234567890123456789"),  
uuid("00000000-0000-0000-0000-000000000001") // C3507 expected  
]  
struct CMyStruct {  
};  
int main() {  
}  
```