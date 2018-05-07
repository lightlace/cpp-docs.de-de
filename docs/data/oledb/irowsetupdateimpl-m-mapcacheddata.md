---
title: 'IRowsetUpdateImpl:: M_mapcacheddata | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetUpdateImpl.m_mapCachedData
- IRowsetUpdateImpl::m_mapCachedData
- m_mapCachedData
dev_langs:
- C++
helpviewer_keywords:
- m_mapCachedData
ms.assetid: 65131743-8580-48c8-bb22-68f17c9dfa13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bd19f8706e50d1eefb26dadfb837d8bd4f13f061
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetupdateimplmmapcacheddata"></a>IRowsetUpdateImpl::m_mapCachedData
Eine Karte mit den ursprünglichen Daten für die verzögerte Ausführung.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
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