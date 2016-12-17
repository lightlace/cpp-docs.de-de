---
title: "Compilerfehler C3420"
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
  - "C3420"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3420"
ms.assetid: 99b53c77-f36b-4574-9199-b53111becccb
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3420
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Finalizer": Ein Finalizer kann nicht virtuell sein.  
  
 Ein Finalizer kann von seinem einschließenden Typ nur nicht virtuell aufgerufen werden. Aus diesem Grund wird die Deklaration eines Finalizers als Fehler angesehen.  
  
 Weitere Informationen finden Sie unter [Destruktoren und Finalizer in Visual C\+\+](../../misc/destructors-and-finalizers-in-visual-cpp.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3420 generiert.  
  
```  
// C3420.cpp // compile with: /clr /c ref class R { virtual !R() {}   // C3420 };  
```