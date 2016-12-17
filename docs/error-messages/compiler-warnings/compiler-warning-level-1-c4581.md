---
title: "Compilerwarnung (Stufe 1) C4581"
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
  - "C4581"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4581"
ms.assetid: 598bcd87-257d-4eb3-94e4-15bb31aadc99
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4581
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Veraltetes Verhalten: '"Zeichenfolge1"' wird zur Verarbeitung des Attributs durch 'Zeichenfolge2' ersetzt  
  
 Dieser Fehler kann infolge einer Verbesserung der Compilerkonformität für Visual C\+\+ 2005 ausgegeben werden, und zwar beim Überprüfen der Parameter für Visual C\+\+\-Attribute.  
  
 In früheren Versionen wurden Attributwerte mit oder ohne Anführungszeichen akzeptiert.  Wenn der Wert eine Enumeration ist, darf er nicht in Anführungszeichen stehen.  
  
## Beispiel  
 Im folgenden Beispiel wird C4581 generiert.  
  
```  
// C4581.cpp  
// compile with: /c /W1  
#include "unknwn.h"  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI : IUnknown {};  
  
[coclass, uuid(12345678-1111-2222-3333-123456789012), threading("free")]   // C4581  
// try the following line instead  
// [coclass, uuid(12345678-1111-2222-3333-123456789012), threading(free)]  
class CSample : public IMyI {};  
```