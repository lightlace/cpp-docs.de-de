---
title: IAtlMemMgr Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 8e63d6dd9197aa3b81f893c58a1c8e41dfe2cc1b
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="iatlmemmgr-class"></a>IAtlMemMgr-Klasse
Diese Klasse stellt eine Schnittstelle zu einem Speichermanager.  
  
## <a name="syntax"></a>Syntax  
  
```
__interface __declspec(uuid("654F7EF5-CFDF-4df9-A450-6C6A13C622C0")) IAtlMemMgr
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[Zuordnen](#allocate)|Rufen Sie diese Methode auf, um einen Speicherblock zu belegen.|  
|[Kostenlose](#free)|Rufen Sie diese Methode, um einen Speicherblock frei.|  
|[GetSize](#getsize)|Rufen Sie diese Methode zum Abrufen der Größe eines belegten Speicherblocks.|  
|[Neu zuordnen](#reallocate)|Rufen Sie diese Methode, um einen Speicherblock neu zuordnen.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle wird implementiert, indem [CComHeap](../../atl/reference/ccomheap-class.md), [CCRTHeap](../../atl/reference/ccrtheap-class.md), [CLocalHeap](../../atl/reference/clocalheap-class.md), [CGlobalHeap](../../atl/reference/cglobalheap-class.md), oder [CWin32Heap](../../atl/reference/cwin32heap-class.md).  
  
> [!NOTE]
>  Lokale und globale Heapfunktionen ist langsamer als die anderen Speicherverwaltungsfunktionen und bieten nicht so viele Features. Neue Anwendungen sollten daher verwenden die [heap Funktionen](http://msdn.microsoft.com/library/windows/desktop/aa366711). Diese stehen in der [CWin32Heap](../../atl/reference/cwin32heap-class.md) Klasse.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#94;](../../atl/codesnippet/cpp/iatlmemmgr-class_1.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlmem.h  
  
##  <a name="allocate"></a>IAtlMemMgr::Allocate  
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
 Rufen Sie [IAtlMemMgr::Free](#free) oder [IAtlMemMgr::Reallocate](#reallocate) , die von dieser Methode belegten Arbeitsspeicher freizugeben.  
  
### <a name="example"></a>Beispiel  
 Ein Beispiel finden Sie unter der [IAtlMemMgr Übersicht](../../atl/reference/iatlmemmgr-class.md).  
  
##  <a name="free"></a>IAtlMemMgr::Free  
 Rufen Sie diese Methode, um einen Speicherblock frei.  
  
```
void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Ein Zeiger auf den Arbeitsspeicher, der zuvor von diesem Speicher-Manager zugeordnet wurde.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Methode können Sie Speicher abgerufen, indem [IAtlMemMgr::Allocate](#allocate) oder [IAtlMemMgr::Reallocate](#reallocate).  
  
### <a name="example"></a>Beispiel  
 Ein Beispiel finden Sie unter der [IAtlMemMgr Übersicht](../../atl/reference/iatlmemmgr-class.md).  
  
##  <a name="getsize"></a>IAtlMemMgr::GetSize  
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
 Ein Beispiel finden Sie unter der [IAtlMemMgr Übersicht](../../atl/reference/iatlmemmgr-class.md).  
  
##  <a name="reallocate"></a>IAtlMemMgr::Reallocate  
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
 Rufen Sie [IAtlMemMgr::Free](#free) oder [IAtlMemMgr::Reallocate](#reallocate) , die von dieser Methode belegten Arbeitsspeicher freizugeben.  
  
 Diese Methode wird vom Konzept her den vorhandenen Speicher frei und weist einen neuen Speicherblock. In der Praxis kann der vorhandene Speicher erweitert oder andernfalls wiederverwendet werden.  
  
### <a name="example"></a>Beispiel  
 Ein Beispiel finden Sie unter der [IAtlMemMgr Übersicht](../../atl/reference/iatlmemmgr-class.md).  
  
##  <a name="get_allowcontextmenu"></a>IAxWinAmbientDispatch::get_AllowContextMenu  
 Die **AllowContextMenu** -Eigenschaft gibt an, ob das gehostete Steuerelement sein eigenes Kontextmenü anzuzeigen.  
  
```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```  
  
### <a name="parameters"></a>Parameter  
 *pbAllowContextMenu*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Objekt-Implementierung von ATL-Host verwendet `VARIANT_TRUE` als der Standardwert dieser Eigenschaft.  
  
##  <a name="get_allowshowui"></a>IAxWinAmbientDispatch::get_AllowShowUI  
 Die **AllowShowUI** -Eigenschaft gibt an, ob das gehostete Steuerelement zulässig ist, um eine eigene Benutzeroberfläche anzuzeigen.  
  
```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```  
  
### <a name="parameters"></a>Parameter  
 *pbAllowShowUI*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Objekt-Implementierung von ATL-Host verwendet **VARIANT_FALSE** als der Standardwert dieser Eigenschaft.  
  
##  <a name="get_allowwindowlessactivation"></a>IAxWinAmbientDispatch::get_AllowWindowlessActivation  
 Die **AllowWindowlessActivation** -Eigenschaft gibt an, ob der Container fensterlosen Aktivierung zulässig sind.  
  
```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```  
  
### <a name="parameters"></a>Parameter  
 *pbAllowWindowless*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Objekt-Implementierung von ATL-Host verwendet `VARIANT_TRUE` als der Standardwert dieser Eigenschaft.  
  
##  <a name="get_backcolor"></a>IAxWinAmbientDispatch::get_BackColor  
 Die `BackColor` -Eigenschaft gibt die ambient-Hintergrundfarbe des Containers an.  
  
```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```  
  
### <a name="parameters"></a>Parameter  
 *pclrBackground*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Objekt-Implementierung von ATL-Host verwendet **COLOR_BTNFACE** oder **COLOR_WINDOW** als der Standardwert dieser Eigenschaft (je nachdem, ob das übergeordnete Element des Hostfensters ein Dialogfeld oder nicht).  
  
##  <a name="get_displayasdefault"></a>IAxWinAmbientDispatch::get_DisplayAsDefault  
 **DisplayAsDefault** ist eine Ambiente-Eigenschaft, die ermöglicht es einem Steuerelement, um festzustellen, ob es sich um das Standardsteuerelement ist.  
  
```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```  
  
### <a name="parameters"></a>Parameter  
 *pbDisplayAsDefault*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Objekt-Implementierung von ATL-Host verwendet **VARIANT_FALSE** als der Standardwert dieser Eigenschaft.  
  
##  <a name="get_dochostdoubleclickflags"></a>IAxWinAmbientDispatch::get_DocHostDoubleClickFlags  
 Die **DocHostDoubleClickFlags** -Eigenschaft gibt die Operation, die als Antwort auf ein Doppelklick stattfinden soll.  
  
```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```  
  
### <a name="parameters"></a>Parameter  
 *pdwDocHostDoubleClickFlags*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Objekt-Implementierung von ATL-Host verwendet **DOCHOSTUIDBLCLK_DEFAULT** als der Standardwert dieser Eigenschaft.  
  
##  <a name="get_dochostflags"></a>IAxWinAmbientDispatch::get_DocHostFlags  
 Die **DocHostFlags** -Eigenschaft gibt die Benutzerberechtigungen für die Schnittstelle des Hostobjekts an.  
  
```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```  
  
### <a name="parameters"></a>Parameter  
 *pdwDocHostFlags*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Objekt-Implementierung von ATL-Host verwendet **DOCHOSTUIFLAG_NO3DBORDER** als der Standardwert dieser Eigenschaft.  
  
##  <a name="get_font"></a>IAxWinAmbientDispatch::get_Font  
 Die **Schriftart** -Eigenschaft gibt die ambient-Schriftart des Containers an.  
  
```
STDMETHOD(get_Font)(IFontDisp** pFont);
```  
  
### <a name="parameters"></a>Parameter  
 `pFont`  
 [out] Die Adresse einer **IFontDisp** Schnittstellenzeiger verwendet, um den aktuellen Wert dieser Eigenschaft zu empfangen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 ATL Server-Objekt-Implementierung verwendet die Standard-GUI-Schriftart oder die Systemschriftart als der Standardwert dieser Eigenschaft.  
  
##  <a name="get_forecolor"></a>IAxWinAmbientDispatch::get_ForeColor  
 Die `ForeColor` -Eigenschaft gibt die Ambiente-Farbe des Containers.  
  
```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```  
  
### <a name="parameters"></a>Parameter  
 *pclrForeground*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 ATL Server-Objekt-Implementierung verwendet die Systemfarbe für Fenster Text als der Standardwert dieser Eigenschaft.  
  
##  <a name="get_localeid"></a>IAxWinAmbientDispatch::get_LocaleID  
 Die **LocaleID** -Eigenschaft gibt die ambient-Gebietsschema-ID des Containers.  
  
```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```  
  
### <a name="parameters"></a>Parameter  
 *plcidLocaleID*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 ATL Server-Objekt-Implementierung verwendet Standardgebietsschema des Benutzers, als der Standardwert dieser Eigenschaft.  
  
 Mit dieser Methode können Sie die Ambient-LocalID ermitteln, d. h. die Gebietsschema-ID des Programms das Steuerelement wird in verwendet. Wenn Sie die Gebietsschema-ID kennen, können Sie Code zum Laden von gebietsschemaspezifische Beschriftungen Text der Fehlermeldung, und so weiter aus einer Ressourcendatei oder Satelliten-DLL aufrufen.  
  
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
 Die Objekt-Implementierung von ATL-Host verwendet `VARIANT_TRUE` als der Standardwert dieser Eigenschaft.  
  
##  <a name="get_optionkeypath"></a>IAxWinAmbientDispatch::get_OptionKeyPath  
 Die **OptionKeyPath** -Eigenschaft gibt den Registrierungsschlüsselpfad an benutzereinstellungen.  
  
```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```  
  
### <a name="parameters"></a>Parameter  
 *pbstrOptionKeyPath*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="get_showgrabhandles"></a>IAxWinAmbientDispatch::get_ShowGrabHandles  
 Die **ShowGrabHandles** ambient-Eigenschaft kann das Steuerelement ermitteln, ob es sich selbst mit Ziehpunkten gezeichnet werden soll.  
  
```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```  
  
### <a name="parameters"></a>Parameter  
 *pbShowGrabHandles*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-Host objektimplementierung gibt immer **VARIANT_FALSE** als Wert dieser Eigenschaft.  
  
##  <a name="get_showhatching"></a>IAxWinAmbientDispatch::get_ShowHatching  
 Die **ShowHatching** ambient-Eigenschaft kann das Steuerelement ermitteln, ob sich die ausgebrütet gezeichnet werden soll.  
  
```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```  
  
### <a name="parameters"></a>Parameter  
 *pbShowHatching*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die ATL-Host objektimplementierung gibt immer **VARIANT_FALSE** als Wert dieser Eigenschaft.  
  
##  <a name="get_usermode"></a>IAxWinAmbientDispatch::get_UserMode  
 Die **UserMode** Eigenschaft gibt den Benutzermodus des Containers.  
  
```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```  
  
### <a name="parameters"></a>Parameter  
 *pbUserMode*  
 [out] Die Adresse einer Variablen auf den aktuellen Wert dieser Eigenschaft zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Objekt-Implementierung von ATL-Host verwendet `VARIANT_TRUE` als der Standardwert dieser Eigenschaft.  
  
##  <a name="put_allowcontextmenu"></a>IAxWinAmbientDispatch::put_AllowContextMenu  
 Die **AllowContextMenu** -Eigenschaft gibt an, ob das gehostete Steuerelement sein eigenes Kontextmenü anzuzeigen.  
  
```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```  
  
### <a name="parameters"></a>Parameter  
 *bAllowContextMenu*  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Objekt-Implementierung von ATL-Host verwendet `VARIANT_TRUE` als der Standardwert dieser Eigenschaft.  
  
##  <a name="put_allowshowui"></a>IAxWinAmbientDispatch::put_AllowShowUI  
 Die **AllowShowUI** -Eigenschaft gibt an, ob das gehostete Steuerelement zulässig ist, um eine eigene Benutzeroberfläche anzuzeigen.  
  
```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```  
  
### <a name="parameters"></a>Parameter  
 *bAllowShowUI*  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Objekt-Implementierung von ATL-Host verwendet **VARIANT_FALSE** als der Standardwert dieser Eigenschaft.  
  
##  <a name="put_allowwindowlessactivation"></a>IAxWinAmbientDispatch::put_AllowWindowlessActivation  
 Die **AllowWindowlessActivation** -Eigenschaft gibt an, ob der Container fensterlosen Aktivierung zulässig sind.  
  
```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```  
  
### <a name="parameters"></a>Parameter  
 *bAllowWindowless*  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Objekt-Implementierung von ATL-Host verwendet `VARIANT_TRUE` als der Standardwert dieser Eigenschaft.  
  
##  <a name="put_backcolor"></a>IAxWinAmbientDispatch::put_BackColor  
 Die `BackColor` -Eigenschaft gibt die ambient-Hintergrundfarbe des Containers an.  
  
```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```  
  
### <a name="parameters"></a>Parameter  
 *clrBackground*  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Objekt-Implementierung von ATL-Host verwendet **COLOR_BTNFACE** oder **COLOR_WINDOW** als der Standardwert dieser Eigenschaft (je nachdem, ob das übergeordnete Element des Hostfensters ein Dialogfeld oder nicht).  
  
##  <a name="put_displayasdefault"></a>IAxWinAmbientDispatch::put_DisplayAsDefault  
 **DisplayAsDefault** ist eine Ambiente-Eigenschaft, die ermöglicht es einem Steuerelement, um festzustellen, ob es sich um das Standardsteuerelement ist.  
  
```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```  
  
### <a name="parameters"></a>Parameter  
 `bDisplayAsDefault`  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Objekt-Implementierung von ATL-Host verwendet **VARIANT_FALSE** als der Standardwert dieser Eigenschaft.  
  
##  <a name="put_dochostdoubleclickflags"></a>IAxWinAmbientDispatch::put_DocHostDoubleClickFlags  
 Die **DocHostDoubleClickFlags** -Eigenschaft gibt die Operation, die als Antwort auf ein Doppelklick stattfinden soll.  
  
```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```  
  
### <a name="parameters"></a>Parameter  
 *dwDocHostDoubleClickFlags*  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Objekt-Implementierung von ATL-Host verwendet **DOCHOSTUIDBLCLK_DEFAULT** als der Standardwert dieser Eigenschaft.  
  
##  <a name="put_dochostflags"></a>IAxWinAmbientDispatch::put_DocHostFlags  
 Die **DocHostFlags** -Eigenschaft gibt die Benutzerberechtigungen für die Schnittstelle des Hostobjekts an.  
  
```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```  
  
### <a name="parameters"></a>Parameter  
 *dwDocHostFlags*  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Objekt-Implementierung von ATL-Host verwendet **DOCHOSTUIFLAG_NO3DBORDER** als der Standardwert dieser Eigenschaft.  
  
##  <a name="put_font"></a>IAxWinAmbientDispatch::put_Font  
 Die **Schriftart** -Eigenschaft gibt die ambient-Schriftart des Containers an.  
  
```
STDMETHOD(put_Font)(IFontDisp* pFont);
```  
  
### <a name="parameters"></a>Parameter  
 `pFont`  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 ATL Server-Objekt-Implementierung verwendet die Standard-GUI-Schriftart oder die Systemschriftart als der Standardwert dieser Eigenschaft.  
  
##  <a name="put_forecolor"></a>IAxWinAmbientDispatch::put_ForeColor  
 Die `ForeColor` -Eigenschaft gibt die Ambiente-Farbe des Containers.  
  
```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```  
  
### <a name="parameters"></a>Parameter  
 *clrForeground*  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 ATL Server-Objekt-Implementierung verwendet die Systemfarbe für Fenster Text als der Standardwert dieser Eigenschaft.  
  
##  <a name="put_localeid"></a>IAxWinAmbientDispatch::put_LocaleID  
 Die **LocaleID** -Eigenschaft gibt die ambient-Gebietsschema-ID des Containers.  
  
```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```  
  
### <a name="parameters"></a>Parameter  
 *lcidLocaleID*  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 ATL Server-Objekt-Implementierung verwendet Standardgebietsschema des Benutzers, als der Standardwert dieser Eigenschaft.  
  
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
 Die Objekt-Implementierung von ATL-Host verwendet `VARIANT_TRUE` als der Standardwert dieser Eigenschaft.  
  
##  <a name="put_optionkeypath"></a>IAxWinAmbientDispatch::put_OptionKeyPath  
 Die **OptionKeyPath** -Eigenschaft gibt den Registrierungsschlüsselpfad an benutzereinstellungen.  
  
```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```  
  
### <a name="parameters"></a>Parameter  
 *bstrOptionKeyPath*  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="put_usermode"></a>IAxWinAmbientDispatch::put_UserMode  
 Die **UserMode** Eigenschaft gibt den Benutzermodus des Containers.  
  
```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```  
  
### <a name="parameters"></a>Parameter  
 `bUserMode`  
 [in] Der neue Wert dieser Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Objekt-Implementierung von ATL-Host verwendet `VARIANT_TRUE` als der Standardwert dieser Eigenschaft.  
  
##  <a name="setambientdispatch"></a>IAxWinAmbientDispatchEx::SetAmbientDispatch  
 Diese Methode wird aufgerufen, um die Standardschnittstelle für die ambient-Eigenschaft mit einer benutzerdefinierten Benutzeroberfläche zu ergänzen.  
  
```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 *pDispatch*  
 Ein Zeiger auf die neue Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `SetAmbientDispatch` aufgerufen wird mit einem Zeiger auf eine neue Schnittstelle, die diese neue Schnittstelle verwendet werden, zum Aufrufen von Eigenschaften oder Methoden, die vom gehosteten Steuerelement angefordert, wenn diese Eigenschaften nicht bereits verfügbar sind [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md).  
  
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
  
 Um ein lizenziertes ActiveX-Steuerelement zu erstellen, finden Sie unter [IAxWinHostWindowLic::CreateControlLic](#createcontrollicex).  
  
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
  
 Um ein lizenziertes ActiveX-Steuerelement zu erstellen, finden Sie unter [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex).  
  
##  <a name="querycontrol"></a>IAxWinHostWindow::QueryControl  
 Gibt den angegebenen Schnittstellenzeiger vom gehosteten Steuerelement bereitgestellt werden.  
  
```
STDMETHOD(QueryControl)(REFIID riid, void** ppvObject);
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
  
##  <a name="createcontrollic"></a>IAxWinHostWindowLic::CreateControlLic  
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
 [in] BSTR, der den Lizenzschlüssel für das Steuerelement enthält.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IAxWinHostWindow::CreateControl](#createcontrol) eine Beschreibung der verbleibenden Parameter und Rückgabewert.  
  
 Das Aufrufen dieser Methode entspricht dem Aufruf [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex)  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel mit `IAxWinHostWindowLic::CreateControlLic`.  
  
##  <a name="createcontrollicex"></a>IAxWinHostWindowLic::CreateControlLicEx  
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
 `bstrLic`  
 [in] BSTR, der den Lizenzschlüssel für das Steuerelement enthält.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IAxWinHostWindow::CreateControlEx](#createcontrolex) eine Beschreibung der verbleibenden Parameter und Rückgabewert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel mit `IAxWinHostWindowLic::CreateControlLicEx`.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

