---
title: IDispEventSimpleImpl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDispEventSimpleImpl
- ATL::IDispEventSimpleImpl
- ATL.IDispEventSimpleImpl
dev_langs:
- C++
helpviewer_keywords:
- IDispEventSimpleImpl class
ms.assetid: 971d82b7-a921-47fa-a4d8-909bed377ab0
caps.latest.revision: 27
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
ms.openlocfilehash: 6b7bc2c64139726f84f1c19c7d6b40e8d68cdc18
ms.lasthandoff: 02/24/2017

---
# <a name="idispeventsimpleimpl-class"></a>IDispEventSimpleImpl-Klasse
Diese Klasse stellt die Implementierung von der `IDispatch` Methoden, ohne das Abrufen von Informationen aus einer Typbibliothek.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <UINT nID, class T, const IID* pdiid>  
class ATL_NO_VTABLE IDispEventSimpleImpl : public _IDispEventLocator<nID, pdiid>
```    
  
#### <a name="parameters"></a>Parameter  
 `nID`  
 Ein eindeutiger Bezeichner für das Quellobjekt. Wenn `IDispEventSimpleImpl` ist die Basisklasse für ein zusammengesetztes Steuerelement, verwenden Sie die Ressourcen-ID des gewünschten enthaltenen Steuerelements für diesen Parameter. Verwenden Sie in anderen Fällen eine beliebige positive ganze Zahl.  
  
 `T`  
 Der Benutzer-Klasse, die von abgeleitet ist `IDispEventSimpleImpl`.  
  
 `pdiid`  
 Der Zeiger auf die IID der ereignisanzeigeschnittstelle, die von dieser Klasse implementiert.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IDispEventSimpleImpl::Advise](#advise)|Stellt eine Verbindung mit der Standard-Ereignisquelle.|  
|[IDispEventSimpleImpl:: DispEventAdvise](#dispeventadvise)|Stellt eine Verbindung mit der Ereignisquelle.|  
|[IDispEventSimpleImpl::DispEventUnadvise](#dispeventunadvise)|Trennt die Verbindung mit der Ereignisquelle.|  
|[IDispEventSimpleImpl::GetIDsOfNames](#getidsofnames)|Gibt **E_NOTIMPL**.|  
|[IDispEventSimpleImpl::GetTypeInfo](#gettypeinfo)|Gibt **E_NOTIMPL**.|  
|[IDispEventSimpleImpl::GetTypeInfoCount](#gettypeinfocount)|Gibt **E_NOTIMPL**.|  
|[IDispEventSimpleImpl::Invoke](#invoke)|Ruft die Ereignishandler aufgeführt im Sink-Zuordnung.|  
|[IDispEventSimpleImpl::Unadvise](#unadvise)|Trennt die Verbindung mit der Standard-Ereignisquelle.|  
  
## <a name="remarks"></a>Hinweise  
 `IDispEventSimpleImpl`bietet eine Möglichkeit der Implementierung einer ereignisanzeigeschnittstelle, ohne dass Sie Implementierungscode für jede Methode/Ereignis auf dieser Schnittstelle bereitstellen. `IDispEventSimpleImpl`bietet die Implementierung von der `IDispatch` Methoden. Sie müssen nur die Implementierungen für die Ereignisse angeben, dass Sie behandeln möchten.  
  
 `IDispEventSimpleImpl`funktioniert in Verbindung mit der [Event Sink-Zuordnung](http://msdn.microsoft.com/library/32542b3d-ac43-4139-8ac4-41c48481744f) in Ihrer Klasse Weiterleiten von Ereignissen an die entsprechenden Handler-Funktion. Diese Klasse verwendet:  
  
-   Hinzufügen einer [SINK_ENTRY_INFO](http://msdn.microsoft.com/library/1a0ae260-2c82-4926-a537-db01e5f206a7) Makro mit der Ereignis-Sink-Zuordnung für jedes Ereignis für jedes Objekt, das Sie behandeln möchten.  
  
-   Geben Sie Informationen für jedes Ereignis durch Übergabe eines Zeigers auf eine [Sie _ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) Struktur als Parameter für jeden Eintrag. Auf der X86-Plattform, die `_ATL_FUNC_INFO.cc` Wert muss mit der Callback-Funktion Aufrufen von __stdcall CC_CDECL sein.  
  
-   Rufen Sie [DispEventAdvise](#dispeventadvise) zum Herstellen der Verbindung zwischen dem Quellobjekt und die Basisklasse.  
  
-   Rufen Sie [DispEventUnadvise](#dispeventunadvise) zu trennen.  
  
 Ableiten von `IDispEventSimpleImpl` (verwenden einen eindeutigen Wert für `nID`) für jedes Objekt, das Ereignisse behandelt werden müssen. Sie können die Basisklasse wiederverwenden, indem Sie für eine Quelle-Objekt für eine andere Quellobjekt dann Anmelden Abmelden, aber die maximale Anzahl der Objekte, die gleichzeitig durch ein einzelnes Objekt behandelt werden kann, wird durch die Anzahl der beschränkt `IDispEventSimpleImpl` Basisklassen.  
  
 **IDispEventSimplImpl** bietet die gleiche Funktionalität wie [IDispEventImpl](../../atl/reference/idispeventimpl-class.md), außer dass keine Typinformationen über die Schnittstelle aus einer Typbibliothek empfangen wird. Die Assistenten generieren Code nur auf Grundlage von `IDispEventImpl`, aber Sie können `IDispEventSimpleImpl` durch den Code manuell hinzufügen. Verwendung `IDispEventSimpleImpl` Wenn Sie keine Typbibliothek, beschreibt die Ereignisschnittstelle oder möchten, den Aufwand bei der Verwendung der Typbibliothek zu verhindern.  
  
> [!NOTE]
> `IDispEventImpl`und `IDispEventSimpleImpl` Geben Sie eine eigene Implementierung von **IUnknown:: QueryInterface** aktivieren jedes `IDispEventImpl` oder `IDispEventSimpleImpl` Basisklasse fungieren Sie als separate COM-Identität und dennoch direkten Zugriffs auf Klassenmember in Ihre wichtigsten COM-Objekt.  
  
 CE ATL-Implementierung von ActiveX-Ereignissenken nur unterstützt die Rückgabewerte vom Typ HRESULT oder Void Ihre Ereignishandlermethoden; Jeder andere Rückgabewert wird nicht unterstützt, und sein Verhalten ist nicht definiert.  
  
 Weitere Informationen finden Sie unter [IDispEventImpl unterstützen](../../atl/supporting-idispeventimpl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 `IDispEventSimpleImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="a-nameadvisea--idispeventsimpleimpladvise"></a><a name="advise"></a>IDispEventSimpleImpl::Advise  
 Rufen Sie diese Methode, um eine Verbindung mit der Ereignisquelle durch dargestellten *pUnk*.  
  
