---
title: IDBPropertiesImpl-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBPropertiesImpl
- ATL.IDBPropertiesImpl
- ATL.IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl
dev_langs:
- C++
helpviewer_keywords:
- IDBPropertiesImpl class
ms.assetid: a7f15a8b-95b2-4316-b944-d5d03f8d74ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3685e6a77e4293ef65b5ee98a0aa326500cfdb2d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="idbpropertiesimpl-class"></a>IDBPropertiesImpl-Klasse
Stellt eine Implementierung für die `IDBProperties` Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T>   
class ATL_NO_VTABLE IDBPropertiesImpl   
   : public IDBProperties, public CUtlProps<T>  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IDBPropertiesImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[getProperties](../../data/oledb/idbpropertiesimpl-getproperties.md)|Gibt die Werte der Eigenschaften in der Datenquelle, von Datenquelleninformationen und Initialisierung Eigenschaftengruppen, die momentan festgelegt sind, auf das Datenquellenobjekt oder die Werte der Eigenschaften in der Gruppe der Initialisierungseigenschaften, die derzeit für festgelegt werden die Enumerator.|  
|[GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)|Gibt Informationen zu allen Eigenschaften, die vom Anbieter unterstützt werden.|  
|[SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)|Legt Eigenschaften für Datenquellenobjekte, die Eigenschaftengruppen Datenquelle und Initialisierung oder der Gruppe der Initialisierungseigenschaften, Enumeratoren fest.|  
  
## <a name="remarks"></a>Hinweise  
 [IDBProperties](https://msdn.microsoft.com/en-us/library/ms719607.aspx) ist keine verbindliche Schnittstelle für Datenquellenobjekte und eine optionale Schnittstelle für Enumeratoren. Jedoch, wenn Sie einen Enumerator verfügbar macht [IDBInitialize](https://msdn.microsoft.com/en-us/library/ms713706.aspx), verfügbar machen `IDBProperties`. `IDBPropertiesImpl` implementiert `IDBProperties` mithilfe einer statischen Funktion durch definierten [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)