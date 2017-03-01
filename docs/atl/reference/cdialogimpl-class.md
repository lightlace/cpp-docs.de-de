---
title: CDialogImpl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDialogImpl
- ATL.CDialogImpl
- ATL::CDialogImpl
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes, ATL
- CDialogImpl class
ms.assetid: d430bc7b-8a28-4ad3-9507-277bdd2c2c2e
caps.latest.revision: 25
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
ms.openlocfilehash: 732227ef8566ce5e2985a3e65a1153a130df6b20
ms.lasthandoff: 02/24/2017

---
# <a name="cdialogimpl-class"></a>CDialogImpl-Klasse
Diese Klasse stellt Methoden zum Erstellen eines Dialogfelds mit oder ohne Modus.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```  
 
template <class T,  
    class TBase = CWindow>  
    class ATL_NO_VTABLE CDialogImpl : public CDialogImplBaseT<TBase>  
 
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Abgeleitet von die Klasse `CDialogImpl`.  
  
 *TBase*  
 Die Basisklasse der neuen Klasse. Die Standardbasisklasse ist [CWindow](../../atl/reference/cwindow-class.md).  
  
## <a name="members"></a>Mitglieder  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[Erstellen](#create)|Erstellt ein modales Dialogfeld.|  
|[DestroyWindow](#destroywindow)|Zerstört ein nicht modales Dialogfeld.|  
|[DoModal](#domodal)|Erstellt ein modales Dialogfeld an.|  
|[EndDialog](#enddialog)|Zerstört ein modales Dialogfeld an.|  
  
### <a name="cdialogimplbaset-methods"></a>CDialogImplBaseT-Methoden  
  
|||  
|-|-|  
|[GetDialogProc](#getdialogproc)|Gibt die aktuelle Prozedur zurück.|  
|[MapDialogRect](#mapdialogrect)|Ordnet die Dialogfeld-Einheiten des angegebenen Rechtecks Bildschirm Einheiten (Pixel).|  
|[OnFinalMessage](#onfinalmessage)|Aufgerufen, nachdem die letzte Meldung erhalten, in der Regel `WM_NCDESTROY`.|  
  
### <a name="static-functions"></a>Statische Funktionen  
  
|||  
|-|-|  
|[DialogProc](#dialogproc)|Verarbeitet die Nachrichten an das Dialogfeld gesendet.|  
|[StartDialogProc](#startdialogproc)|Wird aufgerufen, wenn die erste Nachricht empfangen wird, zum Verarbeiten von Nachrichten an das Dialogfeld gesendet.|  
  
## <a name="remarks"></a>Hinweise  
 Mit `CDialogImpl` können Sie ein Dialogfeld mit oder ohne Modus erstellen. `CDialogImpl`Stellt die Prozedur für Standarddialogfelder, die die Standardkurve für die Nachricht verwendet wird, um Nachrichten an die entsprechenden Handler zu leiten.  
  
 Basisklassendestruktor **~ CWindowImplRoot** wird sichergestellt, dass das Fenster verschwunden ist, vor dem Löschen des Objekts.  
  
 `CDialogImpl`leitet sich von **CDialogImplBaseT**, die wiederum abgeleitet wird, von **CWindowImplRoot**.  
  
> [!NOTE]
>  Muss Ihre Klasse definiert ein **IDD** Member, der die Dialogfeld Vorlage die Ressourcen-ID angibt. ATL-Projekt-Assistenten fügt z. B. die folgende Zeile automatisch zu Ihrer Klasse hinzu:  
  
 [!code-cpp[NVC_ATL_Windowing&#41;](../../atl/codesnippet/cpp/cdialogimpl-class_1.h)]  
  
 wobei `MyDlg` ist die **Kurznamen** in den Assistenten eingegeben **Namen** Seite.  
  
|Weitere Informationen finden Sie unter|Siehe|  
|--------------------------------|---------|  
|Erstellen von Steuerelementen|[ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md)|  
|Mithilfe der Dialogfelder in ATL|[ATL-Fensterklassen](../../atl/atl-window-classes.md)|  
|ATL-Projekt-Assistent|[Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)|  
|Dialogfelder|[Dialogfelder](http://msdn.microsoft.com/library/windows/desktop/ms632588) und nachfolgenden Themen in der[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  
  
##  <a name="a-namecreatea--cdialogimplcreate"></a><a name="create"></a>CDialogImpl::Create  
 Erstellt ein modales Dialogfeld.  
  
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
 [in] Ein [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die Größe und Position des Dialogfelds angibt.  
  
 `dwInitParam`  
 [in] Gibt den Wert der Übergabe an das Dialogfeld in der **lParam** Parameter von der **WM_INITDIALOG** Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle für das neu erstellte Dialogfeld.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Dialogfeld wird automatisch angefügt, um die `CDialogImpl` Objekt. Rufen Sie zum Erstellen eines modalen Dialogfelds [DoModal](#domodal). Die zweite Außerkraftsetzung wird verwendet, nur mit [CComControl](../../atl/reference/ccomcontrol-class.md).  
  
##  <a name="a-namedestroywindowa--cdialogimpldestroywindow"></a><a name="destroywindow"></a>CDialogImpl::DestroyWindow  
 Zerstört ein nicht modales Dialogfeld.  
  
```  
 
