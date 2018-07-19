---
title: 'Idbpropertiesimpl:: SetProperties | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBPropertiesImpl.SetProperties
- SetProperties
- IDBPropertiesImpl::SetProperties
dev_langs:
- C++
helpviewer_keywords:
- SetProperties method
ms.assetid: 2f9fc1de-7f35-4bca-bab3-7b427bf92c26
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5067173da531bb8a4f437666ccfc9c9c61bb47f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106478"
---
# <a name="idbpropertiesimplsetproperties"></a>IDBPropertiesImpl::SetProperties
Legt Eigenschaften für Datenquellenobjekte, die Eigenschaftengruppen Datenquelle und Initialisierung oder der Gruppe der Initialisierungseigenschaften, Enumeratoren fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(SetProperties)(ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IDBProperties:: SetProperties](https://msdn.microsoft.com/en-us/library/ms723049.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Anbieter initialisiert wird, legt diese Methode die Werte der Eigenschaften in der **DBPROPSET_DATASOURCE**, **DBPROPSET_DATASOURCEINFO**, **DBPROPSET_DBINIT** Eigenschaft Gruppen für das Datenquellenobjekt. Wenn der Anbieter nicht initialisiert wurde, wird **DBPROPSET_DBINIT** nur Eigenschaften für Gruppe.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IDBPropertiesImpl-Klasse](../../data/oledb/idbpropertiesimpl-class.md)   
 [IDBPropertiesImpl::GetProperties](../../data/oledb/idbpropertiesimpl-getproperties.md)   
 [IDBPropertiesImpl::GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)