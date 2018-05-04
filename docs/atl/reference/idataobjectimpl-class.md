---
title: IDataObjectImpl Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl::DAdvise
- ATLCTL/ATL::IDataObjectImpl::DUnadvise
- ATLCTL/ATL::IDataObjectImpl::EnumDAdvise
- ATLCTL/ATL::IDataObjectImpl::EnumFormatEtc
- ATLCTL/ATL::IDataObjectImpl::FireDataChange
- ATLCTL/ATL::IDataObjectImpl::GetCanonicalFormatEtc
- ATLCTL/ATL::IDataObjectImpl::GetData
- ATLCTL/ATL::IDataObjectImpl::GetDataHere
- ATLCTL/ATL::IDataObjectImpl::QueryGetData
- ATLCTL/ATL::IDataObjectImpl::SetData
dev_langs:
- C++
helpviewer_keywords:
- data transfer [C++]
- data transfer [C++], Uniform Data Transfer
- IDataObjectImpl class
- IDataObject, ATL implementation
ms.assetid: b680f0f7-7795-40a1-a0f6-f48768201c89
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3ffcdd8cc8320b2534d928171fe75619062b300
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="idataobjectimpl-class"></a>IDataObjectImpl-Klasse
Diese Klasse stellt Methoden für die Unterstützung, Uniform Data Transfer und Verwalten von Verbindungen bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>  
class IDataObjectImpl
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IDataObjectImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IDataObjectImpl::DAdvise](#dadvise)|Herstellen einer Verbindung zwischen dem Datenobjekt und einer Advise-Senke. Dies ermöglicht die Advise-Senke, um Benachrichtigungen über Änderungen in das Objekt zu erhalten.|  
|[IDataObjectImpl::DUnadvise](#dunadvise)|Beendet eine Verbindung zuvor über `DAdvise`.|  
|[IDataObjectImpl::EnumDAdvise](#enumdadvise)|Erstellt einen Enumerator zum Durchlaufen der aktuellen Advise-Verbindungen.|  
|[IDataObjectImpl::EnumFormatEtc](#enumformatetc)|Erstellt einen Enumerator zum Durchlaufen der **FORMATETC** Strukturen, die durch das Datenobjekt unterstützt. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
|[IDataObjectImpl::FireDataChange](#firedatachange)|Sendet eine Benachrichtigung an jeden Advise-Senke.|  
|[IDataObjectImpl::GetCanonicalFormatEtc](#getcanonicalformatetc)|Ruft ab einen logisch equivalent **FORMATETC** Struktur, die komplexer ist. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
|[IDataObjectImpl::GetData](#getdata)|Werden Daten aus dem Datenobjekt an den Client übertragen. Die Daten beschrieben, einer **FORMATETC** strukturieren und übertragen wird, über eine **STGMEDIUM** Struktur.|  
|[IDataObjectImpl::GetDataHere](#getdatahere)|Ähnlich wie `GetData`, abgesehen von der Client zuordnen, muss der **STGMEDIUM** Struktur. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
|[IDataObjectImpl::QueryGetData](#querygetdata)|Bestimmt, ob das Datenobjekt mit eine bestimmten unterstützt **FORMATETC** Struktur zum Übertragen von Daten. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
|[IDataObjectImpl::SetData](#setdata)|Überträgt Daten vom Client auf das Datenobjekt. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Hinweise  
 Die ["IDataObject"](http://msdn.microsoft.com/library/windows/desktop/ms688421) Schnittstelle stellt Methoden zur Unterstützung von Uniform Data Transfer. `IDataObject` verwendet die Strukturen Standardformat [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) und [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) abrufen und Speichern von Daten.  
  
 `IDataObject` Außerdem verwaltet Verbindungen, um die advise-senken, änderungsbenachrichtigungen für Daten zu behandeln. Der Client muss in der Reihenfolge für den Client zum Empfangen von änderungsbenachrichtigungen für Daten aus dem Datenobjekt, implementieren die [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) Schnittstelle in einem Objekt eine Advise-Senke aufgerufen. Wenn dann ruft der Client **IDataObject::DAdvise**, eine Verbindung zwischen dem Datenobjekt und die Advise-Senke hergestellt wird.  
  
 Klasse `IDataObjectImpl` stellt eine Standardimplementierung von `IDataObject` und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
 **Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IDataObject`  
  
 `IDataObjectImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="dadvise"></a>  IDataObjectImpl::DAdvise  
 Herstellen einer Verbindung zwischen dem Datenobjekt und einer Advise-Senke.  
  
```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>Hinweise  
 Dies ermöglicht die Advise-Senke, um Benachrichtigungen über Änderungen in das Objekt zu erhalten.  
  
 Um die Verbindung zu beenden, rufen [DUnadvise](#dunadvise).  
  
 Finden Sie unter [IDataObject::DAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692579) im Windows SDK.  
  
##  <a name="dunadvise"></a>  IDataObjectImpl::DUnadvise  
 Beendet eine Verbindung zuvor über [DAdvise](#dadvise).  
  
```
HRESULT DUnadvise(DWORD dwConnection);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDataObject::DUnadvise](http://msdn.microsoft.com/library/windows/desktop/ms692448) im Windows SDK.  
  
##  <a name="enumdadvise"></a>  IDataObjectImpl::EnumDAdvise  
 Erstellt einen Enumerator zum Durchlaufen der aktuellen Advise-Verbindungen.  
  
```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDataObject::EnumDAdvise](http://msdn.microsoft.com/library/windows/desktop/ms680127) im Windows SDK.  
  
##  <a name="enumformatetc"></a>  IDataObjectImpl::EnumFormatEtc  
 Erstellt einen Enumerator zum Durchlaufen der **FORMATETC** Strukturen, die durch das Datenobjekt unterstützt.  
  
```
HRESULT EnumFormatEtc(  
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDataObject::EnumFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms683979) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
##  <a name="firedatachange"></a>  IDataObjectImpl::FireDataChange  
 Sendet eine Benachrichtigung an jeden Advise-Senke, die zurzeit verwaltet wird.  
  
```
HRESULT FireDataChange();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="getcanonicalformatetc"></a>  IDataObjectImpl::GetCanonicalFormatEtc  
 Ruft ab einen logisch equivalent **FORMATETC** Struktur, die komplexer ist.  
  
```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDataObject::GetCanonicalFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms680685) im Windows SDK.  
  
##  <a name="getdata"></a>  IDataObjectImpl::GetData  
 Werden Daten aus dem Datenobjekt an den Client übertragen.  
  
```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```  
  
### <a name="remarks"></a>Hinweise  
 Die *PformatetcIn* Parameter muss geben einen Speicher mittlere **TYMED_MFPICT**.  
  
 Finden Sie unter [IDataObject:: GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) im Windows SDK.  
  
##  <a name="getdatahere"></a>  IDataObjectImpl::GetDataHere  
 Ähnlich wie `GetData`, abgesehen von der Client zuordnen, muss der **STGMEDIUM** Struktur.  
  
```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDataObject::GetDataHere](http://msdn.microsoft.com/library/windows/desktop/ms687266) im Windows SDK.  
  
##  <a name="querygetdata"></a>  IDataObjectImpl::QueryGetData  
 Bestimmt, ob das Datenobjekt mit eine bestimmten unterstützt **FORMATETC** Struktur zum Übertragen von Daten.  
  
```
HRESULT QueryGetData(FORMATETC* pformatetc);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDataObject::QueryGetData](http://msdn.microsoft.com/library/windows/desktop/ms680637) im Windows SDK.  
  
##  <a name="setdata"></a>  IDataObjectImpl::SetData  
 Überträgt Daten vom Client auf das Datenobjekt.  
  
```
HRESULT SetData(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium,
    BOOL fRelease);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDataObject::SetData](http://msdn.microsoft.com/library/windows/desktop/ms686626) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
