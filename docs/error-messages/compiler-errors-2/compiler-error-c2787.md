---
title: "Compilerfehler C2787 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2787"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2787"
ms.assetid: 34cb57e6-cafe-4ce7-bcc6-53d194629bd0
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C2787
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Keine GUID mit diesem Objekt verbunden  
  
 Der Operator [\_\_uuidof](../../cpp/uuidof-operator.md) akzeptiert entweder einen mit einer GUID verbundenen benutzerdefinierten Typ oder ein Objekt eines solchen benutzerdefinierten Typs.  Dieser Fehler tritt auf, wenn das Argument ein benutzerdefinierter Typ ohne GUID ist.  
  
 Im folgenden Beispiel wird C2787 generiert:  
  
```  
// C2787.cpp  
#include <windows.h>  
struct F {};  
  
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) F2;  
  
int main() {  
   __uuidof(F);   // C2787  
   __uuidof(F2);   // OK  
}  
```