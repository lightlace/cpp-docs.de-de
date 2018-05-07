---
title: IColumnsInfoImpl-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IColumnsInfoImpl<T>
- ATL::IColumnsInfoImpl
- IColumnsInfoImpl
- ATL.IColumnsInfoImpl
- ATL::IColumnsInfoImpl<T>
dev_langs:
- C++
helpviewer_keywords:
- IColumnsInfoImpl class
ms.assetid: ba74c1c5-2eda-4452-8b57-84919fa0d066
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 93cc4c44031d2091de64f2d82c1866135d1702cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icolumnsinfoimpl-class"></a>IColumnsInfoImpl-Klasse
Stellt eine Implementierung von der [IColumnsInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx) Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
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