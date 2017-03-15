---
title: "Compilerfehler C3136 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3136"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3136"
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C3136
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Schnittstelle': Eine COM\-Schnittstelle kann nur von einer anderen COM\-Schnittstelle erben, 'Schnittstelle' ist keine COM\-Schnittstelle  
  
 Eine Schnittstelle, auf die ein [interface\-Attribut](../../windows/interface-attributes.md) angewendet wurde, erbt von einer Schnittstelle, die keine COM\-Schnittstelle ist.  Eine COM\-Schnittstelle erbt schließlich von `IUnknown`.  Alle Schnittstellen, denen ein Schnittstellenattribut vorausgeht, sind COM\-Schnittstellen.  
  
 Im folgenden Beispiel wird C3136 generiert:  
  
```  
// C3136.cpp  
#include "unknwn.h"  
  
__interface A   // C3136  
// try the following line instead  
// _interface A : IUnknown  
{  
   int a();  
};  
  
[object]  
__interface B : A  
{  
   int aa();  
};  
```