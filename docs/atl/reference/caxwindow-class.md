---
title: CAxWindow-Klasse
ms.date: 11/04/2016
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
helpviewer_keywords:
- CAxWindow class
- ATL, hosting ActiveX controls
ms.assetid: 85e79261-43e4-4770-bde0-1ff87f222b0f
ms.openlocfilehash: 3cf1c773c96a2bf1bc6c67420d72052e68ee2a53
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57297592"
---
# <a name="caxwindow-class"></a>CAxWindow-Klasse

Diese Klasse stellt Methoden zum Bearbeiten eines Fensters, das Hosten eines ActiveX-Steuerelements.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

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
|[CreateControl](#createcontrol)|Erstellt ein ActiveX-Steuerelement, initialisiert es und hostet es in der `CAxWindow` Fenster.|
|[CreateControlEx](#createcontrolex)|Erstellt ein ActiveX-Steuerelement, und ruft einen Schnittstellenzeiger (oder Zeiger) aus dem Steuerelement ab.|
|[GetWndClassName](#getwndclassname)|(Statisch) Ruft ab, der vordefinierten Klassenname, der die `CAxWindow` Objekt.|
|[QueryControl](#querycontrol)|Ruft die `IUnknown` des gehosteten ActiveX-Steuerelements.|
|[QueryHost](#queryhost)|Ruft die `IUnknown` Zeiger, der die `CAxWindow` Objekt.|
|[SetExternalDispatch](#setexternaldispatch)|Legt die externen Dispatchschnittstelle ein, die die `CAxWindow` Objekt.|
|[SetExternalUIHandler](#setexternaluihandler)|Legt den externen `IDocHostUIHandler` Schnittstelle, die verwendet werden, indem die `CAxWindow` Objekt.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator =](#operator_eq)|Weist ein HWND zu einem vorhandenen `CAxWindow` Objekt.|

## <a name="remarks"></a>Hinweise

Diese Klasse stellt Methoden zum Bearbeiten eines Fensters, hostet ein ActiveX-Steuerelement. Das hosting erfolgt über " **AtlAxWin80"**, der umschlossen ist `CAxWindow`.

Klasse `CAxWindow` wird als eine Spezialisierung der implementiert die `CAxWindowT` Klasse. Diese Spezialisierung wird folgendermaßen deklariert:

`typedef CAxWindowT<CWindow> CAxWindow;`

Wenn Sie die Basisklasse der Klasse ändern müssen, können Sie `CAxWindowT` , und geben Sie die neue Basisklasse als Vorlagenargument.

## <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="attachcontrol"></a>  CAxWindow::AttachControl

Erstellt ein neues Hostobjekt an, wenn eine nicht bereits vorhanden ist, und das angegebene Steuerelement an den Host fügt.

```
HRESULT AttachControl(
    IUnknown* pControl,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>Parameter

*pControl*<br/>
[in] Ein Zeiger auf die `IUnknown` des Steuerelements.

*ppUnkContainer*<br/>
[out] Ein Zeiger auf die `IUnknown` des Hosts (die `AxWin` Objekt).

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Das Steuerelementobjekt anzufügende muss korrekt initialisiert werden, vor dem Aufruf `AttachControl`.

##  <a name="caxwindow"></a>  CAxWindow::CAxWindow

Erstellt eine `CAxWindow` -Objekt unter Verwendung eines vorhandenen Fenster Objekt-Handles.

```
CAxWindow(HWND hWnd = NULL);
```

### <a name="parameters"></a>Parameter

*hWnd*<br/>
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

*Wert*<br/>
Ein Zeiger auf eine Zeichenfolge, die das Steuerelement zu erstellen. Muss in einem der folgenden Arten formatiert werden:

- Eine ProgID, z. B. "MSCAL. Calendar.7 "

- Eine CLSID wie z. B. "{8E27C92B-1264-101C-8A2F-040224009C02}"

- Eine URL wie z. B. "<http://www.microsoft.com>"

- Ein Verweis auf ein aktives Dokument wie "file://\\\Documents\MyDoc.doc"

- Ein Fragment der HTML wie z. B. "MSHTML:\<HTML >\<Text > Dies ist eine Textzeile\</BODY > \< /HTML >"

   > [!NOTE]
   > "MSHTML:" muss vor der HTML-Fragment stehen, damit es als einen MSHTML-Datenstrom festgelegt ist. Nur die ProgID und CLSID werden in Windows Mobile-Plattformen unterstützt. Embedded Windows CE-Plattformen, außer Windows Mobile mit Unterstützung für CE-IE-Unterstützung aller Typen, die ProgID einschließlich, CLSID, URL, verweisen auf das aktive Dokument und der HTML-Fragment.

*pStream*<br/>
[in] Ein Zeiger auf einen Stream, der zum Initialisieren der Eigenschaften des Steuerelements verwendet wird. NULL kann sein.

*ppUnkContainer*<br/>
[out] Die Adresse eines Zeigers, der erhält die `IUnknown` des Containers. NULL kann sein.

*dwResID*<br/>
Die Ressourcen-ID, der eine HTML-Ressource. Das WebBrowser-Steuerelement wird erstellt und mit der angegebenen Ressource geladen werden.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Wenn die zweite Version dieser Methode verwendet wird, wird ein HTML-Steuerelement erstellt und an die identifizierte Ressource gebunden *DwResID*.

Diese Methode bietet das gleiche Ergebnis wie das aufrufen:

[!code-cpp[NVC_ATL_Windowing#42](../../atl/codesnippet/cpp/caxwindow-class_1.cpp)]

Finden Sie unter [CAxWindow2T::CreateControlLic](../../atl/reference/caxwindow2t-class.md#createcontrollic) zum Erstellen, initialisieren und ein lizenziertes ActiveX-Steuerelement zu hosten.

### <a name="example"></a>Beispiel

Finden Sie unter [Hosten von ActiveX-Steuerelemente mithilfe von ATL-xhost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, verwendet `CreateControl`.

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

*Wert*<br/>
Ein Zeiger auf eine Zeichenfolge, die das Steuerelement zu erstellen. Muss in einem der folgenden Arten formatiert werden:

- Eine ProgID, z. B. "MSCAL. Calendar.7 "

- Eine CLSID wie z. B. "{8E27C92B-1264-101C-8A2F-040224009C02}"

- Eine URL wie z. B. "<http://www.microsoft.com>"

- Ein Verweis auf ein aktives Dokument wie "file://\\\Documents\MyDoc.doc"

- Ein Fragment der HTML wie z. B. "MSHTML:\<HTML >\<Text > Dies ist eine Textzeile\</BODY > \< /HTML >"

   > [!NOTE]
   > "MSHTML:" muss vor der HTML-Fragment stehen, damit es als einen MSHTML-Datenstrom festgelegt ist. Nur die ProgID und CLSID werden in Windows Mobile-Plattformen unterstützt. Embedded Windows CE-Plattformen, außer Windows Mobile mit Unterstützung für CE-IE-Unterstützung aller Typen, die ProgID einschließlich, CLSID, URL, verweisen auf das aktive Dokument und der HTML-Fragment.

*pStream*<br/>
[in] Ein Zeiger auf einen Stream, der zum Initialisieren der Eigenschaften des Steuerelements verwendet wird. NULL kann sein.

*ppUnkContainer*<br/>
[out] Die Adresse eines Zeigers, der erhält die `IUnknown` des Containers. NULL kann sein.

*ppUnkControl*<br/>
[out] Die Adresse eines Zeigers, der erhält die `IUnknown` des Steuerelements. NULL kann sein.

*iidSink*<br/>
[in] Der Schnittstellenbezeichner einer ausgehenden Schnittstelle für das enthaltene Objekt. Can be IID_NULL.

*punkSink*<br/>
[in] Ein Zeiger auf die `IUnknown` -Schnittstelle des Senkenobjekts mit dem Verbindungspunkt am anhand des enthaltenen Objekts verbunden sein, *IidSink*.

*dwResID*<br/>
[in] Die Ressourcen-ID, der eine HTML-Ressource. Das WebBrowser-Steuerelement wird erstellt und mit der angegebenen Ressource geladen werden.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Diese Methode ähnelt [CAxWindow::CreateControl](#createcontrol), aber im Gegensatz zu dieser Methode `CreateControlEx` auch können Sie einen Schnittstellenzeiger auf das neu erstellte Steuerelement zu empfangen, und richten Sie eine Ereignissenke, zum Empfangen von Ereignissen, die vom Steuerelement ausgelöst.

Finden Sie unter [CAxWindow2T::CreateControlLicEx](../../atl/reference/caxwindow2t-class.md#createcontrollicex) zum Erstellen, initialisieren und ein lizenziertes ActiveX-Steuerelement zu hosten.

### <a name="example"></a>Beispiel

Finden Sie unter [Hosten von ActiveX-Steuerelemente mithilfe von ATL-xhost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, verwendet `CreateControlEx`.

##  <a name="getwndclassname"></a>  CAxWindow::GetWndClassName

Ruft den Namen der Fensterklasse ab.

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine Zeichenfolge, die mit dem Namen der Window-Klasse, die Lizenzpaketdatei ActiveX-Steuerelemente hosten können.

##  <a name="operator_eq"></a>  CAxWindow::operator =

Weist ein HWND zu einem vorhandenen `CAxWindow` Objekt.

```
CAxWindow<TBase>& operator=(HWND hWnd);
```

### <a name="parameters"></a>Parameter

*hWnd*<br/>
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

*iid*<br/>
[in] Gibt die IID der Schnittstelle des Steuerelements an.

*ppUnk*<br/>
[out] Ein Zeiger auf die Schnittstelle des Steuerelements. In der Vorlagenversion dieser Methode besteht keine Notwendigkeit für eine Verweis-ID, solange eine typisierte Schnittstelle mit einer zugewiesenen UUID übergeben wird.

*Q*<br/>
[in] Die Schnittstelle, die abgefragt wird.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

##  <a name="queryhost"></a>  CAxWindow::QueryHost

Gibt die angegebene Schnittstelle des Hosts zurück.

```
HRESULT QueryHost(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryHost(Q** ppUnk);
```

### <a name="parameters"></a>Parameter

*iid*<br/>
[in] Gibt die IID der Schnittstelle des Steuerelements an.

*ppUnk*<br/>
[out] Ein Zeiger auf die Schnittstelle auf dem Host. In der Vorlagenversion dieser Methode besteht keine Notwendigkeit für eine Verweis-ID, solange eine typisierte Schnittstelle mit einer zugewiesenen UUID übergeben wird.

*Q*<br/>
[in] Die Schnittstelle, die abgefragt wird.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Schnittstelle des Hosts ermöglicht den Zugriff auf die zugrunde liegende Funktionalität des Fenster-hosting Codes implementiert `AxWin`.

##  <a name="setexternaldispatch"></a>  CAxWindow::SetExternalDispatch

Legt die externen Dispatchschnittstelle für die `CAxWindow` Objekt.

```
HRESULT SetExternalDispatch(IDispatch* pDisp);
```

### <a name="parameters"></a>Parameter

*pDisp*<br/>
[in] Ein Zeiger auf ein `IDispatch` Schnittstelle.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

##  <a name="setexternaluihandler"></a>  CAxWindow::SetExternalUIHandler

Legt den externen [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) eine Schnittstelle für die `CAxWindow` Objekt.

```
HRESULT SetExternalUIHandler(IDocHostUIHandlerDispatch* pUIHandler);
```

### <a name="parameters"></a>Parameter

*pUIHandler*<br/>
[in] Ein Zeiger auf ein `IDocHostUIHandlerDispatch` Schnittstelle.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die externe `IDocHostUIHandlerDispatch` Schnittstelle wird von Steuerelementen, die der Hostwebsite für Abfragen verwendet die `IDocHostUIHandlerDispatch` Schnittstelle. Das WebBrowser-Steuerelement ist ein Steuerelement, die dies tut.

## <a name="see-also"></a>Siehe auch

[ATLCON-Beispiel](../../visual-cpp-samples.md)<br/>
[CWindow-Klasse](../../atl/reference/cwindow-class.md)<br/>
[Grundlagen von zusammengesetzten Steuerelementen](../../atl/atl-composite-control-fundamentals.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[Steuerelementkapselung – häufig gestellte Fragen](../../atl/atl-control-containment-faq.md)
