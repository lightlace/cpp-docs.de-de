---
title: IDispEventImpl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDispEventImpl
- ATLCOM/ATL::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::GetFuncInfoFromId
- ATLCOM/ATL::IDispEventImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventImpl::GetUserDefinedType
dev_langs:
- C++
helpviewer_keywords:
- IDispEventImpl class
ms.assetid: a64b5288-35cb-4638-aad6-2d15b1c7cf7b
caps.latest.revision: 22
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
ms.openlocfilehash: 07aa3e37dfb1a986f083d3efb007ea8f7c0c9243
ms.contentlocale: de-de
ms.lasthandoff: 03/31/2017

---
# <a name="idispeventimpl-class"></a>IDispEventImpl-Klasse
Diese Klasse stellt Implementierungen von der `IDispatch` Methoden.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <UINT nID, class T,
    const IID* pdiid = &IID_NULL,
    const GUID* plibid = &GUID_NULL,
    WORD wMajor = 0,
    WORD wMinor = 0, 
    class tihclass = CcomTypeInfoHolder>  
class ATL_NO_VTABLE IDispEventImpl : public IDispEventSimpleImpl<nID, T, pdiid>
```  
  
#### <a name="parameters"></a>Parameter  
 `nID`  
 Ein eindeutiger Bezeichner für das Quellobjekt. Wenn `IDispEventImpl` ist die Basisklasse für ein zusammengesetztes Steuerelement verwenden Sie die Ressourcen-ID des gewünschten Steuerelements enthaltenen für diesen Parameter. Verwenden Sie in anderen Fällen eine beliebige positive ganze Zahl.  
  
 `T`  
 Der Benutzer-Klasse, die abgeleitet ist `IDispEventImpl`.  
  
 `pdiid`  
 Der Zeiger auf die IID der ereignisanzeigeschnittstelle, die von dieser Klasse implementiert. Diese Schnittstelle muss definiert werden, in der Typbibliothek gekennzeichnet durch `plibid`, `wMajor`, und `wMinor`.  
  
 `plibid`  
 Ein Zeiger auf die Typbibliothek, die die Dispatchschnittstelle definiert verweist `pdiid`. Wenn **/ GUID_NULL**, aus dem Objekt, das als Quelle der Ereignisse wird die Typbibliothek geladen werden.  
  
 `wMajor`  
 Die Hauptversion der Typbibliothek. Der Standardwert ist 0.  
  
 `wMinor`  
 Die Nebenversion der Typbibliothek. Der Standardwert ist 0.  
  
 `tihclass`  
 Die Klasse, die zum Verwalten der Typinformationen für `T`. Der Standardwert ist eine Klasse des Typs `CComTypeInfoHolder`, aber Sie können diesen Vorlagenparameter überschreiben, indem Sie eine Klasse von einem Typ außer bereitstellen `CComTypeInfoHolder`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IDispEventImpl::_tihclass](../../atl/reference/idispeventimpl-class.md)|Die Klasse verwendet, um die Typinformationen zu verwalten. Standardmäßig `CComTypeInfoHolder`.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IDispEventImpl::IDispEventImpl](#idispeventimpl)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IDispEventImpl::GetFuncInfoFromId](#getfuncinfofromid)|Sucht den Index der Funktion für die angegebene Dispatch-ID an.|  
|[IDispEventImpl::GetIDsOfNames](#getidsofnames)|Ordnet ein einzelnes Element und einen optionalen Satz Argumentnamen mit den Namen einer entsprechenden Reihe von ganzzahligen DISPIDs.|  
|[IDispEventImpl::GetTypeInfo](#gettypeinfo)|Ruft die Typinformationen für ein Objekt ab.|  
|[IDispEventImpl::GetTypeInfoCount](#gettypeinfocount)|Ruft die Anzahl der Schnittstellen mit Typinformationen ab.|  
|[IDispEventImpl::GetUserDefinedType](#getuserdefinedtype)|Ruft den einfachen Typ eines benutzerdefinierten Typs ab.|  
  
## <a name="remarks"></a>Hinweise  
 `IDispEventImpl`bietet eine Möglichkeit, eine ereignisanzeigeschnittstelle implementieren, ohne dass Sie Implementierungscode für jede Methode/Event an dieser Schnittstelle bereitstellen. `IDispEventImpl`bietet Implementierungen von der `IDispatch` Methoden. Sie müssen nur die Implementierungen für die Ereignisse angeben, dass Sie Behandlung interessiert sind.  
  
 `IDispEventImpl`funktioniert in Verbindung mit der Ereignis-Sink-Zuordnung in die Klasse, um Ereignisse weiterzuleiten, an die entsprechenden Handler-Funktion. Diese Klasse verwenden zu können:  
  

 Hinzufügen einer [SINK_ENTRY](composite-control-macros.md#sink_entry) oder [SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex) Makro, das die Senke ereigniszuordnung für jedes Ereignis für jedes Objekt, das Sie behandeln möchten. Bei Verwendung `IDispEventImpl` als Basisklasse für ein zusammengesetztes Steuerelement, rufen Sie [AtlAdviseSinkMap](connection-point-global-functions.md#atladvisesinkmap) um festzustellen, und heben die Verbindung mit der Ereignisquellen aus, für alle Einträge in der ereignismeldung Zuordnung sink. Rufen Sie in anderen Fällen oder für größere Kontrolle [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) zum Herstellen der Verbindung zwischen dem Quellobjekt und die Basisklasse. Rufen Sie [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise) die Verbindung unterbrochen.  

  
 Leiten Sie von `IDispEventImpl` (verwenden einen eindeutigen Wert für `nID`) für jedes Objekt, das für die Ereignisse behandelt werden müssen. Sie können die Basisklasse wiederverwenden, indem Sie für ein Quellobjekt, das dann für eine andere Quellobjekt Beratung abmelden, aber die maximale Anzahl der Objekte, die gleichzeitig durch ein einzelnes Objekt behandelt werden kann, wird durch die Anzahl der beschränkt `IDispEventImpl` Basisklassen.  
  
 `IDispEventImpl`bietet die gleiche Funktionalität wie [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md), außer dass er Ruft Typinformationen über die Schnittstelle aus einer Typbibliothek, anstatt sie bereitgestellt, als Zeiger auf eine [Sie _ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) Struktur. Verwendung `IDispEventSimpleImpl` bei eine Typbibliothek, beschreibt die Ereignisschnittstelle haben oder nicht den Mehrbedarf in Verbindung mit der Verwendung der Typbibliothek vermeiden möchten.  
  
> [!NOTE]
> `IDispEventImpl`und `IDispEventSimpleImpl` Geben Sie eine eigene Implementierung von **IUnknown:: QueryInterface** aktivieren jedes `IDispEventImpl` und `IDispEventSimpleImpl` -Basisklasse als separate COM-Identität fungieren, während nach wie vor direkten Zugriff auf Member der Klasse in der wichtigsten COM-Objekt.  
  
 CE ATL-Implementierung von ActiveX-Ereignissenken nur unterstützt Rückgabewerte vom Typ HRESULT oder "void" aus Ihrem Ereignishandlermethoden; Jeder andere Rückgabewert wird nicht unterstützt, und sein Verhalten ist nicht definiert.  
  
 Weitere Informationen finden Sie unter [unterstützen IDispEventImpl](../../atl/supporting-idispeventimpl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)  
  
 `IDispEventImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="getfuncinfofromid"></a>IDispEventImpl::GetFuncInfoFromId  
 Sucht den Index der Funktion für die angegebene Dispatch-ID an.  
  
