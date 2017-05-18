---
title: IAxWinHostWindow Schnittstelle | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: ecf88a3a6b115088dd605fff2b633bff86fb086a
ms.contentlocale: de-de
ms.lasthandoff: 03/31/2017

---
# <a name="iaxwinhostwindow-interface"></a>IAxWinHostWindow-Schnittstelle
Diese Schnittstelle bietet Methoden zum Bearbeiten von einem Steuerelement und seine Hostobjekt.  
  
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
|[AttachControl](#attachcontrol)|Fügt ein vorhandenes Steuerelement an das Hostobjekt, das an.|  
|[CreateControl](#createcontrol)|Erstellt ein Steuerelement, und fügt ihn das Hostobjekt.|  
|[CreateControlEx](#createcontrolex)|Erstellt ein Steuerelement, das Hostobjekt fügt ihn und optional einen Ereignishandler eingerichtet.|  
|[QueryControl](#querycontrol)|Gibt einen Schnittstellenzeiger auf das gehostete Steuerelement zurück.|  
|[SetExternalDispatch](#setexternaldispatch)|Legt den externen `IDispatch` Schnittstelle.|  
|[SetExternalUIHandler](#setexternaluihandler)|Legt den externen `IDocHostUIHandlerDispatch` Schnittstelle.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle wird von ATL ActiveX-Steuerelement hosten von Objekten verfügbar gemacht. Rufen Sie die Methoden für diese Schnittstelle zum Erstellen und/oder fügen Sie ein Steuerelement an das Hostobjekt, können Sie eine Schnittstelle von einem gehosteten Steuerelement abzurufen und zum Festlegen von externen Dispinterface oder UI-Handler für die Verwendung beim Hosten des Webbrowsers.  
  
## <a name="requirements"></a>Anforderungen  
 Die Definition dieser Schnittstelle ist als IDL oder C++ zur Verfügung, wie unten dargestellt.  
  
|Der Definitionstyp|Datei|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|Konnte IRegistrar (auch in ATLBase.h enthalten)|  
  
##  <a name="attachcontrol"></a>IAxWinHostWindow:: AttachControl  
 Fügt eine vorhandene (und zuvor initialisierten)-Steuerelement an das Hostobjekt, das im Fenster "" identifizierte `hWnd`.  
  
```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```  
  
### <a name="parameters"></a>Parameter  
 *pUnkControl*  
 [in] Ein Zeiger auf die **IUnknown** Schnittstelle des Steuerelements das Hostobjekt zugeordnet werden soll.  
  
 `hWnd`  
 [in] Ein Handle für das Fenster für das hosting verwendet werden soll.  
  
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
 [in] Eine Zeichenfolge, die das zu erstellende Steuerelement identifiziert wird. Kann eine (müssen auch die geschweiften Klammern) CLSID, ProgID, URL oder unformatierten HTML (mit dem Präfix **MSHTML:**).  
  
 `hWnd`  
 [in] Ein Handle für das Fenster für das hosting verwendet werden soll.  
  
 `pStream`  
 [in] Ein Schnittstellenzeiger für einen Datenstrom, die Initialisierungsdaten für das Steuerelement enthält. Kann **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Fenster wird als Unterklasse werden, indem Sie das Hostobjekt, das diese Schnittstelle verfügbar macht, sodass Nachrichten an das Steuerelement gespiegelt werden können, und andere Container-Funktionen verwendet werden können.  
  
 Beim Aufrufen dieser Methode entspricht dem Aufruf [IAxWinHostWindow::CreateControlEx](#createcontrolex).  
  
 Um ein lizenziertes ActiveX-Steuerelement zu erstellen, finden Sie unter [IAxWinHostWindowLic::CreateControlLic](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).  
  
##  <a name="createcontrolex"></a>IAxWinHostWindow::CreateControlEx  
 Erstellt ein ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster, ähnlich wie [IAxWinHostWindow::CreateControl](#createcontrol).  
  
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
 [in] Eine Zeichenfolge, die das zu erstellende Steuerelement identifiziert wird. Kann eine (müssen auch die geschweiften Klammern) CLSID, ProgID, URL oder unformatierten HTML (mit dem Präfix **MSHTML:**).  
  
 `hWnd`  
 [in] Ein Handle für das Fenster für das hosting verwendet werden soll.  
  
 `pStream`  
 [in] Ein Schnittstellenzeiger für einen Datenstrom, die Initialisierungsdaten für das Steuerelement enthält. Kann **NULL**.  
  
 `ppUnk`  
 [out] Die Adresse eines Zeigers, die erhalten die **IUnknown** Schnittstelle des erstellten Steuerelements. Kann **NULL**.  
  
 *riidAdvise*  
 [in] Der Schnittstellenbezeichner einer ausgehenden Schnittstelle auf die darin enthaltenen Objekte. Kann **IID_NULL**.  
  
 *punkAdvise*  
 [in] Ein Zeiger auf die **IUnknown** -Schnittstelle des Senkenobjekts Verbindung mit dem Verbindungspunkt am der darin enthaltenen Objekte angegeben werden `iidSink`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Im Gegensatz zu den `CreateControl` Methode `CreateControlEx` können außerdem erhalten einen Schnittstellenzeiger auf das neu erstellte Steuerelement, und richten Sie eine Ereignissenke zum Empfangen von Ereignissen, die vom Steuerelement ausgelöst.  
  
 Um ein lizenziertes ActiveX-Steuerelement zu erstellen, finden Sie unter [IAxWinHostWindowLic::CreateControlLicEx](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex).  
  
##  <a name="querycontrol"></a>IAxWinHostWindow::QueryControl  
 Gibt den angegebenen Schnittstellenzeiger vom gehosteten Steuerelement bereitgestellte zurück.  
  
```
STDMETHOD(QueryControl)(
    REFIID riid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Parameter  
 `riid`  
 [in] Die ID einer Schnittstelle für das Steuerelement, das angefordert wird.  
  
 `ppvObject`  
 [out] Die Adresse eines Zeigers, die die angegebene Schnittstelle des erstellten Steuerelements empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="setexternaldispatch"></a>IAxWinHostWindow::SetExternalDispatch  
 Legt die externen Disp-Schnittstelle, die darin enthaltenen Steuerelemente bis hin zur Verfügung steht die [IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) Methode.  
  
```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>Parameter  
 `pDisp`  
 [in] Ein Zeiger auf eine `IDispatch` Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="setexternaluihandler"></a>IAxWinHostWindow::SetExternalUIHandler  
 Mit dieser Funktion wird zum Festlegen von externen [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) eine Schnittstelle für die `CAxWindow` Objekt.  
  
```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```  
  
### <a name="parameters"></a>Parameter  
 `pDisp`  
 [in] Ein Zeiger auf ein **IDocHostUIHandlerDispatch** Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird von allen Steuerelementen (z. B. das Webbrowser-Steuerelement), die dem Host der Website für Abfragen verwendet die `IDocHostUIHandlerDispatch` Schnittstelle.  
  
## <a name="see-also"></a>Siehe auch  
 [IAxWinAmbientDispatch-Schnittstelle](../../atl/reference/iaxwinambientdispatch-interface.md)   
 [CAxWindow:: QueryHost](../../atl/reference/caxwindow-class.md#queryhost)   
 [AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)










