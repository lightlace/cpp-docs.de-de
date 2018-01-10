---
title: CDialogImpl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDialogImpl
- ATLWIN/ATL::CDialogImpl
- ATLWIN/ATL::Create
- ATLWIN/ATL::DestroyWindow
- ATLWIN/ATL::DoModal
- ATLWIN/ATL::EndDialog
- ATLWIN/ATL::GetDialogProc
- ATLWIN/ATL::MapDialogRect
- ATLWIN/ATL::OnFinalMessage
- ATLWIN/ATL::DialogProc
- ATLWIN/ATL::StartDialogProc
dev_langs: C++
helpviewer_keywords:
- dialog boxes, ATL
- CDialogImpl class
ms.assetid: d430bc7b-8a28-4ad3-9507-277bdd2c2c2e
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ab4bb1e04bd21900cdf8d8122af51547e79aea22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdialogimpl-class"></a>CDialogImpl-Klasse
Diese Klasse stellt Methoden zum Erstellen eines Dialogfelds mit oder ohne Modus.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```  
 
template <class T,  
    class TBase = CWindow>  
    class ATL_NO_VTABLE CDialogImpl : public CDialogImplBaseT<TBase>  
 
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `CDialogImpl`.  
  
 *TBase*  
 Die Basisklasse der neuen Klasse. Die Standardbasisklasse ist [CWindow](../../atl/reference/cwindow-class.md).  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[Erstellen](#create)|Erstellt ein nicht modales Dialogfeld an.|  
|[DestroyWindow](#destroywindow)|Zerstört ein nicht modales Dialogfeld an.|  
|[DoModal](#domodal)|Erstellt ein modales Dialogfeld an.|  
|["EndDialog"](#enddialog)|Zerstört ein modales Dialogfeld an.|  
  
### <a name="cdialogimplbaset-methods"></a>CDialogImplBaseT-Methoden  
  
|||  
|-|-|  
|[GetDialogProc](#getdialogproc)|Gibt die aktuelle für Standarddialogfelder zurück.|  
|[MapDialogRect](#mapdialogrect)|Ordnet die im Dialogfeld Einheiten des angegebenen Rechtecks Bildschirm Einheiten (in Pixel).|  
|[OnFinalMessage](#onfinalmessage)|Wird aufgerufen, nachdem die letzte Meldung erhalten, in der Regel `WM_NCDESTROY`.|  
  
### <a name="static-functions"></a>Statische Funktionen  
  
|||  
|-|-|  
|[DialogProc-Funktion](#dialogproc)|Verarbeitet die Nachrichten gesendet, um das Dialogfeld.|  
|[StartDialogProc](#startdialogproc)|Wird aufgerufen, wenn die erste Nachricht empfangen wird, um Nachrichten gesendet, um das Dialogfeld zu verarbeiten.|  
  
## <a name="remarks"></a>Hinweise  
 Mit `CDialogImpl` können Sie ein Dialogfeld mit oder ohne Modus erstellen. `CDialogImpl`Stellt die für Standarddialogfelder, die die Standard-meldungszuordnung zur Weiterleitung von Nachrichten an die entsprechenden Handler verwendet.  
  
 Basisklassendestruktor **~ CWindowImplRoot** wird sichergestellt, dass das Fenster verlassen wird, vor dem Löschen des Objekts.  
  
 `CDialogImpl`leitet sich von **CDialogImplBaseT**, der wiederum abgeleitet aus **CWindowImplRoot**.  
  
> [!NOTE]
>  Muss Ihre Klasse definiert ein **LEISTE** Member, der angibt, das Dialogfeld Vorlage Ressourcen-ID. ATL-Projekt-Assistent fügt z. B. automatisch die folgende Zeile auf die Klasse:  
  
 [!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/cdialogimpl-class_1.h)]  
  
 auf dem `MyDlg` ist die **Kurzname** in des Assistenten eingegebenen **Namen** Seite.  
  
|Weitere Informationen finden Sie unter|Siehe|  
|--------------------------------|---------|  
|Erstellen von Steuerelementen|[ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md)|  
|Mithilfe der Dialogfelder in ATL|[ATL-Fensterklassen](../../atl/atl-window-classes.md)|  
|ATL-Projekt-Assistent|[Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)|  
|Dialogfelder|[Dialogfelder](http://msdn.microsoft.com/library/windows/desktop/ms632588) und nachfolgenden Themen im Windows SDK|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  
  
##  <a name="create"></a>CDialogImpl::Create  
 Erstellt ein nicht modales Dialogfeld an.  
  
```  
HWND Create(
    HWND hWndParent,  
    LPARAM dwInitParam = NULL );  

