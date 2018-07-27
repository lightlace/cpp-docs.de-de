---
title: ICommandPropertiesImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandPropertiesImpl
- ATL.ICommandPropertiesImpl
- ATL::ICommandPropertiesImpl
- ICommandPropertiesImpl::GetProperties
- ICommandPropertiesImpl.GetProperties
- GetProperties
- ICommandPropertiesImpl.SetProperties
- ICommandPropertiesImpl::SetProperties
- SetProperties
dev_langs:
- C++
helpviewer_keywords:
- ICommandPropertiesImpl class
- GetProperties method
- SetProperties method
ms.assetid: b3cf6aea-527e-4f0d-96e0-669178b021a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 13f170aa27cdc52b98729b0953568575292f6f6b
ms.sourcegitcommit: b0d6777cf4b580d093eaf6104d80a888706e7578
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2018
ms.locfileid: "39269585"
---
# <a name="icommandpropertiesimpl-class"></a>ICommandPropertiesImpl-Klasse
Stellt eine Implementierung der [ICommandProperties](https://msdn.microsoft.com/library/ms723044.aspx) Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ICommandPropertiesImpl   
   : public ICommandProperties, public CUtlProps<PropClass>  
```  
  
### <a name="parameters"></a>Parameter  
 *T*  
 Der Klasse abgeleitet  
  
 *PropClass*  
 Ihre Eigenschaftenklasse.  

## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="members"></a>Member  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[GetProperties](#getproperties)|Gibt die Liste der Eigenschaften in der Gruppe der Rowset-Eigenschaften, die derzeit für das Rowset angefordert werden.|  
|[SetProperties](#setproperties)|Legt die Eigenschaften in der Gruppe der Rowset-Eigenschaften fest.|  
  
## <a name="remarks"></a>Hinweise  
 Dies ist obligatorisch einschaltbefehle. Die Implementierung erfolgt durch eine statische Funktion, die definiert, die von der [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) Makro.  

## <a name="getproperties"></a> Icommandpropertiesimpl:: GetProperties
Gibt alle angeforderten Eigenschaftensätze, die mithilfe des Befehlsparameters eigenschaftenzuordnung zurück.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(GetProperties)(const ULONG cPropertyIDSets,   
   const DBPROPIDSET rgPropertyIDSets[],   
   ULONG * pcPropertySets,   
   DBPROPSET ** prgPropertySets);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [ICommandProperties:: GetProperties](https://msdn.microsoft.com/library/ms723119.aspx) in die *OLE DB-Programmierreferenz*.  
  
### <a name="remarks"></a>Hinweise  
 Siehe [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  
  
## <a name="setproperties"></a> Icommandpropertiesimpl:: SetProperties
Stellt Eigenschaften für das Command-Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(SetProperties)(ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [ICommandProperties:: SetProperties](https://msdn.microsoft.com/library/ms711497.aspx) in die *OLE DB-Programmierreferenz*.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)
