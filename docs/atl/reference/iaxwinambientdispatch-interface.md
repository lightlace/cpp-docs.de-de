---
title: IAxWinAmbientDispatch-Schnittstelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2cf8747275325332f6a2d0072e2c0ba2a66ae276
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057612"
---
# <a name="iaxwinambientdispatch-interface"></a>IAxWinAmbientDispatch-Schnittstelle

Diese Schnittstelle stellt Methoden zur Angabe der Merkmale des gehosteten Steuerelements oder des Containers.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
interface IAxWinAmbientDispatch : IDispatch
```

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[get_AllowContextMenu](#get_allowcontextmenu)|Die `AllowContextMenu` Eigenschaft gibt an, ob das gehostete Steuerelement zulässig ist, um sein eigenes Kontextmenü anzuzeigen.|
|[get_AllowShowUI](#get_allowshowui)|Die `AllowShowUI` Eigenschaft gibt an, ob das gehostete Steuerelement zulässig ist, um eine eigene Benutzeroberfläche anzuzeigen.|
|[get_AllowWindowlessActivation](#get_allowwindowlessactivation)|Die `AllowWindowlessActivation` Eigenschaft gibt an, ob der Container fensterlosen Aktivierung zulässig sind.|
|[get_BackColor](#get_backcolor)|Die `BackColor` Eigenschaft gibt an, die ambient-Hintergrundfarbe des Containers.|
|[get_DisplayAsDefault](#get_displayasdefault)|`DisplayAsDefault` ist eine Ambiente-Eigenschaft, die ermöglicht es einem Steuerelement, um herauszufinden, ob es sich um das Standardsteuerelement ist.|
|[get_DocHostDoubleClickFlags](#get_dochostdoubleclickflags)|Die `DocHostDoubleClickFlags` Eigenschaft gibt an, den Vorgang, der als Reaktion auf einen Doppelklick stattfinden sollen.|
|[get_DocHostFlags](#get_dochostflags)|Die `DocHostFlags` Eigenschaft gibt an, die Benutzeroptionen für die Schnittstelle des Hostobjekts.|
|[get_Font](#get_font)|Die `Font` Eigenschaft gibt an, die ambient-Schriftart des Containers.|
|[get_ForeColor](#get_forecolor)|Die `ForeColor` Eigenschaft gibt an, die ambient-Vordergrundfarbe des Containers.|
|[get_LocaleID](#get_localeid)|Die `LocaleID` Eigenschaft gibt an, die ambient-Gebietsschema-ID des Containers.|
|[get_MessageReflect](#get_messagereflect)|Die `MessageReflect` ambient-Eigenschaft gibt an, ob der Container die Nachrichten an das gehostete Steuerelement angegeben wird.|
|[get_OptionKeyPath](#get_optionkeypath)|Die `OptionKeyPath` Eigenschaft gibt an, den Registrierungsschlüsselpfad an den benutzereinstellungen.|
|[get_ShowGrabHandles](#get_showgrabhandles)|Die `ShowGrabHandles` ambient-Eigenschaft ermöglicht das Steuerelement, um herauszufinden, ob es sich selbst mit Ziehpunkte zeichnen soll.|
|[get_ShowHatching](#get_showhatching)|Die `ShowHatching` ambient-Eigenschaft ermöglicht das Steuerelement, um herauszufinden, ob er selbst die ausgebrütet gezeichnet werden soll.|
|[get_UserMode](#get_usermode)|Die `UserMode` Eigenschaft gibt an, die ambient-Benutzermodus des Containers.|
|[put_AllowContextMenu](#put_allowcontextmenu)|Die `AllowContextMenu` Eigenschaft gibt an, ob das gehostete Steuerelement zulässig ist, um sein eigenes Kontextmenü anzuzeigen.|
|[put_AllowShowUI](#put_allowshowui)|Die `AllowShowUI` Eigenschaft gibt an, ob das gehostete Steuerelement zulässig ist, um eine eigene Benutzeroberfläche anzuzeigen.|
|[put_AllowWindowlessActivation](#put_allowwindowlessactivation)|Die `AllowWindowlessActivation` Eigenschaft gibt an, ob der Container fensterlosen Aktivierung zulässig sind.|
|[put_BackColor](#put_backcolor)|Die `BackColor` Eigenschaft gibt an, die ambient-Hintergrundfarbe des Containers.|
|[put_DisplayAsDefault](#put_displayasdefault)|`DisplayAsDefault` ist eine Ambiente-Eigenschaft, die ermöglicht es einem Steuerelement, um herauszufinden, ob es sich um das Standardsteuerelement ist.|
|[put_DocHostDoubleClickFlags](#put_dochostdoubleclickflags)|Die `DocHostDoubleClickFlags` Eigenschaft gibt an, den Vorgang, der als Reaktion auf einen Doppelklick stattfinden sollen.|
|[put_DocHostFlags](#put_dochostflags)|Die `DocHostFlags` Eigenschaft gibt an, die Benutzeroptionen für die Schnittstelle des Hostobjekts.|
|[put_Font](#put_font)|Die `Font` Eigenschaft gibt an, die ambient-Schriftart des Containers.|
|[put_ForeColor](#put_forecolor)|Die `ForeColor` Eigenschaft gibt an, die ambient-Vordergrundfarbe des Containers.|
|[put_LocaleID](#put_localeid)|Die `LocaleID` Eigenschaft gibt an, die ambient-Gebietsschema-ID des Containers.|
|[put_MessageReflect](#put_messagereflect)|Die `MessageReflect` ambient-Eigenschaft gibt an, ob der Container die Nachrichten an das gehostete Steuerelement angegeben wird.|
|[put_OptionKeyPath](#put_optionkeypath)|Die `OptionKeyPath` Eigenschaft gibt an, den Registrierungsschlüsselpfad an den benutzereinstellungen.|
|[put_UserMode](#put_usermode)|Die `UserMode` Eigenschaft gibt an, die ambient-Benutzermodus des Containers.|

## <a name="remarks"></a>Hinweise

Diese Schnittstelle wird durch die ATL-ActiveX-Steuerelement hosten von Objekten verfügbar gemacht. Rufen Sie die Methoden für diese Schnittstelle für das gehostete Steuerelement verfügbaren Umgebungseigenschaften festzulegen, oder andere Aspekte des Verhaltens für den Container angeben. Ergänzen Sie die Eigenschaften von bereitgestellten `IAxWinAmbientDispatch`, verwenden Sie [IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md).

[AXHost](https://msdn.microsoft.com/library/system.windows.forms.axhost.aspx) wird versucht, Typinformationen zum Laden `IAxWinAmbientDispatch` und `IAxWinAmbientDispatchEx` aus der Typbibliothek, die den Code enthält.

Wenn Sie ATL90.dll, verknüpfen möchten **AXHost** lädt die Typinformationen aus der Typbibliothek in der DLL.

Finden Sie unter [Hosten von ActiveX-Steuerelemente mithilfe von ATL-xhost](../../atl/hosting-activex-controls-using-atl-axhost.md) Weitere Details.

## <a name="requirements"></a>Anforderungen

Die Definition dieser Schnittstelle ist in einer Reihe von Formen annehmen, verfügbar, wie in der folgenden Tabelle gezeigt.

|Definitionstyp|Datei|
|---------------------|----------|
|IDL|atliface.idl|
|Typbibliothek|ATL.dll|
|C++|konnte IRegistrar (ebenfalls in ATLBase.h enthalten)|

##  <a name="get_allowcontextmenu"></a>  IAxWinAmbientDispatch::get_AllowContextMenu

Die `AllowContextMenu` Eigenschaft gibt an, ob das gehostete Steuerelement zulässig ist, um sein eigenes Kontextmenü anzuzeigen.

```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```

### <a name="parameters"></a>Parameter

*pbAllowContextMenu*<br/>
[out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Objekt-Implementierung von ATL-Host wird auf VARIANT_TRUE festgelegt als der Standardwert dieser Eigenschaft verwendet.

##  <a name="get_allowshowui"></a>  IAxWinAmbientDispatch::get_AllowShowUI

Die `AllowShowUI` Eigenschaft gibt an, ob das gehostete Steuerelement zulässig ist, um eine eigene Benutzeroberfläche anzuzeigen.

```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```

### <a name="parameters"></a>Parameter

*pbAllowShowUI*<br/>
[out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Objekt-Implementierung von ATL-Hosts wird VARIANT_FALSE als der Standardwert dieser Eigenschaft verwendet.

##  <a name="get_allowwindowlessactivation"></a>  IAxWinAmbientDispatch::get_AllowWindowlessActivation

Die `AllowWindowlessActivation` Eigenschaft gibt an, ob der Container fensterlosen Aktivierung zulässig sind.

```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```

### <a name="parameters"></a>Parameter

*pbAllowWindowless*<br/>
[out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Objekt-Implementierung von ATL-Host wird auf VARIANT_TRUE festgelegt als der Standardwert dieser Eigenschaft verwendet.

##  <a name="get_backcolor"></a>  IAxWinAmbientDispatch::get_BackColor

Die `BackColor` Eigenschaft gibt an, die ambient-Hintergrundfarbe des Containers.

```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```

### <a name="parameters"></a>Parameter

*pclrBackground*<br/>
[out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Objekt-Implementierung von ATL-Hosts verwendet COLOR_BTNFACE oder COLOR_WINDOW, als der Standardwert dieser Eigenschaft (je nachdem, ob das übergeordnete Element des Hostfensters ein Dialogfeld oder nicht).

##  <a name="get_displayasdefault"></a>  IAxWinAmbientDispatch::get_DisplayAsDefault

`DisplayAsDefault` ist eine Ambiente-Eigenschaft, die ermöglicht es einem Steuerelement, um herauszufinden, ob es sich um das Standardsteuerelement ist.

```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```

### <a name="parameters"></a>Parameter

*pbDisplayAsDefault*<br/>
[out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Objekt-Implementierung von ATL-Hosts wird VARIANT_FALSE als der Standardwert dieser Eigenschaft verwendet.

##  <a name="get_dochostdoubleclickflags"></a>  IAxWinAmbientDispatch::get_DocHostDoubleClickFlags

Die `DocHostDoubleClickFlags` Eigenschaft gibt an, den Vorgang, der als Reaktion auf einen Doppelklick stattfinden sollen.

```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>Parameter

