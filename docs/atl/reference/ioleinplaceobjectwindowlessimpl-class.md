---
title: Klasse IOleInPlaceObjectWindowlessImpl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IOleInPlaceObjectWindowlessImpl
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
caps.latest.revision: 20
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
ms.openlocfilehash: 06ce03a896c9948bff14b4f91ae48000d07c3edd
ms.lasthandoff: 02/24/2017

---
# <a name="ioleinplaceobjectwindowlessimpl-class"></a>IOleInPlaceObjectWindowlessImpl-Klasse
Diese Klasse implementiert **IUnknown** und bietet Methoden, mit denen ein fensterloses Steuerelement Fensternachrichten empfangen und an Drag & Drop-Vorgängen beteiligt sind.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>
class IOleInPlaceObjectWindowlessImpl
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Abgeleitet von die Klasse `IOleInPlaceObjectWindowlessImpl`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp](#contextsensitivehelp)|Können kontextbezogene Hilfe an. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::GetDropTarget](#getdroptarget)|Stellt die `IDropTarget` Schnittstelle für ein direktes aktiv, fensterlose Objekt, das per Drag & drop unterstützt. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::GetWindow](#getwindow)|Ruft einen Fenster-Handle ab.|  
|[IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate](#inplacedeactivate)|Deaktiviert ein aktives in-Place-Steuerelement.|  
|[IOleInPlaceObjectWindowlessImpl::OnWindowMessage](#onwindowmessage)|Sendet eine Nachricht aus dem Container um ein fensterloses Steuerelement, das in-Place aktiv ist.|  
|[IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo](#reactivateandundo)|Aktiviert ein zuvor deaktivierte Steuerelement. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::SetObjectRects](#setobjectrects)|Gibt an, welcher Teil der in-Place-Steuerelement angezeigt wird.|  
|[IOleInPlaceObjectWindowlessImpl::UIDeactivate](#uideactivate)|Deaktiviert und entfernt die Benutzeroberfläche, die direkte Aktivierung unterstützt.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) Schnittstelle verwaltet die erneute Aktivierung und Deaktivierung des direkten steuert und bestimmt, wie viel des Steuerelements angezeigt werden soll. Die [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304) Schnittstelle ermöglicht ein fensterloses Steuerelement Fensternachrichten empfangen und an Drag & Drop-Vorgängen beteiligt sind. Klasse `IOleInPlaceObjectWindowlessImpl` stellt eine Standardimplementierung der `IOleInPlaceObject` und `IOleInPlaceObjectWindowless` und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
 **Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IOleInPlaceObjectWindowless`  
  
 `IOleInPlaceObjectWindowlessImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="a-namecontextsensitivehelpa--ioleinplaceobjectwindowlessimplcontextsensitivehelp"></a><a name="contextsensitivehelp"></a>IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp  
 Gibt **E_NOTIMPL**.  
  
```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleWindow::ContextSensitiveHelp](http://msdn.microsoft.com/library/windows/desktop/ms680059) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetdroptargeta--ioleinplaceobjectwindowlessimplgetdroptarget"></a><a name="getdroptarget"></a>IOleInPlaceObjectWindowlessImpl::GetDropTarget  
 Gibt **E_NOTIMPL**.  
  
```
HRESULT GetDropTarget(IDropTarget** ppDropTarget);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleInPlaceObjectWindowless::GetDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms678535) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetwindowa--ioleinplaceobjectwindowlessimplgetwindow"></a><a name="getwindow"></a>IOleInPlaceObjectWindowlessImpl::GetWindow  
 Der Container ruft diese Funktion, um das Fensterhandle des Steuerelements abzurufen.  
  
```
HRESULT GetWindow(HWND* phwnd);
```  
  
### <a name="remarks"></a>Hinweise  
 Einige Container funktioniert nicht mit einem Steuerelement, die fensterlose, selbst wenn sie derzeit im Fenstermodus ist. In ATL Implementierung Wenn der Steuerelementklasse Datenmember `m_bWasOnceWindowless` ist **TRUE**, gibt die Funktion **E_FAIL**. Andernfalls gilt: Wenn *Phwnd* nicht **NULL**, `GetWindow` legt \* *Phwnd* in der Steuerelementklasse-Datenmember `m_hWnd` und gibt `S_OK`.  
  
 Finden Sie unter [IOleWindow::GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms687282) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameinplacedeactivatea--ioleinplaceobjectwindowlessimplinplacedeactivate"></a><a name="inplacedeactivate"></a>IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate  
 Wird von der Container So deaktivieren Sie ein aktives in-Place-Steuerelement aufgerufen.  
  
```
HRESULT InPlaceDeactivate(HWND* phwnd);
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt eine vollständige oder teilweise Deaktivierung je nach Zustand des Steuerelements. Bei Bedarf die Steuerelement-Benutzeroberfläche wird deaktiviert und das Steuerelementfenster ggf. zerstört. Der Container wird benachrichtigt, dass das Steuerelement an nicht mehr aktiv ist. Die **IOleInPlaceUIWindow** -Schnittstelle, die vom Container verwendet werden, zum Aushandeln von Menüs und Rahmen der Speicherplatz wird freigegeben.  
  
 Finden Sie unter [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameonwindowmessagea--ioleinplaceobjectwindowlessimplonwindowmessage"></a><a name="onwindowmessage"></a>IOleInPlaceObjectWindowlessImpl::OnWindowMessage  
 Sendet eine Nachricht von einem Container für ein fensterloses Steuerelement, das in-Place aktiv ist.  
  
```
HRESULT OnWindowMessage(
    UINT msg,
    WPARAM WParam,
    LPARAM LParam,
    LRESULT plResultParam);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleInPlaceObjectWindowless::OnWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms693783) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namereactivateandundoa--ioleinplaceobjectwindowlessimplreactivateandundo"></a><a name="reactivateandundo"></a>IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo  
 Gibt **E_NOTIMPL**.  
  
```
HRESULT ReactivateAndUndo();
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleInPlaceObject::ReactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms691372) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetobjectrectsa--ioleinplaceobjectwindowlessimplsetobjectrects"></a><a name="setobjectrects"></a>IOleInPlaceObjectWindowlessImpl::SetObjectRects  
 Wird von der Container informiert das Steuerelement, das die Größe und/oder die Position geändert hat.  
  
```
HRESULT SetObjectRects(LPCRECT prcPos, LPCRECT prcClip);
```  
  
### <a name="remarks"></a>Hinweise  
 Aktualisiert das Steuerelement `m_rcPos` Datenmember und die Steuerelementanzeige. Es wird nur der Teil des Steuerelements, das die Clip-Bereich überschneidet angezeigt. Wenn die Anzeige eines Steuerelements wurde zuvor abgeschnitten, aber das Clipping entfernt wurde, kann diese Funktion aufgerufen werden, um eine vollständige Ansicht des Steuerelements neu zu zeichnen.  
  
 Finden Sie unter [IOleInPlaceObject::SetObjectRects](http://msdn.microsoft.com/library/windows/desktop/ms683767) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameuideactivatea--ioleinplaceobjectwindowlessimpluideactivate"></a><a name="uideactivate"></a>IOleInPlaceObjectWindowlessImpl::UIDeactivate  
 Deaktiviert und entfernt die Steuerelement-Benutzeroberfläche, die direkte Aktivierung unterstützt.  
  
```
HRESULT UIDeactivate();
```  
  
### <a name="remarks"></a>Hinweise  
 Legt die Control-Klasse Datenmember `m_bUIActive` auf **FALSE**. Die ATL-Implementierung dieser Funktion immer gibt `S_OK`.  
  
 Finden Sie unter [IOleInPlaceObject::UIDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms693348) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

