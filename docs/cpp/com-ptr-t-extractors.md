---
title: "_com_ptr_t-Extraktoren | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t::operatorInterface&"
  - "operatorInterface*"
  - "operatorInterface&"
  - "_com_ptr_t::operatorbool"
  - "_com_ptr_t.operator->"
  - "_com_ptr_t.operator*"
  - "_com_ptr_t::operator->"
  - "_com_ptr_t::operator*"
  - "_com_ptr_t.operatorInterface&"
  - "_com_ptr_t.operatorbool"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "&-Operator, Mit spezifischen Objekten"
  - "*-Operator, Mit spezifischen Objekten"
  - "->-Operator, Mit spezifischen Objekten"
  - "Extraktoren"
  - "Extraktoren, _com_ptr_t-Klasse"
  - "Operator *"
  - "operator bool"
  - "Operator Interface&"
  - "Operator Interface*"
  - "Operator&"
  - "Operator*"
  - "Operator->"
ms.assetid: 194b9e0e-123c-49ff-a187-0a7fcd68145a
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_ptr_t-Extraktoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Extrahieren Sie den gekapselten COM\-Schnittstellenzeiger.  
  
## Syntax  
  
```  
  
      operator Interface*( ) const throw( );   
operator Interface&( ) const;   
Interface& operator*( ) const;   
Interface* operator->( ) const;   
Interface** operator&( ) throw( );   
operator bool( ) const throw( );  
```  
  
## Hinweise  
  
-   **operator Interface\*** Gibt den gekapselten Schnittstellenzeiger zurück, der möglicherweise **NULL** ist.  
  
-   **operator Interface&** Gibt einen Verweis auf den gekapselten Schnittstellenzeiger zurück, und gibt eine Fehlermeldung heraus, wenn der Zeiger **NULL** ist.  
  
-   **operator\*** Ermöglicht es einem intelligenten Zeigerobjekt, so zu fungieren, als wäre es die tatsächliche gekapselte Schnittstelle beim Dereferenzieren.  
  
-   **operator\-\>** Ermöglicht es einem intelligenten Zeigerobjekt, so zu fungieren, als wäre es die tatsächliche gekapselte Schnittstelle beim Dereferenzieren.  
  
-   **operator&** Gibt jeden gekapselten Schnittstellenzeiger frei, ersetzt ihn durch **NULL** und gibt die Adresse des gekapselten Zeigers zurück.  Dies ermöglicht es dem intelligenten Zeiger, durch eine Adresse einer Funktion übergeben zu werden, die einen **out**\-Parameter hat, durch den sie einen Schnittstellenzeiger zurückgibt.  
  
-   **operator bool** Ermöglicht die Verwendung eines intelligenten Zeigerobjekts in einem bedingten Ausdruck.  Dieser Operator gibt **true** zurück, wenn der Zeiger nicht **NULL** ist.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_com\_ptr\_t\-Klasse](../cpp/com-ptr-t-class.md)