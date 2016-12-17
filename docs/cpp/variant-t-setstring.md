---
title: "_variant_t::SetString"
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
  - "_variant_t::SetString"
  - "_variant_t.SetString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetString-Methode"
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
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