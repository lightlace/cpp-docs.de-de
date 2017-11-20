---
title: "Compilerwarnung (Stufe 1) C4489 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4489"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4489"
ms.assetid: 43b51c8c-27b5-44c9-b974-fe4b48f4896f
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# Compilerwarnung (Stufe 1) C4489
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Spezifizierer': Nicht zulässig für die Schnittstellenmethode 'Methode'; Überschreibungsspezifizierer sind nur für Verweisklassen\- und Werteklassenmethoden zulässig  
  
 Ein Spezifiziererschlüsselwort wurde für eine Schnittstellenmethode falsch verwendet.  
  
 Weitere Informationen finden Sie unter [Überschreibungsspezifizierer](../../windows/override-specifiers-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C4489 generiert.  
  
```  
// C4489.cpp  
// compile with: /clr /c /W1  
public interface class I {   
   void f() new;   // C4489  
   virtual void b() override;   // C4489  
  
   void g();   // OK  
};  
```