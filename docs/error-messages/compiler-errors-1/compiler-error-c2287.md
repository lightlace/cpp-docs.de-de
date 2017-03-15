---
title: "Compilerfehler C2287 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2287"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2287"
ms.assetid: 64556299-4e1f-4437-88b7-2464fc0b95bb
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2287
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse': Vererbungsdarstellung: 'Darstellung1' ist weniger allgemein als die erforderliche 'Darstellung2'  
  
 Eine Klasse wurde mit einer einfacheren Darstellung als erforderlich deklariert.  
  
 Im folgenden Beispiel wird C2287 generiert:  
  
```  
// C2287.cpp  
// compile with: /vmg /c  
class __single_inheritance X;  
class __single_inheritance Y;  
  
struct A { };  
struct B { };  
struct X : A, B { };  // C2287  X uses multiple inheritance  
struct Y : A { };  // OK  
```