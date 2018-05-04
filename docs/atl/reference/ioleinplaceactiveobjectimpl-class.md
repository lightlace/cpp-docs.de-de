---
title: IOleInPlaceActiveObjectImpl Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a0d98b8dd082a09de461452b43b70ddeb9431abe
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ioleinplaceactiveobjectimpl-class"></a>IOleInPlaceActiveObjectImpl-Klasse
Diese Klasse stellt Methoden für die Unterstützung der Kommunikation zwischen einer direkten-Steuerelement und dessen Container.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>
class IOleInPlaceActiveObjectImpl
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IOleInPlaceActiveObjectImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IOleInPlaceActiveObjectImpl::ContextSensitiveHelp](#contextsensitivehelp)|Ermöglicht die kontextbezogene Hilfe. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
|[IOleInPlaceActiveObjectImpl::EnableModeless](#enablemodeless)|Ermöglicht nicht modale Dialogfelder. Gibt die ATL-Implementierung `S_OK`.|  
|[IOleInPlaceActiveObjectImpl::GetWindow](#getwindow)|Ruft ein Fensterhandle ab.|  
|[IOleInPlaceActiveObjectImpl::OnDocWindowActivate](#ondocwindowactivate)|Benachrichtigt das Steuerelement aus, wenn das Dokumentfenster des Containers aktiviert oder deaktiviert wird. Gibt die ATL-Implementierung `S_OK`.|  
|[IOleInPlaceActiveObjectImpl::OnFrameWindowActivate](#onframewindowactivate)|Benachrichtigt das Steuerelement aus, wenn der Container der obersten Ebene Rahmenfenster aktiviert oder deaktiviert ist. Gibt die ATL-Implementierung|  
|[IOleInPlaceActiveObjectImpl::ResizeBorder](#resizeborder)|Benachrichtigt das Steuerelement an, es muss sich um die Größe von Rahmen. Gibt die ATL-Implementierung `S_OK`.|  
|[IOleInPlaceActiveObjectImpl::TranslateAccelerator](#translateaccelerator)|Verarbeitet die im Menü Tastenkombinations-menünachrichten aus dem Container. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
  
  
## <a name="remarks"></a>Hinweise  
 Die [IOleInPlaceActiveObject](http://msdn.microsoft.com/library/windows/desktop/ms691299) Schnittstelle unterstützt die Kommunikation zwischen einer direkten-Steuerelement und dessen Container; für die Kommunikation von des aktiven Status des das Steuerelement und Container, und informiert das Steuerelement muss es die Größe ändern selbst. Klasse `IOleInPlaceActiveObjectImpl` stellt eine Standardimplementierung von `IOleInPlaceActiveObject` und unterstützt **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
 **Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IOleInPlaceActiveObject`  
  
 `IOleInPlaceActiveObjectImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="contextsensitivehelp"></a>  IOleInPlaceActiveObjectImpl::ContextSensitiveHelp  
 Ermöglicht die kontextbezogene Hilfe.  
  
```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleWindow::ContextSensitiveHelp](http://msdn.microsoft.com/library/windows/desktop/ms680059) im Windows SDK.  
  
##  <a name="enablemodeless"></a>  IOleInPlaceActiveObjectImpl::EnableModeless  
 Ermöglicht nicht modale Dialogfelder.  
  
```
HRESULT EnableModeless(BOOL fEnable);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleInPlaceActiveObject::EnableModeless](http://msdn.microsoft.com/library/windows/desktop/ms680115) im Windows SDK.  
  
##  <a name="getwindow"></a>  IOleInPlaceActiveObjectImpl::GetWindow  
 Der Container und Funktionsaufrufe, um das Fensterhandle des Steuerelements zu erhalten.  
  
```
HRESULT GetWindow(HWND* phwnd);
```  
  
### <a name="remarks"></a>Hinweise  
 Einige Container funktioniert nicht mit einem Steuerelement, die fensterlose, selbst wenn es derzeit im Fenstermodus handelt. In ATLs-Implementierung Wenn die **CComControl::m_bWasOnceWindowless** -Datenmember ist **"true"**, gibt die Funktion **E_FAIL**. Andernfalls gilt: Wenn \* *Phwnd* nicht **NULL**, `GetWindow` weist *Phwnd* Datenmember der Steuerelementklasse `m_hWnd` und zurückgibt`S_OK`.  
  
 Finden Sie unter [IOleWindow::GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms687282) im Windows SDK.  
  
##  <a name="ondocwindowactivate"></a>  IOleInPlaceActiveObjectImpl::OnDocWindowActivate  
 Benachrichtigt das Steuerelement aus, wenn das Dokumentfenster des Containers aktiviert oder deaktiviert wird.  
  
```
HRESULT OnDocWindowActivate(BOOL fActivate);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleInPlaceActiveObject:: OnDocWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms687281) im Windows SDK.  
  
##  <a name="onframewindowactivate"></a>  IOleInPlaceActiveObjectImpl::OnFrameWindowActivate  
 Benachrichtigt das Steuerelement aus, wenn der Container der obersten Ebene Rahmenfenster aktiviert oder deaktiviert ist.  
  
```
HRESULT OnFrameWindowActivate(BOOL fActivate);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleInPlaceActiveObject:: OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969) im Windows SDK.  
  
##  <a name="resizeborder"></a>  IOleInPlaceActiveObjectImpl::ResizeBorder  
 Benachrichtigt das Steuerelement an, es muss sich um die Größe von Rahmen.  
  
```
HRESULT ResizeBorder(
    LPRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fFrameWindow);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleInPlaceActiveObject](http://msdn.microsoft.com/library/windows/desktop/ms680053) im Windows SDK.  
  
##  <a name="translateaccelerator"></a>  IOleInPlaceActiveObjectImpl::TranslateAccelerator  
 Verarbeitet die im Menü Tastenkombinations-menünachrichten aus dem Container.  
  
```
HRESULT TranslateAccelerator(LPMSG lpmsg);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode unterstützt die folgenden Rückgabewerte:  
  
 `S_OK` Wenn die Nachricht erfolgreich übersetzt wurden.  
  
 **"S_FALSE"** , wenn die Nachricht nicht übersetzt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleInPlaceActiveObject:: TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)  
 [ActiveX-Steuerelemente Schnittstellen](http://msdn.microsoft.com/library/windows/desktop/ms692724)  
 [Klassenübersicht](../../atl/atl-class-overview.md)
