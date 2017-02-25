---
title: "Compilerfehler C3115 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3115"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3115"
ms.assetid: 51726145-9782-4ec9-84b9-286f366d9cbd
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Compilerfehler C3115
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Attribut' : Dieses Attribut ist für 'Konstrukt' nicht zulässig  
  
 Ein Attribut wurde auf ein Konstrukt angewendet, für das es nicht vorgesehen ist.  Weitere Informationen finden Sie unter [Attributes by Usage](../../windows/attributes-by-usage.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3115 generiert.  
  
```  
// C3115.cpp  
// compile with: /c  
#include <unknwn.h>  
[module(name="xx")];  
  
[object, helpstringdll(xx.dll), uuid("00000000-0000-0000-0000-000000000001")]   // C3115  
// try the following line instead  
// [object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI {  
   HRESULT xx();  
};  
```