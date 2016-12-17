---
title: "_bstr_t::operator ="
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
  - "_bstr_t::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "=-Operator, Mit spezifischen Visual C++-Objekten"
  - "Operator =, bstr"
  - "Operator=, bstr"
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t::operator =
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Weist einem vorhandenen `_bstr_t`\-Objekt einen neuen Wert zu.  
  
## Syntax  
  
```  
  
      _bstr_t& operator=(  
   const _bstr_t& s1   
) throw ( );  
_bstr_t& operator=(  
   const char* s2   
);  
_bstr_t& operator=(  
   const wchar_t* s3   
);  
_bstr_t& operator=(  
   const _variant_t& var   
);  
```  
  
#### Parameter  
 *s1*  
 Ein `_bstr_t`\-Objekt, das einem vorhandenen `_bstr_t`\-Objekt zugewiesen werden soll.  
  
 *s2*  
 Eine Multibyte\-Zeichenfolge, die einem vorhandenen `_bstr_t` Objekt zugewiesen werden soll.  
  
 `s3`  
 Eine Unicode\-Zeichenfolge, die einem vorhandenen `_bstr_t` Objekt zugewiesen werden soll.  
  
 `var`  
 Ein `_variant_t`\-Objekt, das einem vorhandenen `_bstr_t`\-Objekt zugewiesen werden soll.  
  
 **END Microsoft\-spezifisch**  
  
## Beispiel  
 Unter [\_bstr\_t::Assign](../cpp/bstr-t-assign.md) finden Sie ein Beispiel für die Verwendung von `operator=`.  
  
## Siehe auch  
 [\_bstr\_t\-Klasse](../cpp/bstr-t-class.md)