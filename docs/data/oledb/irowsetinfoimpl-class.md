---
title: IRowsetInfoImpl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetInfoImpl
- IRowsetInfoImpl
- ATL::IRowsetInfoImpl
dev_langs: C++
helpviewer_keywords: IRowsetInfoImpl class
ms.assetid: 9c654155-7727-464e-bd31-143e68391a47
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cba03cfdda0b7a55c8f4719d5340566ee5dc6050
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetinfoimpl-class"></a>IRowsetInfoImpl-Klasse
Stellt eine Implementierung für die [IRowsetInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx) Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```  
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