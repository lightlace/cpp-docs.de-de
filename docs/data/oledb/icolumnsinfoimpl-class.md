---
title: IColumnsInfoImpl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IColumnsInfoImpl<T>
- ATL::IColumnsInfoImpl
- IColumnsInfoImpl
- ATL.IColumnsInfoImpl
- ATL::IColumnsInfoImpl<T>
dev_langs: C++
helpviewer_keywords: IColumnsInfoImpl class
ms.assetid: ba74c1c5-2eda-4452-8b57-84919fa0d066
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 18d23120a4a84f9d637a50e379a579389354ff08
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="icolumnsinfoimpl-class"></a>IColumnsInfoImpl-Klasse
Stellt eine Implementierung von der [IColumnsInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx) Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class T>  
class ATL_NO_VTABLE IColumnsInfoImpl :   
   public IColumnsInfo,    
   public CDBIDOps  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IColumnsInfoImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[GetColumnInfo](../../data/oledb/icolumnsinfoimpl-getcolumninfo.md)|Gibt die von den meisten Consumern benötigte Spaltenmetadaten zurück.|  
|[MapColumnIDs](../../data/oledb/icolumnsinfoimpl-mapcolumnids.md)|Gibt ein Array von Ordinalzahlen der Spalten in einem Rowset, das durch die angegebenen Spalten-IDs gekennzeichnet sind.|  
  
## <a name="remarks"></a>Hinweise  
 Keine verbindliche Schnittstelle für Rowsets und Befehle. So ändern Sie das Verhalten Ihres Anbieters `IColumnsInfo` Implementierung müssen Sie die Anbieter-Spalte-Zuordnung zu ändern.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)