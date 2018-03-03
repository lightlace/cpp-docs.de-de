---
title: IPersistPropertyBagImpl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl::GetClassID
- ATLCOM/ATL::IPersistPropertyBagImpl::InitNew
- ATLCOM/ATL::IPersistPropertyBagImpl::Load
- ATLCOM/ATL::IPersistPropertyBagImpl::Save
dev_langs:
- C++
helpviewer_keywords:
- IPersistPropertyBagImpl class
ms.assetid: 712af24d-99f8-40f2-9811-53b3ff6e5b19
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3783d505c989b11205104cd70a9c440aa6f645f7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ipersistpropertybagimpl-class"></a>IPersistPropertyBagImpl-Klasse
Diese Klasse implementiert **IUnknown** und einem Objekt Gelegenheit zu seiner Eigenschaften auf einem Client bereitgestellte Eigenschaftensammlung zu speichern.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
class ATL_NO_VTABLE IPersistPropertyBagImpl : public IPersistPropertyBag
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IPersistPropertyBagImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IPersistPropertyBagImpl::GetClassID](#getclassid)|Ruft die CLSID des Objekts ab.|  
|[IPersistPropertyBagImpl::InitNew](#initnew)|Initialisiert ein neu erstelltes Objekt. Gibt die ATL-Implementierung `S_OK`.|  
|[IPersistPropertyBagImpl::Load](#load)|Lädt die Eigenschaften des Objekts aus einem Client bereitgestellte Eigenschaftenbehälter.|  
|[IPersistPropertyBagImpl::Save](#save)|Die Eigenschaften des Objekts in einem Client bereitgestellte Eigenschaftenbehälter gespeichert.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IPersistPropertyBag](https://msdn.microsoft.com/library/aa768205.aspx) Schnittstelle ermöglicht es, ein Objekt, dessen Eigenschaften auf einem Client bereitgestellte Eigenschaftensammlung zu speichern. Klasse `IPersistPropertyBagImpl` stellt eine Standardimplementierung dieser Schnittstelle und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
 **IPersistPropertyBag** funktioniert in Verbindung mit [IPropertyBag](https://msdn.microsoft.com/library/aa768196.aspx) und [IErrorLog](https://msdn.microsoft.com/library/aa768231.aspx). Diese zweiten zwei Schnittstellen müssen vom Client implementiert werden. Über `IPropertyBag`, der Client speichert und lädt die einzelnen Eigenschaften des Objekts. Über **IErrorLog**, können das Objekt und der Client alle aufgetretenen melden.  
  
 **Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IPersistPropertyBag`  
  
 `IPersistPropertyBagImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="getclassid"></a>IPersistPropertyBagImpl::GetClassID  
 Ruft die CLSID des Objekts ab.  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPersist:: GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) im Windows SDK.  
  
##  <a name="initnew"></a>IPersistPropertyBagImpl::InitNew  
 Initialisiert ein neu erstelltes Objekt.  
  
```
STDMETHOD(InitNew)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPersistPropertyBag::InitNew](https://msdn.microsoft.com/library/aa768204.aspx) im Windows SDK.  
  
##  <a name="load"></a>IPersistPropertyBagImpl::Load  
 Lädt die Eigenschaften des Objekts aus einem Client bereitgestellte Eigenschaftenbehälter.  
  
```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```  
  
### <a name="remarks"></a>Hinweise  
 ATL verwendet eigenschaftenzuordnung für das Objekt, um diese Informationen abzurufen.  
  
 Finden Sie unter [IPersistPropertyBag::Load](https://msdn.microsoft.com/library/aa768206.aspx) im Windows SDK.  
  
##  <a name="save"></a>IPersistPropertyBagImpl::Save  
 Die Eigenschaften des Objekts in einem Client bereitgestellte Eigenschaftenbehälter gespeichert.  
  
```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```  
  
### <a name="remarks"></a>Hinweise  
 ATL verwendet der objektzuordnung-Eigenschaft, um diese Informationen speichern. Diese Methode speichert standardmäßig alle Eigenschaften, unabhängig vom Wert der *fSaveAllProperties*.  
  
 Finden Sie unter [IPersistPropertyBag::Save](https://msdn.microsoft.com/library/aa768207.aspx) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [BEGIN_PROP_MAP](property-map-macros.md#begin_prop_map)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
