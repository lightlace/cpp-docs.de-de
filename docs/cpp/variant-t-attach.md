---
title: "_variant_t::Attach | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t::Attach"
  - "_variant_t.Attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Attach-Methode"
  - "VARIANT-Objekt"
  - "VARIANT-Objekt, attach"
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _variant_t::Attach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Fügt ein **VARIANT**\-Objekt an das `_variant_t`\-Objekt an.  
  
## Syntax  
  
```  
  
      void Attach(  
   VARIANT& varSrc   
);  
```  
  
#### Parameter  
 *varSrc*  
 Ein an dieses `_variant_t`\-Objekt anzufügendes  **VARIANT**\-Objekt.  
  
## Hinweise  
 Übernimmt den Besitz des **VARIANT**\-Objekts durch Kapselung.  Diese Memberfunktion gibt jedes vorhandene gekapselte **VARIANT**\-Objekt frei und kopiert dann das angegebene **VARIANT**\-Objekt und legt den **VARTYPE** auf `VT_EMPTY` fest, um sicherzustellen, dass seine Ressourcen nur vom Destruktor `_variant_t` freigegeben werden können.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_variant\_t\-Klasse](../cpp/variant-t-class.md)