HWND Create(
    HWND hWndParent,  
    RECT&, 
    LPARAM dwInitParam = NULL); 
```  
  
### <a name="parameters"></a>Parameter  
 `hWndParent`  
 [in] Das Handle an das Besitzerfenster.  
  
 **RECT &**`rect`  
 [in] Ein [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die Größe und Position im Dialogfelds angibt.  
  
 `dwInitParam`  
 [in] Gibt den Wert zu übergeben, um das Dialogfeld in der **lParam** Parameter von der **WM_INITDIALOG** Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle für das neu erstellte Dialogfeld.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Dialogfeld wird automatisch angefügt, um die `CDialogImpl` Objekt. Rufen Sie zum Erstellen eines modales Dialogfelds [DoModal](#domodal). Die zweite Außerkraftsetzung wird verwendet, nur mit [CComControl](../../atl/reference/ccomcontrol-class.md).  
  
##  <a name="destroywindow"></a>CDialogImpl::DestroyWindow  
 Zerstört ein nicht modales Dialogfeld an.  
  
```  
 
BOOL DestroyWindow();

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** , wenn das Dialogfeld erfolgreich getrennt wurde; andernfalls wurde **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Gibt **"true"** , wenn das Dialogfeld erfolgreich getrennt wurde; andernfalls wurde **"false"**.  
  
##  <a name="dialogproc"></a>CDialogImpl::DialogProc  
 Diese statische Funktion implementiert, die für Standarddialogfelder.  
  
```  
 
static LRESULT CALLBACK DialogProc(
    HWND hWnd,  
    UINT uMsg,  
    WPARAM wParam,  
    LPARAM lParam);

 
```  
  
### <a name="parameters"></a>Parameter  
 `hWnd`  
 [in] Das Handle für das Dialogfeld.  
  
 `uMsg`  
 [in] Die Nachricht gesendet, um das Dialogfeld.  
  
 `wParam`  
 [in] Zusätzliche Meldung-spezifische Informationen.  
  
 `lParam`  
 [in] Zusätzliche Meldung-spezifische Informationen.  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** ist die Nachricht verarbeitet wird; andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 `DialogProc`verwendet die Standard-meldungszuordnung zur Weiterleitung von Nachrichten an die entsprechenden Handler.  
  
 Sie können außer Kraft setzen `DialogProc` angeben ein anderen Mechanismus zum Verarbeiten von Nachrichten.  
  
##  <a name="domodal"></a>CDialogImpl::DoModal  
 Erstellt ein modales Dialogfeld an.  
  
```   
INT_PTR DoModal(  
    HWND hWndParent = ::GetActiveWindow(),   
    LPARAM dwInitParam = NULL); 
```  
  
