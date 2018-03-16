---
title: _com_ptr_t-extraktoren | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::operatorInterface&
- _com_ptr_t::operatorbool
- _com_ptr_t::operator->
- _com_ptr_t::operator*
dev_langs:
- C++
helpviewer_keywords:
- operator Interface& [C++]
- '* operator [C++], with specific objects'
- operator& [C++]
- operator* [C++]
- -> operator [C++], with specific objects
- '& operator [C++], with specific objects'
- operator Interface* [C++]
- operator * [C++]
- operator->
- operator bool
- extractors, _com_ptr_t class
- extractors [C++]
ms.assetid: 194b9e0e-123c-49ff-a187-0a7fcd68145a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1c006c18b9e00e5c79ff686dfb31fa9ccf56fd4e
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2018
---
# <a name="comptrt-extractors"></a>_com_ptr_t-Extraktoren
**Microsoft-spezifisch**  
  
 Extrahieren Sie den gekapselten COM-Schnittstellenzeiger.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      operator Interface*( ) const throw( );   
operator Interface&( ) const;   
Interface& operator*( ) const;   
Interface* operator->( ) const;   
Interface** operator&( ) throw( );   
operator bool( ) const throw( );  
```  
  
## <a name="remarks"></a>Hinweise  
  
-   **Operator Interface\* ** gibt den gekapselten Schnittstellenzeiger, der möglicherweise **NULL**.  
  
-   **Operator Interface &** gibt einen Verweis auf den gekapselten Schnittstellenzeiger und gibt einen Fehler aus, wenn der Zeiger **NULL**.  
  
-   **Operator\* ** ermöglicht es einem intelligenten Zeigerobjekt fungieren, als wäre es die tatsächliche gekapselte Schnittstelle beim Dereferenzieren.  
  
-   **Operator ->** ermöglicht es einem intelligenten Zeigerobjekt fungieren, als wäre es die tatsächliche gekapselte Schnittstelle beim Dereferenzieren.  
  
-   **Operator &** gibt jeden gekapselten Schnittstellenzeiger, ersetzt ihn durch frei **NULL**, und gibt die Adresse des gekapselten Zeigers zurück. Dies ermöglicht es den intelligenten Zeiger, durch die Adresse an eine Funktion übergeben zu werden, ein **out** Parameter, die über den er gibt einen Schnittstellenzeiger zurück.  
  
-   **Operator Bool** ermöglicht es einem intelligenten Zeigerobjekt, die in einem bedingten Ausdruck verwendet werden. Dieser Operator gibt **"true"** ist der Zeiger nicht **NULL**.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)