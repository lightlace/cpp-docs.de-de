---
title: CAtlPreviewCtrlImpl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Create
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Destroy
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Focus
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::OnPaint
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Redraw
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetHost
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetPreviewVisuals
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetRect
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::DoPaint
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_plf
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_clrBack
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_clrText
dev_langs: C++
helpviewer_keywords: CAtlPreviewCtrlImpl class
ms.assetid: 39b3299e-07e4-4abc-9b6e-b54bfa3b0802
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 281bc00e46cf28f7cc7d5f1e072fd41ad4cce61a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="catlpreviewctrlimpl-class"></a>CAtlPreviewCtrlImpl-Klasse
Diese Klasse ist eine ATL-Implementierung eines Fensters, das auf ein Hostfenster bereitgestellt von der Shell for Rich Preview eingefügt wird.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CAtlPreviewCtrlImpl : public CWindowImpl<CAtlPreviewCtrlImpl>, public IPreviewCtrl;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl:: ~ CAtlPreviewCtrlImpl](#dtor)|Destructs ein Vorschau-Control-Objekt.|  
|[CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl](#catlpreviewctrlimpl)|Erstellt ein Objekt der Preview-Steuerelement.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::Create](#create)|Wird aufgerufen, von einem Rich Preview-Handler, um das Windows-Fenster zu erstellen.|  
|[CAtlPreviewCtrlImpl::Destroy](#destroy)|Wird von einem Rich Preview-Handler aufgerufen, wenn es zerstört das Steuerelement muss.|  
|[CAtlPreviewCtrlImpl::Focus](#focus)|Setzt den Eingabefokus auf dieses Steuerelement.|  
|[CAtlPreviewCtrlImpl::OnPaint](#onpaint)|Behandelt die WM_PAINT-Meldung.|  
|[CAtlPreviewCtrlImpl::Redraw](#redraw)|Weist das Steuerelement zum Neuzeichnen an.|  
|[CAtlPreviewCtrlImpl::SetHost](#sethost)|Legt einen neuen übergeordneten für dieses Steuerelement fest.|  
|[CAtlPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|Wird aufgerufen, von einem Rich Preview Handler Wenn visuelle Elemente von rich Preview festgelegt werden muss Inhalt.|  
|[CAtlPreviewCtrlImpl::SetRect](#setrect)|Legt einen neuen umschließenden Rechtecks für dieses Steuerelement fest.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::DoPaint](#dopaint)|Vom Framework aufgerufen, die Vorschau zu rendern.|  
  
### <a name="protected-constants"></a>Geschützte Konstanten  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::m_plf](#m_plf)|Zum Anzeigen von Text im Vorschaufenster verwendete Schriftart.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::m_clrBack](#m_clrback)|Hintergrundfarbe des Vorschaufensters.|  
|[CAtlPreviewCtrlImpl::m_clrText](#m_clrtext)|Die Textfarbe des Vorschaufensters.|  

  
## <a name="remarks"></a>Hinweise  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `TBase`  
  
 `ATL::CMessageMap`  
  
 `ATL::CWindowImplRoot<TBase>`  
  
 `ATL::CWindowImplBaseT<TBase,TWinTraits>`  
  
 [ATL::CWindowImpl\<CAtlPreviewCtrlImpl >](../../atl/reference/cwindowimpl-class.md)  
  
 `IPreviewCtrl`  
  
 `ATL::CAtlPreviewCtrlImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlpreviewctrlimpl.h  
  
##  <a name="catlpreviewctrlimpl"></a>CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl  
 Erstellt ein Objekt der Preview-Steuerelement.  
  
```
CAtlPreviewCtrlImpl(void) : m_clrText(0),
   m_clrBack(RGB(255, 255, 255)), m_plf(NULL);
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="dtor"></a>CAtlPreviewCtrlImpl:: ~ CAtlPreviewCtrlImpl  
 Destructs ein Vorschau-Control-Objekt.  
  
```
virtual ~CAtlPreviewCtrlImpl(void);
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="create"></a>CAtlPreviewCtrlImpl::Create  
 Wird aufgerufen, von einem Rich Preview-Handler, um das Windows-Fenster zu erstellen.  
  
```
virtual BOOL Create(HWND hWndParent, const RECT* prc);
```  
  
### <a name="parameters"></a>Parameter  
 `hWndParent`  
 Ein Handle für das Hostfenster, die von der Shell for Rich Preview angegeben.  
  
 `prc`  
 Gibt an, die ursprüngliche Größe und Position des Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn erfolgreich, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="destroy"></a>CAtlPreviewCtrlImpl::Destroy  
 Wird von einem Rich Preview-Handler aufgerufen, wenn es zerstört das Steuerelement muss.  
  
```
virtual void Destroy();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="dopaint"></a>CAtlPreviewCtrlImpl::DoPaint  
 Vom Framework aufgerufen, die Vorschau zu rendern.  
  
```
virtual void DoPaint(HDC hdc);
```  
  
### <a name="parameters"></a>Parameter  
 `hdc`  
 Ein Handle für einen Gerätekontext für das Paint-Ereignisse.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="focus"></a>CAtlPreviewCtrlImpl::Focus  
 Setzt den Eingabefokus auf dieses Steuerelement.  
  
```
virtual void Focus();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_clrback"></a>CAtlPreviewCtrlImpl::m_clrBack  
 Hintergrundfarbe des Vorschaufensters.  
  
```
COLORREF m_clrBack;
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_clrtext"></a>CAtlPreviewCtrlImpl::m_clrText  
 Die Textfarbe des Vorschaufensters.  
  
```
COLORREF m_clrText;
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_plf"></a>CAtlPreviewCtrlImpl::m_plf  
 Zum Anzeigen von Text im Vorschaufenster verwendete Schriftart.  
  
```
const LOGFONTW* m_plf;
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onpaint"></a>CAtlPreviewCtrlImpl::OnPaint  
 Behandelt die WM_PAINT-Meldung.  
  
```
LRESULT OnPaint(  
    UINT nMsg,
    WPARAM wParam,
    LPARAM lParam,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>Parameter  
 `nMsg`  
 Legen Sie auf WM_PAINT.  
  
 `wParam`  
 Dieser Parameter wird nicht verwendet.  
  
 `lParam`  
 Dieser Parameter wird nicht verwendet.  
  
 `bHandled`  
 Wenn diese Funktion zurückgibt, enthält Sie `TRUE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="redraw"></a>CAtlPreviewCtrlImpl::Redraw  
 Weist das Steuerelement zum Neuzeichnen an.  
  
```
virtual void Redraw();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="sethost"></a>CAtlPreviewCtrlImpl::SetHost  
 Legt einen neuen übergeordneten für dieses Steuerelement fest.  
  
```
virtual void SetHost(HWND hWndParent);
```  
  
### <a name="parameters"></a>Parameter  
 `hWndParent`  
 Ein Handle für das neue übergeordnete Fenster.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpreviewvisuals"></a>CAtlPreviewCtrlImpl::SetPreviewVisuals  
 Wird aufgerufen, von einem Rich Preview Handler Wenn visuelle Elemente von rich Preview festgelegt werden muss Inhalt.  
  
```
virtual void SetPreviewVisuals(
    COLORREF clrBack,
    COLORREF clrText,
    const LOGFONTW* plf);
```  
  
### <a name="parameters"></a>Parameter  
 `clrBack`  
 Hintergrundfarbe des Vorschaufensters.  
  
 `clrText`  
 Die Textfarbe des Vorschaufensters.  
  
 `plf`  
 Zum Anzeigen von Text im Vorschaufenster verwendete Schriftart.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setrect"></a>CAtlPreviewCtrlImpl::SetRect  
 Legt einen neuen umschließenden Rechtecks für dieses Steuerelement fest.  
  
```
virtual void SetRect(const RECT* prc, BOOL bRedraw);
```  
  
### <a name="parameters"></a>Parameter  
 `prc`  
 Gibt an, die neue Größe und Position des Steuerelements Preview.  
  
 `bRedraw`  
 Gibt an, ob das Steuerelement neu gezeichnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md)
