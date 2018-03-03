---
title: IAxWinAmbientDispatch Schnittstelle | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAxWinAmbientDispatch
- ATLIFACE/ATL::IAxWinAmbientDispatch
- ATLIFACE/ATL::get_AllowContextMenu
- ATLIFACE/ATL::get_AllowShowUI
- ATLIFACE/ATL::get_AllowWindowlessActivation
- ATLIFACE/ATL::get_BackColor
- ATLIFACE/ATL::get_DisplayAsDefault
- ATLIFACE/ATL::get_DocHostDoubleClickFlags
- ATLIFACE/ATL::get_DocHostFlags
- ATLIFACE/ATL::get_Font
- ATLIFACE/ATL::get_ForeColor
- ATLIFACE/ATL::get_LocaleID
- ATLIFACE/ATL::get_MessageReflect
- ATLIFACE/ATL::get_OptionKeyPath
- ATLIFACE/ATL::get_ShowGrabHandles
- ATLIFACE/ATL::get_ShowHatching
- ATLIFACE/ATL::get_UserMode
- ATLIFACE/ATL::put_AllowContextMenu
- ATLIFACE/ATL::put_AllowShowUI
- ATLIFACE/ATL::put_AllowWindowlessActivation
- ATLIFACE/ATL::put_BackColor
- ATLIFACE/ATL::put_DisplayAsDefault
- ATLIFACE/ATL::put_DocHostDoubleClickFlags
- ATLIFACE/ATL::put_DocHostFlags
- ATLIFACE/ATL::put_Font
- ATLIFACE/ATL::put_ForeColor
- ATLIFACE/ATL::put_LocaleID
- ATLIFACE/ATL::put_MessageReflect
- ATLIFACE/ATL::put_OptionKeyPath
- ATLIFACE/ATL::put_UserMode
dev_langs:
- C++
helpviewer_keywords:
- IAxWinAmbientDispatch interface
ms.assetid: 55ba6f7b-7a3c-4792-ae47-c8a84b683ca9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e9d53dc257920e40dbf6a2f360d1289676d121fd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="iaxwinambientdispatch-interface"></a>IAxWinAmbientDispatch-Schnittstelle
Diese Schnittstelle bietet Methoden zur Angabe der Merkmale des gehosteten Steuerelements oder des Containers.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
interface IAxWinAmbientDispatch : IDispatch
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[get_AllowContextMenu](#get_allowcontextmenu)|Die **AllowContextMenu** Eigenschaft gibt an, ob das gehostete Steuerelement zugelassen wird, um sein eigenes Kontextmenü anzuzeigen.|  
|[get_AllowShowUI](#get_allowshowui)|Die **AllowShowUI** Eigenschaft gibt an, ob das gehostete Steuerelement zugelassen wird, um eine eigene Benutzeroberfläche anzuzeigen.|  
|[get_AllowWindowlessActivation](#get_allowwindowlessactivation)|Die **AllowWindowlessActivation** Eigenschaft gibt an, ob der Container fensterlosen Aktivierung zulässig sind.|  
|[get_BackColor](#get_backcolor)|Die `BackColor` Eigenschaft gibt die Ambiente-Hintergrundfarbe des Containers an.|  
|[get_DisplayAsDefault](#get_displayasdefault)|**DisplayAsDefault** ist eine ambient-Eigenschaft, die ermöglicht es einem Steuerelement, um herauszufinden, ob es sich um das Standardsteuerelement ist.|  
|[get_DocHostDoubleClickFlags](#get_dochostdoubleclickflags)|Die **DocHostDoubleClickFlags** Eigenschaft gibt den Vorgang, die als Antwort auf einen Doppelklick erfolgen soll.|  
|[get_DocHostFlags](#get_dochostflags)|Die **DocHostFlags** Eigenschaft gibt an, die Benutzeroptionen für die Schnittstelle des Hostobjekts.|  
|[get_Font](#get_font)|Die **Schriftart** Eigenschaft gibt an, die ambient-Schriftart des Containers.|  
|[get_ForeColor](#get_forecolor)|Die `ForeColor` Eigenschaft gibt die Ambiente-Farbe des Containers.|  
|[get_LocaleID](#get_localeid)|Die **LocaleID** Eigenschaft gibt an, die ambient-Gebietsschema-ID des Containers.|  
|[get_MessageReflect](#get_messagereflect)|Die **MessageReflect** ambient-Eigenschaft gibt an, ob der Container, die Nachrichten an das gehostete Steuerelement widerspiegeln.|  
|[get_OptionKeyPath](#get_optionkeypath)|Die **OptionKeyPath** Eigenschaft gibt den Registrierungsschlüsselpfad an benutzereinstellungen an.|  
|[get_ShowGrabHandles](#get_showgrabhandles)|Die **ShowGrabHandles** ambient-Eigenschaft ermöglicht die Steuerung zu ermitteln, ob es sich selbst mit Ziehpunkten gezeichnet werden soll.|  
|[get_ShowHatching](#get_showhatching)|Die **ShowHatching** ambient-Eigenschaft ermöglicht die Steuerung zu ermitteln, ob sich die eingestellt gezeichnet werden soll.|  
|[get_UserMode](#get_usermode)|Die **UserMode** Eigenschaft gibt an, die ambient-Benutzermodus des Containers.|  
|[put_AllowContextMenu](#put_allowcontextmenu)|Die **AllowContextMenu** Eigenschaft gibt an, ob das gehostete Steuerelement zugelassen wird, um sein eigenes Kontextmenü anzuzeigen.|  
|[put_AllowShowUI](#put_allowshowui)|Die **AllowShowUI** Eigenschaft gibt an, ob das gehostete Steuerelement zugelassen wird, um eine eigene Benutzeroberfläche anzuzeigen.|  
|[put_AllowWindowlessActivation](#put_allowwindowlessactivation)|Die **AllowWindowlessActivation** Eigenschaft gibt an, ob der Container fensterlosen Aktivierung zulässig sind.|  
|[put_BackColor](#put_backcolor)|Die `BackColor` Eigenschaft gibt die Ambiente-Hintergrundfarbe des Containers an.|  
|[put_DisplayAsDefault](#put_displayasdefault)|**DisplayAsDefault** ist eine ambient-Eigenschaft, die ermöglicht es einem Steuerelement, um herauszufinden, ob es sich um das Standardsteuerelement ist.|  
|[put_DocHostDoubleClickFlags](#put_dochostdoubleclickflags)|Die **DocHostDoubleClickFlags** Eigenschaft gibt den Vorgang, die als Antwort auf einen Doppelklick erfolgen soll.|  
|[put_DocHostFlags](#put_dochostflags)|Die **DocHostFlags** Eigenschaft gibt an, die Benutzeroptionen für die Schnittstelle des Hostobjekts.|  
|[put_Font](#put_font)|Die **Schriftart** Eigenschaft gibt an, die ambient-Schriftart des Containers.|  
|[put_ForeColor](#put_forecolor)|Die `ForeColor` Eigenschaft gibt die Ambiente-Farbe des Containers.|  
|[put_LocaleID](#put_localeid)|Die **LocaleID** Eigenschaft gibt an, die ambient-Gebietsschema-ID des Containers.|  
|[put_MessageReflect](#put_messagereflect)|Die **MessageReflect** ambient-Eigenschaft gibt an, ob der Container, die Nachrichten an das gehostete Steuerelement widerspiegeln.|  
|[put_OptionKeyPath](#put_optionkeypath)|Die **OptionKeyPath** Eigenschaft gibt den Registrierungsschlüsselpfad an benutzereinstellungen an.|  
|[put_UserMode](#put_usermode)|Die **UserMode** Eigenschaft gibt an, die ambient-Benutzermodus des Containers.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle wird von ATL ActiveX-Steuerelement hosten von Objekten verfügbar gemacht. Rufen Sie die Methoden für diese Schnittstelle, um die verfügbaren Umgebungseigenschaften auf das gehostete Steuerelement festgelegt oder andere Aspekte des Verhaltens des Containers anzugeben. Ergänzen Sie die Eigenschaften von bereitgestellten `IAxWinAmbientDispatch`, verwenden Sie [IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md).  
  
 [AXHost](https://msdn.microsoft.com/library/system.windows.forms.axhost.aspx) Typinformationen zu laden versucht `IAxWinAmbientDispatch` und `IAxWinAmbientDispatchEx` aus der Typbibliothek, die den Code enthält.  
  
 Wenn Sie ATL90.dll, verknüpfen möchten **AXHost** lädt die Typinformationen aus der Typbibliothek in der DLL.  
  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) Weitere Details.  
  
## <a name="requirements"></a>Anforderungen  
 Die Definition der diese Schnittstelle ist in verschiedene Formate, verfügbar, wie in der folgenden Tabelle gezeigt.  
  
|Der Definitionstyp|Datei|  
|---------------------|----------|  
|IDL|atliface.idl|  
|Typbibliothek|ATL.dll|  
|C++|konnte IRegistrar (auch in ATLBase.h enthalten)|  
  
##  <a name="get_allowcontextmenu"></a>IAxWinAmbientDispatch::get_AllowContextMenu  
 Die **AllowContextMenu** Eigenschaft gibt an, ob das gehostete Steuerelement zugelassen wird, um sein eigenes Kontextmenü anzuzeigen.  
  
```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```  
  
### <a name="parameters"></a>Parameter  
 *pbAllowContextMenu*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-hostimplementierung von Objekt verwendet `VARIANT_TRUE` als der Standardwert dieser Eigenschaft.  
  
##  <a name="get_allowshowui"></a>IAxWinAmbientDispatch::get_AllowShowUI  
 Die **AllowShowUI** Eigenschaft gibt an, ob das gehostete Steuerelement zugelassen wird, um eine eigene Benutzeroberfläche anzuzeigen.  
  
```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```  
  
### <a name="parameters"></a>Parameter  
 *pbAllowShowUI*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Verwendet die ATL-hostimplementierung Objekt **VARIANT_FALSE** als der Standardwert dieser Eigenschaft.  
  
##  <a name="get_allowwindowlessactivation"></a>IAxWinAmbientDispatch::get_AllowWindowlessActivation  
 Die **AllowWindowlessActivation** Eigenschaft gibt an, ob der Container fensterlosen Aktivierung zulässig sind.  
  
```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```  
  
### <a name="parameters"></a>Parameter  
 *pbAllowWindowless*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-hostimplementierung von Objekt verwendet `VARIANT_TRUE` als der Standardwert dieser Eigenschaft.  
  
##  <a name="get_backcolor"></a>IAxWinAmbientDispatch::get_BackColor  
 Die `BackColor` Eigenschaft gibt die Ambiente-Hintergrundfarbe des Containers an.  
  
```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```  
  
### <a name="parameters"></a>Parameter  
 *pclrBackground*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Verwendet die ATL-hostimplementierung Objekt **COLOR_BTNFACE** oder **COLOR_WINDOW** als der Standardwert dieser Eigenschaft (je nachdem, ob das übergeordnete Element des Hostfenster ein Dialogfeld oder nicht).  
  
##  <a name="get_displayasdefault"></a>IAxWinAmbientDispatch::get_DisplayAsDefault  
 **DisplayAsDefault** ist eine ambient-Eigenschaft, die ermöglicht es einem Steuerelement, um herauszufinden, ob es sich um das Standardsteuerelement ist.  
  
```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```  
  
### <a name="parameters"></a>Parameter  
 *pbDisplayAsDefault*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Verwendet die ATL-hostimplementierung Objekt **VARIANT_FALSE** als der Standardwert dieser Eigenschaft.  
  
##  <a name="get_dochostdoubleclickflags"></a>IAxWinAmbientDispatch::get_DocHostDoubleClickFlags  
 Die **DocHostDoubleClickFlags** Eigenschaft gibt den Vorgang, die als Antwort auf einen Doppelklick erfolgen soll.  
  
```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```  
  
### <a name="parameters"></a>Parameter  
 *pdwDocHostDoubleClickFlags*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Verwendet die ATL-hostimplementierung Objekt **DOCHOSTUIDBLCLK_DEFAULT** als der Standardwert dieser Eigenschaft.  
  
##  <a name="get_dochostflags"></a>IAxWinAmbientDispatch::get_DocHostFlags  
 Die **DocHostFlags** Eigenschaft gibt an, die Benutzeroptionen für die Schnittstelle des Hostobjekts.  
  
```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```  
  
### <a name="parameters"></a>Parameter  
 *pdwDocHostFlags*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Verwendet die ATL-hostimplementierung Objekt **DOCHOSTUIFLAG_NO3DBORDER** als der Standardwert dieser Eigenschaft.  
  
##  <a name="get_font"></a>IAxWinAmbientDispatch::get_Font  
 Die **Schriftart** Eigenschaft gibt an, die ambient-Schriftart des Containers.  
  
```
STDMETHOD(get_Font)(IFontDisp** pFont);
```  
  
### <a name="parameters"></a>Parameter  
 `pFont`  
 [out] Die Adresse des ein **IFontDisp** Schnittstellenzeiger, der zum Empfangen des aktuellen Werts dieser Eigenschaft verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-hostimplementierung von Objekt verwendet die Standard-GUI-Schriftart oder Systemschriftart als der Standardwert dieser Eigenschaft.  
  
##  <a name="get_forecolor"></a>IAxWinAmbientDispatch::get_ForeColor  
 Die `ForeColor` Eigenschaft gibt die Ambiente-Farbe des Containers.  
  
```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```  
  
### <a name="parameters"></a>Parameter  
 *pclrForeground*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-hostimplementierung von Objekt verwendet die Systemfarbe für Fenster Text als der Standardwert dieser Eigenschaft.  
  
##  <a name="get_localeid"></a>IAxWinAmbientDispatch::get_LocaleID  
 Die **LocaleID** Eigenschaft gibt an, die ambient-Gebietsschema-ID des Containers.  
  
```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```  
  
### <a name="parameters"></a>Parameter  
 *plcidLocaleID*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-hostimplementierung von Objekt verwendet Standard-Gebietsschema des Benutzers als der Standardwert dieser Eigenschaft.  
  
 Mit dieser Methode können Sie ermitteln, die Ambient-LocalID, d. h. der LocaleID-Wert des Programms das Steuerelement wird in verwendet. Sobald Sie die Gebietsschema-ID kennen, können Sie Code zum Laden von gebietsschemaspezifische Beschriftungen Fehlermeldungstext, usw. aus einer Ressourcendatei oder Satelliten-DLL aufrufen.  
  
##  <a name="get_messagereflect"></a>IAxWinAmbientDispatch::get_MessageReflect  
 Die **MessageReflect** ambient-Eigenschaft gibt an, ob der Container, die Nachrichten an das gehostete Steuerelement widerspiegeln.  
  
```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```  
  
### <a name="parameters"></a>Parameter  
 *pbMessageReflect*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-hostimplementierung von Objekt verwendet `VARIANT_TRUE` als der Standardwert dieser Eigenschaft.  
  
##  <a name="get_optionkeypath"></a>IAxWinAmbientDispatch::get_OptionKeyPath  
 Die **OptionKeyPath** Eigenschaft gibt den Registrierungsschlüsselpfad an benutzereinstellungen an.  
  
```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```  
  
### <a name="parameters"></a>Parameter  
 *pbstrOptionKeyPath*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="get_showgrabhandles"></a>IAxWinAmbientDispatch::get_ShowGrabHandles  
 Die **ShowGrabHandles** ambient-Eigenschaft ermöglicht die Steuerung zu ermitteln, ob es sich selbst mit Ziehpunkten gezeichnet werden soll.  
  
```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```  
  
### <a name="parameters"></a>Parameter  
 *pbShowGrabHandles*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die ATL-Objekt-hostimplementierung immer **VARIANT_FALSE** als der Wert dieser Eigenschaft.  
  
##  <a name="get_showhatching"></a>IAxWinAmbientDispatch::get_ShowHatching  
 Die **ShowHatching** ambient-Eigenschaft ermöglicht die Steuerung zu ermitteln, ob sich die eingestellt gezeichnet werden soll.  
  
```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```  
  
### <a name="parameters"></a>Parameter  
 *pbShowHatching*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die ATL-Objekt-hostimplementierung immer **VARIANT_FALSE** als der Wert dieser Eigenschaft.  
  
##  <a name="get_usermode"></a>IAxWinAmbientDispatch::get_UserMode  
 Die **UserMode** Eigenschaft gibt an, die ambient-Benutzermodus des Containers.  
  
```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```  
  
### <a name="parameters"></a>Parameter  
 *pbUserMode*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-hostimplementierung von Objekt verwendet `VARIANT_TRUE` als der Standardwert dieser Eigenschaft.  
  
##  <a name="put_allowcontextmenu"></a>IAxWinAmbientDispatch::put_AllowContextMenu  
 Die **AllowContextMenu** Eigenschaft gibt an, ob das gehostete Steuerelement zugelassen wird, um sein eigenes Kontextmenü anzuzeigen.  
  
```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```  
  
### <a name="parameters"></a>Parameter  
 *bAllowContextMenu*  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-hostimplementierung von Objekt verwendet `VARIANT_TRUE` als der Standardwert dieser Eigenschaft.  
  
##  <a name="put_allowshowui"></a>IAxWinAmbientDispatch::put_AllowShowUI  
 Die **AllowShowUI** Eigenschaft gibt an, ob das gehostete Steuerelement zugelassen wird, um eine eigene Benutzeroberfläche anzuzeigen.  
  
```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```  
  
### <a name="parameters"></a>Parameter  
 *bAllowShowUI*  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Verwendet die ATL-hostimplementierung Objekt **VARIANT_FALSE** als der Standardwert dieser Eigenschaft.  
  
##  <a name="put_allowwindowlessactivation"></a>IAxWinAmbientDispatch::put_AllowWindowlessActivation  
 Die **AllowWindowlessActivation** Eigenschaft gibt an, ob der Container fensterlosen Aktivierung zulässig sind.  
  
```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```  
  
### <a name="parameters"></a>Parameter  
 *bAllowWindowless*  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-hostimplementierung von Objekt verwendet `VARIANT_TRUE` als der Standardwert dieser Eigenschaft.  
  
##  <a name="put_backcolor"></a>IAxWinAmbientDispatch::put_BackColor  
 Die `BackColor` Eigenschaft gibt die Ambiente-Hintergrundfarbe des Containers an.  
  
```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```  
  
### <a name="parameters"></a>Parameter  
 *clrBackground*  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Verwendet die ATL-hostimplementierung Objekt **COLOR_BTNFACE** oder **COLOR_WINDOW** als der Standardwert dieser Eigenschaft (je nachdem, ob das übergeordnete Element des Hostfenster ein Dialogfeld oder nicht).  
  
##  <a name="put_displayasdefault"></a>IAxWinAmbientDispatch::put_DisplayAsDefault  
 **DisplayAsDefault** ist eine ambient-Eigenschaft, die ermöglicht es einem Steuerelement, um herauszufinden, ob es sich um das Standardsteuerelement ist.  
  
```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```  
  
### <a name="parameters"></a>Parameter  
 `bDisplayAsDefault`  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Verwendet die ATL-hostimplementierung Objekt **VARIANT_FALSE** als der Standardwert dieser Eigenschaft.  
  
##  <a name="put_dochostdoubleclickflags"></a>IAxWinAmbientDispatch::put_DocHostDoubleClickFlags  
 Die **DocHostDoubleClickFlags** Eigenschaft gibt den Vorgang, die als Antwort auf einen Doppelklick erfolgen soll.  
  
```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```  
  
### <a name="parameters"></a>Parameter  
 *dwDocHostDoubleClickFlags*  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Verwendet die ATL-hostimplementierung Objekt **DOCHOSTUIDBLCLK_DEFAULT** als der Standardwert dieser Eigenschaft.  
  
##  <a name="put_dochostflags"></a>IAxWinAmbientDispatch::put_DocHostFlags  
 Die **DocHostFlags** Eigenschaft gibt an, die Benutzeroptionen für die Schnittstelle des Hostobjekts.  
  
```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```  
  
### <a name="parameters"></a>Parameter  
 *dwDocHostFlags*  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Verwendet die ATL-hostimplementierung Objekt **DOCHOSTUIFLAG_NO3DBORDER** als der Standardwert dieser Eigenschaft.  
  
##  <a name="put_font"></a>IAxWinAmbientDispatch::put_Font  
 Die **Schriftart** Eigenschaft gibt an, die ambient-Schriftart des Containers.  
  
```
STDMETHOD(put_Font)(IFontDisp* pFont);
```  
  
### <a name="parameters"></a>Parameter  
 `pFont`  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-hostimplementierung von Objekt verwendet die Standard-GUI-Schriftart oder Systemschriftart als der Standardwert dieser Eigenschaft.  
  
##  <a name="put_forecolor"></a>IAxWinAmbientDispatch::put_ForeColor  
 Die `ForeColor` Eigenschaft gibt die Ambiente-Farbe des Containers.  
  
```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```  
  
### <a name="parameters"></a>Parameter  
 *clrForeground*  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-hostimplementierung von Objekt verwendet die Systemfarbe für Fenster Text als der Standardwert dieser Eigenschaft.  
  
##  <a name="put_localeid"></a>IAxWinAmbientDispatch::put_LocaleID  
 Die **LocaleID** Eigenschaft gibt an, die ambient-Gebietsschema-ID des Containers.  
  
```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```  
  
### <a name="parameters"></a>Parameter  
 *lcidLocaleID*  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-hostimplementierung von Objekt verwendet Standard-Gebietsschema des Benutzers als der Standardwert dieser Eigenschaft.  
  
##  <a name="put_messagereflect"></a>IAxWinAmbientDispatch::put_MessageReflect  
 Die **MessageReflect** ambient-Eigenschaft gibt an, ob der Container, die Nachrichten an das gehostete Steuerelement widerspiegeln.  
  
```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```  
  
### <a name="parameters"></a>Parameter  
 `bMessageReflect`  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-hostimplementierung von Objekt verwendet `VARIANT_TRUE` als der Standardwert dieser Eigenschaft.  
  
##  <a name="put_optionkeypath"></a>IAxWinAmbientDispatch::put_OptionKeyPath  
 Die **OptionKeyPath** Eigenschaft gibt den Registrierungsschlüsselpfad an benutzereinstellungen an.  
  
```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```  
  
### <a name="parameters"></a>Parameter  
 *bstrOptionKeyPath*  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="put_usermode"></a>IAxWinAmbientDispatch::put_UserMode  
 Die **UserMode** Eigenschaft gibt an, die ambient-Benutzermodus des Containers.  
  
```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```  
  
### <a name="parameters"></a>Parameter  
 `bUserMode`  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-hostimplementierung von Objekt verwendet `VARIANT_TRUE` als der Standardwert dieser Eigenschaft.  
  
## <a name="see-also"></a>Siehe auch  
 [IAxWinAmbientDispatchEx-Schnittstelle](../../atl/reference/iaxwinambientdispatchex-interface.md)   
 [IAxWinHostWindow-Schnittstelle](../../atl/reference/iaxwinhostwindow-interface.md)   
 [CAxWindow:: QueryHost](../../atl/reference/caxwindow-class.md#queryhost)   
 [AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)