### <a name="parameters"></a>Parameter  
 `hWndParent`  
 [in] Das Handle an das Besitzerfenster. Der Standardwert ist der Rückgabewert von der [GetActiveWindow](http://msdn.microsoft.com/library/windows/desktop/ms646292) Win32-Funktion.  
  
 `dwInitParam`  
 [in] Gibt den Wert zu übergeben, um das Dialogfeld in der **lParam** Parameter von der **WM_INITDIALOG** Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall den Wert von der `nRetCode` Parameter im Aufruf angegebenen ["EndDialog"](#enddialog). Andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Dialogfeld wird automatisch angefügt, um die `CDialogImpl` Objekt.  
  
 Rufen Sie zum Erstellen eines nicht modalen Dialogfelds [erstellen](#create).  
  
##  <a name="enddialog"></a>CDialogImpl::EndDialog  
 Zerstört ein modales Dialogfeld an.  
  
```   
BOOL EndDialog(int nRetCode); 
```  
  
### <a name="parameters"></a>Parameter  
 `nRetCode`  
 [in] Der Wert von zurückgegeben werden sollen [CDialogImpl::DoModal](#domodal).  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** ist das Dialogfeld getrennt ist, andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 `EndDialog`muss über die Dialogfeldprozedur aufgerufen werden. Nachdem Sie das Dialogfeld zerstört wird, verwendet Windows den Wert der `nRetCode` als Rückgabewert für `DoModal`, der das Dialogfeld erstellt.  
  
> [!NOTE]
>  Rufen Sie nicht `EndDialog` , ein nicht modales Dialogfeld zu zerstören. Rufen Sie [CWindow::DestroyWindow](../../atl/reference/cwindow-class.md#destroywindow) stattdessen.  
  
##  <a name="getdialogproc"></a>CDialogImpl::GetDialogProc  
 Gibt `DialogProc`, die aktuellen für Standarddialogfelder.  
  
```   
virtual WNDPROC GetDialogProc(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Standarddialogfelder.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um das Dialogfeld Verfahren durch eigene ersetzen.  
  
##  <a name="mapdialogrect"></a>CDialogImpl::MapDialogRect  
 Konvertiert (Maps) die Einheiten im Dialogfeld des angegebenen Rechtecks Bildschirm Einheiten (in Pixel).  
  
```   
BOOL MapDialogRect(LPRECT lpRect); 
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf eine `CRect` Objekt oder [RECT](../../mfc/reference/rect-structure1.md) -Struktur, die der Clientkoordinaten des Updates zu erhalten, die dem Aktualisierungsbereich einschließt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Update erfolgreich ausgeführt wird; 0, wenn das Update ein Fehler auftritt. Um erweiterte Fehlerinformationen abzurufen, rufen Sie `GetLastError` auf.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion ersetzt die Koordinaten im angegebenen `RECT` Struktur mit den Koordinaten konvertierte, sodass die Struktur, die zum Erstellen eines Dialogfelds oder positionieren ein Steuerelement in einem Dialogfeld verwendet werden.  
  
##  <a name="onfinalmessage"></a>CDialogImpl::OnFinalMessage  
 Nach dem Empfang der letzten Nachricht aufgerufen (in der Regel `WM_NCDESTROY`).  
  
```   
virtual void OnFinalMessage(HWND hWnd); 
```  
  
### <a name="parameters"></a>Parameter  
 `hWnd`  
 [in] Ein Handle für das Fenster zerstört wird.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass wenn Ihr Objekt auf die fensterzerstörung automatisch gelöscht werden sollen, Sie aufrufen können `delete this;` hier.  
  
##  <a name="startdialogproc"></a>CDialogImpl::StartDialogProc  
 Wenn die erste Nachricht, zum Verarbeiten von Nachrichten gesendet, um das Dialogfeld empfangen wird, nur einmal aufgerufen.  
  
```   
static LRESULT CALLBACK StartDialogProc(
    HWND hWnd,  
    UINT uMsg,  
    WPARAM wParam,  
    LPARAM lParam); 
```  
  
### <a name="parameters"></a>Parameter  
 `hWnd`  
 [in] Das Handle für das Dialogfeld.  
  
 `uMsg`  
 [in] Die Nachricht gesendet, um das Dialogfeld.  
  
 `wParam`  
 [in] Zusätzliche Meldung-spezifische Informationen.  
  
 `lParam`  
 [in] Zusätzliche Meldung-spezifische Informationen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Fensterprozedur.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem ersten Aufruf von `StartDialogProc`, `DialogProc` festgelegt ist, wie eine Dialogfeldprozedur und weitere Aufrufe da ist er.  
  
## <a name="see-also"></a>Siehe auch  
 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)   
 [Klassenübersicht](../../atl/atl-class-overview.md)