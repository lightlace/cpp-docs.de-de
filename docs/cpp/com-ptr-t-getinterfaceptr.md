---
title: _com_ptr_t::GetInterfacePtr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_ptr_t::GetInterfacePtr
dev_langs: C++
helpviewer_keywords: GetInterfacePtr method [C++]
ms.assetid: 55e3e2c7-c939-48b5-a905-4b9cbefeea7e
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8d570b7d1d25ee14b0cabd5ecec02d6f7d1573d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="comptrtgetinterfaceptr"></a>_com_ptr_t::GetInterfacePtr
**Microsoft-spezifisch**  
  
 Gibt den gekapselten Schnittstellenzeiger zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      Interface* GetInterfacePtr( ) const throw( );   
Interface*& GetInterfacePtr() throw();  
```  
  
## <a name="remarks"></a>Hinweise  
 Gibt den gekapselten Schnittstellenzeiger, der möglicherweise **NULL**.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)