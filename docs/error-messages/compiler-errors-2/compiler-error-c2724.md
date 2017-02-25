---
title: "Compilerfehler C2724 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2724"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2724"
ms.assetid: 4e4664bc-8c96-4156-b79f-03436f532ea8
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C2724
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner' : 'static' sollte nicht für Memberfunktionen verwendet werden, die im Dateigültigkeitsbereich definiert sind  
  
 Static\-Memberfunktionen sollten mit externer Bindung deklariert werden.  
  
 Im folgenden Beispiel wird C2724 generiert:  
  
```  
// C2724.cpp  
class C {  
   static void func();  
};  
  
static void C::func(){};   // C2724  
// try the following line instead  
// void C::func(){};  
```