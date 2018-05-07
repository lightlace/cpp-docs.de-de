---
title: 'Idbpropertiesimpl:: GetProperties | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBPropertiesImpl::GetProperties
- IDBPropertiesImpl.GetProperties
- GetProperties
dev_langs:
- C++
helpviewer_keywords:
- GetProperties method
ms.assetid: ab24aebd-366d-49a1-b49b-bb46c6d90f05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ee384683d83845b88cb4026f8ff67f6bb69ba8b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="idbpropertiesimplgetproperties"></a>IDBPropertiesImpl::GetProperties
Gibt die Werte der Eigenschaften in der Datenquelle, von Datenquelleninformationen und Initialisierung Eigenschaftengruppen, die momentan festgelegt sind, auf das Datenquellenobjekt oder die Werte der Eigenschaften in der Gruppe der Initialisierungseigenschaften, die derzeit für festgelegt werden die Enumerator.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(GetProperties)(ULONG cPropertySets,   
   const DBPROPIDSET rgPropertySets[],   
   ULONG * pcProperties,   
   DBPROPSET ** prgProperties);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IDBProperties::GetProperties](https://msdn.microsoft.com/en-us/library/ms714344.aspx) in der *OLE DB Programmer's Reference*.  
  
 Einige Parameter entsprechen den *OLE DB Programmer's Reference* Parameter unterschiedliche Namen verwendet, die in beschriebenen **IDBProperties::GetProperties**:  
  
|OLE DB-Vorlagenparameter|*OLE DB Programmer's Reference* Parameter|  
|--------------------------------|------------------------------------------------|  
|`cPropertySets`|`cPropertyIDSets`|  
|`rgPropertySets`|`rgPropertyIDSets`|  
|*pcProperties*|*pcPropertySets*|  
|*prgProperties*|*prgPropertySets*|  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Anbieter initialisiert wird, gibt diese Methode die Werte der Eigenschaften in der **DBPROPSET_DATASOURCE**, **DBPROPSET_DATASOURCEINFO**, **DBPROPSET_DBINIT** Eigenschaftengruppen, die derzeit für das Datenquellenobjekt festgelegt werden. Wenn der Anbieter nicht initialisiert wurde, gibt es **DBPROPSET_DBINIT** nur Eigenschaften für Gruppe.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IDBPropertiesImpl-Klasse](../../data/oledb/idbpropertiesimpl-class.md)   
 [IDBPropertiesImpl::GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)   
 [IDBPropertiesImpl::SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)