*pdwDocHostDoubleClickFlags*<br/>
[out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Objekt-Implementierung von ATL-Hosts wird DOCHOSTUIDBLCLK_DEFAULT als der Standardwert dieser Eigenschaft verwendet.

##  <a name="get_dochostflags"></a>  IAxWinAmbientDispatch::get_DocHostFlags

Die `DocHostFlags` Eigenschaft gibt an, die Benutzeroptionen für die Schnittstelle des Hostobjekts.

```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```

### <a name="parameters"></a>Parameter

*pdwDocHostFlags*<br/>
[out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Objekt-Implementierung von ATL-Hosts wird DOCHOSTUIFLAG_NO3DBORDER als der Standardwert dieser Eigenschaft verwendet.

##  <a name="get_font"></a>  IAxWinAmbientDispatch::get_Font

Die `Font` Eigenschaft gibt an, die ambient-Schriftart des Containers.

```
STDMETHOD(get_Font)(IFontDisp** pFont);
```

### <a name="parameters"></a>Parameter

*pFont*<br/>
[out] Die Adresse einer `IFontDisp` Schnittstellenzeiger verwendet, um den aktuellen Wert dieser Eigenschaft zu erhalten.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die ATL-Host-Objekt-Implementierung verwendet die Standardschriftart für die grafische Benutzeroberfläche oder der Systemschriftart, als der Standardwert dieser Eigenschaft.

##  <a name="get_forecolor"></a>  IAxWinAmbientDispatch::get_ForeColor

Die `ForeColor` Eigenschaft gibt an, die ambient-Vordergrundfarbe des Containers.

```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```

### <a name="parameters"></a>Parameter

*pclrForeground*<br/>
[out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Objekt-Implementierung von ATL-Host verwendet die Systemfarbe für Fenster Text als der Standardwert dieser Eigenschaft.

##  <a name="get_localeid"></a>  IAxWinAmbientDispatch::get_LocaleID

Die `LocaleID` Eigenschaft gibt an, die ambient-Gebietsschema-ID des Containers.

```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```

### <a name="parameters"></a>Parameter

*plcidLocaleID*<br/>
[out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Objekt-Implementierung von ATL-Hosts verwendet Standardgebietsschema des Benutzers, als der Standardwert dieser Eigenschaft.

Mit dieser Methode können Sie ermitteln, die Ambient-localId darf, d. h. der LocaleID-Wert des Programms das Steuerelement wird in verwendet. Wenn Sie die Gebietsschema-ID kennen, können Sie Code zum Laden von Beschriftungen Gebietsschema-spezifische Fehlermeldung angezeigt, und so weiter aus einer Ressourcendatei oder Satelliten-DLL aufrufen.

##  <a name="get_messagereflect"></a>  IAxWinAmbientDispatch::get_MessageReflect

Die `MessageReflect` ambient-Eigenschaft gibt an, ob der Container die Nachrichten an das gehostete Steuerelement angegeben wird.

```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```

### <a name="parameters"></a>Parameter

*pbMessageReflect*<br/>
[out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Objekt-Implementierung von ATL-Host wird auf VARIANT_TRUE festgelegt als der Standardwert dieser Eigenschaft verwendet.

##  <a name="get_optionkeypath"></a>  IAxWinAmbientDispatch::get_OptionKeyPath

Die `OptionKeyPath` Eigenschaft gibt an, den Registrierungsschlüsselpfad an den benutzereinstellungen.

```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```

### <a name="parameters"></a>Parameter

*pbstrOptionKeyPath*<br/>
[out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

##  <a name="get_showgrabhandles"></a>  IAxWinAmbientDispatch::get_ShowGrabHandles

Die `ShowGrabHandles` ambient-Eigenschaft ermöglicht das Steuerelement, um herauszufinden, ob es sich selbst mit Ziehpunkte zeichnen soll.

```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```

### <a name="parameters"></a>Parameter

*pbShowGrabHandles*<br/>
[out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die ATL-Host-objektimplementierung gibt immer VARIANT_FALSE als der Wert dieser Eigenschaft.

##  <a name="get_showhatching"></a>  IAxWinAmbientDispatch::get_ShowHatching

Die `ShowHatching` ambient-Eigenschaft ermöglicht das Steuerelement, um herauszufinden, ob er selbst die ausgebrütet gezeichnet werden soll.

```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```

### <a name="parameters"></a>Parameter

*pbShowHatching*<br/>
[out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die ATL-Host-objektimplementierung gibt immer VARIANT_FALSE als der Wert dieser Eigenschaft.

##  <a name="get_usermode"></a>  IAxWinAmbientDispatch::get_UserMode

Die `UserMode` Eigenschaft gibt an, die ambient-Benutzermodus des Containers.

```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```

### <a name="parameters"></a>Parameter

*pbUserMode*<br/>
[out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Objekt-Implementierung von ATL-Host wird auf VARIANT_TRUE festgelegt als der Standardwert dieser Eigenschaft verwendet.

##  <a name="put_allowcontextmenu"></a>  IAxWinAmbientDispatch::put_AllowContextMenu

Die `AllowContextMenu` Eigenschaft gibt an, ob das gehostete Steuerelement zulässig ist, um sein eigenes Kontextmenü anzuzeigen.

```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```

### <a name="parameters"></a>Parameter

*bAllowContextMenu*<br/>
[in] Der neue Wert dieser Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Objekt-Implementierung von ATL-Host wird auf VARIANT_TRUE festgelegt als der Standardwert dieser Eigenschaft verwendet.

##  <a name="put_allowshowui"></a>  IAxWinAmbientDispatch::put_AllowShowUI

Die `AllowShowUI` Eigenschaft gibt an, ob das gehostete Steuerelement zulässig ist, um eine eigene Benutzeroberfläche anzuzeigen.

```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```

### <a name="parameters"></a>Parameter

*bAllowShowUI*<br/>
[in] Der neue Wert dieser Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Objekt-Implementierung von ATL-Hosts wird VARIANT_FALSE als der Standardwert dieser Eigenschaft verwendet.

##  <a name="put_allowwindowlessactivation"></a>  IAxWinAmbientDispatch::put_AllowWindowlessActivation

Die `AllowWindowlessActivation` Eigenschaft gibt an, ob der Container fensterlosen Aktivierung zulässig sind.

```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```

### <a name="parameters"></a>Parameter

*bAllowWindowless*<br/>
[in] Der neue Wert dieser Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Objekt-Implementierung von ATL-Host wird auf VARIANT_TRUE festgelegt als der Standardwert dieser Eigenschaft verwendet.

##  <a name="put_backcolor"></a>  IAxWinAmbientDispatch::put_BackColor

Die `BackColor` Eigenschaft gibt an, die ambient-Hintergrundfarbe des Containers.

```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```

### <a name="parameters"></a>Parameter

*clrBackground*<br/>
[in] Der neue Wert dieser Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Objekt-Implementierung von ATL-Hosts verwendet COLOR_BTNFACE oder COLOR_WINDOW, als der Standardwert dieser Eigenschaft (je nachdem, ob das übergeordnete Element des Hostfensters ein Dialogfeld oder nicht).

##  <a name="put_displayasdefault"></a>  IAxWinAmbientDispatch::put_DisplayAsDefault

`DisplayAsDefault` ist eine Ambiente-Eigenschaft, die ermöglicht es einem Steuerelement, um herauszufinden, ob es sich um das Standardsteuerelement ist.

```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```

### <a name="parameters"></a>Parameter

*bDisplayAsDefault*<br/>
[in] Der neue Wert dieser Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Objekt-Implementierung von ATL-Hosts wird VARIANT_FALSE als der Standardwert dieser Eigenschaft verwendet.

##  <a name="put_dochostdoubleclickflags"></a>  IAxWinAmbientDispatch::put_DocHostDoubleClickFlags

Die `DocHostDoubleClickFlags` Eigenschaft gibt an, den Vorgang, der als Reaktion auf einen Doppelklick stattfinden sollen.

```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>Parameter

*dwDocHostDoubleClickFlags*<br/>
[in] Der neue Wert dieser Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Objekt-Implementierung von ATL-Hosts wird DOCHOSTUIDBLCLK_DEFAULT als der Standardwert dieser Eigenschaft verwendet.

##  <a name="put_dochostflags"></a>  IAxWinAmbientDispatch::put_DocHostFlags

Die `DocHostFlags` Eigenschaft gibt an, die Benutzeroptionen für die Schnittstelle des Hostobjekts.

```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```

### <a name="parameters"></a>Parameter

*dwDocHostFlags*<br/>
[in] Der neue Wert dieser Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Objekt-Implementierung von ATL-Hosts wird DOCHOSTUIFLAG_NO3DBORDER als der Standardwert dieser Eigenschaft verwendet.

##  <a name="put_font"></a>  IAxWinAmbientDispatch::put_Font

Die `Font` Eigenschaft gibt an, die ambient-Schriftart des Containers.

```
STDMETHOD(put_Font)(IFontDisp* pFont);
```

### <a name="parameters"></a>Parameter

*pFont*<br/>
[in] Der neue Wert dieser Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die ATL-Host-Objekt-Implementierung verwendet die Standardschriftart für die grafische Benutzeroberfläche oder der Systemschriftart, als der Standardwert dieser Eigenschaft.

##  <a name="put_forecolor"></a>  IAxWinAmbientDispatch::put_ForeColor

Die `ForeColor` Eigenschaft gibt an, die ambient-Vordergrundfarbe des Containers.

```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```

### <a name="parameters"></a>Parameter

*clrForeground*<br/>
[in] Der neue Wert dieser Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Objekt-Implementierung von ATL-Host verwendet die Systemfarbe für Fenster Text als der Standardwert dieser Eigenschaft.

##  <a name="put_localeid"></a>  IAxWinAmbientDispatch::put_LocaleID

Die `LocaleID` Eigenschaft gibt an, die ambient-Gebietsschema-ID des Containers.

```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```

### <a name="parameters"></a>Parameter

*lcidLocaleID*<br/>
[in] Der neue Wert dieser Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Objekt-Implementierung von ATL-Hosts verwendet Standardgebietsschema des Benutzers, als der Standardwert dieser Eigenschaft.

##  <a name="put_messagereflect"></a>  IAxWinAmbientDispatch::put_MessageReflect

Die `MessageReflect` ambient-Eigenschaft gibt an, ob der Container die Nachrichten an das gehostete Steuerelement angegeben wird.

```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```

### <a name="parameters"></a>Parameter

*bMessageReflect*<br/>
[in] Der neue Wert dieser Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Objekt-Implementierung von ATL-Host wird auf VARIANT_TRUE festgelegt als der Standardwert dieser Eigenschaft verwendet.

##  <a name="put_optionkeypath"></a>  IAxWinAmbientDispatch::put_OptionKeyPath

Die `OptionKeyPath` Eigenschaft gibt an, den Registrierungsschlüsselpfad an den benutzereinstellungen.

```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```

### <a name="parameters"></a>Parameter

*bstrOptionKeyPath*<br/>
[in] Der neue Wert dieser Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

##  <a name="put_usermode"></a>  IAxWinAmbientDispatch::put_UserMode

Die `UserMode` Eigenschaft gibt an, die ambient-Benutzermodus des Containers.

```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```

### <a name="parameters"></a>Parameter

*bUserMode*<br/>
[in] Der neue Wert dieser Eigenschaft.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Objekt-Implementierung von ATL-Host wird auf VARIANT_TRUE festgelegt als der Standardwert dieser Eigenschaft verwendet.

## <a name="see-also"></a>Siehe auch

[IAxWinAmbientDispatchEx-Schnittstelle](../../atl/reference/iaxwinambientdispatchex-interface.md)<br/>
[IAxWinHostWindow-Schnittstelle](../../atl/reference/iaxwinhostwindow-interface.md)<br/>
[CAxWindow:: QueryHost](../../atl/reference/caxwindow-class.md#queryhost)<br/>
[AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)

