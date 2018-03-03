---
title: IOleInPlaceObjectWindowlessImpl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetDropTarget
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::OnWindowMessage
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::SetObjectRects
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::UIDeactivate
dev_langs:
- C++
helpviewer_keywords:
- IOleInPlaceObjectWindowless, ATL implementation
- activation [C++], ATL
- IOleInPlaceObjectWindowlessImpl class
- ActiveX controls [C++], communication between container and control
- controls [ATL], windowless
- deactivating ATL
ms.assetid: a2e0feb4-bc59-4adf-aab2-105457bbdbb4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f455172723be4f46751b45d244e74dda5fcacae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ioleinplaceobjectwindowlessimpl-class"></a>IOleInPlaceObjectWindowlessImpl-Klasse
Diese Klasse implementiert **IUnknown** und bietet Methoden, mit denen ein fensterloses Steuerelement fenstermeldungen empfangen und Drag & Drop-Vorgängen teilnehmen können.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>
class IOleInPlaceObjectWindowlessImpl
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IOleInPlaceObjectWindowlessImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp](#contextsensitivehelp)|Ermöglicht die kontextbezogene Hilfe. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::GetDropTarget](#getdroptarget)|Stellt die `IDropTarget` Schnittstelle für ein direktes aktiv, fensterlose Objekt, das Ziehen und Ablegen unterstützt. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::GetWindow](#getwindow)|Ruft ein Fensterhandle ab.|  
|[IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate](#inplacedeactivate)|Deaktiviert ein aktives direktes-Steuerelement.|  
|[IOleInPlaceObjectWindowlessImpl::OnWindowMessage](#onwindowmessage)|Sendet eine Nachricht aus dem Container um ein fensterloses Steuerelement, das in-Place aktiv ist.|  
|[IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo](#reactivateandundo)|Reaktiviert ein zuvor deaktiviertes Steuerelements. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::SetObjectRects](#setobjectrects)|Gibt an, welcher Teil der direkten-Steuerelement angezeigt wird.|  
|[IOleInPlaceObjectWindowlessImpl::UIDeactivate](#uideactivate)|Deaktiviert, und entfernt die Benutzeroberfläche, die direkte Aktivierung unterstützt.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) Schnittstelle verwaltet die erneute Aktivierung und Deaktivierung von direkten gesteuert wird und bestimmt, wie viel des Steuerelements sichtbar sein soll. Die [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304) Schnittstelle ermöglicht ein fensterloses Steuerelement, um fenstermeldungen zu empfangen und zur Teilnahme an Drag-and-Drop-Vorgänge. Klasse `IOleInPlaceObjectWindowlessImpl` stellt eine Standardimplementierung von `IOleInPlaceObject` und `IOleInPlaceObjectWindowless` und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
 **Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IOleInPlaceObjectWindowless`  
  
 `IOleInPlaceObjectWindowlessImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="contextsensitivehelp"></a>IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp  
 Gibt **E_NOTIMPL**.  
  
```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleWindow::ContextSensitiveHelp](http://msdn.microsoft.com/library/windows/desktop/ms680059) im Windows SDK.  
  
##  <a name="getdroptarget"></a>IOleInPlaceObjectWindowlessImpl::GetDropTarget  
 Gibt **E_NOTIMPL**.  
  
```
HRESULT GetDropTarget(IDropTarget** ppDropTarget);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleInPlaceObjectWindowless::GetDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms678535) im Windows SDK.  
  
##  <a name="getwindow"></a>IOleInPlaceObjectWindowlessImpl::GetWindow  
 Der Container und Funktionsaufrufe, um das Fensterhandle des Steuerelements zu erhalten.  
  
```
HRESULT GetWindow(HWND* phwnd);
```  
  
### <a name="remarks"></a>Hinweise  
 Einige Container funktioniert nicht mit einem Steuerelement, die fensterlose, selbst wenn es derzeit im Fenstermodus handelt. In ATLs-Implementierung Wenn der Steuerelementklasse-Datenmember `m_bWasOnceWindowless` ist **"true"**, gibt die Funktion **E_FAIL**. Andernfalls gilt: Wenn *Phwnd* ist nicht **NULL**, `GetWindow` legt \* *Phwnd* Datenmember der Steuerelementklasse `m_hWnd` und gibt`S_OK`.  
  
 Finden Sie unter [IOleWindow::GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms687282) im Windows SDK.  
  
##  <a name="inplacedeactivate"></a>IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate  
 Vom Container So deaktivieren Sie ein direktes aktives Steuerelement aufgerufen.  
  
```
HRESULT InPlaceDeactivate(HWND* phwnd);
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt eine vollständige oder teilweise Deaktivierung abhängig vom Status des Steuerelements. Bei Bedarf das Steuerelement-Benutzeroberfläche deaktiviert ist, und die Steuerelementfensters, sofern vorhanden, zerstört wird. Der Container wird benachrichtigt, dass das Steuerelement nicht mehr aktiv, erfüllt ist. Die **IOleInPlaceUIWindow** Schnittstelle, die vom Container verwendet werden, zum Aushandeln von Menüs und Rahmen Speicherplatz wird freigegeben.  
  
 Finden Sie unter [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) im Windows SDK.  
  
##  <a name="onwindowmessage"></a>IOleInPlaceObjectWindowlessImpl::OnWindowMessage  
 Sendet eine Nachricht von einem Container für ein fensterloses Steuerelement, das in-Place aktiv ist.  
  
```
HRESULT OnWindowMessage(
    UINT msg,
    WPARAM WParam,
    LPARAM LParam,
    LRESULT plResultParam);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleInPlaceObjectWindowless::OnWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms693783) im Windows SDK.  
  
##  <a name="reactivateandundo"></a>IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo  
 Gibt **E_NOTIMPL**.  
  
```
HRESULT ReactivateAndUndo();
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleInPlaceObject::ReactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms691372) im Windows SDK.  
  
##  <a name="setobjectrects"></a>IOleInPlaceObjectWindowlessImpl::SetObjectRects  
 Wird aufgerufen, durch den Container zu informieren das Steuerelement, das die Größe und/oder die Position geändert hat.  
  
```
HRESULT SetObjectRects(LPCRECT prcPos, LPCRECT prcClip);
```  
  
### <a name="remarks"></a>Hinweise  
 Aktualisiert das Steuerelement `m_rcPos` -Datenmember und die Steuerelementanzeige. Nur der Teil des Steuerelements, das die Clip-Bereich überschneidet wird angezeigt. Wenn die Anzeige eines Steuerelements wurde zuvor abgeschnitten, aber das Clipping entfernt wurde, kann diese Funktion aufgerufen werden, um eine umfassende Ansicht der das Steuerelement neu gezeichnet werden.  
  
 Finden Sie unter [IOleInPlaceObject::SetObjectRects](http://msdn.microsoft.com/library/windows/desktop/ms683767) im Windows SDK.  
  
##  <a name="uideactivate"></a>IOleInPlaceObjectWindowlessImpl::UIDeactivate  
 Deaktiviert, und entfernt das Steuerelement-Benutzeroberfläche, die direkte Aktivierung unterstützt.  
  
```
HRESULT UIDeactivate();
```  
  
### <a name="remarks"></a>Hinweise  
 Legt die Steuerelementklasse Datenmember `m_bUIActive` auf **"false"**. Die ATL-Implementierung dieser Funktion immer gibt `S_OK`.  
  
 Finden Sie unter [IOleInPlaceObject::UIDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms693348) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
