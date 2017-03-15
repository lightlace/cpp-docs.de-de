---
title: Klasse CAtlPreviewCtrlImpl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlpreviewctrlimpl/ATL::CAtlPreviewCtrlImpl
- CAtlPreviewCtrlImpl
dev_langs:
- C++
helpviewer_keywords:
- CAtlPreviewCtrlImpl class
ms.assetid: 39b3299e-07e4-4abc-9b6e-b54bfa3b0802
caps.latest.revision: 26
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
ms.openlocfilehash: 979dc23eabc2ba2362f7301fc34ca89016d58f37
ms.lasthandoff: 02/24/2017

---
# <a name="catlpreviewctrlimpl-class"></a>CAtlPreviewCtrlImpl-Klasse
Diese Klasse ist eine ATL-Implementierung eines Fensters, das ein von der Shell for Rich Preview bereitgestellten Hostfenster platziert wird.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
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
|[CAtlPreviewCtrlImpl::Create](#create)|Aufgerufen von einem Rich Preview-Handler, der Windows-Fenster zu erstellen.|  
|[CAtlPreviewCtrlImpl::Destroy](#destroy)|Von eine umfassende Vorschauhandler aufgerufen, wenn dieses Steuerelement gelöscht werden muss.|  
|[CAtlPreviewCtrlImpl::Focus](#focus)|Legt den Eingabefokus auf das Steuerelement.|  
|[CAtlPreviewCtrlImpl::OnPaint](#onpaint)|Behandelt die WM_PAINT-Meldung.|  
|[CAtlPreviewCtrlImpl::Redraw](#redraw)|Weist diesem Steuerelement neu gezeichnet werden.|  
|[CAtlPreviewCtrlImpl::SetHost](#sethost)|Legt ein neues übergeordnetes Element für dieses Steuerelement.|  
|[CAtlPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|Aufgerufen von einem Rich-Vorschauhandler wenn umfangreiche Vorschau visuellen Elemente festgelegt werden muss Inhalt.|  
|[CAtlPreviewCtrlImpl::SetRect](#setrect)|Legt ein neues umschließendes Rechteck für dieses Steuerelement.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::DoPaint](#dopaint)|Vom Framework aufgerufen wird, die Vorschau zu rendern.|  
  
### <a name="protected-constants"></a>Geschützte Konstanten  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::m_plf](#m_plf)|Schriftart für Text in einem Vorschaufenster angezeigt.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlPreviewCtrlImpl::m_clrBack](#m_clrback)|Hintergrundfarbe des Vorschaufensters.|  
|[CAtlPreviewCtrlImpl::m_clrText](#m_clrtext)|Textfarbe des Vorschaufensters.|  

  
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
  
##  <a name="a-namecatlpreviewctrlimpla--catlpreviewctrlimplcatlpreviewctrlimpl"></a><a name="catlpreviewctrlimpl"></a>CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl  
 Erstellt ein Objekt der Preview-Steuerelement.  
  
```
CAtlPreviewCtrlImpl(void) : m_clrText(0),
   m_clrBack(RGB(255, 255, 255)), m_plf(NULL);
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namedtora--catlpreviewctrlimplcatlpreviewctrlimpl"></a><a name="dtor"></a>CAtlPreviewCtrlImpl:: ~ CAtlPreviewCtrlImpl  
 Destructs ein Vorschau-Control-Objekt.  
  
```
virtual ~CAtlPreviewCtrlImpl(void);
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namecreatea--catlpreviewctrlimplcreate"></a><a name="create"></a>CAtlPreviewCtrlImpl::Create  
 Aufgerufen von einem Rich Preview-Handler, der Windows-Fenster zu erstellen.  
  
```
virtual BOOL Create(HWND hWndParent, const RECT* prc);
```  
  
### <a name="parameters"></a>Parameter  
 `hWndParent`  
 Ein Handle für das Hostfenster, die von der Shell for Rich Preview bereitgestellt.  
  
 `prc`  
 Gibt die ursprüngliche Größe und Position des Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn erfolgreich, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namedestroya--catlpreviewctrlimpldestroy"></a><a name="destroy"></a>CAtlPreviewCtrlImpl::Destroy  
 Von eine umfassende Vorschauhandler aufgerufen, wenn dieses Steuerelement gelöscht werden muss.  
  
```
virtual void Destroy();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namedopainta--catlpreviewctrlimpldopaint"></a><a name="dopaint"></a>CAtlPreviewCtrlImpl::DoPaint  
 Vom Framework aufgerufen wird, die Vorschau zu rendern.  
  
```
virtual void DoPaint(HDC hdc);
```  
  
### <a name="parameters"></a>Parameter  
 `hdc`  
 Ein Handle für einen Gerätekontext zum Zeichnen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namefocusa--catlpreviewctrlimplfocus"></a><a name="focus"></a>CAtlPreviewCtrlImpl::Focus  
 Legt den Eingabefokus auf das Steuerelement.  
  
```
virtual void Focus();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namemclrbacka--catlpreviewctrlimplmclrback"></a><a name="m_clrback"></a>CAtlPreviewCtrlImpl::m_clrBack  
 Hintergrundfarbe des Vorschaufensters.  
  
```
COLORREF m_clrBack;
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namemclrtexta--catlpreviewctrlimplmclrtext"></a><a name="m_clrtext"></a>CAtlPreviewCtrlImpl::m_clrText  
 Die Textfarbe des Vorschaufensters.  
  
```
COLORREF m_clrText;
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namemplfa--catlpreviewctrlimplmplf"></a><a name="m_plf"></a>CAtlPreviewCtrlImpl::m_plf  
 Schriftart für Text in einem Vorschaufenster angezeigt.  
  
```
const LOGFONTW* m_plf;
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonpainta--catlpreviewctrlimplonpaint"></a><a name="onpaint"></a>CAtlPreviewCtrlImpl::OnPaint  
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
 WM_PAINT festgelegt.  
  
 `wParam`  
 Dieser Parameter wird nicht verwendet.  
  
 `lParam`  
 Dieser Parameter wird nicht verwendet.  
  
 `bHandled`  
 Wenn diese Funktion zurückgibt, enthält `TRUE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameredrawa--catlpreviewctrlimplredraw"></a><a name="redraw"></a>CAtlPreviewCtrlImpl::Redraw  
 Weist diesem Steuerelement neu gezeichnet werden.  
  
```
virtual void Redraw();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesethosta--catlpreviewctrlimplsethost"></a><a name="sethost"></a>CAtlPreviewCtrlImpl::SetHost  
 Legt ein neues übergeordnetes Element für dieses Steuerelement.  
  
```
virtual void SetHost(HWND hWndParent);
```  
  
### <a name="parameters"></a>Parameter  
 `hWndParent`  
 Ein Handle für das neue übergeordnete Fenster.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetpreviewvisualsa--catlpreviewctrlimplsetpreviewvisuals"></a><a name="setpreviewvisuals"></a>CAtlPreviewCtrlImpl::SetPreviewVisuals  
 Aufgerufen von einem Rich-Vorschauhandler wenn umfangreiche Vorschau visuellen Elemente festgelegt werden muss Inhalt.  
  
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
 Schriftart für Text in einem Vorschaufenster angezeigt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetrecta--catlpreviewctrlimplsetrect"></a><a name="setrect"></a>CAtlPreviewCtrlImpl::SetRect  
 Legt ein neues umschließendes Rechteck für dieses Steuerelement.  
  
```
virtual void SetRect(const RECT* prc, BOOL bRedraw);
```  
  
### <a name="parameters"></a>Parameter  
 `prc`  
 Gibt die neue Größe und Position des Steuerelements Vorschau.  
  
 `bRedraw`  
 Gibt an, ob das Steuerelement neu gezeichnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md)

