---
title: Klasse IPersistStorageImpl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::IPersistStorageImpl
- ATL::IPersistStorageImpl<T>
- ATL.IPersistStorageImpl<T>
- IPersistStorageImpl
- ATL.IPersistStorageImpl
dev_langs:
- C++
helpviewer_keywords:
- storage, ATL
- IPersistStorageImpl class
ms.assetid: d652f02c-239c-47c7-9a50-3e9fc3014fff
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a5a855f81072316510efb47c3f9650a5feafa39b
ms.lasthandoff: 02/24/2017

---
# <a name="ipersiststorageimpl-class"></a>IPersistStorageImpl-Klasse
Diese Klasse implementiert die [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) Schnittstelle.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
class ATL_NO_VTABLE IPersistStorageImpl : public IPersistStorage
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Abgeleitet von die Klasse `IPersistStorageImpl`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IPersistStorageImpl::GetClassID](#getclassid)|Ruft die CLSID des Objekts ab.|  
|[IPersistStorageImpl::HandsOffStorage](#handsoffstorage)|Weist das Objekt, das alle Speicherobjekte freizugeben, und geben HandsOff-Modus. Der ATL-Implementierung zurückgegeben `S_OK`.|  
|[IPersistStorageImpl::InitNew](#initnew)|Initialisiert einen neuen Speicher.|  
|[IPersistStorageImpl::IsDirty](#isdirty)|Überprüft, ob die Daten des Objekts geändert wurde, seit es zuletzt gespeichert wurde.|  
|[IPersistStorageImpl::Load](#load)|Lädt die Eigenschaften des Objekts aus dem angegebenen Speicher.|  
|[IPersistStorageImpl::Save](#save)|Speichert die Eigenschaften des Objekts im angegebenen Speicher.|  
|[IPersistStorageImpl::SaveCompleted](#savecompleted)|Benachrichtigt ein Objekt, das zum normalen Modus zum Schreiben in das Speicherobjekt zurückgegeben werden kann. Der ATL-Implementierung zurückgegeben `S_OK`.|  
  
## <a name="remarks"></a>Hinweise  
 `IPersistStorageImpl`implementiert die [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) Schnittstelle, die ermöglicht einem Client anfordern, die Ihre laden und speichern Sie ihre permanenten Daten mit einem Speicher.  
  
 Erfordert die Implementierung dieser Klasse Klasse `T` , stellen Sie eine Implementierung der `IPersistStreamInit` Schnittstelle über `QueryInterface`. Normalerweise bedeutet dies die Klasse `T` sollte abgeleitet [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md), geben Sie einen Eintrag für `IPersistStreamInit` in der [COM-Zuordnung](http://msdn.microsoft.com/library/ead2a1e3-334d-44ad-bb1f-b94bb14c2333), und verwenden eine [Eigenschaft zuordnen](http://msdn.microsoft.com/library/bfe30be6-62c3-4dc2-bd49-21ef96f15427) , die Klasse persistente Daten zu beschreiben.  
  
 **Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IPersistStorage`  
  
 `IPersistStorageImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="a-namegetclassida--ipersiststorageimplgetclassid"></a><a name="getclassid"></a>IPersistStorageImpl::GetClassID  
 Ruft die CLSID des Objekts ab.  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPersist:: GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namehandsoffstoragea--ipersiststorageimplhandsoffstorage"></a><a name="handsoffstorage"></a>IPersistStorageImpl::HandsOffStorage  
 Weist das Objekt, das alle Speicherobjekte freizugeben, und geben HandsOff-Modus.  
  
```
STDMETHOD(HandsOffStorage)(void);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPersistStorage::HandsOffStorage](http://msdn.microsoft.com/library/windows/desktop/ms679742) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameinitnewa--ipersiststorageimplinitnew"></a><a name="initnew"></a>IPersistStorageImpl::InitNew  
 Initialisiert einen neuen Speicher.  
  
```
STDMETHOD(InitNew)(IStorage*);
```  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-Implementierung delegiert an die [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) Schnittstelle.  
  
 Finden Sie unter [IPersistStorage:InitNew](http://msdn.microsoft.com/library/windows/desktop/ms687194) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameisdirtya--ipersiststorageimplisdirty"></a><a name="isdirty"></a>IPersistStorageImpl::IsDirty  
 Überprüft, ob die Daten des Objekts geändert wurde, seit es zuletzt gespeichert wurde.  
  
```
STDMETHOD(IsDirty)(void);
```  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-Implementierung delegiert an die [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) Schnittstelle.  
  
 Finden Sie unter [IPersistStorage:IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms683910) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameloada--ipersiststorageimplload"></a><a name="load"></a>IPersistStorageImpl::Load  
 Lädt die Eigenschaften des Objekts aus dem angegebenen Speicher.  
  
```
STDMETHOD(Load)(IStorage* pStorage);
```  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-Implementierung delegiert an die [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) Schnittstelle. **Load** einen Stream mit dem Namen "Inhalt" zum Abrufen von Daten für das Objekt verwendet. Die [speichern](#save) Methode ursprünglich dieser Stream erstellt.  
  
 Finden Sie unter [IPersistStorage:Load](http://msdn.microsoft.com/library/windows/desktop/ms680557) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesavea--ipersiststorageimplsave"></a><a name="save"></a>IPersistStorageImpl::Save  
 Speichert die Eigenschaften des Objekts im angegebenen Speicher.  
  
```
STDMETHOD(Save)(IStorage* pStorage, BOOL fSameAsLoad);
```  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-Implementierung delegiert an die [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) Schnittstelle. Wenn **speichern** wird zuerst aufgerufen wird, einen Stream mit dem Namen "Inhalt" im angegebenen Speicher erstellt. Dieser Datenstrom wird dann in späteren Aufrufen von verwendet **speichern** und Aufrufe [Load](#load).  
  
 Finden Sie unter [IPersistStorage:Save](http://msdn.microsoft.com/library/windows/desktop/ms680680) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesavecompleteda--ipersiststorageimplsavecompleted"></a><a name="savecompleted"></a>IPersistStorageImpl::SaveCompleted  
 Benachrichtigt ein Objekt, das zum normalen Modus zum Schreiben in das Speicherobjekt zurückgegeben werden kann.  
  
```
STDMETHOD(SaveCompleted)(IStorage*);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPersistStorage:SaveCompleted](http://msdn.microsoft.com/library/windows/desktop/ms679713) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [Speichern und Streams](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [IPersistStreamInitImpl-Klasse](../../atl/reference/ipersiststreaminitimpl-class.md)   
 [IPersistPropertyBagImpl-Klasse](../../atl/reference/ipersistpropertybagimpl-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

