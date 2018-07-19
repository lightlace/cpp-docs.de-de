---
title: _com_ptr_t::QueryInterface | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c455ce81a869d64b3a9019088028e384c6a06217
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943151"
---
# <a name="comptrtqueryinterface"></a>_com_ptr_t::QueryInterface
**Microsoft-spezifisch**  
  
 Ruft die `QueryInterface` Memberfunktion `IUnknown` für den gekapselten Schnittstellenzeiger auf.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
template<typename _InterfaceType> HRESULT QueryInterface (  
   const IID& iid,  
   _InterfaceType*& p   
) throw ( );  
template<typename _InterfaceType> HRESULT QueryInterface (  
   const IID& iid,  
   _InterfaceType** p  
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 *IID*  
 `IID` eines Schnittstellenzeigers.  
  
 *p*  
 Nicht formatierter Schnittstellenzeiger.  
  
## <a name="remarks"></a>Hinweise  
 Aufrufe `IUnknown::QueryInterface` für den gekapselten Schnittstellenzeiger mit dem angegebenen `IID` und gibt den resultierenden unformatierten Schnittstellenzeiger in *p*. Diese Routine gibt zurück, das HRESULT, um den Erfolg oder Fehler anzuzeigen.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)