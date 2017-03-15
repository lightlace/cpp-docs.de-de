---
title: Klasse IDataObjectImpl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDataObjectImpl
dev_langs:
- C++
helpviewer_keywords:
- data transfer [C++]
- data transfer [C++], Uniform Data Transfer
- IDataObjectImpl class
- IDataObject, ATL implementation
ms.assetid: b680f0f7-7795-40a1-a0f6-f48768201c89
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: afd5fe7cf9bbac582e59ed46dc33e99de5fc2876
ms.lasthandoff: 02/24/2017

---
# <a name="idataobjectimpl-class"></a>IDataObjectImpl-Klasse
Diese Klasse stellt Methoden für die Unterstützung, Uniform Data Transfer und Verwalten von Verbindungen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>  
class IDataObjectImpl
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Abgeleitet von die Klasse `IDataObjectImpl`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IDataObjectImpl::DAdvise](#dadvise)|Stellt eine Verbindung zwischen einem Datenobjekt und einer Advise-Senke. Dies ermöglicht die Advise-Senke, um Benachrichtigungen zu Änderungen im Objekt zu erhalten.|  
|[IDataObjectImpl::DUnadvise](#dunadvise)|Beendet eine Verbindung zuvor mit `DAdvise`.|  
|[IDataObjectImpl::EnumDAdvise](#enumdadvise)|Erstellt einen Enumerator zum Durchlaufen der aktuellen Advise-Verbindungen.|  
|[IDataObjectImpl::EnumFormatEtc](#enumformatetc)|Erstellt einen Enumerator zum Durchlaufen der **FORMATETC** Strukturen vom Datenobjekt unterstützt. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.|  
|[IDataObjectImpl::FireDataChange](#firedatachange)|Sendet eine Benachrichtigung an jeden Advise-Senke.|  
|[IDataObjectImpl::GetCanonicalFormatEtc](#getcanonicalformatetc)|Ruft eine logisch äquivalente **FORMATETC** in eine komplexere Struktur. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.|  
|[IDataObjectImpl::GetData](#getdata)|Überträgt Daten aus dem Datenobjekt an den Client. Die Daten werden beschrieben eine **FORMATETC** Struktur und übertragen wird, über eine **STGMEDIUM** Struktur.|  
|[IDataObjectImpl::GetDataHere](#getdatahere)|Ähnlich wie `GetData`, außer dass der Client zugewiesen werden, muss die **STGMEDIUM** Struktur. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.|  
|[IDataObjectImpl::QueryGetData](#querygetdata)|Bestimmt, ob das Datenobjekt eine bestimmte unterstützt **FORMATETC** Struktur zum Übertragen von Daten. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.|  
|[IDataObjectImpl::SetData](#setdata)|Überträgt Daten vom Client auf das Datenobjekt. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) Schnittstelle stellt Methoden zur Unterstützung Uniform Data Transfer. `IDataObject`verwendet die standardmäßige Strukturen [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) und [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) abrufen und Speichern von Daten.  
  
 `IDataObject`Außerdem verwaltet Verbindungen, um darauf hinzuweisen senken, änderungsbenachrichtigungen für Daten zu behandeln. In der Reihenfolge für den Client zum Empfangen von änderungsbenachrichtigungen für Daten aus dem Datenobjekt, muss der Client Implementieren der [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) Schnittstelle für ein Objekt, das eine Advise-Senke aufgerufen haben. Wenn dann ruft der Client **IDataObject::DAdvise**, eine Verbindung zwischen einem Datenobjekt und die Advise-Senke hergestellt wird.  
  
 Klasse `IDataObjectImpl` stellt eine Standardimplementierung der `IDataObject` und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
 **Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IDataObject`  
  
 `IDataObjectImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="a-namedadvisea--idataobjectimpldadvise"></a><a name="dadvise"></a>IDataObjectImpl::DAdvise  
 Stellt eine Verbindung zwischen einem Datenobjekt und einer Advise-Senke.  
  
```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>Hinweise  
 Dies ermöglicht die Advise-Senke, um Benachrichtigungen zu Änderungen im Objekt zu erhalten.  
  
 Um die Verbindung zu beenden, rufen Sie [DUnadvise](#dunadvise).  
  
 Finden Sie unter [IDataObject::DAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692579) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namedunadvisea--idataobjectimpldunadvise"></a><a name="dunadvise"></a>IDataObjectImpl::DUnadvise  
 Beendet eine Verbindung zuvor mit [DAdvise](#dadvise).  
  
```
HRESULT DUnadvise(DWORD dwConnection);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDataObject::DUnadvise](http://msdn.microsoft.com/library/windows/desktop/ms692448) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameenumdadvisea--idataobjectimplenumdadvise"></a><a name="enumdadvise"></a>IDataObjectImpl::EnumDAdvise  
 Erstellt einen Enumerator zum Durchlaufen der aktuellen Advise-Verbindungen.  
  
```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDataObject::EnumDAdvise](http://msdn.microsoft.com/library/windows/desktop/ms680127) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameenumformatetca--idataobjectimplenumformatetc"></a><a name="enumformatetc"></a>IDataObjectImpl::EnumFormatEtc  
 Erstellt einen Enumerator zum Durchlaufen der **FORMATETC** Strukturen vom Datenobjekt unterstützt.  
  
```
HRESULT EnumFormatEtc(  
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDataObject::EnumFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms683979) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
##  <a name="a-namefiredatachangea--idataobjectimplfiredatachange"></a><a name="firedatachange"></a>IDataObjectImpl::FireDataChange  
 Sendet eine Benachrichtigung an jeden Advise-Empfänger, der gerade verwaltet wird.  
  
```
HRESULT FireDataChange();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="a-namegetcanonicalformatetca--idataobjectimplgetcanonicalformatetc"></a><a name="getcanonicalformatetc"></a>IDataObjectImpl::GetCanonicalFormatEtc  
 Ruft eine logisch äquivalente **FORMATETC** in eine komplexere Struktur.  
  
```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDataObject::GetCanonicalFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms680685) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetdataa--idataobjectimplgetdata"></a><a name="getdata"></a>IDataObjectImpl::GetData  
 Überträgt Daten aus dem Datenobjekt an den Client.  
  
```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```  
  
### <a name="remarks"></a>Hinweise  
 Die *PformatetcIn* Parameter geben einen Typ des Speichermediums des **TYMED_MFPICT**.  
  
 Finden Sie unter [IDataObject:: GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetdataherea--idataobjectimplgetdatahere"></a><a name="getdatahere"></a>IDataObjectImpl::GetDataHere  
 Ähnlich wie `GetData`, außer dass der Client zugewiesen werden, muss die **STGMEDIUM** Struktur.  
  
```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDataObject::GetDataHere](http://msdn.microsoft.com/library/windows/desktop/ms687266) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namequerygetdataa--idataobjectimplquerygetdata"></a><a name="querygetdata"></a>IDataObjectImpl::QueryGetData  
 Bestimmt, ob das Datenobjekt eine bestimmte unterstützt **FORMATETC** Struktur zum Übertragen von Daten.  
  
```
HRESULT QueryGetData(FORMATETC* pformatetc);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDataObject::QueryGetData](http://msdn.microsoft.com/library/windows/desktop/ms680637) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetdataa--idataobjectimplsetdata"></a><a name="setdata"></a>IDataObjectImpl::SetData  
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
 Finden Sie unter [IDataObject::SetData](http://msdn.microsoft.com/library/windows/desktop/ms686626) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

