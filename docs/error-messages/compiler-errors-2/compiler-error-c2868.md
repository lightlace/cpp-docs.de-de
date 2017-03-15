---
title: "Compilerfehler C2868 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2868"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2868"
ms.assetid: 6ff5837b-e66d-44d1-9d17-80af35e08d08
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C2868
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Unzulässige Syntax für using\-Deklaration; vollständiger Name erwartet  
  
 Eine [using\-Deklaration](../../cpp/using-declaration.md) erfordert einen [qualifizierten Namen](assetId:///3fefb16d-8120-4627-8b3f-3d90fbdcd1df).  
  
 Im folgenden Beispiel wird C2868 generiert:  
  
```  
// C2868.cpp  
class X {  
public:  
   int i;  
};  
  
class Y : X {  
public:  
   using X::i;   // OK  
};  
  
int main() {  
   using X;   // C2868  
}  
```