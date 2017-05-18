---
title: Klasse IOleInPlaceActiveObjectImpl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::EnableModeless
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnDocWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnFrameWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ResizeBorder
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::TranslateAccelerator
dev_langs:
- C++
helpviewer_keywords:
- IOleInPlaceActiveObjectImpl class
- ActiveX controls [C++], communication between container and control
- IOleInPlaceActiveObject, ATL implementation
ms.assetid: 44e6cc6d-a2dc-4187-98e3-73cf0320dea9
caps.latest.revision: 22
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
ms.openlocfilehash: 766ac40bb0a09902914feab1acc54a960261a768
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="ioleinplaceactiveobjectimpl-class"></a>IOleInPlaceActiveObjectImpl-Klasse
Diese Klasse stellt Methoden für die Kommunikation zwischen einem in-Place-Steuerelement und dessen Container unterstützen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>
class IOleInPlaceActiveObjectImpl
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Abgeleitet von die Klasse `IOleInPlaceActiveObjectImpl`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IOleInPlaceActiveObjectImpl::ContextSensitiveHelp](#contextsensitivehelp)|Können kontextbezogene Hilfe an. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.|  
|[IOleInPlaceActiveObjectImpl::EnableModeless](#enablemodeless)|Ermöglicht nicht modale Dialogfelder. Der ATL-Implementierung zurückgegeben `S_OK`.|  
|[IOleInPlaceActiveObjectImpl::GetWindow](#getwindow)|Ruft einen Fenster-Handle ab.|  
|[IOleInPlaceActiveObjectImpl::OnDocWindowActivate](#ondocwindowactivate)|Benachrichtigt das Steuerelement, wenn der Container-Dokumentfenster aktiviert oder deaktiviert wird. Der ATL-Implementierung zurückgegeben `S_OK`.|  
|[IOleInPlaceActiveObjectImpl::OnFrameWindowActivate](#onframewindowactivate)|Benachrichtigt das Steuerelement, wenn der Container der obersten Ebene Rahmenfenster aktiviert oder deaktiviert wird. Der ATL-Implementierung zurückgegeben|  
|[IOleInPlaceActiveObjectImpl::ResizeBorder](#resizeborder)|Benachrichtigt das Steuerelement, benötigt die Rahmen in der Größe anpassen. Der ATL-Implementierung zurückgegeben `S_OK`.|  
|[IOleInPlaceActiveObjectImpl::TranslateAccelerator](#translateaccelerator)|Menü Zugriffstaste Nachrichten aus dem Container verarbeitet. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.|  
  
  
## <a name="remarks"></a>Hinweise  
 Die [IOleInPlaceActiveObject](http://msdn.microsoft.com/library/windows/desktop/ms691299) Schnittstelle unterstützt die Kommunikation zwischen einem in-Place-Steuerelement und dessen Container, z. B. für die Kommunikation der aktiven Status des Steuerelements und Container und informiert das Steuerelement muss seine Größe selbst. Klasse `IOleInPlaceActiveObjectImpl` stellt eine Standardimplementierung der `IOleInPlaceActiveObject` und unterstützt **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
 **Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IOleInPlaceActiveObject`  
  
 `IOleInPlaceActiveObjectImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="contextsensitivehelp"></a>IOleInPlaceActiveObjectImpl::ContextSensitiveHelp  
 Können kontextbezogene Hilfe an.  
  
```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleWindow::ContextSensitiveHelp](http://msdn.microsoft.com/library/windows/desktop/ms680059) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="enablemodeless"></a>IOleInPlaceActiveObjectImpl::EnableModeless  
 Ermöglicht nicht modale Dialogfelder.  
  
```
HRESULT EnableModeless(BOOL fEnable);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleInPlaceActiveObject::EnableModeless](http://msdn.microsoft.com/library/windows/desktop/ms680115) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getwindow"></a>IOleInPlaceActiveObjectImpl::GetWindow  
 Der Container ruft diese Funktion, um das Fensterhandle des Steuerelements abzurufen.  
  
```
HRESULT GetWindow(HWND* phwnd);
```  
  
### <a name="remarks"></a>Hinweise  
 Einige Container funktioniert nicht mit einem Steuerelement, die fensterlose, selbst wenn sie derzeit im Fenstermodus ist. In ATL Implementierung Wenn die **CComControl::m_bWasOnceWindowless** -Datenmember ist **TRUE**, gibt die Funktion **E_FAIL**. Andernfalls gilt: Wenn \* *Phwnd* nicht **NULL**, `GetWindow` weist *Phwnd* der Steuerelementklasse Datenelement `m_hWnd` und gibt `S_OK`.  
  
 Finden Sie unter [IOleWindow::GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms687282) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="ondocwindowactivate"></a>IOleInPlaceActiveObjectImpl::OnDocWindowActivate  
 Benachrichtigt das Steuerelement, wenn der Container-Dokumentfenster aktiviert oder deaktiviert wird.  
  
```
HRESULT OnDocWindowActivate(BOOL fActivate);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleInPlaceActiveObject::OnDocWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms687281) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onframewindowactivate"></a>IOleInPlaceActiveObjectImpl::OnFrameWindowActivate  
 Benachrichtigt das Steuerelement, wenn der Container der obersten Ebene Rahmenfenster aktiviert oder deaktiviert wird.  
  
```
HRESULT OnFrameWindowActivate(BOOL fActivate);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="resizeborder"></a>IOleInPlaceActiveObjectImpl::ResizeBorder  
 Benachrichtigt das Steuerelement, benötigt die Rahmen in der Größe anpassen.  
  
```
HRESULT ResizeBorder(
    LPRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fFrameWindow);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="translateaccelerator"></a>IOleInPlaceActiveObjectImpl::TranslateAccelerator  
 Menü Zugriffstaste Nachrichten aus dem Container verarbeitet.  
  
```
HRESULT TranslateAccelerator(LPMSG lpmsg);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode unterstützt die folgenden Rückgabewerte:  
  
 `S_OK`Wenn die Nachricht erfolgreich übersetzt wurde.  
  
 **S_FALSE** , wenn die Nachricht nicht übersetzt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)  
 [ActiveX-Steuerelemente Schnittstellen](http://msdn.microsoft.com/library/windows/desktop/ms692724)  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

