---
title: Klasse Ipersiststreaminitimpl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl::GetClassID
- ATLCOM/ATL::IPersistStreamInitImpl::GetSizeMax
- ATLCOM/ATL::IPersistStreamInitImpl::InitNew
- ATLCOM/ATL::IPersistStreamInitImpl::IsDirty
- ATLCOM/ATL::IPersistStreamInitImpl::Load
- ATLCOM/ATL::IPersistStreamInitImpl::Save
dev_langs: C++
helpviewer_keywords:
- IPersistStreamInit ATL implementation
- IPersistStreamInitImpl class
- streams, ATL
ms.assetid: ef217c3c-020f-4cf8-871e-ef68e57865b8
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1fe1bcd8d8198304c92584f01522048c4d29b827
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ipersiststreaminitimpl-class"></a>Klasse Ipersiststreaminitimpl
Diese Klasse implementiert **IUnknown** und stellt eine Standardimplementierung von der [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) Schnittstelle.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>  
class ATL_NO_VTABLE IPersistStreamInitImpl 
   : public IPersistStreamInit
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IPersistStreamInitImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IPersistStreamInitImpl::GetClassID](#getclassid)|Ruft die CLSID des Objekts ab.|  
|[IPersistStreamInitImpl::GetSizeMax](#getsizemax)|Ruft die Größe des Datenstroms, der zum Speichern von Daten für das Objekt ab. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
|[IPersistStreamInitImpl::InitNew](#initnew)|Initialisiert ein neu erstelltes Objekt.|  
|[IPersistStreamInitImpl::IsDirty](#isdirty)|Überprüft, ob die Daten des Objekts geändert wurde, seit es zuletzt gespeichert wurde.|  
|[IPersistStreamInitImpl::Load](#load)|Lädt die Eigenschaften des Objekts aus dem angegebenen Stream.|  
|[IPersistStreamInitImpl::Save](#save)|Speichert die Eigenschaften des Objekts in den angegebenen Stream.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) Schnittstelle ermöglicht es einen Client, um anzufordern, dass das Objekt lädt und ihre permanenten Daten in einem einzelnen Stream speichert. Klasse `IPersistStreamInitImpl` stellt eine Standardimplementierung dieser Schnittstelle und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
 **Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IPersistStreamInit`  
  
 `IPersistStreamInitImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="getclassid"></a>IPersistStreamInitImpl::GetClassID  
 Ruft die CLSID des Objekts ab.  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPersist:: GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) im Windows SDK.  
  
##  <a name="getsizemax"></a>IPersistStreamInitImpl::GetSizeMax  
 Ruft die Größe des Datenstroms, der zum Speichern von Daten für das Objekt ab.  
  
```
STDMETHOD(GetSizeMax)(ULARGE_INTEGER FAR* pcbSize);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPersistStreamInit::GetSizeMax](http://msdn.microsoft.com/library/windows/desktop/ms687287) im Windows SDK.  
  
##  <a name="initnew"></a>IPersistStreamInitImpl::InitNew  
 Initialisiert ein neu erstelltes Objekt.  
  
```
STDMETHOD(InitNew)();
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms690234) im Windows SDK.  
  
##  <a name="isdirty"></a>IPersistStreamInitImpl::IsDirty  
 Überprüft, ob die Daten des Objekts geändert wurde, seit es zuletzt gespeichert wurde.  
  
```
STDMETHOD(IsDirty)();
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPersistStreamInit::IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms680092) im Windows SDK.  
  
##  <a name="load"></a>IPersistStreamInitImpl::Load  
 Lädt die Eigenschaften des Objekts aus dem angegebenen Stream.  
  
```
STDMETHOD(Load)(LPSTREAM pStm);
```  
  
### <a name="remarks"></a>Hinweise  
 ATL verwendet eigenschaftenzuordnung für das Objekt, um diese Informationen abzurufen.  
  
 Finden Sie unter [IPersistStreamInit::Load](http://msdn.microsoft.com/library/windows/desktop/ms680730) im Windows SDK.  
  
##  <a name="save"></a>IPersistStreamInitImpl::Save  
 Speichert die Eigenschaften des Objekts in den angegebenen Stream.  
  
```
STDMETHOD(Save)(LPSTREAM pStm, BOOL fClearDirty);
```  
  
### <a name="remarks"></a>Hinweise  
 ATL verwendet der objektzuordnung-Eigenschaft, um diese Informationen speichern.  
  
 Finden Sie unter [IPersistStreamInit::Save](http://msdn.microsoft.com/library/windows/desktop/ms694439) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [Speicher und Streams](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