```
HRESULT GetFuncInfoFromId(
    const IID& iid,
    DISPID dispidMember,
    LCID lcid,
    _ATL_FUNC_INFO& info);
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Ein Verweis auf die ID der Funktion.  
  
 *dispidMember*  
 [in] Die Dispatch-ID der Funktion.  
  
 `lcid`  
 [in] Der Gebietsschemakontext der Funktions-ID  
  
 `info`  
 [in] Die Struktur, der angibt, wie die Funktion aufgerufen wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="getidsofnames"></a>IDispEventImpl::GetIDsOfNames  
 Ordnet ein einzelnes Element und einen optionalen Satz Argumentnamen mit den Namen einer entsprechenden Reihe von ganzzahligen DISPIDs, das für nachfolgende Aufrufe verwendet werden können [IDispatch:: Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d).  
  
```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [GetIDsOfNames](http://msdn.microsoft.com/en-us/6f6cf233-3481-436e-8d6a-51f93bf91619) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="gettypeinfo"></a>IDispEventImpl::GetTypeInfo  
 Ruft die Typinformationen für ein Objekt ab, die dann zum Abrufen der Typinformationen für eine Schnittstelle verwendet werden können.  
  
```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gettypeinfocount"></a>IDispEventImpl::GetTypeInfoCount  
 Ruft die Anzahl der Schnittstellen mit Typinformationen ab, die von einem Objekt bereitgestellt werden (0 oder 1).  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDispatch:: GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getuserdefinedtype"></a>IDispEventImpl::GetUserDefinedType  
 Ruft den einfachen Typ eines benutzerdefinierten Typs ab.  
  
```
VARTYPE GetUserDefinedType(
    ITypeInfo* pTI,
    HREFTYPE hrt);
```  
  
### <a name="parameters"></a>Parameter  
 `pTI`  
 [in] Ein Zeiger auf die [ITypeInfo](http://msdn.microsoft.com/en-us/f3356463-3373-4279-bae1-953378aa2680) Schnittstelle, die den benutzerdefinierten Typ enthält.  
  
 *hrt*  
 [in] Ein Handle für die Beschreibung des abgerufen werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Typ der Variante.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [ITypeInfo:: GetRefTypeInfo](http://msdn.microsoft.com/en-us/61d3b31d-6591-4e55-9e82-5246a168be00).  
  
##  <a name="idispeventimpl"></a>IDispEventImpl::IDispEventImpl  
 Der Konstruktor. Speichert die Werte von den Vorlagenparametern Klasse `plibid`, `pdiid`, `wMajor`, und `wMinor`.  
  
```
IDispEventImpl();
```  
  
##  <a name="tihclass"></a>IDispEventImpl::tihclass  
 Diese Typdefinition ist eine Instanz der Klassenvorlagenparameter `tihclass`.  
  
```
typedef tihclass _tihclass;
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig ist die Klasse `CComTypeInfoHolder`. `CComTypeInfoHolder`verwaltet die Typinformationen für die Klasse an.  
  
## <a name="see-also"></a>Siehe auch  
 [Sie _ATL_FUNC_INFO-Struktur](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl-Klasse](../../atl/reference/idispatchimpl-class.md)   
 [IDispEventSimpleImpl-Klasse](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK_ENTRY](composite-control-macros.md#sink_entry)   
 [SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex)   
 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
