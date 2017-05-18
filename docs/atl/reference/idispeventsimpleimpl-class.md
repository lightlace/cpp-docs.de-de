---
title: IDispEventSimpleImpl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl::Advise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventAdvise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventUnadvise
- ATLCOM/ATL::IDispEventSimpleImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventSimpleImpl::Invoke
- ATLCOM/ATL::IDispEventSimpleImpl::Unadvise
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 392e8a8d8d38b0eaacce4ab013c46476516f46f7
ms.contentlocale: de-de
ms.lasthandoff: 03/31/2017

---
# <a name="idispeventsimpleimpl-class"></a>IDispEventSimpleImpl-Klasse
Diese Klasse stellt Implementierungen von der `IDispatch` Methoden ohne das Abrufen von Informationen aus einer Typbibliothek.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <UINT nID, class T, const IID* pdiid>  
class ATL_NO_VTABLE IDispEventSimpleImpl : public _IDispEventLocator<nID, pdiid>
```    
  
#### <a name="parameters"></a>Parameter  
 `nID`  
 Ein eindeutiger Bezeichner für das Quellobjekt. Wenn `IDispEventSimpleImpl` ist die Basisklasse für ein zusammengesetztes Steuerelement verwenden Sie die Ressourcen-ID des gewünschten Steuerelements enthaltenen für diesen Parameter. Verwenden Sie in anderen Fällen eine beliebige positive ganze Zahl.  
  
 `T`  
 Der Benutzer-Klasse, die abgeleitet ist `IDispEventSimpleImpl`.  
  
 `pdiid`  
 Der Zeiger auf die IID der ereignisanzeigeschnittstelle, die von dieser Klasse implementiert.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IDispEventSimpleImpl::Advise](#advise)|Herstellen einer Verbindung mit der Standard-Ereignisquelle.|  
|[IDispEventSimpleImpl:: DispEventAdvise](#dispeventadvise)|Herstellen einer Verbindung mit der Ereignisquelle.|  
|[IDispEventSimpleImpl::DispEventUnadvise](#dispeventunadvise)|Trennt die Verbindung mit der Ereignisquelle.|  
|[IDispEventSimpleImpl::GetIDsOfNames](#getidsofnames)|Gibt **E_NOTIMPL**.|  
|[IDispEventSimpleImpl::GetTypeInfo](#gettypeinfo)|Gibt **E_NOTIMPL**.|  
|[IDispEventSimpleImpl::GetTypeInfoCount](#gettypeinfocount)|Gibt **E_NOTIMPL**.|  
|[IDispEventSimpleImpl::Invoke](#invoke)|Ruft die Ereignishandler aufgeführt im Ereignistext Sink-Zuordnung.|  
|[IDispEventSimpleImpl::Unadvise](#unadvise)|Trennt die Verbindung mit der Standard-Ereignisquelle.|  
  
## <a name="remarks"></a>Hinweise  
 `IDispEventSimpleImpl`bietet eine Möglichkeit, eine ereignisanzeigeschnittstelle implementieren, ohne dass Sie Implementierungscode für jede Methode/Event an dieser Schnittstelle bereitstellen. `IDispEventSimpleImpl`bietet Implementierungen von der `IDispatch` Methoden. Sie müssen nur die Implementierungen für die Ereignisse angeben, dass Sie Behandlung interessiert sind.  
  
 `IDispEventSimpleImpl`funktioniert in Verbindung mit der Ereignis-Sink-Zuordnung in die Klasse, um Ereignisse weiterzuleiten, an die entsprechenden Handler-Funktion. Diese Klasse verwenden zu können:  
  
-   Hinzufügen einer [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info) Makro, das die Senke ereigniszuordnung für jedes Ereignis für jedes Objekt, das Sie behandeln möchten.  
  
-   Geben Sie Typinformationen für jedes Ereignis, durch die Übergabe eines Zeigers auf ein [Sie _ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) Struktur als Parameter für jeden Eintrag. Auf der X86-Plattform, die `_ATL_FUNC_INFO.cc` Wert muss die Rückruffunktion, die beim Aufrufen der Methode der __stdcall CC_CDECL befinden.  
  
-   Rufen Sie [DispEventAdvise](#dispeventadvise) zum Herstellen der Verbindung zwischen dem Quellobjekt und die Basisklasse.  
  
-   Rufen Sie [DispEventUnadvise](#dispeventunadvise) die Verbindung unterbrochen.  
  
 Leiten Sie von `IDispEventSimpleImpl` (verwenden einen eindeutigen Wert für `nID`) für jedes Objekt, das für die Ereignisse behandelt werden müssen. Sie können die Basisklasse wiederverwenden, indem Sie für ein Quellobjekt, das dann für eine andere Quellobjekt Beratung abmelden, aber die maximale Anzahl der Objekte, die gleichzeitig durch ein einzelnes Objekt behandelt werden kann, wird durch die Anzahl der beschränkt `IDispEventSimpleImpl` Basisklassen.  
  
 **IDispEventSimplImpl** bietet die gleiche Funktionalität wie [IDispEventImpl](../../atl/reference/idispeventimpl-class.md), außer dass Typinformationen über die Schnittstelle aus einer Typbibliothek nicht abgerufen werden wird. Die Assistenten Generieren von Code, die nur auf Grundlage `IDispEventImpl`, Sie können jedoch `IDispEventSimpleImpl` durch Hinzufügen des Codes per hand katalogisiert wird. Verwendung `IDispEventSimpleImpl` Wenn Sie keine Typbibliothek, die Ereignisschnittstelle beschreibt oder den Mehrbedarf in Verbindung mit der Verwendung der Typbibliothek vermeiden möchten.  
  
> [!NOTE]
> `IDispEventImpl`und `IDispEventSimpleImpl` Geben Sie eine eigene Implementierung von **IUnknown:: QueryInterface** aktivieren jedes `IDispEventImpl` oder `IDispEventSimpleImpl` -Basisklasse als separate COM-Identität fungieren, während nach wie vor direkten Zugriff auf Member der Klasse in der wichtigsten COM-Objekt.  
  
 CE ATL-Implementierung von ActiveX-Ereignissenken nur unterstützt Rückgabewerte vom Typ HRESULT oder "void" aus Ihrem Ereignishandlermethoden; Jeder andere Rückgabewert wird nicht unterstützt, und sein Verhalten ist nicht definiert.  
  
 Weitere Informationen finden Sie unter [unterstützen IDispEventImpl](../../atl/supporting-idispeventimpl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 `IDispEventSimpleImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="advise"></a>IDispEventSimpleImpl::Advise  
 Rufen Sie diese Methode zum Herstellen einer Verbindung mit der Ereignisquelle dargestellte *pUnk*.  
  