BOOL DestroyWindow();

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** , wenn das Dialogfeld erfolgreich getrennt wurde; andernfalls wurde **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Gibt **TRUE** , wenn das Dialogfeld erfolgreich getrennt wurde; andernfalls wurde **FALSE**.  
  
##  <a name="a-namedialogproca--cdialogimpldialogproc"></a><a name="dialogproc"></a>CDialogImpl::DialogProc  
 Die statische Funktion implementiert die Prozedur.  
  
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
 [in] Die Nachricht an das Dialogfeld gesendet.  
  
 `wParam`  
 [in] Zusätzliche Message-spezifische Informationen.  
  
 `lParam`  
 [in] Zusätzliche Message-spezifische Informationen.  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** ist die Nachricht verarbeitet wird; andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 `DialogProc`verwendet die Standard-meldungszuordnung, um Nachrichten an die entsprechenden Handler zu leiten.  
  
 Sie können außer Kraft setzen `DialogProc` unterschiedliche Mechanismen für die Verarbeitung von Nachrichten angeben.  
  
##  <a name="a-namedomodala--cdialogimpldomodal"></a><a name="domodal"></a>CDialogImpl::DoModal  
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
 [in] Gibt den Wert der Übergabe an das Dialogfeld in der **lParam** Parameter von der **WM_INITDIALOG** Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall den Wert der `nRetCode` Parameter im Aufruf angegeben [EndDialog](#enddialog). Andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Dialogfeld wird automatisch angefügt, um die `CDialogImpl` Objekt.  
  
 Rufen Sie zum Erstellen eines nicht modalen Dialogfelds [erstellen](#create).  
  
##  <a name="a-nameenddialoga--cdialogimplenddialog"></a><a name="enddialog"></a>CDialogImpl::EndDialog  
 Zerstört ein modales Dialogfeld an.  
  
```   
BOOL EndDialog(int nRetCode); 
```  
  
### <a name="parameters"></a>Parameter  
 `nRetCode`  
 [in] Der Wert von zurückgegeben werden [CDialogImpl::DoModal](#domodal).  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** ist das Dialogfeld zerstört, andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 `EndDialog`muss über die Dialogfeldprozedur aufgerufen werden. Nachdem Sie das Dialogfeld zerstört wird, verwendet Windows den Wert der `nRetCode` als Rückgabewert für `DoModal`, der das Dialogfeld erstellt.  
  
> [!NOTE]
>  Rufen Sie nicht `EndDialog` , ein nicht modales Dialogfeld zu zerstören. Rufen Sie [CWindow::DestroyWindow](../../atl/reference/cwindow-class.md#destroywindow) stattdessen.  
  
##  <a name="a-namegetdialogproca--cdialogimplgetdialogproc"></a><a name="getdialogproc"></a>CDialogImpl::GetDialogProc  
 Gibt `DialogProc`, der aktuellen Prozedur.  
  
```   
virtual WNDPROC GetDialogProc(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Prozedur.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um das Dialogfeld Verfahren durch Ihren eigenen ersetzen.  
  
##  <a name="a-namemapdialogrecta--cdialogimplmapdialogrect"></a><a name="mapdialogrect"></a>CDialogImpl::MapDialogRect  
 Konvertiert (Maps), die im Dialogfeld Einheiten des angegebenen Rechtecks Bildschirm Einheiten (Pixel).  
  
```   
BOOL MapDialogRect(LPRECT lpRect); 
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf eine `CRect` Objekt oder [RECT](../../mfc/reference/rect-structure1.md) -Struktur, die die Clientkoordinaten des Updates zu erhalten, die den Aktualisierungsbereich einschließt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Update erfolgreich ist; 0, wenn die Aktualisierung fehlschlägt. Um erweiterte Fehlerinformationen abzurufen, rufen Sie `GetLastError` auf.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion ersetzt die Koordinaten in der angegebenen `RECT` Struktur mit den Koordinaten konvertierten, sodass die Struktur, die zum Erstellen eines Dialogfelds oder Positionieren Sie ein Steuerelement in einem Dialogfeld verwendet werden.  
  
##  <a name="a-nameonfinalmessagea--cdialogimplonfinalmessage"></a><a name="onfinalmessage"></a>CDialogImpl::OnFinalMessage  
 Nach dem Empfang der letzten Nachricht aufgerufen (in der Regel `WM_NCDESTROY`).  
  
```   
virtual void OnFinalMessage(HWND hWnd); 
```  
  
### <a name="parameters"></a>Parameter  
 `hWnd`  
 [in] Ein Handle für das Fenster zerstört wird.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, wenn das Objekt nach dem Zerstören automatisch gelöscht werden sollen, können Sie aufrufen `delete this;` hier.  
  
##  <a name="a-namestartdialogproca--cdialogimplstartdialogproc"></a><a name="startdialogproc"></a>CDialogImpl::StartDialogProc  
 Wenn die erste Nachricht, zum Verarbeiten von Nachrichten an das Dialogfeld gesendet empfangen wird, nur einmal aufgerufen.  
  
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
 [in] Die Nachricht an das Dialogfeld gesendet.  
  
 `wParam`  
 [in] Zusätzliche Message-spezifische Informationen.  
  
 `lParam`  
 [in] Zusätzliche Message-spezifische Informationen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Fensterprozedur.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem ersten Aufruf von `StartDialogProc`, `DialogProc` festgelegt ist, wie eine Dialogfeldprozedur und weitere Aufrufe vorhanden.  
  
## <a name="see-also"></a>Siehe auch  
 [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