```
HRESULT Advise(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>Parameter  
 *pUnk*  
 [in] Ein Zeiger auf die **IUnknown** Schnittstelle das Ereignisquellobjekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`oder Ausfälle `HRESULT` Wert.  
  
### <a name="remarks"></a>Hinweise  
 Sobald die Verbindung eingerichtet wurde, ausgelöste Ereignisse aus *pUnk* weitergeleitet werden, an die Handler in der Klasse in der Ereignis-Sink-Zuordnung.  
  
> [!NOTE]
>  Wenn Ihre Klasse abgeleitet, aus mehreren wird `IDispEventSimpleImpl` Klassen, müssen Sie diese Methode aufrufen, durch Festlegen des Gültigkeitsbereichs des Aufrufs mit einer bestimmten Basisklasse, die Sie interessiert sind unterscheiden.  
  
 `Advise`Stellt eine Verbindung mit der Standard-Ereignisquelle, ruft es die IID der Ereignisquelle des Objekts laut Standardeinstellung [AtlGetObjectSourceInterface](http://msdn.microsoft.com/library/a8528f45-fbfb-4e24-ad1a-1d69b2897155).  
  
##  <a name="a-namedispeventadvisea--idispeventsimpleimpldispeventadvise"></a><a name="dispeventadvise"></a>IDispEventSimpleImpl:: DispEventAdvise  
 Rufen Sie diese Methode, um eine Verbindung mit der Ereignisquelle durch dargestellten *pUnk*.  
  
```
HRESULT DispEventAdvise(IUnknown* pUnk  const IID* piid);
```  
  
### <a name="parameters"></a>Parameter  
 *pUnk*  
 [in] Ein Zeiger auf die **IUnknown** Schnittstelle das Ereignisquellobjekt.  
  
 `piid`  
 Ein Zeiger auf die IID des Quellobjekts Ereignis.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`oder Ausfälle `HRESULT` Wert.  
  
### <a name="remarks"></a>Hinweise  
 Anschließend kann ausgelöste Ereignisse aus *pUnk* weitergeleitet werden, an die Handler in der Klasse in der Ereignis-Sink-Zuordnung.  
  
> [!NOTE]
>  Wenn Ihre Klasse abgeleitet, aus mehreren wird `IDispEventSimpleImpl` Klassen, müssen Sie diese Methode aufrufen, durch Festlegen des Gültigkeitsbereichs des Aufrufs mit einer bestimmten Basisklasse, die Sie interessiert sind unterscheiden.  
  
 `DispEventAdvise`Stellt eine Verbindung mit der Ereignisquelle, die im angegebenen `pdiid`.  
  
##  <a name="a-namedispeventunadvisea--idispeventsimpleimpldispeventunadvise"></a><a name="dispeventunadvise"></a>IDispEventSimpleImpl::DispEventUnadvise  
 Trennt die Verbindung mit der Ereignisquelle durch dargestellten *pUnk*.  
  
```
HRESULT DispEventUnadvise(IUnknown* pUnk  const IID* piid);
```  
  
### <a name="parameters"></a>Parameter  
 *pUnk*  
 [in] Ein Zeiger auf die **IUnknown** Schnittstelle das Ereignisquellobjekt.  
  
 `piid`  
 Ein Zeiger auf die IID des Quellobjekts Ereignis.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`oder Ausfälle `HRESULT` Wert.  
  
### <a name="remarks"></a>Hinweise  
 Nachdem die Verbindung unterbrochen wird, werden Ereignisse nicht mehr an Handlerfunktionen in der Ereignis-Sink-Zuordnung weitergeleitet.  
  
> [!NOTE]
>  Wenn Ihre Klasse abgeleitet, aus mehreren wird `IDispEventSimpleImpl` Klassen, müssen Sie diese Methode aufrufen, durch Festlegen des Gültigkeitsbereichs des Aufrufs mit einer bestimmten Basisklasse, die Sie interessiert sind unterscheiden.  
  
 `DispEventAdvise`eine Verbindung mit der Ereignisquelle, die im angegebenen aufgebaut wurde unterbrochen `pdiid`.  
  
##  <a name="a-namegetidsofnamesa--idispeventsimpleimplgetidsofnames"></a><a name="getidsofnames"></a>IDispEventSimpleImpl::GetIDsOfNames  
 Diese Implementierung der **GetIDsOfNames** gibt **E_NOTIMPL**.  
  
```
STDMETHOD(GetIDsOfNames)(
    REFIID /* riid */,
    LPOLESTR* /* rgszNames */,
    UINT /* cNames */,
    LCID /* lcid */,
    DISPID* /* rgdispid */);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [GetIDsOfNames](http://msdn.microsoft.com/en-us/6f6cf233-3481-436e-8d6a-51f93bf91619) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegettypeinfoa--idispeventsimpleimplgettypeinfo"></a><a name="gettypeinfo"></a>IDispEventSimpleImpl::GetTypeInfo  
 Diese Implementierung der **IDispatch:: GetTypeInfo** gibt **E_NOTIMPL**.  
  
```
STDMETHOD(GetTypeInfo)(
    UINT /* itinfo */,
    LCID /* lcid */,
    ITypeInfo** /* pptinfo */);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDispatch:: GetTypeInfo](http://msdn.microsoft.com/en-us/cc1ec9aa-6c40-4e70-819c-a7c6dd6b8c99) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegettypeinfocounta--idispeventsimpleimplgettypeinfocount"></a><a name="gettypeinfocount"></a>IDispEventSimpleImpl::GetTypeInfoCount  
 Diese Implementierung der **IDispatch:: GetTypeInfoCount** gibt **E_NOTIMPL**.  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* /* pctinfo */);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDispatch:: GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameinvokea--idispeventsimpleimplinvoke"></a><a name="invoke"></a>IDispEventSimpleImpl::Invoke  
 Diese Implementierung der **IDispatch:: Invoke** Aufrufe, die die Ereignishandler aufgeführten im Sink-Zuordnung.  
  
