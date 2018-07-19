---
title: IDataObjectImpl-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: ef7db05e8e8eb0a723354bcd6f53fb283aebe0c8
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880884"
---
# <a name="idataobjectimpl-class"></a>IDataObjectImpl-Klasse
Diese Klasse stellt Methoden für die Unterstützung, Uniform Data Transfer und Verwalten von Verbindungen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>  
class IDataObjectImpl
```  
  
#### <a name="parameters"></a>Parameter  
 *T*  
 Abgeleitet von die Klasse `IDataObjectImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IDataObjectImpl::DAdvise](#dadvise)|Herstellen einer Verbindung zwischen dem Datenobjekt und einer Advise-Senke. Dies ermöglicht die Advise-Senke zum Empfangen von Benachrichtigungen über Änderungen im-Objekt.|  
|[IDataObjectImpl::DUnadvise](#dunadvise)|Beendet eine Verbindung zuvor mit `DAdvise`.|  
|[IDataObjectImpl::EnumDAdvise](#enumdadvise)|Erstellt einen Enumerator zum Durchlaufen der aktuellen Advise-Verbindungen.|  
|[IDataObjectImpl::EnumFormatEtc](#enumformatetc)|Erstellt einen Enumerator zum Durchlaufen der `FORMATETC` Strukturen, die vom Datenobjekt unterstützt. Die ATL-Implementierung gibt E_NOTIMPL zurück.|  
|[IDataObjectImpl::FireDataChange](#firedatachange)|Sendet eine Benachrichtigung an jede Advise-Senke.|  
|[IDataObjectImpl::GetCanonicalFormatEtc](#getcanonicalformatetc)|Ruft eine logisch äquivalente `FORMATETC` Struktur, die komplexer ist. Die ATL-Implementierung gibt E_NOTIMPL zurück.|  
|[IDataObjectImpl::GetData](#getdata)|Überträgt Daten aus dem Datenobjekt an den Client an. Die Daten werden beschrieben eine `FORMATETC` strukturieren und übertragen wird, über eine `STGMEDIUM` Struktur.|  
|[IDataObjectImpl::GetDataHere](#getdatahere)|Ähnlich wie `GetData`, außer dass der Client zuweisen, muss die `STGMEDIUM` Struktur. Die ATL-Implementierung gibt E_NOTIMPL zurück.|  
|[IDataObjectImpl::QueryGetData](#querygetdata)|Bestimmt, ob das Datenobjekt, das eine bestimmte unterstützt `FORMATETC` Struktur zum Übertragen von Daten. Die ATL-Implementierung gibt E_NOTIMPL zurück.|  
|[IDataObjectImpl::SetData](#setdata)|Überträgt Daten vom Client, auf das Datenobjekt. Die ATL-Implementierung gibt E_NOTIMPL zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) Schnittstelle stellt Methoden zur Unterstützung von Uniform Data Transfer. `IDataObject` verwendet die Strukturen Standardformat [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) und [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) zum Abrufen und Speichern von Daten.  
  
 `IDataObject` Außerdem verwaltet Verbindungen herstellen, um das empfehlen von senken, änderungsbenachrichtigungen für Daten zu behandeln. Implementieren des Clients muss in der Reihenfolge für den Client zum Empfangen von änderungsbenachrichtigungen für Daten aus dem Datenobjekt, das [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) Schnittstelle für ein Objekt, das eine Advisesenke aufgerufen haben. Wenn der Client ruft dann `IDataObject::DAdvise`, eine Verbindung zwischen dem Datenobjekt und der Advise-Senke hergestellt wird.  
  
 Klasse `IDataObjectImpl` stellt eine Standardimplementierung von `IDataObject` und implementiert `IUnknown` durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus wird erstellt.  
  
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
 Dies ermöglicht die Advise-Senke zum Empfangen von Benachrichtigungen über Änderungen im-Objekt.  
  
 Um die Verbindung zu beenden, rufen Sie [DUnadvise](#dunadvise).  
  
 Finden Sie unter [IDataObject::DAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692579) in das Windows SDK.  
  
##  <a name="dunadvise"></a>  IDataObjectImpl::DUnadvise  
 Beendet eine Verbindung zuvor mit [DAdvise](#dadvise).  
  
```
HRESULT DUnadvise(DWORD dwConnection);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDataObject::DUnadvise](http://msdn.microsoft.com/library/windows/desktop/ms692448) in das Windows SDK.  
  
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
 Finden Sie unter [IDataObject::EnumDAdvise](http://msdn.microsoft.com/library/windows/desktop/ms680127) in das Windows SDK.  
  
##  <a name="enumformatetc"></a>  IDataObjectImpl::EnumFormatEtc  
 Erstellt einen Enumerator zum Durchlaufen der `FORMATETC` Strukturen, die vom Datenobjekt unterstützt.  
  
```
HRESULT EnumFormatEtc(  
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDataObject::EnumFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms683979) in das Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt E_NOTIMPL zurück.  
  
##  <a name="firedatachange"></a>  IDataObjectImpl::FireDataChange  
 Sendet eine Benachrichtigung an jede Advise-Senke, die gerade verwaltet wird.  
  
```
HRESULT FireDataChange();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
##  <a name="getcanonicalformatetc"></a>  IDataObjectImpl::GetCanonicalFormatEtc  
 Ruft eine logisch äquivalente `FORMATETC` Struktur, die komplexer ist.  
  
```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt E_NOTIMPL zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDataObject::GetCanonicalFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms680685) in das Windows SDK.  
  
##  <a name="getdata"></a>  IDataObjectImpl::GetData  
 Überträgt Daten aus dem Datenobjekt an den Client an.  
  
```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```  
  
### <a name="remarks"></a>Hinweise  
 Die *PformatetcIn* Parameter muss einen Speichermedientyp TYMED_MFPICT angeben.  
  
 Finden Sie unter [IDataObject:: GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) in das Windows SDK.  
  
##  <a name="getdatahere"></a>  IDataObjectImpl::GetDataHere  
 Ähnlich wie `GetData`, außer dass der Client zuweisen, muss die `STGMEDIUM` Struktur.  
  
```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt E_NOTIMPL zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDataObject::GetDataHere](http://msdn.microsoft.com/library/windows/desktop/ms687266) in das Windows SDK.  
  
##  <a name="querygetdata"></a>  IDataObjectImpl::QueryGetData  
 Bestimmt, ob das Datenobjekt, das eine bestimmte unterstützt `FORMATETC` Struktur zum Übertragen von Daten.  
  
```
HRESULT QueryGetData(FORMATETC* pformatetc);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt E_NOTIMPL zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDataObject::QueryGetData](http://msdn.microsoft.com/library/windows/desktop/ms680637) in das Windows SDK.  
  
##  <a name="setdata"></a>  IDataObjectImpl::SetData  
 Überträgt Daten vom Client, auf das Datenobjekt.  
  
```
HRESULT SetData(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium,
    BOOL fRelease);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt E_NOTIMPL zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDataObject::SetData](http://msdn.microsoft.com/library/windows/desktop/ms686626) in das Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
