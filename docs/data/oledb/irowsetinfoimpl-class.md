---
title: IRowsetInfoImpl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetInfoImpl
- IRowsetInfoImpl
- ATL::IRowsetInfoImpl
dev_langs:
- C++
helpviewer_keywords:
- IRowsetInfoImpl class
ms.assetid: 9c654155-7727-464e-bd31-143e68391a47
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 659d3d55635f957ffab2893f2a042564d62abad1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="irowsetinfoimpl-class"></a>IRowsetInfoImpl-Klasse
Stellt eine Implementierung für die [IRowsetInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx) Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T, class PropClass = T>  
class ATL_NO_VTABLE IRowsetInfoImpl :   
   public IRowsetInfo,    
   public CUtlProps<PropClass>  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IRowsetInfoImpl`.  
  
 `PropClass`  
 Eine benutzerdefinierbare Eigenschaftsklasse, die standardmäßig `T`.  
  
## <a name="members"></a>Member  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/irowsetinfoimpl-getproperties.md)|Gibt die aktuellen Einstellungen aller Eigenschaften, die vom Rowset unterstützt wird.|  
|[GetReferencedRowset](../../data/oledb/irowsetinfoimpl-getreferencedrowset.md)|Gibt einen Schnittstellenzeiger auf das Rowset ein Lesezeichen gilt zurück.|  
|[GetSpecification](../../data/oledb/irowsetinfoimpl-getspecification.md)|Gibt einen Schnittstellenzeiger auf das Objekt (Befehl oder Sitzung), die dieses Rowset erstellt.|  
  
## <a name="remarks"></a>Hinweise  
 Keine verbindliche Schnittstelle für Rowsets. Diese Klasse implementiert die Rowseteigenschaften mit dem [Satz eigenschaftenzuordnung](../../data/oledb/begin-propset-map.md) in Ihre Befehlsklasse definiert. Obwohl die Rowsetklasse angezeigt wird, legt die Befehlsklasse-Eigenschaft verwenden, wird das Rowset mit eine eigene Kopie der Laufzeiteigenschaften bereitgestellt, während der Erstellung von einem Befehl oder Session-Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** altdb.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)