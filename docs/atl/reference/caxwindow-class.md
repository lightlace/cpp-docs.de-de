---
title: CAxWindow Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAxWindowT
- CAxWindow
dev_langs:
- C++
helpviewer_keywords:
- CAxWindow class
- ATL, hosting ActiveX controls
ms.assetid: 85e79261-43e4-4770-bde0-1ff87f222b0f
caps.latest.revision: 24
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
ms.openlocfilehash: 202c68fa4044a7c7a6c47c52b8095c5e7227b56d
ms.lasthandoff: 02/24/2017

---
# <a name="caxwindow-class"></a>CAxWindow-Klasse
Diese Klasse stellt Methoden zum Bearbeiten eines Fensters ein ActiveX-Steuerelement hostet.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CAxWindow : public CWindow
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[AttachControl](#attachcontrol)|Fügt ein vorhandenes ActiveX-Steuerelement die `CAxWindow` Objekt.|  
|[CAxWindow](#caxwindow)|Erstellt ein `CAxWindow`-Objekt.|  
|[CreateControl](#createcontrol)|Erstellt ein ActiveX-Steuerelement, initialisiert es und hostet es in die `CAxWindow` Fenster.|  
|[CreateControlEx](#createcontrolex)|Erstellt ein ActiveX-Steuerelement und einen Schnittstellenzeiger (oder Zeiger) vom Steuerelement abruft.|  
|[GetWndClassName](#getwndclassname)|(Statisch) Ruft den vordefinierten Klassennamen der `CAxWindow` Objekt.|  
|[QueryControl](#querycontrol)|Ruft die **IUnknown** des gehosteten ActiveX-Steuerelements.|  
|[QueryHost](#queryhost)|Ruft die **IUnknown** Zeiger, der die `CAxWindow` Objekt.|  
|[SetExternalDispatch](#setexternaldispatch)|Legt die externen Dispatchschnittstelle, über die `CAxWindow` Objekt.|  
|[SetExternalUIHandler](#setexternaluihandler)|Legt die externen **IDocHostUIHandler** Schnittstelle, verwendet die `CAxWindow` Objekt.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator =](#operator_eq)|Weist eine **HWND** zu einer vorhandenen **CAxWindow** Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt Methoden zum Bearbeiten eines Fensters, hostet ein ActiveX-Steuerelement. Das hosting erfolgt über " **AtlAxWin80"**, die vom umschlossen ist `CAxWindow`.  
  
 Klasse `CAxWindow` wird als eine Spezialisierung der implementiert die `CAxWindowT` Klasse. Diese Spezialisierung wird folgendermaßen deklariert:  
  
 `typedef CAxWindowT<CWindow> CAxWindow;`  
  
 Wenn Sie die Basisklasse ändern müssen, können Sie `CAxWindowT` , und geben Sie die neue Basisklasse als Vorlagenargument.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  
  
##  <a name="a-nameattachcontrola--caxwindowattachcontrol"></a><a name="attachcontrol"></a>CAxWindow::AttachControl  
 Ein neues Objekt erstellt, wenn eine nicht bereits vorhanden ist, und das angegebene Steuerelement an den Host fügt.  
  
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
 Das Steuerelementobjekt anzufügende muss korrekt initialisiert werden, vor dem Aufruf von `AttachControl`.  
  
##  <a name="a-namecaxwindowa--caxwindowcaxwindow"></a><a name="caxwindow"></a>CAxWindow::CAxWindow  
 Erstellt ein `CAxWindow` -Objekt mit einem vorhandenen Objekt Fensterhandle.  
  
```
CAxWindow(HWND hWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `hWnd`  
 Ein Handle für ein vorhandenes Fensterobjekt.  
  
##  <a name="a-namecreatecontrola--caxwindowcreatecontrol"></a><a name="createcontrol"></a>CAxWindow::CreateControl  
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
 Ein Zeiger auf eine Zeichenfolge, die das Steuerelement zu erstellen. Muss in einem der folgenden Arten formatiert sein:  
  
-   Eine ProgID, z. B. "MSCAL. Calendar.7 "  
  
-   Der CLSID wie z. B. "{8E27C92B-1264-101C-8A2F-040224009C02}"  
  
-   Eine URL wie "http://www.microsoft.com"  
  
-   Ein Verweis auf ein aktives Dokument wie "file://\\\Documents\MyDoc.doc"  
  
-   Ein Fragment der HTML, wie z. B. "MSHTML:\<HTML >\<Text > Dies ist eine Textzeile\</BODY > \< /HTML >"  
  
    > [!NOTE]
    >  "MSHTML:" muss vor der HTML-Fragment ausgeführt werden, damit es als eine MSHTML-Stream festgelegt ist. Nur die ProgID und CLSID werden in Windows Mobile-Plattformen unterstützt. Embedded Windows CE-Plattformen, außer Windows Mobile mit Unterstützung für CE IE alle Typen, einschließlich der Programm-ID, CLSID, URL, auf zum aktiven Dokument und HTML-Fragment.  
  
 `pStream`  
 [in] Ein Zeiger auf einen Stream, der zum Initialisieren der Eigenschaften des Steuerelements verwendet wird. Kann **NULL**.  
  
 `ppUnkContainer`  
 [out] Die Adresse eines Zeigers, die erhalten die **IUnknown** des Containers. Kann **NULL**.  
  
 `dwResID`  
 Die Ressourcen-ID, der eine HTML-Ressource. Das WebBrowser-Steuerelement wird erstellt und mit der angegebenen Ressource geladen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die zweite Version dieser Methode verwendet wird, wird ein HTML-Steuerelement erstellt und an die durch identifizierte Ressource gebunden `dwResID`.  
  
 Diese Methode bietet das gleiche Ergebnis wie das aufrufen:  
  
 [!code-cpp[NVC_ATL_Windowing&#42;](../../atl/codesnippet/cpp/caxwindow-class_1.cpp)]  
  
 Finden Sie unter [CAxWindow2T::CreateControlLic](../../atl/reference/caxwindow2t-class.md#createcontrollic) zum Erstellen, initialisieren und ein lizenziertes ActiveX-Steuerelement zu hosten.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel mit `CreateControl`.  
  
##  <a name="a-namecreatecontrolexa--caxwindowcreatecontrolex"></a><a name="createcontrolex"></a>CAxWindow::CreateControlEx  
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
 Ein Zeiger auf eine Zeichenfolge, die das Steuerelement zu erstellen. Muss in einem der folgenden Arten formatiert sein:  
  
-   Eine ProgID, z. B. "MSCAL. Calendar.7 "  
  
-   Der CLSID wie z. B. "{8E27C92B-1264-101C-8A2F-040224009C02}"  
  
-   Eine URL wie "http://www.microsoft.com"  
  
-   Ein Verweis auf ein aktives Dokument wie "file://\\\Documents\MyDoc.doc"  
  
-   Ein Fragment der HTML, wie z. B. "MSHTML:\<HTML >\<Text > Dies ist eine Textzeile\</BODY > \< /HTML >"  
  
    > [!NOTE]
    >  "MSHTML:" muss vor der HTML-Fragment ausgeführt werden, damit es als eine MSHTML-Stream festgelegt ist. Nur die ProgID und CLSID werden in Windows Mobile-Plattformen unterstützt. Embedded Windows CE-Plattformen, außer Windows Mobile mit Unterstützung für CE IE alle Typen, einschließlich der Programm-ID, CLSID, URL, auf zum aktiven Dokument und HTML-Fragment.  
  
 `pStream`  
 [in] Ein Zeiger auf einen Stream, der zum Initialisieren der Eigenschaften des Steuerelements verwendet wird. Kann **NULL**.  
  
 `ppUnkContainer`  
 [out] Die Adresse eines Zeigers, die erhalten die **IUnknown** des Containers. Kann **NULL**.  
  
 `ppUnkControl`  
 [out] Die Adresse eines Zeigers, die erhalten die **IUnknown** des Steuerelements. Kann **NULL**.  
  
 `iidSink`  
 [in] Der Schnittstellenbezeichner des Ausgangsschnittstelle enthaltenen Objekts. Kann **IID_NULL**.  
  
 *punkSink*  
 [in] Ein Zeiger auf die **IUnknown** Schnittstelle des Senkenobjekts zum Verbindungspunkt anhand des enthaltenen Objekts verbunden sein `iidSink`.  
  
 `dwResID`  
 [in] Die Ressourcen-ID, der eine HTML-Ressource. Das WebBrowser-Steuerelement wird erstellt und mit der angegebenen Ressource geladen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ähnelt [CAxWindow::CreateControl](#createcontrol), aber im Gegensatz zu dieser Methode `CreateControlEx` darüber hinaus können Sie erhalten einen Schnittstellenzeiger auf das neu erstellte Steuerelement und eine Ereignissenke zum Empfangen von Ereignissen, die vom Steuerelement ausgelöst.  
  
 Finden Sie unter [CAxWindow2T::CreateControlLicEx](../../atl/reference/caxwindow2t-class.md#createcontrollicex) zum Erstellen, initialisieren und ein lizenziertes ActiveX-Steuerelement zu hosten.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel mit `CreateControlEx`.  
  
##  <a name="a-namegetwndclassnamea--caxwindowgetwndclassname"></a><a name="getwndclassname"></a>CAxWindow::GetWndClassName  
 Ruft den Namen der Fensterklasse ab.  
  
```
static LPCTSTR GetWndClassName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine Zeichenfolge mit dem Namen des Window-Klasse, die Lizenzpaketdatei ActiveX-Steuerelemente hosten können.  
  
##  <a name="a-nameoperatoreqa--caxwindowoperator-"></a><a name="operator_eq"></a>CAxWindow::operator =  
 Weist eine `HWND` zu einer vorhandenen `CAxWindow` Objekt.  
  
```
CAxWindow<TBase>& operator=(HWND hWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `hWnd`  
 Ein Handle für ein vorhandenes Fenster.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf das aktuelle `CAxWindow`-Objekt zurück.  
  
##  <a name="a-namequerycontrola--caxwindowquerycontrol"></a><a name="querycontrol"></a>CAxWindow::QueryControl  
 Ruft die angegebene Schnittstelle des gehosteten Steuerelements ab.  
  
```
HRESULT QueryControl(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryControl(Q** ppUnk);
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Gibt die ID der Schnittstelle des Steuerelements an.  
  
 `ppUnk`  
 [out] Ein Zeiger auf die Schnittstelle des Steuerelements. In der Vorlagenversion dieser Methode besteht keine Notwendigkeit für eine Verweis-ID als eine typisierte Schnittstelle mit einer zugewiesenen UUID übergeben wird.  
  
 `Q`  
 [in] Die Schnittstelle, die abgefragt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="a-namequeryhosta--caxwindowqueryhost"></a><a name="queryhost"></a>CAxWindow:: QueryHost  
 Gibt die angegebene Schnittstelle des Hosts zurück.  
  
```
HRESULT QueryHost(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryHost(Q** ppUnk);
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Gibt die ID der Schnittstelle des Steuerelements an.  
  
 `ppUnk`  
 [out] Ein Zeiger auf die Schnittstelle auf dem Host. In der Vorlagenversion dieser Methode besteht keine Notwendigkeit für eine Verweis-ID als eine typisierte Schnittstelle mit einer zugewiesenen UUID übergeben wird.  
  
 `Q`  
 [in] Die Schnittstelle, die abgefragt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Schnittstelle des Hosts ermöglicht den Zugriff auf die zugrunde liegenden Funktionen des Fenster hosting-Codes von implementiert **AxWin**.  
  
##  <a name="a-namesetexternaldispatcha--caxwindowsetexternaldispatch"></a><a name="setexternaldispatch"></a>CAxWindow::SetExternalDispatch  
 Legt die externen Dispatchschnittstelle für die `CAxWindow` Objekt.  
  
```
HRESULT SetExternalDispatch(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>Parameter  
 `pDisp`  
 [in] Ein Zeiger auf eine `IDispatch` Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="a-namesetexternaluihandlera--caxwindowsetexternaluihandler"></a><a name="setexternaluihandler"></a>CAxWindow::SetExternalUIHandler  
 Legt die externen [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) Schnittstelle für die `CAxWindow` Objekt.  
  
```
HRESULT SetExternalUIHandler(IDocHostUIHandlerDispatch* pUIHandler);
```  
  
### <a name="parameters"></a>Parameter  
 *pUIHandler*  
 [in] Ein Zeiger auf eine **IDocHostUIHandlerDispatch** Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die externe `IDocHostUIHandlerDispatch` Schnittstelle wird von Steuerelementen, die die Hostwebsite für Abfragen verwendet die `IDocHostUIHandlerDispatch` Schnittstelle. Das WebBrowser-Steuerelement ist ein Steuerelement, das diese Aufgaben erfüllt.  
  
## <a name="see-also"></a>Siehe auch  
 [ATLCON-Beispiel](../../visual-cpp-samples.md)   
 [CWindow-Klasse](../../atl/reference/cwindow-class.md)   
 [Grundlagen von zusammengesetzten Steuerelementen](../../atl/atl-composite-control-fundamentals.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Steuerelementcontainern – häufig gestellte Fragen](../../atl/atl-control-containment-faq.md)


