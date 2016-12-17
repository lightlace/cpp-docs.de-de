---
title: "Compilerfehler C2598"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2598"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2598"
ms.assetid: 40777c62-39ba-441e-b081-f49f94b43547
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2598
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bindungsinformationen müssen einen globalen Gültigkeitsbereich haben  
  
 Der Bindungsspezifizierer wurde im lokalen Gültigkeitsbereich deklariert.  
  
 Im folgenden Beispiel wird C2598 generiert:  
  
```  
// C2598.cpp  
// compile with: /c  
void func() {  
   extern "C" int func2();   // C2598  
}  
  
extern "C" int func( int i );  
```