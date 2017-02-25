---
title: "_bstr_t-Operatoren (relational) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::operator>"
  - "_bstr_t::operator=="
  - "_bstr_t::operator>="
  - "_bstr_t::operator!="
  - "_bstr_t::operator<"
  - "_bstr_t::operator<="
  - "_bstr_t::operator!"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "!=-Operator"
  - "<-Operator, Vergleichen von spezifischen Objekten"
  - "<=-Operator, Mit spezifischen Objekten"
  - "==-Operator, Mit spezifischen Visual C++-Objekten"
  - ">-Operator, Vergleichen von spezifischen Objekten"
  - ">=-Operator, Vergleichen von spezifischen Objekten"
  - "Operator !=, Relationale Operatoren"
  - "Operator <, bstr"
  - "Operator <=, bstr"
  - "Operator ==, bstr"
  - "Operator >, bstr"
  - "Operator >=, bstr"
  - "Operator!=, Relationale Operatoren"
  - "Operator<, bstr"
  - "Operator<=, bstr"
  - "Operator==, bstr"
  - "Operator>=, bstr"
  - "Relationale Operatoren, _bstr_t-Klasse"
ms.assetid: e153da72-37c3-4d8a-b8eb-730d65da64dd
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _bstr_t-Operatoren (relational)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Vergleicht zwei `_bstr_t`\-Objekte.  
  
## Syntax  
  
```  
  
      bool operator!( ) const throw( );   
bool operator==(  
   const _bstr_t& str   
) const throw( );  
bool operator!=(  
   const _bstr_t& str   
) const throw( );  
bool operator<(  
   const _bstr_t& str   
) const throw( );  
bool operator>(  
   const _bstr_t& str   
) const throw( );  
bool operator<=(  
   const _bstr_t& str   
) const throw( );  
bool operator>=(  
   const _bstr_t& str   
) const throw( );  
```  
  
## Hinweise  
 Diese Operatoren vergleichen zwei `_bstr_t`\-Objekte auf lexikografischer Ebene.  Die Operatoren geben **true** an, wenn die Vergleiche stimmen; andernfalls geben sie **false** zurück.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_bstr\_t\-Klasse](../cpp/bstr-t-class.md)