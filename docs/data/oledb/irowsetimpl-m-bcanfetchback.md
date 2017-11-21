---
title: 'IRowsetImpl:: M_bcanfetchback | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetImpl.m_bCanFetchBack
- ATL::IRowsetImpl::m_bCanFetchBack
- IRowsetImpl.m_bCanFetchBack
- IRowsetImpl::m_bCanFetchBack
- m_bCanFetchBack
dev_langs: C++
helpviewer_keywords: m_bCanFetchBack
ms.assetid: cfa007b0-7ba5-48a3-9d05-9f1916305fb7
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 09440f8453fe0ee13297c600b148927bacafc5da
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetimplmbcanfetchback"></a>IRowsetImpl::m_bCanFetchBack
Gibt an, ob ein Anbieter rückwärts abrufen unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
unsigned m_bCanFetchBack:1;  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Verknüpft die **DBPROP_CANFETCHBACKWARDS** Eigenschaft in der **DBPROPSET_ROWSET** Gruppe. Der Anbieter muss unterstützen **DBPROP_CANFETCHBACKWARDS** für **M_bCanFetchBackwards** auf "true" sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetImpl-Klasse](../../data/oledb/irowsetimpl-class.md)   
 [IRowsetImpl::m_bCanScrollBack](../../data/oledb/irowsetimpl-m-bcanscrollback.md)