```
HRESULT Advise(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>Parameter  
 *pUnk*  
 [in] Ein Zeiger auf die **IUnknown** Schnittstelle des Quellobjekts Ereignis.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`oder jeder Fehler `HRESULT` Wert.  
  
### <a name="remarks"></a>Hinweise  
 Nachdem die Verbindung hergestellt ist, werden Ereignisse aus ausgelöst *pUnk* wird an Handler in der Klasse über die Senke ereigniszuordnung weitergeleitet werden.  
  
> [!NOTE]
>  Wenn Ihre Klasse abgeleitet, aus mehreren ist `IDispEventSimpleImpl` Klassen, müssen Sie eindeutig zu machen Aufrufe dieser Methode durch Bereichsauswahl den Aufruf mit einer bestimmten Basisklasse, die Sie von Interesse sind.  
  
 `Advise`Stellt eine Verbindung mit der Standard-Ereignisquelle, ruft es die IID der Ereignisquelle Standardwert des Objekts gemäß [AtlGetObjectSourceInterface](composite-control-global-functions.md#atlgetobjectsourceinterface).  
  
##  <a name="dispeventadvise"></a>IDispEventSimpleImpl:: DispEventAdvise  
 Rufen Sie diese Methode zum Herstellen einer Verbindung mit der Ereignisquelle dargestellte *pUnk*.  
  
```
HRESULT DispEventAdvise(IUnknown* pUnk  const IID* piid);
```  
  
### <a name="parameters"></a>Parameter  
 *pUnk*  
 [in] Ein Zeiger auf die **IUnknown** Schnittstelle des Quellobjekts Ereignis.  
  
 `piid`  
 Ein Zeiger auf die IID des Quellobjekts Ereignis.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`oder jeder Fehler `HRESULT` Wert.  
  
### <a name="remarks"></a>Hinweise  
 Anschließend Ereignisse ausgelöst von *pUnk* wird an Handler in der Klasse über die Senke ereigniszuordnung weitergeleitet werden.  
  
> [!NOTE]
>  Wenn Ihre Klasse abgeleitet, aus mehreren ist `IDispEventSimpleImpl` Klassen, müssen Sie eindeutig zu machen Aufrufe dieser Methode durch Bereichsauswahl den Aufruf mit einer bestimmten Basisklasse, die Sie von Interesse sind.  
  
 `DispEventAdvise`Stellt eine Verbindung mit der Ereignisquelle, die im angegebenen `pdiid`.  
  
##  <a name="dispeventunadvise"></a>IDispEventSimpleImpl::DispEventUnadvise  
 Trennt die Verbindung mit der Ereignisquelle dargestellte *pUnk*.  
  
```
HRESULT DispEventUnadvise(IUnknown* pUnk  const IID* piid);
```  
  
### <a name="parameters"></a>Parameter  
 *pUnk*  
 [in] Ein Zeiger auf die **IUnknown** Schnittstelle des Quellobjekts Ereignis.  
  
 `piid`  
 Ein Zeiger auf die IID des Quellobjekts Ereignis.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`oder jeder Fehler `HRESULT` Wert.  
  
### <a name="remarks"></a>Hinweise  
 Sobald die Verbindung unterbrochen wird, werden Ereignisse nicht mehr an Handlerfunktionen in der Senke ereigniszuordnung weitergeleitet werden.  
  
> [!NOTE]
>  Wenn Ihre Klasse abgeleitet, aus mehreren ist `IDispEventSimpleImpl` Klassen, müssen Sie eindeutig zu machen Aufrufe dieser Methode durch Bereichsauswahl den Aufruf mit einer bestimmten Basisklasse, die Sie von Interesse sind.  
  
 `DispEventAdvise`eine Verbindung mit der Ereignisquelle, die im angegebenen aufgebaut wurde unterbrochen `pdiid`.  
  
##  <a name="getidsofnames"></a>IDispEventSimpleImpl::GetIDsOfNames  
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
  
##  <a name="gettypeinfo"></a>IDispEventSimpleImpl::GetTypeInfo  
 Diese Implementierung der **IDispatch:: GetTypeInfo** gibt **E_NOTIMPL**.  
  
```
STDMETHOD(GetTypeInfo)(
    UINT /* itinfo */,
    LCID /* lcid */,
    ITypeInfo** /* pptinfo */);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDispatch:: GetTypeInfo](http://msdn.microsoft.com/en-us/cc1ec9aa-6c40-4e70-819c-a7c6dd6b8c99) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="gettypeinfocount"></a>IDispEventSimpleImpl::GetTypeInfoCount  
 Diese Implementierung der **IDispatch:: GetTypeInfoCount** gibt **E_NOTIMPL**.  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* /* pctinfo */);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDispatch:: GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="invoke"></a>IDispEventSimpleImpl::Invoke  
 Diese Implementierung der **IDispatch:: Invoke** Aufrufe, die die Ereignishandler aufgeführten im Ereignistext Sink-Zuordnung.  
  
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
  
##  <a name="unadvise"></a>IDispEventSimpleImpl::Unadvise  
 Trennt die Verbindung mit der Ereignisquelle dargestellte *pUnk*.  
  
```
HRESULT Unadvise(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>Parameter  
 *pUnk*  
 [in] Ein Zeiger auf die **IUnknown** Schnittstelle des Quellobjekts Ereignis.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`oder jeder Fehler `HRESULT` Wert.  
  
### <a name="remarks"></a>Hinweise  
 Sobald die Verbindung unterbrochen wird, werden Ereignisse nicht mehr an Handlerfunktionen in der Senke ereigniszuordnung weitergeleitet werden.  
  
> [!NOTE]
>  Wenn Ihre Klasse abgeleitet, aus mehreren ist `IDispEventSimpleImpl` Klassen, müssen Sie eindeutig zu machen Aufrufe dieser Methode durch Bereichsauswahl den Aufruf mit einer bestimmten Basisklasse, die Sie von Interesse sind.  
  
 `Unadvise`eine Verbindung mit der Standard-Ereignisquelle, die im angegebenen aufgebaut wurde unterbrochen `pdiid`.  
  
 **Unavise** hält eine Verbindung mit der Standard-Ereignisquelle, ruft die IID der Ereignisquelle des Objekts gemäß Standardeinstellung ab [AtlGetObjectSourceInterface](composite-control-global-functions.md#atlgetobjectsourceinterface).  
  
## <a name="see-also"></a>Siehe auch  
 [Sie _ATL_FUNC_INFO-Struktur](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl-Klasse](../../atl/reference/idispatchimpl-class.md)   
 [IDispEventImpl-Klasse](../../atl/reference/idispeventimpl-class.md)   
 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)   
 [Klassenübersicht](../../atl/atl-class-overview.md)

