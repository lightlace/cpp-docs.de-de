---
title: "Compilerfehler C3168 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3168"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3168"
ms.assetid: 4c36fcfb-c351-48ff-b4eb-78d2aa1b4d55
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C3168
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ' : Ungültiger zugrunde liegender Typ für Enumeration  
  
 Der für den `enum`\-Typ angegebene, zugrunde liegende Typ war ungültig.  Der zugrunde liegende Typ muss ein ganzzahliger C\+\+\-Typ oder ein entsprechender CLR\-Typ sein.  
  
 Im folgenden Beispiel wird C3168 generiert:  
  
```  
// C3168.cpp  
// compile with: /clr /c  
ref class G{};  
  
enum class E : G { e };   // C3168  
enum class F { f };   // OK  
```  
  
 Im folgenden Beispiel wird C3168 generiert:  
  
```  
// C3168_2.cpp  
// compile with: /clr:oldSyntax /c  
__gc class G {};  
  
__value enum E : G {e};   // C3168  
__value enum F {f};   // OK  
```