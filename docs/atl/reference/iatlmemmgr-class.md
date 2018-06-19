---
title: IAtlMemMgr Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IAtlMemMgr
- ATLMEM/ATL::IAtlMemMgr
- ATLMEM/ATL::Allocate
- ATLMEM/ATL::Free
- ATLMEM/ATL::GetSize
- ATLMEM/ATL::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- IAtlMemMgr class
- memory, managing
- memory, memory manager
ms.assetid: 18b2c569-25fe-4464-bdb6-3b1abef7154a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 35cc685c06eaa3992ec8444cfc5d99f2191145a0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366207"
---
# <a name="iatlmemmgr-class"></a>IAtlMemMgr-Klasse
Diese Klasse stellt die Schnittstelle in einen Speichermanager.  
  
## <a name="syntax"></a>Syntax  
  
```
__interface __declspec(uuid("654F7EF5-CFDF-4df9-A450-6C6A13C622C0")) IAtlMemMgr
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[Zuordnen](#allocate)|Rufen Sie diese Methode auf, um einen Speicherblock zu belegen.|  
|[Frei](#free)|Rufen Sie diese Methode, um einen Speicherblock frei.|  
|[GetSize](#getsize)|Rufen Sie diese Methode zum Abrufen der Größe eines belegten Speicherblocks.|  
|[Wenn ein Speicher neu](#reallocate)|Rufen Sie diese Methode, um einen Speicherblock neu zuzuordnen.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle wird implementiert, indem [CComHeap](../../atl/reference/ccomheap-class.md), [CCRTHeap](../../atl/reference/ccrtheap-class.md), [clocalheap –](../../atl/reference/clocalheap-class.md), [CGlobalHeap](../../atl/reference/cglobalheap-class.md), oder [CWin32Heap](../../atl/reference/cwin32heap-class.md).  
  
> [!NOTE]
>  Lokale und globale Heapfunktionen sind langsamer als die anderen Speicherverwaltungsfunktionen und bieten keine so viele Funktionen. Neue Anwendungen sollten daher verwenden die [heap Funktionen](http://msdn.microsoft.com/library/windows/desktop/aa366711). Diese Seiten sind verfügbar, in der [CWin32Heap](../../atl/reference/cwin32heap-class.md) Klasse.  
  
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
 `nBytes`  
 Die angeforderte Anzahl von Bytes im neuen Speicherblock.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf den Anfang des neu belegten Speicherblocks zurück.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [IAtlMemMgr::Free](#free) oder [IAtlMemMgr::Reallocate](#reallocate) um den von dieser Methode belegten Arbeitsspeicher freizugeben.  
  
### <a name="example"></a>Beispiel  
 Ein Beispiel finden Sie die [IAtlMemMgr Übersicht](../../atl/reference/iatlmemmgr-class.md).  
  
##  <a name="free"></a>  IAtlMemMgr::Free  
 Rufen Sie diese Methode, um einen Speicherblock frei.  
  
```
void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Methode können Sie Speicher erhalten, indem [IAtlMemMgr::Allocate](#allocate) oder [IAtlMemMgr::Reallocate](#reallocate).  
  
### <a name="example"></a>Beispiel  
 Ein Beispiel finden Sie die [IAtlMemMgr Übersicht](../../atl/reference/iatlmemmgr-class.md).  
  
##  <a name="getsize"></a>  IAtlMemMgr::GetSize  
 Rufen Sie diese Methode zum Abrufen der Größe eines belegten Speicherblocks.  
  
```
size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Größe des Speicherblocks in Bytes zurück.  
  
### <a name="example"></a>Beispiel  
 Ein Beispiel finden Sie die [IAtlMemMgr Übersicht](../../atl/reference/iatlmemmgr-class.md).  
  
##  <a name="reallocate"></a>  IAtlMemMgr::Reallocate  
 Rufen Sie diese Methode auf, um den von diesem Speicher-Manager zugeordneten Arbeitsspeicher neu zuzuordnen.  
  
```
void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde.  
  
 `nBytes`  
 Die angeforderte Anzahl von Bytes im neuen Speicherblock.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf den Anfang des neu belegten Speicherblocks zurück.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [IAtlMemMgr::Free](#free) oder [IAtlMemMgr::Reallocate](#reallocate) um den von dieser Methode belegten Arbeitsspeicher freizugeben.  
  
 Grundsätzlich wird diese Methode gibt die vorhandenen Arbeitsspeicher frei, und weist einen neuen Speicherblock. In Wirklichkeit kann der vorhandene Speicher erweitert oder andernfalls wiederverwendet werden.  
  
### <a name="example"></a>Beispiel  
 Ein Beispiel finden Sie die [IAtlMemMgr Übersicht](../../atl/reference/iatlmemmgr-class.md).  
  
##  <a name="get_allowcontextmenu"></a>  IAxWinAmbientDispatch::get_AllowContextMenu  
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
  
##  <a name="get_allowshowui"></a>  IAxWinAmbientDispatch::get_AllowShowUI  
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
  
##  <a name="get_allowwindowlessactivation"></a>  IAxWinAmbientDispatch::get_AllowWindowlessActivation  
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
  
##  <a name="get_backcolor"></a>  IAxWinAmbientDispatch::get_BackColor  
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
  
##  <a name="get_displayasdefault"></a>  IAxWinAmbientDispatch::get_DisplayAsDefault  
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
  
##  <a name="get_dochostdoubleclickflags"></a>  IAxWinAmbientDispatch::get_DocHostDoubleClickFlags  
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
  
##  <a name="get_dochostflags"></a>  IAxWinAmbientDispatch::get_DocHostFlags  
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
  
##  <a name="get_font"></a>  IAxWinAmbientDispatch::get_Font  
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
  
##  <a name="get_forecolor"></a>  IAxWinAmbientDispatch::get_ForeColor  
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
  
##  <a name="get_localeid"></a>  IAxWinAmbientDispatch::get_LocaleID  
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
  
##  <a name="get_messagereflect"></a>  IAxWinAmbientDispatch::get_MessageReflect  
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
  
##  <a name="get_optionkeypath"></a>  IAxWinAmbientDispatch::get_OptionKeyPath  
 Die **OptionKeyPath** Eigenschaft gibt den Registrierungsschlüsselpfad an benutzereinstellungen an.  
  
```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```  
  
### <a name="parameters"></a>Parameter  
 *pbstrOptionKeyPath*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="get_showgrabhandles"></a>  IAxWinAmbientDispatch::get_ShowGrabHandles  
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
  
##  <a name="get_showhatching"></a>  IAxWinAmbientDispatch::get_ShowHatching  
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
  
##  <a name="get_usermode"></a>  IAxWinAmbientDispatch::get_UserMode  
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
  
##  <a name="put_allowcontextmenu"></a>  IAxWinAmbientDispatch::put_AllowContextMenu  
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
  
##  <a name="put_allowshowui"></a>  IAxWinAmbientDispatch::put_AllowShowUI  
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
  
##  <a name="put_allowwindowlessactivation"></a>  IAxWinAmbientDispatch::put_AllowWindowlessActivation  
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
  
##  <a name="put_backcolor"></a>  IAxWinAmbientDispatch::put_BackColor  
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
  
##  <a name="put_displayasdefault"></a>  IAxWinAmbientDispatch::put_DisplayAsDefault  
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
  
##  <a name="put_dochostdoubleclickflags"></a>  IAxWinAmbientDispatch::put_DocHostDoubleClickFlags  
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
  
##  <a name="put_dochostflags"></a>  IAxWinAmbientDispatch::put_DocHostFlags  
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
  
##  <a name="put_font"></a>  IAxWinAmbientDispatch::put_Font  
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
  
##  <a name="put_forecolor"></a>  IAxWinAmbientDispatch::put_ForeColor  
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
  
##  <a name="put_localeid"></a>  IAxWinAmbientDispatch::put_LocaleID  
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
  
##  <a name="put_messagereflect"></a>  IAxWinAmbientDispatch::put_MessageReflect  
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
  
##  <a name="put_optionkeypath"></a>  IAxWinAmbientDispatch::put_OptionKeyPath  
 Die **OptionKeyPath** Eigenschaft gibt den Registrierungsschlüsselpfad an benutzereinstellungen an.  
  
```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```  
  
### <a name="parameters"></a>Parameter  
 *bstrOptionKeyPath*  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="put_usermode"></a>  IAxWinAmbientDispatch::put_UserMode  
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
  
##  <a name="setambientdispatch"></a>  IAxWinAmbientDispatchEx::SetAmbientDispatch  
 Diese Methode wird aufgerufen, um die ambient-Eigenschaft Standardschnittstelle mit einer benutzerdefinierten Benutzeroberfläche zu ergänzen.  
  
```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 *pDispatch*  
 Zeiger auf die neue Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `SetAmbientDispatch` wird aufgerufen, durch einen Zeiger auf eine neue Schnittstelle und die neue Oberfläche wird verwendet, um alle Eigenschaften oder Methoden, die vom gehosteten Steuerelement hat aufrufen – Wenn diese Eigenschaften nicht bereits enthalten sind [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md).  
  
##  <a name="attachcontrol"></a>  IAxWinHostWindow:: AttachControl  
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
  
##  <a name="createcontrol"></a>  IAxWinHostWindow::CreateControl  
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
  
 Um ein lizenziertes ActiveX-Steuerelement zu erstellen, finden Sie unter [IAxWinHostWindowLic::CreateControlLic](#createcontrollicex).  
  
##  <a name="createcontrolex"></a>  IAxWinHostWindow::CreateControlEx  
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
  
 Um ein lizenziertes ActiveX-Steuerelement zu erstellen, finden Sie unter [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex).  
  
##  <a name="querycontrol"></a>  IAxWinHostWindow::QueryControl  
 Gibt den angegebenen Schnittstellenzeiger vom gehosteten Steuerelement bereitgestellte zurück.  
  
```
STDMETHOD(QueryControl)(REFIID riid, void** ppvObject);
```  
  
### <a name="parameters"></a>Parameter  
 `riid`  
 [in] Die ID einer Schnittstelle für das Steuerelement, das angefordert wird.  
  
 `ppvObject`  
 [out] Die Adresse eines Zeigers, die die angegebene Schnittstelle des erstellten Steuerelements empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="setexternaldispatch"></a>  IAxWinHostWindow::SetExternalDispatch  
 Legt die externen Disp-Schnittstelle, die darin enthaltenen Steuerelemente bis hin zur Verfügung steht die [IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) Methode.  
  
```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>Parameter  
 `pDisp`  
 [in] Ein Zeiger auf eine `IDispatch` Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="setexternaluihandler"></a>  IAxWinHostWindow::SetExternalUIHandler  
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
  
##  <a name="createcontrollic"></a>  IAxWinHostWindowLic::CreateControlLic  
 Erstellt ein lizenziertes Steuerelement, initialisiert es und hostet es im Fenster identifizierten `hWnd`.  
  
```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```  
  
### <a name="parameters"></a>Parameter  
 `bstrLic`  
 [in] BSTR, die den Lizenzschlüssel für das Steuerelement enthält.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IAxWinHostWindow::CreateControl](#createcontrol) eine Beschreibung der verbleibenden Parameter und Rückgabewert.  
  
 Beim Aufrufen dieser Methode entspricht dem Aufruf [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex)  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, verwendet `IAxWinHostWindowLic::CreateControlLic`.  
  
##  <a name="createcontrollicex"></a>  IAxWinHostWindowLic::CreateControlLicEx  
 Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster, ähnlich wie [IAxWinHostWindow::CreateControl](#createcontrol).  
  
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
 `bstrLic`  
 [in] BSTR, die den Lizenzschlüssel für das Steuerelement enthält.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IAxWinHostWindow::CreateControlEx](#createcontrolex) eine Beschreibung der verbleibenden Parameter und Rückgabewert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, verwendet `IAxWinHostWindowLic::CreateControlLicEx`.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
