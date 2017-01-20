---
title: "Compilerfehler C3084"
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
  - "C3084"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3084"
ms.assetid: 0362cb70-e24e-476f-a24d-8f5bb97c3afd
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3084
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Funktion": ein Finalizer\/Destruktor kann nicht "Schlüsselwort" sein.  
  
 Ein Finalizer oder Destruktor wurde falsch deklariert.  
  
 Beispielsweise sollte ein Destruktor nicht als versiegelt gekennzeichnet werden.  Abgeleitete Typen können nicht auf den Destruktor zugreifen.  Weitere Informationen finden Sie unter [Explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md) und [Destruktoren und Finalizer in Visual C\+\+](../../misc/destructors-and-finalizers-in-visual-cpp.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3084 generiert.  
  
```  
// C3084.cpp // compile with: /clr /c ref struct R { protected: !R() sealed;   // C3084 !R() abstract;   // C3084 !R(); };  
```