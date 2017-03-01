---
title: Klasse IPersistPropertyBagImpl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPersistPropertyBagImpl
- ATL.IPersistPropertyBagImpl<T>
- ATL::IPersistPropertyBagImpl
- ATL::IPersistPropertyBagImpl<T>
- ATL.IPersistPropertyBagImpl
dev_langs:
- C++
helpviewer_keywords:
- IPersistPropertyBagImpl class
ms.assetid: 712af24d-99f8-40f2-9811-53b3ff6e5b19
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 901a6a6bf4097b6aa78a898254766f122bb2f959
ms.lasthandoff: 02/24/2017

---
# <a name="ipersistpropertybagimpl-class"></a>IPersistPropertyBagImpl-Klasse
Diese Klasse implementiert **IUnknown** und ermöglicht es einem Objekt, dessen Eigenschaften in einer vom Client bereitgestellte Eigenschaftensammlung speichern.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
class ATL_NO_VTABLE IPersistPropertyBagImpl : public IPersistPropertyBag
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Abgeleitet von die Klasse `IPersistPropertyBagImpl`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IPersistPropertyBagImpl::GetClassID](#getclassid)|Ruft die CLSID des Objekts ab.|  
|[IPersistPropertyBagImpl::InitNew](#initnew)|Initialisiert ein neu erstelltes Objekt. Der ATL-Implementierung zurückgegeben `S_OK`.|  
|[IPersistPropertyBagImpl::Load](#load)|Lädt die Eigenschaften des Objekts in einem Client bereitgestellte Eigenschaftensammlung.|  
|[IPersistPropertyBagImpl::Save](#save)|Die Eigenschaften des Objekts in einem Client bereitgestellte Eigenschaftenbehälter gespeichert.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IPersistPropertyBag](https://msdn.microsoft.com/library/aa768205.aspx) Schnittstelle ermöglicht es, ein Objekt, dessen Eigenschaften in einer vom Client bereitgestellte Eigenschaftensammlung speichern. Klasse `IPersistPropertyBagImpl` bietet eine Standardimplementierung dieser Schnittstelle und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
 **IPersistPropertyBag** zusammen mit [IPropertyBag](https://msdn.microsoft.com/library/aa768196.aspx) und [IErrorLog](https://msdn.microsoft.com/library/aa768231.aspx). Diese letzten beiden Schnittstellen müssen vom Client implementiert werden. Über `IPropertyBag`, der Client speichert und lädt die einzelnen Eigenschaften des Objekts. Durch **IErrorLog**, das Objekt und der Client können gefundene Fehler melden.  
  
 **Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IPersistPropertyBag`  
  
 `IPersistPropertyBagImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="a-namegetclassida--ipersistpropertybagimplgetclassid"></a><a name="getclassid"></a>IPersistPropertyBagImpl::GetClassID  
 Ruft die CLSID des Objekts ab.  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPersist:: GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameinitnewa--ipersistpropertybagimplinitnew"></a><a name="initnew"></a>IPersistPropertyBagImpl::InitNew  
 Initialisiert ein neu erstelltes Objekt.  
  
```
STDMETHOD(InitNew)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPersistPropertyBag::InitNew](https://msdn.microsoft.com/library/aa768204.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameloada--ipersistpropertybagimplload"></a><a name="load"></a>IPersistPropertyBagImpl::Load  
 Lädt die Eigenschaften des Objekts in einem Client bereitgestellte Eigenschaftensammlung.  
  
```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```  
  
### <a name="remarks"></a>Hinweise  
 ATL verwendet die Objekttabelle Eigenschaft zum Abrufen dieser Informationen.  
  
 Finden Sie unter [IPersistPropertyBag::Load](https://msdn.microsoft.com/library/aa768206.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesavea--ipersistpropertybagimplsave"></a><a name="save"></a>IPersistPropertyBagImpl::Save  
 Die Eigenschaften des Objekts in einem Client bereitgestellte Eigenschaftenbehälter gespeichert.  
  
```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```  
  
### <a name="remarks"></a>Hinweise  
 ATL verwendet die Objekttabelle Eigenschaft zum Speichern dieser Informationen. Diese Methode speichert standardmäßig alle Eigenschaften, unabhängig vom Wert der *fSaveAllProperties*.  
  
 Finden Sie unter [IPersistPropertyBag::Save](https://msdn.microsoft.com/library/aa768207.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [BEGIN_PROP_MAP](http://msdn.microsoft.com/library/bfe30be6-62c3-4dc2-bd49-21ef96f15427)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

