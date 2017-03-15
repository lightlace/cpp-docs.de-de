---
title: "Compilerfehler C2861 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2861"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2861"
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
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