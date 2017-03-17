---
title: IAxWinHostWindow Schnittstelle | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAxWinHostWindow
- No header/ATL::IAxWinHostWindow
- No header/ATL::AttachControl
- No header/ATL::CreateControl
- No header/ATL::CreateControlEx
- No header/ATL::QueryControl
- No header/ATL::SetExternalDispatch
- No header/ATL::SetExternalUIHandler
dev_langs:
- C++
helpviewer_keywords:
- IAxWinHostWindow interface
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
caps.latest.revision: 21
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
ms.openlocfilehash: 6e366e7e30e7b4080462fbc21c29b4ecdf0214ae
ms.lasthandoff: 02/24/2017

---
# <a name="iaxwinhostwindow-interface"></a>IAxWinHostWindow-Schnittstelle
Diese Schnittstelle stellt Methoden zum Bearbeiten eines Steuerelements und seiner Host-Objekt.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
interface IAxWinHostWindow : IUnknown
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[AttachControl](#attachcontrol)|Fügt ein vorhandenes Steuerelement an das Hostobjekt an.|  
|[CreateControl](#createcontrol)|Erstellt ein Steuerelement, und fügt es dem Host-Objekt.|  
|[CreateControlEx](#createcontrolex)|Erstellt ein Steuerelement, fügt es auf das Hostobjekt und optional einen Ereignishandler eingerichtet.|  
|[QueryControl](#querycontrol)|Gibt einen Schnittstellenzeiger auf das gehostete Steuerelement zurück.|  
|[SetExternalDispatch](#setexternaldispatch)|Legt die externen `IDispatch` Schnittstelle.|  
|[SetExternalUIHandler](#setexternaluihandler)|Legt die externen `IDocHostUIHandlerDispatch` Schnittstelle.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle wird von ATL ActiveX-Steuerelement hosten von Objekten verfügbar gemacht. Rufen Sie die Methoden dieser Schnittstelle zum Erstellen bzw. Fügen Sie ein Steuerelement an die Hostobjekt, um eine Schnittstelle von einem gehosteten Steuerelement abzurufen oder zum Festlegen von externen Dispinterface oder UI-Handler für die Verwendung beim Hosten von einem Webbrowser aus.  
  
## <a name="requirements"></a>Anforderungen  
 Die Definition dieser Schnittstelle ist als IDL oder C++ verfügbar, wie unten dargestellt.  
  
|Definitionstyp|Datei|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|Konnte IRegistrar (auch in ATLBase.h enthalten)|  
  
##  <a name="attachcontrol"></a>IAxWinHostWindow:: AttachControl  
 Fügt eine vorhandene (und zuvor initialisierten)-Steuerelement an das Hostobjekt, das mit dem Fenster identifizierten `hWnd`.  
  
```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```  
  
### <a name="parameters"></a>Parameter  
 *pUnkControl*  
 [in] Ein Zeiger auf die **IUnknown** Schnittstelle des Hostobjekts zugeordnet werden soll.  
  
 `hWnd`  
 [in] Ein Handle für das Fenster, für das Hosten von verwendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="createcontrol"></a>IAxWinHostWindow::CreateControl  
 Erstellt ein Steuerelement, initialisiert es und hostet es im Fenster identifizierten `hWnd`.  
  
```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```  
  
### <a name="parameters"></a>Parameter  
 `lpTricsData`  
 [in] Eine Zeichenfolge, die das zu erstellende Steuerelement identifiziert. Kann (müssen, einschließlich der geschweiften Klammern) CLSID, ProgID, URL oder unformatierten HTML (mit dem Präfix **MSHTML:**).  
  
 `hWnd`  
 [in] Ein Handle für das Fenster, für das Hosten von verwendet werden.  
  
 `pStream`  
 [in] Ein Schnittstellenzeiger für einen Stream, der Daten für das Steuerelement enthält. Kann **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Fenster wird durch das Hostobjekt, das diese Schnittstelle verfügbar macht, damit Nachrichten an das Steuerelement wiedergegeben werden können und andere Container Features funktionieren als Unterklasse definiert werden.  
  
 Das Aufrufen dieser Methode entspricht dem Aufruf [IAxWinHostWindow::CreateControlEx](#createcontrolex).  
  
 Um ein lizenziertes ActiveX-Steuerelement zu erstellen, finden Sie unter [IAxWinHostWindowLic::CreateControlLic](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).  
  
##  <a name="createcontrolex"></a>IAxWinHostWindow::CreateControlEx  
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
 `lpTricsData`  
 [in] Eine Zeichenfolge, die das zu erstellende Steuerelement identifiziert. Kann (müssen, einschließlich der geschweiften Klammern) CLSID, ProgID, URL oder unformatierten HTML (mit dem Präfix **MSHTML:**).  
  
 `hWnd`  
 [in] Ein Handle für das Fenster, für das Hosten von verwendet werden.  
  
 `pStream`  
 [in] Ein Schnittstellenzeiger für einen Stream, der Daten für das Steuerelement enthält. Kann **NULL**.  
  
 `ppUnk`  
 [out] Die Adresse eines Zeigers, die erhalten die **IUnknown** Schnittstelle erstellt. Kann **NULL**.  
  
 *riidAdvise*  
 [in] Der Schnittstellenbezeichner des Ausgangsschnittstelle enthaltenen Objekts. Kann **IID_NULL**.  
  
 *punkAdvise*  
 [in] Ein Zeiger auf die **IUnknown** Schnittstelle des Senkenobjekts zum Verbindungspunkt anhand des enthaltenen Objekts verbunden sein `iidSink`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Im Gegensatz zu den `CreateControl` -Methode `CreateControlEx` darüber hinaus können Sie erhalten einen Schnittstellenzeiger auf das neu erstellte Steuerelement und eine Ereignissenke zum Empfangen von Ereignissen, die vom Steuerelement ausgelöst.  
  
 Um ein lizenziertes ActiveX-Steuerelement zu erstellen, finden Sie unter [IAxWinHostWindowLic::CreateControlLicEx](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).  
  
##  <a name="querycontrol"></a>IAxWinHostWindow::QueryControl  
 Gibt den angegebenen Schnittstellenzeiger vom gehosteten Steuerelement bereitgestellt werden.  
  
```
STDMETHOD(QueryControl)(
    REFIID riid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Parameter  
 `riid`  
 [in] Die ID einer Schnittstelle für das Steuerelement angefordert wird.  
  
 `ppvObject`  
 [out] Die Adresse eines Zeigers, der die angegebene Schnittstelle für das erstellte Steuerelement erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="setexternaldispatch"></a>IAxWinHostWindow::SetExternalDispatch  
 Legt die externen Disp-Schnittstelle, die enthaltenen Steuerelemente über zur Verfügung steht die [IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) Methode.  
  
```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>Parameter  
 `pDisp`  
 [in] Ein Zeiger auf eine `IDispatch` Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="setexternaluihandler"></a>IAxWinHostWindow::SetExternalUIHandler  
 Rufen Sie diese Funktion zum Festlegen der externen [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) Schnittstelle für die `CAxWindow` Objekt.  
  
```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```  
  
### <a name="parameters"></a>Parameter  
 `pDisp`  
 [in] Ein Zeiger auf eine **IDocHostUIHandlerDispatch** Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird von Steuerelementen (z. B. das Webbrowser-Steuerelement), die die Hostwebsite für Abfragen verwendet die `IDocHostUIHandlerDispatch` Schnittstelle.  
  
## <a name="see-also"></a>Siehe auch  
 [IAxWinAmbientDispatch-Schnittstelle](../../atl/reference/iaxwinambientdispatch-interface.md)   
 [CAxWindow:: QueryHost](../../atl/reference/caxwindow-class.md#queryhost)   
 [AtlAxGetHost](http://msdn.microsoft.com/library/ad1f4f16-608d-4e96-8d30-04d4ca906a7b)










