---
title: "Compilerfehler C2861"
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
  - "C2861"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2861"
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2861
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktionsname' : Eine Schnittstellen\-Memberfunktion kann nicht definiert werden  
  
 Der Compiler hat das interface\-Schlüsselwort gefunden oder eine Struktur als Schnittstelle abgeleitet, traf dann jedoch auf eine Memberfunktionsdefinition.  Eine Schnittstelle kann keine Definition für eine Memberfunktion enthalten.  
  
## Beispiel  
 Im folgenden Beispiel wird C2861 generiert:  
  
```  
// C2861.cpp  
// compile with: /c  
#include <objbase.h>   // required for IUnknown definition  
[ object, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface IMyInterface : IUnknown {  
   HRESULT mf(int a);  
};  
  
HRESULT IMyInterface::mf(int a) {}   // C2861  
  
```