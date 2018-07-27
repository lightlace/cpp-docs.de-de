---
title: IAccessorImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IAccessorImpl
- ATL.IAccessorImpl.IAccessorImpl
- ATL::IAccessorImpl::IAccessorImpl
- IAccessorImpl::IAccessorImpl
- IAccessorImpl.IAccessorImpl
- IAccessorImpl
- ATL::IAccessorImpl::AddRefAccessor
- AddRefAccessor
- IAccessorImpl::AddRefAccessor
- IAccessorImpl.AddRefAccessor
- ATL.IAccessorImpl.AddRefAccessor
- IAccessorImpl::CreateAccessor
- CreateAccessor
- ATL::IAccessorImpl::CreateAccessor
- IAccessorImpl.CreateAccessor
- ATL.IAccessorImpl.CreateAccessor
- IAccessorImpl.GetBindings
- ATL::IAccessorImpl::GetBindings
- IAccessorImpl::GetBindings
- GetBindings
- ATL.IAccessorImpl.GetBindings
- ReleaseAccessor
- IAccessorImpl::ReleaseAccessor
- ATL.IAccessorImpl.ReleaseAccessor
- ATL::IAccessorImpl::ReleaseAccessor
- IAccessorImpl.ReleaseAccessor
dev_langs:
- C++
helpviewer_keywords:
- IAccessorImpl class
- IAccessorImpl class, constructor
- IAccessorImpl constructor
- AddRefAccessor method
- CreateAccessor method
- GetBindings method
- ReleaseAccessor method
ms.assetid: 768606da-8b71-417c-a62c-88069ce7730d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0ac22d8ee45209ad6a20dcb34a75c06dd9b80b58
ms.sourcegitcommit: b0d6777cf4b580d093eaf6104d80a888706e7578
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2018
ms.locfileid: "39269887"
---
# <a name="iaccessorimpl-class"></a>IAccessorImpl-Klasse
Stellt eine Implementierung der [IAccessor](https://msdn.microsoft.com/library/ms719672.aspx) Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T, 
          class BindType = ATLBINDINGS,
          class BindingVector = CAtlMap <HACCESSOR hAccessor, BindType* pBindingsStructure>>  
class ATL_NO_VTABLE IAccessorImpl : public IAccessorImplBase<BindType>  
```  
  
### <a name="parameters"></a>Parameter  
 *T*  
 Ihre Rowset oder Object-Klasse.  
  
 *BindType*  
 Storage-Einheit für die Bindungsinformationen. Der Standardwert ist die `ATLBINDINGS` Struktur (finden Sie unter "atldb.h").  
  
 *BindingVector*  
 Storage-Einheit für die Spalteninformationen. Der Standardwert ist [CAtlMap](../../atl/reference/catlmap-class.md) , in denen das Schlüsselelement ist ein HACCESSOR-Wert und die Value-Element ist ein Zeiger auf eine `BindType` Struktur.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  

## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[IAccessorImpl](#iaccessorimpl)|Der Konstruktor.|  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[AddRefAccessor](#addrefaccessor)|Fügt einem vorhandenen Accessor einen Verweiszähler hinzu.|  
|[CreateAccessor](#createaccessor)|Erstellt einen Accessor aus einem Satz von Bindungen.|  
|[GetBindings](#getbindings)|Gibt die Bindungen in einem Accessor zurück.|  
|[ReleaseAccessor](#releaseaccessor)|Gibt einen Accessor frei.|  
  
## <a name="remarks"></a>Hinweise  
 Dies ist erforderlich für Rowsets und Befehle. OLE DB verlangt von Anbietern zum Implementieren einer HACCESSOR, dies ist ein Tag auf ein Array von [DBBINDING](https://msdn.microsoft.com/library/ms716845.aspx) Strukturen. Von bereitgestellten HACCESSORs `IAccessorImpl` Adressen sind die `BindType` Strukturen. In der Standardeinstellung `BindType` ist definiert als eine `ATLBINDINGS` in `IAccessorImpl`der Vorlagendefinition. `BindType` Stellt einen Mechanismus, der von verwendeten `IAccessorImpl` zum Nachverfolgen der Anzahl der Elemente in der `DBBINDING` array sowie einen Verweis Count "und"-Accessor-Flags.  

## <a name="iaccessorimpl"></a> IAccessorImpl:: IAccessorImpl
Der Konstruktor.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
IAccessorImpl();  
  
```  

## <a name="addrefaccessor"></a> IAccessorImpl:: Addrefaccessor
Fügt einem vorhandenen Accessor einen Verweiszähler hinzu.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(AddRefAccessor)(HACCESSOR hAccessor,  
   DBREFCOUNT* pcRefCount);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IAccessor::AddRefAccessor](https://msdn.microsoft.com/library/ms714978.aspx) in die *OLE DB-Programmierreferenz*.

## <a name="createaccessor"></a> IAccessorImpl:: CreateAccessor
Erstellt einen Accessor aus einem Satz von Bindungen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(CreateAccessor)(DBACCESSORFLAGS dwAccessorFlags,  
   DBCOUNTITEM cBindings,  
   const DBBINDING rgBindings[],  
   DBLENGTH cbRowSize,  
   HACCESSOR* phAccessor,  
   DBBINDSTATUS rgStatus[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IAccessor:: CreateAccessor](https://msdn.microsoft.com/library/ms720969.aspx) in die *OLE DB-Programmierreferenz*.  

## <a name="getbindings"></a> IAccessorImpl:: Getbindings
Gibt die grundlegenden Spalten Bindungen aus der Consumer in einem Accessor zurück.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(GetBindings)(HACCESSOR hAccessor,  
   DBACCESSORFLAGS* pdwAccessorFlags,  
   DBCOUNTITEM* pcBindings,  
   DBBINDING** prgBindings);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IAccessor::GetBindings](https://msdn.microsoft.com/library/ms721253.aspx) in die *OLE DB-Programmierreferenz*. 

## <a name="releaseaccessor"></a> IAccessorImpl:: ReleaseAccessor
Gibt einen Accessor frei.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(ReleaseAccessor)(HACCESSOR hAccessor,  
   DBREFCOUNT* pcRefCount);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [ReleaseAccessor](https://msdn.microsoft.com/library/ms719717.aspx) in die *OLE DB-Programmierreferenz*.
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)
