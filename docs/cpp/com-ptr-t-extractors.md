---
title: _com_ptr_t-extraktoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b0bfe0cdb5ea9dd524f2e81fcb2719bf40001758
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943639"
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
  
-   **Operator Interface\***  gibt den gekapselten Schnittstellenzeiger, der NULL sein kann.  
  
-   **Operator Interface &** gibt einen Verweis auf den gekapselten Schnittstellenzeiger und gibt einen Fehler aus, wenn der Zeiger NULL ist.  
  
-   **Operator\***  ermöglicht es einem intelligenten Zeigerobjekt, fungiert, als wäre es die tatsächliche gekapselte Schnittstelle beim Dereferenzieren.  
  
-   **Operator ->** ermöglicht es einem intelligenten Zeigerobjekt, fungiert, als wäre es die tatsächliche gekapselte Schnittstelle beim Dereferenzieren.  
  
-   **Operator &** gibt jeden gekapselten Schnittstellenzeiger, der sie durch NULL ersetzen und gibt die Adresse des gekapselten Zeigers zurück. Dadurch wird den intelligenten Zeiger als Adresse an eine Funktion übergeben wird, die eine *out* Parameter, die durch die es gibt einen Schnittstellenzeiger zurück.  
  
-   **Operator Bool** ermöglicht es einem intelligenten Zeigerobjekt, die in einem bedingten Ausdruck verwendet werden. Dieser Operator gibt TRUE zurück, wenn der Zeiger nicht NULL ist.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)