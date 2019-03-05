---
title: IAtlMemMgr-Klasse
ms.date: 11/04/2016
f1_keywords:
- IAtlMemMgr
- ATLMEM/ATL::IAtlMemMgr
- ATLMEM/ATL::Allocate
- ATLMEM/ATL::Free
- ATLMEM/ATL::GetSize
- ATLMEM/ATL::Reallocate
helpviewer_keywords:
- IAtlMemMgr class
- memory, managing
- memory, memory manager
ms.assetid: 18b2c569-25fe-4464-bdb6-3b1abef7154a
ms.openlocfilehash: b9b6ac6dc265378f617e053bc48ac6030425cef4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57297917"
---
# <a name="iatlmemmgr-class"></a>IAtlMemMgr-Klasse

Diese Klasse stellt die Schnittstelle, um einen Speicher-Manager.

## <a name="syntax"></a>Syntax

```
__interface __declspec(uuid("654F7EF5-CFDF-4df9-A450-6C6A13C622C0")) IAtlMemMgr
```

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[zuordnen](#allocate)|Rufen Sie diese Methode auf, um einen Speicherblock zu belegen.|
|[kostenlos](#free)|Rufen Sie diese Methode, um einen Speicherblock frei.|
|[GetSize](#getsize)|Rufen Sie diese Methode zum Abrufen der Größe eines belegten Speicherblocks.|
|[Zum erneuten Zuweisen](#reallocate)|Rufen Sie diese Methode, um einen Speicherblock neu zuordnen.|

## <a name="remarks"></a>Hinweise

Diese Schnittstelle wird implementiert von [CComHeap](../../atl/reference/ccomheap-class.md), [CCRTHeap](../../atl/reference/ccrtheap-class.md), [clocalheap –](../../atl/reference/clocalheap-class.md), [CGlobalHeap](../../atl/reference/cglobalheap-class.md), oder [CWin32Heap](../../atl/reference/cwin32heap-class.md).

> [!NOTE]
>  Die lokale und globale Heapfunktionen sind langsamer als die anderen Speicherverwaltungsfunktionen und bieten keine so viele Features. Neue Anwendungen sollten daher verwenden die [Heapfunktionen](/windows/desktop/Memory/heap-functions). Diese stehen in der [CWin32Heap](../../atl/reference/cwin32heap-class.md) Klasse.

## <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#94](../../atl/codesnippet/cpp/iatlmemmgr-class_1.cpp)]

## <a name="requirements"></a>Anforderungen

**Header:** atlmem.h

##  <a name="allocate"></a>  IAtlMemMgr::Allocate

Rufen Sie diese Methode auf, um einen Speicherblock zu belegen.

```
void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parameter

*nBytes*<br/>
Die angeforderte Anzahl von Bytes im neuen Speicherblock.

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf den Anfang des neu belegten Speicherblocks zurück.

### <a name="remarks"></a>Hinweise

Rufen Sie [IAtlMemMgr::Free](#free) oder [IAtlMemMgr::Reallocate](#reallocate) um den von dieser Methode belegten Arbeitsspeicher freizugeben.

### <a name="example"></a>Beispiel

Ein Beispiel finden Sie unter den [IAtlMemMgr-Übersicht](../../atl/reference/iatlmemmgr-class.md).

##  <a name="free"></a>  IAtlMemMgr::Free

Rufen Sie diese Methode, um einen Speicherblock frei.

```
void Free(void* p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde.

### <a name="remarks"></a>Hinweise

Mit dieser Methode können Sie Speicher abgerufen, indem freigeben [IAtlMemMgr::Allocate](#allocate) oder [IAtlMemMgr::Reallocate](#reallocate).

### <a name="example"></a>Beispiel

Ein Beispiel finden Sie unter den [IAtlMemMgr-Übersicht](../../atl/reference/iatlmemmgr-class.md).

##  <a name="getsize"></a>  IAtlMemMgr::GetSize

Rufen Sie diese Methode zum Abrufen der Größe eines belegten Speicherblocks.

```
size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde.

### <a name="return-value"></a>Rückgabewert

Gibt die Größe des Speicherblocks in Bytes zurück.

### <a name="example"></a>Beispiel

Ein Beispiel finden Sie unter den [IAtlMemMgr-Übersicht](../../atl/reference/iatlmemmgr-class.md).

##  <a name="reallocate"></a>  IAtlMemMgr::Reallocate

Rufen Sie diese Methode auf, um den von diesem Speicher-Manager zugeordneten Arbeitsspeicher neu zuzuordnen.

```
void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde.

*nBytes*<br/>
Die angeforderte Anzahl von Bytes im neuen Speicherblock.

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf den Anfang des neu belegten Speicherblocks zurück.

### <a name="remarks"></a>Hinweise

Rufen Sie [IAtlMemMgr::Free](#free) oder [IAtlMemMgr::Reallocate](#reallocate) um den von dieser Methode belegten Arbeitsspeicher freizugeben.

Vom Konzept her ist diese Methode gibt die vorhandenen Arbeitsspeicher frei, und weist einen neuen Speicherblock. In der Praxis kann der vorhandene Speicher erweitert oder andernfalls erneut verwendet werden.

### <a name="example"></a>Beispiel

Ein Beispiel finden Sie unter den [IAtlMemMgr-Übersicht](../../atl/reference/iatlmemmgr-class.md).

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

##  <a name="setambientdispatch"></a>  IAxWinAmbientDispatchEx::SetAmbientDispatch

Diese Methode wird aufgerufen, um die Standardschnittstelle für die ambient-Eigenschaft mit einer benutzerdefinierten Benutzeroberfläche zu ergänzen.

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>Parameter

*pDispatch*<br/>
Zeiger auf die neue Benutzeroberfläche.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Bei `SetAmbientDispatch` wird aufgerufen, mit einem Zeiger auf eine neue Schnittstelle, die diese neue Schnittstelle verwendet werden, zum Aufrufen von Eigenschaften oder Methoden, die für das gehostete Steuerelement aufgefordert, wenn diese Eigenschaften nicht bereits enthalten sind [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md).

##  <a name="attachcontrol"></a>  IAxWinHostWindow::AttachControl

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

Ein lizenziertes ActiveX-Steuerelement erstellen zu können, finden Sie unter [IAxWinHostWindowLic::CreateControlLic](#createcontrollicex).

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
[in] Der Schnittstellenbezeichner einer ausgehenden Schnittstelle für das enthaltene Objekt. Can be IID_NULL.

*punkAdvise*<br/>
[in] Ein Zeiger auf die `IUnknown` -Schnittstelle des Senkenobjekts mit dem Verbindungspunkt am anhand des enthaltenen Objekts verbunden sein, `iidSink`.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Im Gegensatz zu den `CreateControl` Methode `CreateControlEx` auch können Sie einen Schnittstellenzeiger auf das neu erstellte Steuerelement zu empfangen, und richten Sie eine Ereignissenke, zum Empfangen von Ereignissen, die vom Steuerelement ausgelöst.

Ein lizenziertes ActiveX-Steuerelement erstellen zu können, finden Sie unter [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex).

##  <a name="querycontrol"></a>  IAxWinHostWindow::QueryControl

Gibt den angegebenen Schnittstellenzeiger vom gehosteten Steuerelement bereitgestellt werden.

```
STDMETHOD(QueryControl)(REFIID riid, void** ppvObject);
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

##  <a name="createcontrollic"></a>  IAxWinHostWindowLic::CreateControlLic

Erstellt ein lizenziertes Steuerelement, initialisiert es und hostet es im Fenster identifizierte `hWnd`.

```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```

### <a name="parameters"></a>Parameter

*bstrLic*<br/>
[in] BSTR, das den Lizenzschlüssel für das Steuerelement enthält.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IAxWinHostWindow::CreateControl](#createcontrol) eine Beschreibung der verbleibende Parameter und Rückgabewert.

Das Aufrufen dieser Methode entspricht dem Aufruf [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex)

### <a name="example"></a>Beispiel

Finden Sie unter [Hosten von ActiveX-Steuerelemente mithilfe von ATL-xhost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, verwendet `IAxWinHostWindowLic::CreateControlLic`.

##  <a name="createcontrollicex"></a>  IAxWinHostWindowLic::CreateControlLicEx

Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster ähnelt [IAxWinHostWindow::CreateControl](#createcontrol).

```
STDMETHOD(CreateControlLicEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise,
    BSTR bstrLic);
```

### <a name="parameters"></a>Parameter

*bstrLic*<br/>
[in] BSTR, das den Lizenzschlüssel für das Steuerelement enthält.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IAxWinHostWindow::CreateControlEx](#createcontrolex) eine Beschreibung der verbleibende Parameter und Rückgabewert.

### <a name="example"></a>Beispiel

Finden Sie unter [Hosten von ActiveX-Steuerelemente mithilfe von ATL-xhost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, verwendet `IAxWinHostWindowLic::CreateControlLicEx`.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
