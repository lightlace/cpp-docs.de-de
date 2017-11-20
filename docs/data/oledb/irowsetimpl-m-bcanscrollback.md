---
title: 'IRowsetImpl:: M_bcanscrollback | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetImpl::m_bCanScrollBack
- ATL::IRowsetImpl::m_bCanScrollBack
- IRowsetImpl.m_bCanScrollBack
- ATL.IRowsetImpl.m_bCanScrollBack
- m_bCanScrollBack
dev_langs: C++
helpviewer_keywords: m_bCanScrollBack
ms.assetid: 69de3179-bf56-415e-935f-e98bcb34debe
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e64e0b63e3ddb06303f50bb774d736718ae59639
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetimplmbcanscrollback"></a>IRowsetImpl::m_bCanScrollBack
Gibt an, ob ein Anbieter die Cursor einen Bildlauf rückwärts aufweisen kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
unsigned  m_bCanScrollBack:1;  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Verknüpft die **DBPROP_CANSCROLLBACKWARDS** Eigenschaft in der **DBPROPSET_ROWSET** Gruppe. Der Anbieter muss unterstützen **DBPROP_CANSCROLLBACKWARDS** für **M_bCanFetchBackwards** auf "true" sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetImpl-Klasse](../../data/oledb/irowsetimpl-class.md)   
 [IRowsetImpl::m_bCanFetchBack](../../data/oledb/irowsetimpl-m-bcanfetchback.md)