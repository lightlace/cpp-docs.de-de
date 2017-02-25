---
title: "Compilerfehler C3749 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3749"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3749"
ms.assetid: 3d26b468-4757-41b8-b5a2-78022a5295fb
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C3749
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Attribut': Ein benutzerdefiniertes Attribut kann nicht innerhalb einer Funktion verwendet werden  
  
 Ein benutzerdefiniertes Attribut kann nicht innerhalb einer Funktion verwendet werden. \(Weitere Informationen zu benutzerdefinierten Attributen finden Sie unter dem Thema [Attribut](../../windows/attribute.md).\)  
  
 Im folgenden Beispiel wird C3749 generiert:  
  
```  
// C3749a.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::All)]  
public ref struct ABC : public Attribute {  
   ABC() {}  
};  
  
void f1() { [ABC]; };  // C3749  
```  
  
 Im folgenden Beispiel wird C3749 generiert:  
  
```  
// C3749b.cpp  
// compile with: /clr:oldSyntax /c  
using namespace System;  
  
[attribute(All)]  
public __gc struct ABC {  
   ABC() {}  
};  
  
void f1() { [ABC]; };  // C3749  
```