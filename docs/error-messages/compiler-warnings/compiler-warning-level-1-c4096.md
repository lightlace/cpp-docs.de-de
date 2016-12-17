---
title: "Compilerwarnung (Stufe 1) C4096"
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
  - "C4096"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4096"
ms.assetid: abf3cca2-2f21-45d8-b025-6b513b00681e
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4096
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**"**   
 ***a* ": die Schnittstelle ist keine COM\-Schnittstelle; wird nicht nach IDL emittiert**  
  
 Eine Schnittstellendefinition, die u. U. als COM\-Schnittstelle fungieren sollte, wurde nicht als COM\-Schnittstelle definiert und wird daher nicht in die IDL\-Datei ausgegeben.  
  
 Eine Liste der Attribute, durch die eine Schnittstelle als COM\-Schnittstelle definiert wird, finden Sie unter [Schnittstellenattribute](../../windows/interface-attributes.md).  
  
 Im folgenden Beispiel wird C4096 generiert:  
  
```  
// C4096.cpp  
// compile with: /W1 /LD  
#include "windows.h"  
[module(name="xx")];  
  
// [object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface a  
{  
};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000002")]  
struct b : a  
{  
};   // C4096, remove coclass or uncomment object  
```