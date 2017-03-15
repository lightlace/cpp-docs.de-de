---
title: "_variant_t::SetString | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t::SetString"
  - "_variant_t.SetString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetString-Methode"
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _variant_t::SetString
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Weist diesem `_variant_t`\-Objekt eine Zeichenfolge zu.  
  
## Syntax  
  
```  
  
      void SetString(  
   const char* pSrc   
);  
```  
  
#### Parameter  
 `pSrc`  
 Zeiger auf die Zeichenfolge.  
  
## Hinweise  
 Konvertiert eine Zeichenfolge mit ANSI\-Zeichen in eine Unicode\-`BSTR`\-Zeichenfolge und weist sie diesem `_variant_t`\-Objekt zu.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_variant\_t\-Klasse](../cpp/variant-t-class.md)