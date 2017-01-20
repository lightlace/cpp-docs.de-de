---
title: "_variant_t-Operatoren (relational)"
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
  - "_variant_t::operator=="
  - "_variant_t.operator!="
  - "_variant_t::operator!="
  - "_variant_t.operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "!=-Operator"
  - "==-Operator, Mit spezifischen Visual C++-Objekten"
  - "Operator !=, Relationale Operatoren"
  - "Operator !=, variant"
  - "Operator ==, variant"
  - "Operator!=, Relationale Operatoren"
  - "Operator!=, variant"
  - "Operator==, variant"
  - "Relationale Operatoren, _variant_t-Klasse"
ms.assetid: 141bacb8-41a2-44dd-b3c0-4ad1f884f4ea
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# _variant_t-Operatoren (relational)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Überprüft zwei `_variant_t`\-Objekte auf Gleichheit bzw. Ungleichheit.  
  
## Syntax  
  
```  
  
      bool operator==(  
   const VARIANT& varSrc   
) const;  
bool operator==(  
   const VARIANT* pSrc   
) const;  
bool operator!=(  
   const VARIANT& varSrc   
) const;  
bool operator!=(  
   const VARIANT* pSrc   
) const;  
```  
  
#### Parameter  
 *varSrc*  
 Ein **VARIANT**\-Objekt, das mit dem `_variant_t`\-Objekt verglichen werden soll.  
  
 `pSrc`  
 Zeiger auf das **VARIANT**\-Objekt, das mit dem `_variant_t`\-Objekt verglichen werden soll.  
  
## Rückgabewert  
 Gibt **true** zurück, wenn der Vergleich zu einer Übereinstimmung führt; andernfalls **false**.  
  
## Hinweise  
 Vergleicht ein `_variant_t`\-Objekt mit einem **VARIANT**\-Objekt und testet auf Gleichheit oder Ungleichheit.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_variant\_t\-Klasse](../cpp/variant-t-class.md)