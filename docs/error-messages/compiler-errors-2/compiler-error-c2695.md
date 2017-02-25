---
title: "Compilerfehler C2695 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2695"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2695"
ms.assetid: 3f6f2091-c38b-40ea-ab6c-f1846f5702d7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2695
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion1': Die überschreibende virtuelle Funktion unterscheidet sich von 'Funktion2' nur durch die Aufrufkonvention  
  
 Durch die Signatur einer Funktion in einer abgeleiteten Klasse kann eine Funktion innerhalb einer Basisklasse nicht überschrieben und auch keine Aufrufkonvention geändert werden.  
  
 Im folgenden Beispiel wird C2695 generiert:  
  
```  
// C2695.cpp  
class C {  
   virtual void __fastcall func();  
};  
  
class D : public C {  
   virtual void __clrcall func();   // C2695  
};  
```