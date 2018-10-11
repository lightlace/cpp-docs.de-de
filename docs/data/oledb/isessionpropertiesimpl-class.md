---
title: ISessionPropertiesImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ISessionPropertiesImpl
- ISessionPropertiesImpl::GetProperties
- ISessionPropertiesImpl.GetProperties
- GetProperties
- ISessionPropertiesImpl.SetProperties
- SetProperties
- ISessionPropertiesImpl::SetProperties
dev_langs:
- C++
helpviewer_keywords:
- ISessionPropertiesImpl class
- GetProperties method
- SetProperties method
ms.assetid: ca0ba254-c7dc-4c52-abec-cf895a0c6a63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 34daf1f1c8624206070c73c9f012192c8b3dec66
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49082630"
---
# <a name="isessionpropertiesimpl-class"></a>ISessionPropertiesImpl-Klasse

Stellt eine Implementierung der [ISessionProperties](/previous-versions/windows/desktop/ms713721) Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ISessionPropertiesImpl :  
   public ISessionProperties,    
   public CUtlProps<PropClass>  
```  
  
### <a name="parameters"></a>Parameter  

*T*<br/>
Abgeleitet von die Klasse `ISessionPropertiesImpl`.  
  
*PropClass*<br/>
Eine mit benutzerdefinierbaren-Eigenschaftsklasse, die standardmäßig *T*.  

## <a name="requirements"></a>Anforderungen  

**Header:** „atldb.h“  
  
## <a name="members"></a>Member  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[GetProperties](#getproperties)|Gibt die Liste der Eigenschaften in der Sitzung-Eigenschaftengruppe, die derzeit für die Sitzung festgelegt sind.|  
|[SetProperties](#setproperties)|Legt die Eigenschaften in der Eigenschaftengruppe Sitzung fest.|  
  
## <a name="remarks"></a>Hinweise  

Eine erforderliche Schnittstelle für Sitzungen. Diese Klasse implementiert die Eigenschaften der leistungssitzung durch Aufrufen der statische Funktion definiert, die von der [Satz eigenschaftenzuordnung](../../data/oledb/begin-propset-map.md). Die Set-eigenschaftenzuordnung sollte in Ihrer Sitzungsklasse angegeben werden.  
  
## <a name="getproperties"></a> Isessionpropertiesimpl:: GetProperties

Gibt die Liste der Eigenschaften in der `DBPROPSET_SESSION` Eigenschaftengruppe, die derzeit für die Sitzung festgelegt sind.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
STDMETHOD(GetProperties)(ULONG cPropertyIDSets,   
   const DBPROPIDSET rgPropertyIDSets[],   
   ULONG * pcPropertySets,   
   DBPROPSET ** prgPropertySets);  
```  
  
#### <a name="parameters"></a>Parameter  

Finden Sie unter [ISessionProperties::GetProperties](/previous-versions/windows/desktop/ms723643) in die *OLE DB-Programmierreferenz*. 

## <a name="setproperties"></a> Isessionpropertiesimpl:: SetProperties

Legt Eigenschaften fest, der `DBPROPSET_SESSION` Eigenschaftengruppe.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]);  
```  
  
#### <a name="parameters"></a>Parameter  

Finden Sie unter [ISessionProperties::SetProperties](/previous-versions/windows/desktop/ms714405) in die *OLE DB-Programmierreferenz*.  
  
## <a name="see-also"></a>Siehe auch  

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)