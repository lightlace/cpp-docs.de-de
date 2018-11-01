---
title: IAxWinHostWindow-Schnittstelle
ms.date: 11/04/2016
f1_keywords:
- IAxWinHostWindow
- ATLIFACE/ATL::IAxWinHostWindow
- ATLIFACE/ATL::AttachControl
- ATLIFACE/ATL::CreateControl
- ATLIFACE/ATL::CreateControlEx
- ATLIFACE/ATL::QueryControl
- ATLIFACE/ATL::SetExternalDispatch
- ATLIFACE/ATL::SetExternalUIHandler
helpviewer_keywords:
- IAxWinHostWindow interface
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
ms.openlocfilehash: 1e389dc253f24eed2fee7e1d552be931a23f5e3f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637319"
---
# <a name="iaxwinhostwindow-interface"></a>IAxWinHostWindow-Schnittstelle

Diese Schnittstelle bietet Methoden zum Bearbeiten eines Steuerelements und dem zugehörigen Hostobjekt.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
interface IAxWinHostWindow : IUnknown
```

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|["AttachControl"](#attachcontrol)|Fügt ein vorhandenes Steuerelement an das Hostobjekt an.|
|[CreateControl](#createcontrol)|Erstellt ein Steuerelement, und hängt es an den Hostobjekt.|
|[CreateControlEx](#createcontrolex)|Erstellt ein Steuerelement, auf das Hostobjekt angefügt und optional ein Ereignishandler eingerichtet.|
|[QueryControl](#querycontrol)|Gibt einen Schnittstellenzeiger auf das gehostete Steuerelement zurück.|
|[SetExternalDispatch](#setexternaldispatch)|Legt den externen `IDispatch` Schnittstelle.|
|[SetExternalUIHandler](#setexternaluihandler)|Legt den externen `IDocHostUIHandlerDispatch` Schnittstelle.|

## <a name="remarks"></a>Hinweise

Diese Schnittstelle wird durch die ATL-ActiveX-Steuerelement hosten von Objekten verfügbar gemacht. Rufen Sie die Methoden für diese Schnittstelle zum Erstellen und/oder fügen Sie ein Steuerelement auf das Hostobjekt aus, um eine Schnittstelle aus einem gehosteten Steuerelement zu erhalten oder die externe Dispinterface oder UI-Handler für die Verwendung festgelegt werden, wenn die Web-Browser-hosting.

## <a name="requirements"></a>Anforderungen

Die Definition dieser Schnittstelle ist als IDL oder C++ verfügbar, wie unten dargestellt.

|Definitionstyp|Datei|
|---------------------|----------|
|IDL|ATLIFace.idl|
|C++|Konnte IRegistrar (ebenfalls in ATLBase.h enthalten)|

##  <a name="attachcontrol"></a>  IAxWinHostWindow:: AttachControl

Fügt einem vorhandenen (und zuvor initialisierten)-Steuerelement auf das Hostobjekt, das Verwenden des Fensters identifizierte *hWnd*.

```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```

### <a name="parameters"></a>Parameter

*pUnkControl*<br/>
[in] Ein Zeiger auf die `IUnknown` Schnittstelle des Steuerelements auf das Hostobjekt angefügt werden.

*hWnd*<br/>
[in] Ein Handle für das Fenster, für das Hosten von verwendet werden.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

##  <a name="createcontrol"></a>  IAxWinHostWindow::CreateControl

Erstellt ein Steuerelement, initialisiert es und hostet es im Fenster identifizierte *hWnd*.

```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```

### <a name="parameters"></a>Parameter

*lpTricsData*<br/>
[in] Eine Zeichenfolge, die das zu erstellende Steuerelement identifiziert. Kann eine CLSID (die geschweiften Klammern müssen einschließen), die ProgID, die URL oder die unformatiertes HTML sein (das Präfix **MSHTML:**).

*hWnd*<br/>
[in] Ein Handle für das Fenster, für das Hosten von verwendet werden.

*pStream*<br/>
[in] Ein Schnittstellenzeiger für einen Stream, der Daten für das Steuerelement enthält. NULL kann sein.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Dieses Fenster wird in Unterklassen unterteilt werden, indem das Hostobjekt, das diese Schnittstelle verfügbar macht, so, dass Nachrichten auf das Steuerelement gespiegelt werden können, und andere Container-Features funktionieren.

Das Aufrufen dieser Methode entspricht dem Aufruf [IAxWinHostWindow::CreateControlEx](#createcontrolex).

Ein lizenziertes ActiveX-Steuerelement erstellen zu können, finden Sie unter [IAxWinHostWindowLic::CreateControlLic](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).

##  <a name="createcontrolex"></a>  IAxWinHostWindow::CreateControlEx

Erstellt ein ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster ähnelt [IAxWinHostWindow::CreateControl](#createcontrol).

```
STDMETHOD(CreateControlEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise);
```

### <a name="parameters"></a>Parameter

*lpTricsData*<br/>
[in] Eine Zeichenfolge, die das zu erstellende Steuerelement identifiziert. Kann eine CLSID (die geschweiften Klammern müssen einschließen), die ProgID, die URL oder die unformatiertes HTML sein (mit dem Präfix **MSHTML:**).

*hWnd*<br/>
[in] Ein Handle für das Fenster, für das Hosten von verwendet werden.

*pStream*<br/>
[in] Ein Schnittstellenzeiger für einen Stream, der Daten für das Steuerelement enthält. NULL kann sein.

*ppUnk*<br/>
[out] Die Adresse eines Zeigers, der erhält die `IUnknown` Schnittstelle des erstellten Steuerelements. NULL kann sein.

*riidAdvise*<br/>
[in] Der Schnittstellenbezeichner einer ausgehenden Schnittstelle für das enthaltene Objekt. IID_NULL kann sein.

*punkAdvise*<br/>
[in] Ein Zeiger auf die `IUnknown` -Schnittstelle des Senkenobjekts mit dem Verbindungspunkt am anhand des enthaltenen Objekts verbunden sein, `iidSink`.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Im Gegensatz zu den `CreateControl` Methode `CreateControlEx` auch können Sie einen Schnittstellenzeiger auf das neu erstellte Steuerelement zu empfangen, und richten Sie eine Ereignissenke, zum Empfangen von Ereignissen, die vom Steuerelement ausgelöst.

Ein lizenziertes ActiveX-Steuerelement erstellen zu können, finden Sie unter [IAxWinHostWindowLic::CreateControlLicEx](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).

##  <a name="querycontrol"></a>  IAxWinHostWindow::QueryControl

Gibt den angegebenen Schnittstellenzeiger vom gehosteten Steuerelement bereitgestellt werden.

```
STDMETHOD(QueryControl)(
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>Parameter

*riid*<br/>
[in] Die ID einer Schnittstelle für das Steuerelement angefordert wird.

*ppvObject*<br/>
[out] Die Adresse eines Zeigers, die die angegebene Schnittstelle des erstellten Steuerelements empfängt.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

##  <a name="setexternaldispatch"></a>  IAxWinHostWindow::SetExternalDispatch

Die externe Disp-Schnittstelle, die enthaltenen Steuerelemente über verfügbar ist, legt die [IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) Methode.

```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```

### <a name="parameters"></a>Parameter

*pDisp*<br/>
[in] Ein Zeiger auf ein `IDispatch` Schnittstelle.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

##  <a name="setexternaluihandler"></a>  IAxWinHostWindow::SetExternalUIHandler

Mit dieser Funktion wird entsprechend den externen [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) eine Schnittstelle für die `CAxWindow` Objekt.

```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```

### <a name="parameters"></a>Parameter

*pDisp*<br/>
[in] Ein Zeiger auf ein `IDocHostUIHandlerDispatch` Schnittstelle.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Diese Funktion wird von Steuerelementen (z. B. das Webbrowser-Steuerelement), die der Hostwebsite für Abfragen verwendet die `IDocHostUIHandlerDispatch` Schnittstelle.

## <a name="see-also"></a>Siehe auch

[IAxWinAmbientDispatch-Schnittstelle](../../atl/reference/iaxwinambientdispatch-interface.md)<br/>
[CAxWindow:: QueryHost](../../atl/reference/caxwindow-class.md#queryhost)<br/>
[AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)

