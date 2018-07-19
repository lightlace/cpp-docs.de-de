---
title: IPersistStorageImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPersistStorageImpl
- ATLCOM/ATL::IPersistStorageImpl
- ATLCOM/ATL::IPersistStorageImpl::GetClassID
- ATLCOM/ATL::IPersistStorageImpl::HandsOffStorage
- ATLCOM/ATL::IPersistStorageImpl::InitNew
- ATLCOM/ATL::IPersistStorageImpl::IsDirty
- ATLCOM/ATL::IPersistStorageImpl::Load
- ATLCOM/ATL::IPersistStorageImpl::Save
- ATLCOM/ATL::IPersistStorageImpl::SaveCompleted
dev_langs:
- C++
helpviewer_keywords:
- storage, ATL
- IPersistStorageImpl class
ms.assetid: d652f02c-239c-47c7-9a50-3e9fc3014fff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 634a7a7373f6686ad36b645a73613a4ae350bbab
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884700"
---
# <a name="ipersiststorageimpl-class"></a>IPersistStorageImpl-Klasse
Diese Klasse implementiert die [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) Schnittstelle.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
class ATL_NO_VTABLE IPersistStorageImpl : public IPersistStorage
```  
  
#### <a name="parameters"></a>Parameter  
 *T*  
 Abgeleitet von die Klasse `IPersistStorageImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IPersistStorageImpl::GetClassID](#getclassid)|Ruft die CLSID des Objekts ab.|  
|[IPersistStorageImpl::HandsOffStorage](#handsoffstorage)|Weist das Objekt, das alle Speicherobjekte freizugeben, und geben HandsOff-Modus. Es gibt S_OK zurück, die ATL-Implementierung.|  
|[IPersistStorageImpl::InitNew](#initnew)|Initialisiert einen neuen Speicher.|  
|[IPersistStorageImpl::IsDirty](#isdirty)|Überprüft, ob die Daten des Objekts geändert hat, seit es zuletzt gespeichert wurde.|  
|[IPersistStorageImpl::Load](#load)|Lädt die Eigenschaften des Objekts aus dem angegebenen Speicher.|  
|[IPersistStorageImpl::Save](#save)|Speichert die Eigenschaften des Objekts im angegebenen Speicher.|  
|[IPersistStorageImpl::SaveCompleted](#savecompleted)|Benachrichtigt ein Objekt, das zum normalen Modus zum Schreiben in das Speicherobjekt zurückgegeben werden kann. Es gibt S_OK zurück, die ATL-Implementierung.|  
  
## <a name="remarks"></a>Hinweise  
 `IPersistStorageImpl` implementiert die [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) Schnittstelle, die kann ein Client anfordern, die Ihre laden und speichern Sie ihre permanenten Daten, die mit einem Speicher.  
  
 Die Implementierung dieser Klasse ist eine Klasse erforderlich `T` , stellen eine Implementierung der `IPersistStreamInit` Schnittstelle, die über `QueryInterface`. In der Regel bedeutet dies die Klasse `T` ableiten sollten [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md), geben Sie einen Eintrag für `IPersistStreamInit` in die [COM-Zuordnung](http://msdn.microsoft.com/library/ead2a1e3-334d-44ad-bb1f-b94bb14c2333), und Verwenden einer [eigenschaftenzuordnung](http://msdn.microsoft.com/library/bfe30be6-62c3-4dc2-bd49-21ef96f15427) persistenten Daten von der Klasse beschreiben.  
  
 **Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IPersistStorage`  
  
 `IPersistStorageImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="getclassid"></a>  IPersistStorageImpl::GetClassID  
 Ruft die CLSID des Objekts ab.  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPersist:: GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) in das Windows SDK.  
  
##  <a name="handsoffstorage"></a>  IPersistStorageImpl::HandsOffStorage  
 Weist das Objekt, das alle Speicherobjekte freizugeben, und geben HandsOff-Modus.  
  
```
STDMETHOD(HandsOffStorage)(void);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPersistStorage::HandsOffStorage](http://msdn.microsoft.com/library/windows/desktop/ms679742) in das Windows SDK.  
  
##  <a name="initnew"></a>  IPersistStorageImpl::InitNew  
 Initialisiert einen neuen Speicher.  
  
```
STDMETHOD(InitNew)(IStorage*);
```  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-Implementierung delegiert an die [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) Schnittstelle.  
  
 Finden Sie unter [IPersistStorage:InitNew](http://msdn.microsoft.com/library/windows/desktop/ms687194) in das Windows SDK.  
  
##  <a name="isdirty"></a>  IPersistStorageImpl::IsDirty  
 Überprüft, ob die Daten des Objekts geändert hat, seit es zuletzt gespeichert wurde.  
  
```
STDMETHOD(IsDirty)(void);
```  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-Implementierung delegiert an die [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) Schnittstelle.  
  
 Finden Sie unter [IPersistStorage:IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms683910) in das Windows SDK.  
  
##  <a name="load"></a>  IPersistStorageImpl::Load  
 Lädt die Eigenschaften des Objekts aus dem angegebenen Speicher.  
  
```
STDMETHOD(Load)(IStorage* pStorage);
```  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-Implementierung delegiert an die [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) Schnittstelle. `Load` verwendet einen Stream mit dem Namen "Inhalt", um die Daten des Objekts abzurufen. Die [speichern](#save) Methode ursprünglich erstellt diesen Stream.  
  
 Finden Sie unter [IPersistStorage:Load](http://msdn.microsoft.com/library/windows/desktop/ms680557) in das Windows SDK.  
  
##  <a name="save"></a>  IPersistStorageImpl::Save  
 Speichert die Eigenschaften des Objekts im angegebenen Speicher.  
  
```
STDMETHOD(Save)(IStorage* pStorage, BOOL fSameAsLoad);
```  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-Implementierung delegiert an die [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) Schnittstelle. Wenn `Save` wird an erster Stelle aufgerufen wird, erstellt es einen Datenstrom mit dem Namen "Inhalt" im angegebenen Speicher. Dieser Datenstrom wird dann verwendet, in späteren Aufrufen von `Save` und Aufrufe [Load](#load).  
  
 Finden Sie unter [IPersistStorage:Save](http://msdn.microsoft.com/library/windows/desktop/ms680680) in das Windows SDK.  
  
##  <a name="savecompleted"></a>  IPersistStorageImpl::SaveCompleted  
 Benachrichtigt ein Objekt, das zum normalen Modus zum Schreiben in das Speicherobjekt zurückgegeben werden kann.  
  
```
STDMETHOD(SaveCompleted)(IStorage*);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPersistStorage:SaveCompleted](http://msdn.microsoft.com/library/windows/desktop/ms679713) in das Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [Speicher und Streams](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [IPersistStreamInitImpl-Klasse](../../atl/reference/ipersiststreaminitimpl-class.md)   
 [IPersistPropertyBagImpl-Klasse](../../atl/reference/ipersistpropertybagimpl-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
