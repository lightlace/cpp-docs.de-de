---
title: 'IRowsetUpdateImpl:: M_mapcacheddata | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetUpdateImpl.m_mapCachedData
- IRowsetUpdateImpl::m_mapCachedData
- m_mapCachedData
dev_langs: C++
helpviewer_keywords: m_mapCachedData
ms.assetid: 65131743-8580-48c8-bb22-68f17c9dfa13
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c3b48a309d10d232eb311b66602e61ff727cdef7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetupdateimplmmapcacheddata"></a>IRowsetUpdateImpl::m_mapCachedData
Eine Karte mit den ursprünglichen Daten für die verzögerte Ausführung.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      CAtlMap<   
   HROW hRow,    
   Storage* pData   
>   
m_mapCachedData;  
```  
  
#### <a name="parameters"></a>Parameter  
 `hRow`  
 Handle für die Zeilen für die Daten.  
  
 `pData`  
 Ein Zeiger auf die Daten zwischengespeichert werden soll. Die Daten sind vom Typ *Speicher* (die Benutzerdatensatz-Klasse). Finden Sie unter der *Speicher* Vorlagenargument in [IRowsetUpdateImpl-Klasse](../../data/oledb/irowsetupdateimpl-class.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetUpdateImpl-Klasse](../../data/oledb/irowsetupdateimpl-class.md)