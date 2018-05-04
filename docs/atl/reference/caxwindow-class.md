---
title: CAxWindow Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAxWindow
- ATLWIN/ATL::CAxWindow
- ATLWIN/ATL::AttachControl
- ATLWIN/ATL::CreateControl
- ATLWIN/ATL::CreateControlEx
- ATLWIN/ATL::GetWndClassName
- ATLWIN/ATL::QueryControl
- ATLWIN/ATL::QueryHost
- ATLWIN/ATL::SetExternalDispatch
- ATLWIN/ATL::SetExternalUIHandler
dev_langs:
- C++
helpviewer_keywords:
- CAxWindow class
- ATL, hosting ActiveX controls
ms.assetid: 85e79261-43e4-4770-bde0-1ff87f222b0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 052e7ad2bfa8cc03c4eadd4926dbd84c4fd60223
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="caxwindow-class"></a>CAxWindow-Klasse
Diese Klasse stellt Methoden zum Bearbeiten eines Fensters, das hosting von ActiveX-Steuerelement.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CAxWindow : public CWindow
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[AttachControl](#attachcontrol)|Fügt ein vorhandenes ActiveX-Steuerelement, das `CAxWindow` Objekt.|  
|[CAxWindow](#caxwindow)|Erstellt ein `CAxWindow`-Objekt.|  
|[CreateControl](#createcontrol)|Erstellt ein ActiveX-Steuerelement, initialisiert es und hostet es im die `CAxWindow` Fenster.|  
|[CreateControlEx](#createcontrolex)|Erstellt ein ActiveX-Steuerelement, und ruft einen Schnittstellenzeiger (oder Zeiger) aus dem Steuerelement ab.|  
|[GetWndClassName](#getwndclassname)|(Statisch) Ruft den vordefinierten Klassennamen der `CAxWindow` Objekt.|  
|[QueryControl](#querycontrol)|Ruft die **IUnknown** des gehosteten ActiveX-Steuerelements.|  
|[QueryHost](#queryhost)|Ruft die **IUnknown** Zeiger, der die `CAxWindow` Objekt.|  
|[SetExternalDispatch](#setexternaldispatch)|Legt die externen Dispatchschnittstelle, die verwendet werden, indem die `CAxWindow` Objekt.|  
|[SetExternalUIHandler](#setexternaluihandler)|Legt den externen **IDocHostUIHandler** von verwendete Schnittstelle die `CAxWindow` Objekt.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[operator =](#operator_eq)|Weist ein **HWND** zu einem vorhandenen **CAxWindow** Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt Methoden zum Bearbeiten eines Fensters, hostet ein ActiveX-Steuerelement. Der Hostprozess gebotenen " **AtlAxWin80"**, die umschlossen `CAxWindow`.  
  
 Klasse `CAxWindow` wird als eine Spezialisierung der implementiert die `CAxWindowT` Klasse. Diese Art der Spezialisierung wird als deklariert:  
  
 `typedef CAxWindowT<CWindow> CAxWindow;`  
  
 Wenn Sie die Basisklasse der Klasse ändern müssen, können Sie `CAxWindowT` , und geben Sie die neue Basisklasse als Vorlagenargument.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  
  
##  <a name="attachcontrol"></a>  CAxWindow::AttachControl  
 Erstellt ein neues Hostobjekt an, nicht bereits vorhanden ist und fügt das angegebene Steuerelement an den Host.  
  
```
HRESULT AttachControl(
    IUnknown* pControl,
    IUnknown** ppUnkContainer);
```  
  
### <a name="parameters"></a>Parameter  
 `pControl`  
 [in] Ein Zeiger auf die **IUnknown** des Steuerelements.  
  
 `ppUnkContainer`  
 [out] Ein Zeiger auf die **IUnknown** des Hosts (die **AxWin** Objekt).  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Das Steuerelementobjekt anzufügende muss ordnungsgemäß initialisiert werden, vor dem Aufruf `AttachControl`.  
  
##  <a name="caxwindow"></a>  CAxWindow::CAxWindow  
 Erstellt eine `CAxWindow` -Objekt mit einem vorhandenen Objekt Fensterhandle.  
  
```
CAxWindow(HWND hWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `hWnd`  
 Ein Handle für ein vorhandenes Fensterobjekt.  
  
##  <a name="createcontrol"></a>  CAxWindow::CreateControl  
 Erstellt ein ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster.  
  
```
HRESULT CreateControl(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL);

HRESULT CreateControl(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Ein Zeiger auf eine Zeichenfolge, die das Steuerelement zu erstellen. Muss in einem der folgenden Arten formatiert werden:  
  
-   Eine ProgID z. B. "MSCAL. Calendar.7 "  
  
-   CLSID z. B. "{8E27C92B-1264-101C-8A2F-040224009C02}"  
  
-   Eine URL wie "http://www.microsoft.com"  
  
-   Ein Verweis auf eine aktive Dokument wie "file://\\\Documents\MyDoc.doc"  
  
-   Ein Fragment von HTML, wie z. B. "MSHTML:\<HTML >\<Text > Dies ist eine Textzeile\</BODY >\<paarweise >"  
  
    > [!NOTE]
    >  "MSHTML:" muss vor der HTML-Fragment ausgeführt werden, damit es als ein MSHTML-Stream nicht festgelegt ist. Nur die ProgID und CLSID werden in Windows Mobile-Plattformen unterstützt. Embedded Windows CE-Plattformen, als Windows Mobile mit Unterstützung für CE IE alle Typen, die ProgID einschließlich, CLSID, URL, verweisen auf aktive Dokument und HTML-Fragment.  
  
 `pStream`  
 [in] Ein Zeiger auf einen Stream, der zum Initialisieren der Eigenschaften des Steuerelements verwendet wird. Kann **NULL**.  
  
 `ppUnkContainer`  
 [out] Die Adresse eines Zeigers, die erhalten die **IUnknown** des Containers. Kann **NULL**.  
  
 `dwResID`  
 Die Ressourcen-ID einer HTML-Ressource. Das WebBrowser-Steuerelement wird erstellt und mit der angegebenen Ressource geladen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die zweite Version dieser Methode verwendet wird, wird ein HTML-Steuerelement erstellt und an die identifizierte Ressource gebunden `dwResID`.  
  
 Diese Methode bietet das gleiche Ergebnis wie das aufrufen:  
  
 [!code-cpp[NVC_ATL_Windowing#42](../../atl/codesnippet/cpp/caxwindow-class_1.cpp)]  
  
 Finden Sie unter [CAxWindow2T::CreateControlLic](../../atl/reference/caxwindow2t-class.md#createcontrollic) zum Erstellen, initialisieren und ein lizenziertes ActiveX-Steuerelement zu hosten.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, verwendet `CreateControl`.  
  
##  <a name="createcontrolex"></a>  CAxWindow::CreateControlEx  
 Erstellt ein ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster.  
  
```
HRESULT CreateControlEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);

HRESULT CreateControlEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Ein Zeiger auf eine Zeichenfolge, die das Steuerelement zu erstellen. Muss in einem der folgenden Arten formatiert werden:  
  
-   Eine ProgID z. B. "MSCAL. Calendar.7 "  
  
-   CLSID z. B. "{8E27C92B-1264-101C-8A2F-040224009C02}"  
  
-   Eine URL wie "http://www.microsoft.com"  
  
-   Ein Verweis auf eine aktive Dokument wie "file://\\\Documents\MyDoc.doc"  
  
-   Ein Fragment von HTML, wie z. B. "MSHTML:\<HTML >\<Text > Dies ist eine Textzeile\</BODY >\<paarweise >"  
  
    > [!NOTE]
    >  "MSHTML:" muss vor der HTML-Fragment ausgeführt werden, damit es als ein MSHTML-Stream nicht festgelegt ist. Nur die ProgID und CLSID werden in Windows Mobile-Plattformen unterstützt. Embedded Windows CE-Plattformen, als Windows Mobile mit Unterstützung für CE IE alle Typen, die ProgID einschließlich, CLSID, URL, verweisen auf aktive Dokument und HTML-Fragment.  
  
 `pStream`  
 [in] Ein Zeiger auf einen Stream, der zum Initialisieren der Eigenschaften des Steuerelements verwendet wird. Kann **NULL**.  
  
 `ppUnkContainer`  
 [out] Die Adresse eines Zeigers, die erhalten die **IUnknown** des Containers. Kann **NULL**.  
  
 `ppUnkControl`  
 [out] Die Adresse eines Zeigers, die erhalten die **IUnknown** des Steuerelements. Kann **NULL**.  
  
 `iidSink`  
 [in] Der Schnittstellenbezeichner einer ausgehenden Schnittstelle auf die darin enthaltenen Objekte. Kann **IID_NULL**.  
  
 *punkSink*  
 [in] Ein Zeiger auf die **IUnknown** -Schnittstelle des Senkenobjekts Verbindung mit dem Verbindungspunkt am der darin enthaltenen Objekte angegeben werden `iidSink`.  
  
 `dwResID`  
 [in] Die Ressourcen-ID einer HTML-Ressource. Das WebBrowser-Steuerelement wird erstellt und mit der angegebenen Ressource geladen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ist vergleichbar mit [CAxWindow::CreateControl](#createcontrol), aber im Gegensatz zu dieser Methode `CreateControlEx` können außerdem erhalten einen Schnittstellenzeiger auf das neu erstellte Steuerelement, und richten Sie eine Ereignissenke zum Empfangen von Ereignissen, die vom Steuerelement ausgelöst.  
  
 Finden Sie unter [CAxWindow2T::CreateControlLicEx](../../atl/reference/caxwindow2t-class.md#createcontrollicex) zum Erstellen, initialisieren und ein lizenziertes ActiveX-Steuerelement zu hosten.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, verwendet `CreateControlEx`.  
  
##  <a name="getwndclassname"></a>  CAxWindow::GetWndClassName  
 Ruft den Namen der Fensterklasse ab.  
  
```
static LPCTSTR GetWndClassName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen der Fensterklasse, die Lizenzpaketdatei ActiveX-Steuerelemente hosten können.  
  
##  <a name="operator_eq"></a>  CAxWindow::operator =  
 Weist ein `HWND` zu einem vorhandenen `CAxWindow` Objekt.  
  
```
CAxWindow<TBase>& operator=(HWND hWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `hWnd`  
 Ein Handle für ein vorhandenes Fenster.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf das aktuelle `CAxWindow`-Objekt zurück.  
  
##  <a name="querycontrol"></a>  CAxWindow::QueryControl  
 Ruft die angegebene Schnittstelle des gehosteten Steuerelements ab.  
  
```
HRESULT QueryControl(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryControl(Q** ppUnk);
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Gibt die IID der Schnittstelle des Steuerelements an.  
  
 `ppUnk`  
 [out] Ein Zeiger auf die Schnittstelle des Steuerelements. In der Vorlagenversion dieser Methode besteht keine Notwendigkeit für eine Verweis-ID als eine typisierte Schnittstelle mit einer zugewiesenen UUID übergeben wird.  
  
 `Q`  
 [in] Die Schnittstelle, die abgefragt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="queryhost"></a>  CAxWindow:: QueryHost  
 Gibt die angegebene Schnittstelle des Hosts zurück.  
  
```
HRESULT QueryHost(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryHost(Q** ppUnk);
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Gibt die IID der Schnittstelle des Steuerelements an.  
  
 `ppUnk`  
 [out] Ein Zeiger auf die Schnittstelle auf dem Host. In der Vorlagenversion dieser Methode besteht keine Notwendigkeit für eine Verweis-ID als eine typisierte Schnittstelle mit einer zugewiesenen UUID übergeben wird.  
  
 `Q`  
 [in] Die Schnittstelle, die abgefragt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Schnittstelle des Hosts ermöglicht den Zugriff auf die zugrunde liegenden Funktionalität Fenster hosting-Code, durch implementiert **AxWin**.  
  
##  <a name="setexternaldispatch"></a>  CAxWindow::SetExternalDispatch  
 Legt die externen Dispatchschnittstelle für die `CAxWindow` Objekt.  
  
```
HRESULT SetExternalDispatch(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>Parameter  
 `pDisp`  
 [in] Ein Zeiger auf eine `IDispatch` Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="setexternaluihandler"></a>  CAxWindow::SetExternalUIHandler  
 Legt den externen [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) eine Schnittstelle für die `CAxWindow` Objekt.  
  
```
HRESULT SetExternalUIHandler(IDocHostUIHandlerDispatch* pUIHandler);
```  
  
### <a name="parameters"></a>Parameter  
 *pUIHandler*  
 [in] Ein Zeiger auf ein **IDocHostUIHandlerDispatch** Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die externe `IDocHostUIHandlerDispatch` Schnittstelle wird von Steuerelementen, die dem Host der Website für Abfragen verwendet die `IDocHostUIHandlerDispatch` Schnittstelle. Das WebBrowser-Steuerelement ist ein Steuerelement, die dies tut.  
  
## <a name="see-also"></a>Siehe auch  
 [ATLCON-Beispiel](../../visual-cpp-samples.md)   
 [CWindow-Klasse](../../atl/reference/cwindow-class.md)   
 [Grundlagen von zusammengesetzten Steuerelementen](../../atl/atl-composite-control-fundamentals.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [Zur steuerelementkapselung](../../atl/atl-control-containment-faq.md)

