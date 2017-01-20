---
title: "_bstr_t::Attach"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::Attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Attach-Methode"
ms.assetid: 8cad867e-40fc-435b-841f-0d412c2f58d3
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t::Attach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Verknüpft einen `_bstr_t`\-Wrapper mit einem `BSTR`.  
  
## Syntax  
  
```  
  
      void Attach(  
   BSTR s  
);  
```  
  
#### Parameter  
 *s*  
 Eine `_bstr_t`\-Variable, die `BSTR` zugeordnet oder zugewiesen werden soll.  
  
## Hinweise  
 Wenn `_bstr_t` zuvor an einen anderen `BSTR` angefügt war, bereinigt `_bstr_t` die `BSTR`\-Ressource, wenn keine anderen `_bstr_t`\-Variablen den `BSTR` verwenden.  
  
## Beispiel  
 Ein Beispiel für die Verwendung von **Anfügen** erhalten Sie unter [\_bstr\_t::Assign](../cpp/bstr-t-assign.md).  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_bstr\_t\-Klasse](../cpp/bstr-t-class.md)