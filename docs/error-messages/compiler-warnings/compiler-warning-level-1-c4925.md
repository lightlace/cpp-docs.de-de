---
title: "Compilerwarnung (Stufe 1) C4925"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C4925"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4925"
ms.assetid: a4b206c0-016a-4f28-873a-bb8bb41bad50
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4925
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„method“: Die dispinterface\-Methode kann nicht von einem Skript aufgerufen werden.  
  
 Skriptsprachen können keine VT\_BYREF\-„in“\-Parameter, sondern nur VT\_BYREF\-„out“\-Parameter erstellen.  
  
 Eine weitere Möglichkeit zum Beheben dieser Warnung besteht darin, den Parameter \(in der Definition und Implementierung\) nicht zu einem Zeigertyp zu machen.  
  
 Im folgenden Beispiel wird C4925 generiert.  
  
```  
// C4925.cpp // compile with: /LD /W1 #define _ATL_ATTRIBUTES 1 #include <atlbase.h> #include <atlcom.h> [ module(name="Test")]; [ dispinterface, uuid("00000000-0000-0000-0000-000000000001") ] __interface IDisp { [id(9)] void f([in] int*); }; [ coclass, uuid("00000000-0000-0000-0000-000000000002")  ] struct CDisp : IDisp {   // C4925 void f(int*) {} };  
```