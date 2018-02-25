---
title: IDBPropertiesImpl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e1b1486d5eff73b4f868f5990ceb628cfb7dd20a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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
|[GetProperties](../../data/oledb/idbpropertiesimpl-getproperties.md)|Gibt die Werte der Eigenschaften in der Datenquelle, von Datenquelleninformationen und Initialisierung Eigenschaftengruppen, die momentan festgelegt sind, auf das Datenquellenobjekt oder die Werte der Eigenschaften in der Gruppe der Initialisierungseigenschaften, die derzeit für festgelegt werden die Enumerator.|  
|[GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)|Gibt Informationen zu allen Eigenschaften, die vom Anbieter unterstützt werden.|  
|[SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)|Legt Eigenschaften für Datenquellenobjekte, die Eigenschaftengruppen Datenquelle und Initialisierung oder der Gruppe der Initialisierungseigenschaften, Enumeratoren fest.|  
  
## <a name="remarks"></a>Hinweise  
 [IDBProperties](https://msdn.microsoft.com/en-us/library/ms719607.aspx) ist keine verbindliche Schnittstelle für Datenquellenobjekte und eine optionale Schnittstelle für Enumeratoren. Jedoch, wenn Sie einen Enumerator verfügbar macht [IDBInitialize](https://msdn.microsoft.com/en-us/library/ms713706.aspx), verfügbar machen `IDBProperties`. `IDBPropertiesImpl` implementiert `IDBProperties` mithilfe einer statischen Funktion durch definierten [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)