```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID /* riid */,
    LCID lcid,
    WORD /* wFlags */,
    DISPPARMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* /* pexcepinfo */,
    UINT* /* puArgErr */);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDispatch:: Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d).  
  
##  <a name="a-nameunadvisea--idispeventsimpleimplunadvise"></a><a name="unadvise"></a>IDispEventSimpleImpl::Unadvise  
 Trennt die Verbindung mit der Ereignisquelle durch dargestellten *pUnk*.  
  
```
HRESULT Unadvise(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>Parameter  
 *pUnk*  
 [in] Ein Zeiger auf die **IUnknown** Schnittstelle das Ereignisquellobjekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`oder Ausfälle `HRESULT` Wert.  
  
### <a name="remarks"></a>Hinweise  
 Nachdem die Verbindung unterbrochen wird, werden Ereignisse nicht mehr an Handlerfunktionen in der Ereignis-Sink-Zuordnung weitergeleitet.  
  
> [!NOTE]
>  Wenn Ihre Klasse abgeleitet, aus mehreren wird `IDispEventSimpleImpl` Klassen, müssen Sie diese Methode aufrufen, durch Festlegen des Gültigkeitsbereichs des Aufrufs mit einer bestimmten Basisklasse, die Sie interessiert sind unterscheiden.  
  
 `Unadvise`eine Verbindung mit der Standard-Ereignisquelle, die im angegebenen aufgebaut wurde unterbrochen `pdiid`.  
  
 **Unavise** Pausen eine Verbindung mit der Standard-Ereignisquelle, ruft die IID der Ereignisquelle des Objekts laut Standardeinstellung ab [AtlGetObjectSourceInterface](http://msdn.microsoft.com/library/a8528f45-fbfb-4e24-ad1a-1d69b2897155).  
  
## <a name="see-also"></a>Siehe auch  
 [Sie _ATL_FUNC_INFO-Struktur](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl-Klasse](../../atl/reference/idispatchimpl-class.md)   
 [IDispEventImpl-Klasse](../../atl/reference/idispeventimpl-class.md)   
 [SINK_ENTRY_INFO](http://msdn.microsoft.com/library/1a0ae260-2c82-4926-a537-db01e5f206a7)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

