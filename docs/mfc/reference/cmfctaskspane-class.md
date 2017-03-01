---
title: Klasse CMFCTasksPane | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTasksPane
dev_langs:
- C++
helpviewer_keywords:
- CMFCTasksPane class
ms.assetid: b456328e-2525-4642-b78b-9edd1a1a7d3f
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
ms.openlocfilehash: 2eb41c24b60bcaea7eadc361c23d5c2273217919
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctaskspane-class"></a>CMFCTasksPane-Klasse
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Die `CMFCTasksPane`-Klasse implementiert eine Liste anklickbarer Elemente (Aufgaben).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCTasksPane : public CDockablePane  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCTasksPane::CMFCTasksPane](#cmfctaskspane)|Erstellt ein `CMFCTasksPane`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Cmfctaskspane:: addgroup](#addgroup)|Fügt dem Aufgabenbereich-Steuerelement eine neue Gruppe von Aufgaben hinzu.|  
|[Cmfctaskspane:: AddLabel](#addlabel)|Fügt der angegebenen Aufgabengruppe eine neue statische Bezeichnung hinzu.|  
|[Cmfctaskspane:: Addmrufileslist](#addmrufileslist)|Fügt Aufgaben anhand einer Dateiliste zuletzt verwendeter Aufgaben in einer Gruppe hinzu.|  
|[CMFCTasksPane::AddPage](#addpage)|Fügt dem Aufgabenbereich eine neue Seite hinzu.|  
|[CMFCTasksPane::AddSeparator](#addseparator)||  
|[Cmfctaskspane:: Addtask](#addtask)|Fügt der angegebenen Aufgabengruppe eine neue Aufgabe hinzu.|  
|[CMFCTasksPane::AddWindow](#addwindow)|Fügt dem Aufgabenbereich ein untergeordnetes Fenster hinzu.|  
|[CMFCTasksPane::CollapseAllGroups](#collapseallgroups)||  
|[CMFCTasksPane::CollapseGroup](#collapsegroup)|Reduziert eine Gruppe programmgesteuert.|  
|[CMFCTasksPane::CreateDefaultMiniframe](#createdefaultminiframe)|(Überschreibt [cpane:: Createdefaultminiframe](../../mfc/reference/cpane-class.md#createdefaultminiframe).)|  
|[CMFCTasksPane::CreateMenu](#createmenu)|Aufgerufen, um ein Menü zum Erstellen der **andere Aufgabenbereiche** -Schaltfläche.|  
|[CMFCTasksPane::EnableAnimation](#enableanimation)|Aktiviert oder deaktiviert die Animation beim Reduzieren oder Erweitern von Aufgabengruppen.|  
|[Cmfctaskspane:: Enablegroupcollapse](#enablegroupcollapse)|Gibt an, ob Aufgabengruppen reduziert werden können.|  
|[CMFCTasksPane::EnableHistoryMenuButtons](#enablehistorymenubuttons)|Aktiviert oder deaktiviert die Dropdown-Menüs in **Weiter** und **vorherige** Navigationsschaltflächen.|  
|[CMFCTasksPane::EnableNavigationToolbar](#enablenavigationtoolbar)|Aktiviert oder deaktiviert die Navigationssymbolleiste.|  
|[CMFCTasksPane::EnableOffsetCustomControls](#enableoffsetcustomcontrols)||  
|[CMFCTasksPane::EnableScrollButtons](#enablescrollbuttons)|Aktiviert die Schaltflächen für Bildlauf statt der Bildlaufleiste.|  
|[CMFCTasksPane::EnableWrapLabels](#enablewraplabels)|Aktiviert oder deaktiviert den Wortumbruch für Bezeichnungen.|  
|[CMFCTasksPane::EnableWrapTasks](#enablewraptasks)|Aktiviert oder deaktiviert den Wortumbruch für Aufgaben.|  
|[CMFCTasksPane::GetActivePage](#getactivepage)|Gibt den nullbasierten Index für die aktive Seite zurück.|  
|[CMFCTasksPane::GetGroupCaptionHeight](#getgroupcaptionheight)|Gibt die Höhe der Gruppenbeschriftungen zurück.|  
|[CMFCTasksPane::GetGroupCaptionHorzOffset](#getgroupcaptionhorzoffset)|Gibt den aktuellen Offset einer Gruppenbeschriftung vom linken und rechten Rand des Aufgabenbereichs zurück.|  
|[CMFCTasksPane::GetGroupCaptionVertOffset](#getgroupcaptionvertoffset)|Gibt den aktuellen Offset einer Gruppenbeschriftung vom oberen und unteren Rand des Aufgabenbereichs zurück.|  
|[CMFCTasksPane::GetGroupCount](#getgroupcount)|Ruft die Gesamtanzahl von Gruppen zurück.|  
|[CMFCTasksPane::GetGroupLocation](#getgrouplocation)|Gibt den internen Gruppenindex für eine angegebene Gruppe zurück.|  
|[CMFCTasksPane::GetGroupVertOffset](#getgroupvertoffset)|Gibt den vertikalen Offset einer Gruppe zurück.|  
|[CMFCTasksPane::GetHorzMargin](#gethorzmargin)|Gibt den horizontalen Abstand zwischen einem Aufgabenbereich und den Rändern des Clientbereichs zurück.|  
|[CMFCTasksPane::GetNextPages](#getnextpages)||  
|[CMFCTasksPane::GetPageByGroup](#getpagebygroup)|Ruft den Seitenindex für eine angegebene Gruppe ab.|  
|[CMFCTasksPane::GetPagesCount](#getpagescount)|Gibt die Anzahl der Seiten zurück.|  
|[CMFCTasksPane::GetPreviousPages](#getpreviouspages)||  
|[CMFCTasksPane::GetScrollBarCtrl](#getscrollbarctrl)|(Überschreibt [CWnd:: Getscrollbarctrl](../../mfc/reference/cwnd-class.md#getscrollbarctrl).)|  
|[CMFCTasksPane::GetTask](#gettask)|Ruft eine Aufgabe ab.|  
|[CMFCTasksPane::GetTaskCount](#gettaskcount)|Gibt die Anzahl von Aufgabenelementen in einer angegebenen Gruppe zurück.|  
|[CMFCTasksPane::GetTaskGroup](#gettaskgroup)|Gibt eine Aufgabengruppe für einen angegebenen Gruppenindex zurück.|  
|[CMFCTasksPane::GetTaskLocation](#gettasklocation)|Gibt die Gruppe und den Index für eine angegebene Aufgabe zurück.|  
|[CMFCTasksPane::GetTasksHorzOffset](#gettaskshorzoffset)|Gibt den horizontale Offset von Aufgaben vom linken und rechten Rand der übergeordneten Gruppen zurück.|  
|[CMFCTasksPane::GetTasksIconHorzOffset](#gettasksiconhorzoffset)||  
|[CMFCTasksPane::GetTasksIconVertOffset](#gettasksiconvertoffset)||  
|[CMFCTasksPane::GetVertMargin](#getvertmargin)|Gibt den horizontalen Abstand zwischen einem Aufgabenbereich und den Rändern des Clientbereichs zurück.|  
|[CMFCTasksPane::IsAccessibilityCompatible](#isaccessibilitycompatible)|(Überschreibt `CDockablePane::IsAccessibilityCompatible`.)|  
|[CMFCTasksPane::IsAnimationEnabled](#isanimationenabled)|Gibt an, ob die Animation aktiviert ist.|  
|[CMFCTasksPane::IsBackButtonEnabled](#isbackbuttonenabled)|Gibt an, ob die Zurück-Schaltfläche aktiviert ist.|  
|[CMFCTasksPane::IsForwardButtonEnabled](#isforwardbuttonenabled)|Gibt an, ob die Weiter-Schaltfläche aktiviert ist.|  
|[CMFCTasksPane::IsGroupCollapseEnabled](#isgroupcollapseenabled)||  
|[CMFCTasksPane::IsHistoryMenuButtonsEnabled](#ishistorymenubuttonsenabled)|Gibt an, ob die **Weiter** und **vorherige** Navigationsschaltflächen Dropdown-Menüs haben.|  
|[CMFCTasksPane::IsNavigationToolbarEnabled](#isnavigationtoolbarenabled)|Gibt an, ob die Navigationssymbolleiste aktiviert ist.|  
|[CMFCTasksPane::IsToolBox](#istoolbox)||  
|[CMFCTasksPane::IsWrapLabelsEnabled](#iswraplabelsenabled)|Gibt an, ob der Aufgabenbereich Wörter in Bezeichnungen umbricht.|  
|[CMFCTasksPane::IsWrapTasksEnabled](#iswraptasksenabled)|Gibt an, ob der Aufgabenbereich Wörter in Aufgaben umbricht.|  
|[CMFCTasksPane::LoadState](#loadstate)|(Überschreibt [CDockablePane:: LoadState](http://msdn.microsoft.com/en-us/96110136-4f46-4764-8a76-3b4abaf77917).)|  
|[CMFCTasksPane::OnCancel](#oncancel)||  
|[CMFCTasksPane::OnClickTask](#onclicktask)|Wird vom Framework aufgerufen, wenn der Benutzer auf ein Element im Aufgabenbereich klickt.|  
|[CMFCTasksPane::OnOK](#onok)||  
|[CMFCTasksPane::OnPressBackButton](#onpressbackbutton)|Wird vom Framework aufgerufen, wenn der Benutzer auf die Zurück-Schaltfläche klickt.|  
|[CMFCTasksPane::OnPressForwardButton](#onpressforwardbutton)|Wird vom Framework aufgerufen, wenn der Benutzer auf die Navigationsschaltfläche Weiter klickt.|  
|[CMFCTasksPane::OnPressHomeButton](#onpresshomebutton)|Wird vom Framework aufgerufen, wenn der Benutzer auf die Navigationsschaltfläche Startseite klickt.|  
|[CMFCTasksPane::OnPressOtherButton](#onpressotherbutton)||  
|[CMFCTasksPane::OnSetAccData](#onsetaccdata)|(Überschreibt [cbasepane:: Onsetaccdata](../../mfc/reference/cbasepane-class.md#onsetaccdata).)|  
|[CMFCTasksPane::OnUpdateCmdUI](#onupdatecmdui)|(Überschreibt [CDockablePane:: OnUpdateCmdUI](http://msdn.microsoft.com/en-us/5dd61606-1c12-40d4-b024-f3839aa5e2e0).)|  
|[CMFCTasksPane::PreTranslateMessage](#pretranslatemessage)|(Überschreibt [CDockablePane:: PreTranslateMessage](http://msdn.microsoft.com/en-us/49a242cc-b158-400e-9e01-0345ec9c3ffd).)|  
|[CMFCTasksPane::RecalcLayout](#recalclayout)|(Überschreibt [cpane:: RecalcLayout](../../mfc/reference/cpane-class.md#recalclayout).)|  
|[CMFCTasksPane::RemoveAllGroups](#removeallgroups)|Entfernt alle Gruppen auf der angegebenen Seite.|  
|[CMFCTasksPane::RemoveAllPages](#removeallpages)|Entfernt alle Seiten aus dem Aufgabenbereich mit Ausnahme der Standardseite (erste).|  
|[CMFCTasksPane::RemoveAllTasks](#removealltasks)|Entfernt alle Aufgaben aus der Gruppe.|  
|[CMFCTasksPane::RemoveGroup](#removegroup)|Entfernt eine Gruppe.|  
|[CMFCTasksPane::RemovePage](#removepage)|Entfernt eine angegebene Seite aus dem Aufgabenbereich.|  
|[CMFCTasksPane::RemoveTask](#removetask)|Entfernt eine Aufgabe aus einer Aufgabengruppe.|  
|[CMFCTasksPane::SaveState](#savestate)|(Überschreibt [CDockablePane:: SaveState](http://msdn.microsoft.com/en-us/c5c24249-8d0d-46cb-96d9-9f5c6dc191db).)|  
|[CMFCTasksPane::Serialize](#serialize)|(Überschreibt [CDockablePane:: SaveState](http://msdn.microsoft.com/en-us/09787e59-e446-4e76-894b-206d303dcfd6).)|  
|[CMFCTasksPane::SetActivePage](#setactivepage)|Aktiviert eine angegebene Seite im Aufgabenbereich.|  
|[CMFCTasksPane::SetCaption](#setcaption)|Legt den Beschriftungsnamen eines Aufgabenbereichs fest.|  
|[CMFCTasksPane::SetGroupCaptionHeight](#setgroupcaptionheight)|Legt die Höhe einer Gruppenbeschriftung fest.|  
|[CMFCTasksPane::SetGroupCaptionHorzOffset](#setgroupcaptionhorzoffset)|Legt den horizontalen Offset einer Gruppenbeschriftung fest.|  
|[CMFCTasksPane::SetGroupCaptionVertOffset](#setgroupcaptionvertoffset)|Legt den vertikalen Offset einer Gruppenbeschriftung fest.|  
|[CMFCTasksPane::SetGroupName](#setgroupname)|Legt einen Gruppennamen fest.|  
|[CMFCTasksPane::SetGroupTextColor](#setgrouptextcolor)|Legt die Textfarbe für eine Gruppenbeschriftung fest.|  
|[CMFCTasksPane::SetGroupVertOffset](#setgroupvertoffset)|Legt den vertikalen Offset für eine Gruppe fest.|  
|[CMFCTasksPane::SetHorzMargin](#sethorzmargin)|Legt den horizontalen Abstand zwischen einem Aufgabenbereich und den Rändern des Clientbereichs fest.|  
|[CMFCTasksPane::SetIconsList](#seticonslist)|Legt die den Aufgaben zugeordnete Bilderliste fest.|  
|[CMFCTasksPane::SetPageCaption](#setpagecaption)|Legt den Beschriftungstext für eine Aufgabenbereichsseite fest.|  
|[CMFCTasksPane::SetTaskName](#settaskname)|Legt den Namen für eine Aufgabe fest.|  
|[CMFCTasksPane::SetTasksIconHorzOffset](#settasksiconhorzoffset)||  
|[CMFCTasksPane::SetTasksIconVertOffset](#settasksiconvertoffset)||  
|[CMFCTasksPane::SetTaskTextColor](#settasktextcolor)|Legt die Textfarbe für eine Aufgabe fest.|  
|[CMFCTasksPane::SetTasksHorzOffset](#settaskshorzoffset)|Legt den horizontale Offset von Aufgaben vom linken und rechten Rand der übergeordneten Gruppen fest.|  
|[CMFCTasksPane::SetVertMargin](#setvertmargin)|Legt den vertikalen Abstand zwischen einem Aufgabenbereich und den Rändern des Clientbereichs fest.|  
|[CMFCTasksPane::SetWindowHeight](#setwindowheight)|Legt die Höhe eines Fensters fest.|  
|[CMFCTasksPane::ShowCommandMessageString](#showcommandmessagestring)||  
|[CMFCTasksPane::ShowTask](#showtask)|Blendet eine Aufgabe ein oder aus.|  
|[CMFCTasksPane::ShowTaskByCmdId](#showtaskbycmdid)|Blendet eine Aufgabe basierend auf der Befehls-ID ein oder aus.|  
|[CMFCTasksPane::Update](#update)|Aktualisiert die GUI-Elemente, die zu einem Aufgabenbereich gehören.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCTasksPane::OnActivateTasksPanePage](#onactivatetaskspanepage)|Wird vom Framework aufgerufen, wenn eine neue Aufgabenbereichsseite aktiviert wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCTasksPane`-Klasse implementiert folgende Funktionen:  
  
-   Elemente können gruppiert werden und jede Elementgruppierung kann eine zugeordnete Beschriftung besitzen.  
  
-   Elementgruppierungen können reduzierte oder erweitert werden.  
  
-   Jedem Element im Aufgabenbereich kann ein Symbol zugewiesen werden.  
  
-   Einzelnen Elementen kann eine Befehls-ID zugeordnet werden, die ausgeführt wird, wenn ein Benutzer auf das Element klickt. Beim Klicken wird die `WM_COMMAND`-Nachricht an den Besitzer des Aufgabenbereich-Steuerelements gesendet.  
  
 Befolgen Sie folgende Schritte, um das `CMFCTasksPane`-Steuerelement in Ihrer Anwendung zu verwenden:  
  
1.  Betten Sie ein `CMFCTasksPane`-Objekt in die Hauptframe-Fensterklasse ein.  
  
2.  Rufen Sie bei der Verarbeitung der `WM_CREATE`-Meldung die `Create`-Methode auf. Sie können reguläre [CControlBar](../../mfc/reference/ccontrolbar-class.md) Formate. Weitere Informationen finden Sie unter `CControlBar::Create`.  
  
3.  Rufen Sie die [cmfctaskspane:: addgroup](#addgroup) Methode, um verschiedene Gruppen hinzuzufügen.  
  
4.  Rufen Sie die [cmfctaskspane:: Addtask](#addtask), [cmfctaskspane:: AddLabel](#addlabel) oder [cmfctaskspane:: Addmrufileslist](#addmrufileslist) Memberfunktionen zum Hinzufügen neuer Elemente (Aufgaben) zu jeder Gruppe.  
  
5.  Rufen Sie [cmfctaskspane:: Enablegroupcollapse](#enablegroupcollapse) an, ob Elementgruppen reduziert werden können.  
  
 Die folgende Abbildung zeigt ein typisches Aufgabenbereich-Steuerelement. Die erste Gruppe ist ein *besondere* Gruppe und die Beschriftung weist eine dunklere Farbe. Die dritte Gruppe wird reduziert. Die letzte Gruppe orientiert sich am unteren Rand des Aufgabenbereichs und besitzt keine Beschriftung und die letzte Aufgabe in der Gruppe ist eine einfache Beschriftung:  
  
 ![Beispiel für den Aufgabenbereich](../../mfc/reference/media/nexttaskpane.png "Nexttaskpane")  
  
 Sie können die Darstellung des Aufgabenbereichs anpassen, indem Sie verschiedene Ränder und Offsets anpassen. Die folgende Abbildung verdeutlicht die Bedeutung dieser Variablen:  
  
 ![Benutzerdefinierte Aufgabengruppe](../../mfc/reference/media/nexttaskgrpcustom.png "Nexttaskgrpcustom")  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen eines `CMFCTasksPane`-Objekts, und die Verwendung verschiedener Methoden in der `CMFCTasksPane`-Klasse. Im Beispiel wird veranschaulicht, wie das Reduzieren von Aufgabengruppen aktivieren, aktivieren Sie das Dropdown-Menüs auf die **Weiter** und **vorherige** Navigationsschaltflächen, aktivieren Sie die Bildlaufschaltflächen statt einer Bildlaufleiste, aktivieren Sie das Wort Wrapper für den Text in Bezeichnungen, legen Sie den Beschriftungsnamen des Aufgabenbereichs, legen Sie die Textfarbe für eine gruppenbeschriftung und legen Sie die horizontale und vertikale Ränder.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#28;](../../mfc/reference/codesnippet/cpp/cmfctaskspane-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 `CMFCTasksPane`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxTasksPane.h  
  
##  <a name="a-nameaddgroupa--cmfctaskspaneaddgroup"></a><a name="addgroup"></a>Cmfctaskspane:: addgroup  
 Fügt dem Aufgabenbereich-Steuerelement eine neue Gruppe von Aufgaben hinzu.  
  
```  
int AddGroup(
    int nPageIdx,  
    LPCTSTR lpszGroupName,  
    BOOL bBottomLocation = FALSE,  
    BOOL bSpecial = FALSE,  
    HICON hIcon = NULL);

 
int AddGroup(
    LPCTSTR lpszGroupName,  
    BOOL bBottomLocation = FALSE,  
    BOOL bSpecial = FALSE,  
    HICON hIcon = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nPageIdx`  
 Gibt den nullbasierten Seitenindex.  
  
 [in] `lpszGroupName`  
 Gibt den Gruppennamen.  
  
 [in] `bBottomLocation`  
 `TRUE`So erstellen Sie die Gruppe am unteren Rand der Aufgabenbereich-Steuerelement; andernfalls `FALSE`.  
  
 [in] `bSpecial`  
 `TRUE`um dieser Gruppe als Markieren einer *besondere* , andernfalls `FALSE`. Weitere Informationen zu speziellen Gruppen, finden Sie im Abschnitt Hinweise der `CMFCTasksPane`.  
  
 [in] `hIcon`  
 Gibt an, welches Symbol in der gruppenbeschriftung angezeigt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index der Gruppe in der internen Liste von Gruppen, die die-Klasse verwaltet.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Erstellen einer Gruppe von Aufgaben und das Steuerelement für den Aufgabenbereich dieser Gruppe hinzu.  
  
 Das Framework zeigt Aufgabengruppen am oberen Rand der Aufgabenbereich-Steuerelement oder am unteren Rand an. Das Framework kann nur eine Gruppe im unteren Bereich anzeigen. Diese Gruppe muss zuletzt hinzugefügt werden.  
  
##  <a name="a-nameaddlabela--cmfctaskspaneaddlabel"></a><a name="addlabel"></a>Cmfctaskspane:: AddLabel  
 Der angegebenen Aufgabengruppe hinzugefügt eine Bezeichnung.  
  
```  
int AddLabel(
    int nGroup,  
    LPCTSTR lpszLabelName,  
    int nTaskIcon = -1,  
    BOOL bIsBold = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nGroup`  
 Gibt den Index der Gruppe, in dem die Bezeichnung hinzugefügt wird.  
  
 [in] `lpszLabelName`  
 Gibt den Namen der Bezeichnung.  
  
 [in] `nTaskIcon`  
 Gibt das Symbol neben der Beschriftung angezeigt. Das Framework speichert Symbole in eine Liste von Bildern. Dieser Parameter ist ein Index in der Liste.  
  
 [in] `bIsBold`  
 `TRUE`um die Bezeichnung in Fettschrift angezeigt werden. andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index der Gruppe, in dem die Bezeichnung hinzugefügt wurde, oder -1, wenn die Gruppe angegeben `nGroup` ist nicht vorhanden.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ist anders Aufgaben und Bezeichnungen. Klickt ein Benutzer auf eine Aufgabe, führt das Framework einen Befehl. Klickt ein Benutzer auf eine Bezeichnung, wird kein Befehl ausgeführt. Weitere Informationen finden Sie unter [cmfctaskspane:: Addtask](#addtask).  
  
##  <a name="a-nameaddmrufileslista--cmfctaskspaneaddmrufileslist"></a><a name="addmrufileslist"></a>Cmfctaskspane:: Addmrufileslist  
 Fügt eine Aufgabe für jede Datei in einer Gruppe in einer Dateiliste zuletzt verwendet (MRU) gespeichert.  
  
```  
int AddMRUFilesList(
    int nGroup,  
    int nMaxFiles = 4);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nGroup`  
 Gibt den Index einer Gruppe. Diese Methode fügt der Liste der zuletzt verwendeten Dateien, die mit diesem Parameter angegebenen Gruppe.  
  
 [in] `nMaxFiles`  
 Gibt die Anzahl der Dateien in der Liste der zuletzt verwendeten Dateien angezeigt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index der Gruppe, in der Liste der zuletzt verwendeten Dateien hinzugefügt wurde, oder -1, wenn von die Gruppe angegeben `nGroup` ist nicht vorhanden.  
  
##  <a name="a-nameaddpagea--cmfctaskspaneaddpage"></a><a name="addpage"></a>CMFCTasksPane::AddPage  
 Im Aufgabenbereich wird eine Seite hinzugefügt.  
  
```  
int AddPage(LPCTSTR lpszPageLabel);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszPageLabel`  
 Gibt die Bezeichnung für die Seite.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index der neuen Seite.  
  
##  <a name="a-nameaddseparatora--cmfctaskspaneaddseparator"></a><a name="addseparator"></a>CMFCTasksPane::AddSeparator  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int AddSeparator(int nGroup);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nGroup`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameaddtaska--cmfctaskspaneaddtask"></a><a name="addtask"></a>Cmfctaskspane:: Addtask  
 Der angegebenen Aufgabengruppe hinzugefügt eine Aufgabe.  
  
```  
int AddTask(
    int nGroup,  
    LPCTSTR lpszTaskName,  
    int nTaskIcon = -1,  
    UINT uiCommandID = 0,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nGroup`  
 Gibt die gruppenindex, an dem die Aufgabe hinzugefügt wird.  
  
 [in] `lpszTaskName`  
 Gibt den Namen des Tasks.  
  
 [in] `nTaskIcon`  
 Gibt das Symbol neben dem Task angezeigt. Das Framework speichert Symbole in eine Liste von Bildern. Dieser Parameter ist ein Index in der Liste.  
  
 [in] `uiCommandID`  
 Gibt die Befehls-ID des Befehls ausführen, wenn der Benutzer auf die Aufgabe klickt. Die Aufgabe wird als Bezeichnung behandelt, wenn `uiCommandID` ist 0.  
  
 [in] `dwUserData`  
 Gibt die benutzerdefinierten Daten der Aufgabe zugeordnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index der Gruppe, in dem die Aufgabe hinzugefügt wurde, andernfalls-1 von die Gruppe angegeben `nGroup` ist nicht vorhanden.  
  
##  <a name="a-nameaddwindowa--cmfctaskspaneaddwindow"></a><a name="addwindow"></a>CMFCTasksPane::AddWindow  
 Fügt dem Aufgabenbereich ein untergeordnetes Fenster hinzu.  
  
```  
int AddWindow(
    int nGroup,  
    HWND hwndTask,  
    int nWndHeight,  
    BOOL bAutoDestroyWindow = FALSE,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nGroup`  
 Gibt den Group-Index, an dem das Fenster hinzugefügt wird.  
  
 [in] `hwndTask`  
 Gibt das Handle des Fensters hinzufügen.  
  
 [in] `nWndHeight`  
 Gibt die Höhe des Fensters.  
  
 [in] `bAutoDestroyWindow`  
 `TRUE`um das Fenster zerstört, wenn die Aufgabe entfernt wird; andernfalls `FALSE`.  
  
 [in] `dwUserData`  
 Gibt die benutzerdefinierten Daten, die dem Vorgang zugeordnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index der Gruppe, in das Fenster hinzugefügt wurde, oder -1, wenn die Gruppe angegeben `nGroup` ist nicht vorhanden.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um ein Steuerelement zu einem Aufgabenbereich hinzufügen. Beispielsweise können Sie ein Edit-Steuerelement hinzufügen, wie eine Suchleiste.  
  
##  <a name="a-namecmfctaskspanea--cmfctaskspanecmfctaskspane"></a><a name="cmfctaskspane"></a>CMFCTasksPane::CMFCTasksPane  
 Erstellt eine [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) Objekt.  
  
```  
CMFCTasksPane();
```  
  
##  <a name="a-namecollapseallgroupsa--cmfctaskspanecollapseallgroups"></a><a name="collapseallgroups"></a>CMFCTasksPane::CollapseAllGroups  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void CollapseAllGroups(BOOL bCollapse = TRUE);

 
void CollapseAllGroups(
    int nPageIdx,  
    BOOL bCollapse);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bCollapse`  
 [in] `nPageIdx`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namecollapsegroupa--cmfctaskspanecollapsegroup"></a><a name="collapsegroup"></a>CMFCTasksPane::CollapseGroup  
 Reduziert oder erweitert eine Gruppe.  
  
```  
BOOL CollapseGroup(
    CMFCTasksPaneTaskGroup* pGroup,  
    BOOL bCollapse = TRUE);

 
BOOL CollapseGroup(
    int nGroup,  
    BOOL bCollapse = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pGroup`  
 Gibt die Gruppe zu reduzieren.  
  
 [in] `bCollapse`  
 `TRUE`um die Gruppe zu reduzieren; `FALSE` zum Erweitern der Gruppe.  
  
 [in] `nGroup`  
 Gibt den nullbasierten Index der Gruppe, die in der internen Liste von Gruppen zu reduzieren.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Gruppe reduziert oder erfolgreich erweitert. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Eine reduzierte Gruppe zeigt nur die gruppenbeschriftung. die Liste der Aufgaben ist ausgeblendet.  
  
##  <a name="a-namecreatedefaultminiframea--cmfctaskspanecreatedefaultminiframe"></a><a name="createdefaultminiframe"></a>CMFCTasksPane::CreateDefaultMiniframe  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rectInitial`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namecreatemenua--cmfctaskspanecreatemenu"></a><a name="createmenu"></a>CMFCTasksPane::CreateMenu  
 Erstellt ein Menü, das angezeigt wird, wenn ein Benutzer klickt auf die **andere Aufgabenbereiche** -Schaltfläche.  
  
```  
HMENU CreateMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für das neue Menü.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Anpassen des Menüs für einen Aufgabenbereich.  
  
 Popup-Menü, das von dieser Methode erstellte enthält die Liste der Seiten im Aufgabenbereich. Klicken Sie im Menü wird ein Häkchen neben die aktive Seite angezeigt.  
  
##  <a name="a-nameenableanimationa--cmfctaskspaneenableanimation"></a><a name="enableanimation"></a>CMFCTasksPane::EnableAnimation  
 Aktiviert oder deaktiviert die Animation, die bei eine Aufgabengruppe erweitert oder reduziert.  
  
```  
void EnableAnimation(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`um die Animation zu aktivieren, die bei eine Aufgabengruppe erweitert oder reduziert; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die Animation, die bei eine Aufgabengruppe erweitert oder reduziert ist standardmäßig aktiviert.  
  
##  <a name="a-nameenablegroupcollapsea--cmfctaskspaneenablegroupcollapse"></a><a name="enablegroupcollapse"></a>Cmfctaskspane:: Enablegroupcollapse  
 Gibt an, ob ein Benutzer Aufgabengruppen reduziert werden kann.  
  
```  
void EnableGroupCollapse(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`Wenn Benutzer Aufgabengruppen reduziert werden können; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Eine Aufgabengruppe, die reduziert ist zeigt nur die gruppenbeschriftung an. die Liste der Aufgaben ist ausgeblendet.  
  
##  <a name="a-nameenablehistorymenubuttonsa--cmfctaskspaneenablehistorymenubuttons"></a><a name="enablehistorymenubuttons"></a>CMFCTasksPane::EnableHistoryMenuButtons  
 Aktiviert die Dropdown-Menüs auf die **Weiter** und **vorherige** Navigationsschaltflächen.  
  
```  
void EnableHistoryMenuButtons(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`So aktivieren Sie die Dropdown-Menüs auf die **Weiter** und **zurück** Navigationsschaltflächen, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung werden die Dropdown-Menüs auf die **Weiter** und **zurück** Schaltflächen werden deaktiviert.  
  
 Die Menüs enthalten den Verlauf der Seiten, die der Benutzer verwendet.  
  
##  <a name="a-nameenablenavigationtoolbara--cmfctaskspaneenablenavigationtoolbar"></a><a name="enablenavigationtoolbar"></a>CMFCTasksPane::EnableNavigationToolbar  
 Aktiviert oder deaktiviert die Navigationssymbolleiste.  
  
```  
void EnableNavigationToolbar(
    BOOL bEnable = TRUE,  
    UINT uiToolbarBmpRes = 0,  
    CSize sizeToolbarImage = CSize(0,
    0),  
    CSize sizeToolbarButton = CSize(0,
    0));
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`So aktivieren Sie die Navigationssymbolleiste; andernfalls `FALSE`.  
  
 [in] `uiToolbarBmpRes`  
 Gibt die Ressourcen-ID der Bitmap mit den Bildern, die auf der Symbolleiste angezeigt.  
  
 [in] `sizeToolbarImage`  
 Gibt die Größe eines Bilds Symbolleiste.  
  
 [in] `sizeToolbarButton`  
 Gibt die Größe einer Symbolleisten-Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
 Die Navigationsleiste ist eine Symbolleiste, die vom Framework am oberen Rand des Aufgabenbereichs angezeigt wird. Die Navigationssymbolleiste enthält die **wieder**, **Vorwärts**, und **Home** Navigationsschaltflächen und einer Menüschaltfläche, die die Liste der verfügbaren Seiten enthält.  
  
 Standardmäßig zeigt das Framework keine die Navigationssymbolleiste. Wenn die Navigationssymbolleiste nicht angezeigt wird, befinden sich die Navigationsschaltflächen in der Titelleiste des andockleiste.  
  
##  <a name="a-nameenableoffsetcustomcontrolsa--cmfctaskspaneenableoffsetcustomcontrols"></a><a name="enableoffsetcustomcontrols"></a>CMFCTasksPane::EnableOffsetCustomControls  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void EnableOffsetCustomControls(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameenablescrollbuttonsa--cmfctaskspaneenablescrollbuttons"></a><a name="enablescrollbuttons"></a>CMFCTasksPane::EnableScrollButtons  
 Ermöglicht die Bildlaufschaltflächen statt einer Bildlaufleiste.  
  
```  
void EnableScrollButtons(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`Um Bildlaufschaltflächen statt einer Bildlaufleiste im Aufgabenbereich angezeigt werden. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig zeigt das Framework Bildlaufschaltflächen im Aufgabenbereich.  
  
##  <a name="a-nameenablewraplabelsa--cmfctaskspaneenablewraplabels"></a><a name="enablewraplabels"></a>CMFCTasksPane::EnableWrapLabels  
 Aktiviert oder deaktiviert den Wortumbruch für den Text in Bezeichnungen.  
  
```  
void EnableWrapLabels(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`um den Text in Bezeichnungen zu umschließen, die im Aufgabenbereich angezeigt werden; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird das Framework nicht den Text in Bezeichnungen umbrochen. Wenn Zeilenumbruch aktiviert ist, kann der Text in Bezeichnungen in mehreren Zeilen angezeigt. Die Bezeichnung kann einen Zeilenumbruch Marker wie enthalten `\n` und die Unterstreichung Marker `&`.  
  
##  <a name="a-nameenablewraptasksa--cmfctaskspaneenablewraptasks"></a><a name="enablewraptasks"></a>CMFCTasksPane::EnableWrapTasks  
 Aktiviert oder deaktiviert den Wortumbruch für den Text in Aufgaben.  
  
```  
void EnableWrapTasks(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`Aufgaben im Aufgabenbereich zu umschließen; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wortumbruch für Aufgaben ist standardmäßig deaktiviert.  
  
##  <a name="a-namegetactivepagea--cmfctaskspanegetactivepage"></a><a name="getactivepage"></a>CMFCTasksPane::GetActivePage  
 Gibt den nullbasierten Index für die aktive Seite zurück.  
  
```  
int GetActivePage() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index der aktiven Seite.  
  
##  <a name="a-namegetgroupcaptionheighta--cmfctaskspanegetgroupcaptionheight"></a><a name="getgroupcaptionheight"></a>CMFCTasksPane::GetGroupCaptionHeight  
 Gibt die Höhe der gruppenbeschriftung.  
  
```  
int GetGroupCaptionHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe der gruppenbeschriftung in Pixel.  
  
##  <a name="a-namegetgroupcaptionhorzoffseta--cmfctaskspanegetgroupcaptionhorzoffset"></a><a name="getgroupcaptionhorzoffset"></a>CMFCTasksPane::GetGroupCaptionHorzOffset  
 Gibt den horizontalen Offset einer gruppenbeschriftung zurück.  
  
```  
int GetGroupCaptionHorzOffset() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der horizontale Offset einer gruppenbeschriftung. Der horizontale Offset ist der Abstand in Pixel vom linken oder rechten Rand des Aufgabenbereichs.  
  
##  <a name="a-namegetgroupcaptionvertoffseta--cmfctaskspanegetgroupcaptionvertoffset"></a><a name="getgroupcaptionvertoffset"></a>CMFCTasksPane::GetGroupCaptionVertOffset  
 Gibt den vertikalen Offset einer gruppenbeschriftung zurück.  
  
```  
int GetGroupCaptionVertOffset() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der vertikale Offset einer gruppenbeschriftung aus der oberen und unteren Rand des Aufgabenbereichs.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardwert für den vertikalen Offset ist 7 Pixel.  
  
##  <a name="a-namegetgroupcounta--cmfctaskspanegetgroupcount"></a><a name="getgroupcount"></a>CMFCTasksPane::GetGroupCount  
 Ruft die Gesamtanzahl von Gruppen zurück.  
  
```  
int GetGroupCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Gesamtanzahl von Gruppen im Aufgabenbereich.  
  
##  <a name="a-namegetgrouplocationa--cmfctaskspanegetgrouplocation"></a><a name="getgrouplocation"></a>CMFCTasksPane::GetGroupLocation  
 Gibt den internen gruppenindex für die angegebene Gruppe zurück.  
  
```  
BOOL GetGroupLocation(
    CMFCTasksPaneTaskGroup* pGroup,  
    int& nGroup) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pGroup`  
 Gibt die Aufgabe, deren Speicherort abgerufen wird.  
  
 [out] `nGroup`  
 Enthält den nullbasierten Index der Aufgabengruppe.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Aufgabengruppe gefunden wurde. andernfalls `FALSE`.  
  
##  <a name="a-namegetgroupvertoffseta--cmfctaskspanegetgroupvertoffset"></a><a name="getgroupvertoffset"></a>CMFCTasksPane::GetGroupVertOffset  
 Gibt den vertikalen Offset einer Gruppe zurück.  
  
```  
int GetGroupVertOffset() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der vertikale Offset einer Gruppe, in Pixel.  
  
##  <a name="a-namegethorzmargina--cmfctaskspanegethorzmargin"></a><a name="gethorzmargin"></a>CMFCTasksPane::GetHorzMargin  
 Gibt den horizontalen Abstand zwischen einem Aufgabenbereich und dem Rand des Clientbereichs zurück.  
  
```  
int GetHorzMargin() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Den horizontalen Abstand zwischen einem Aufgabenbereich und dem Rand des Clientbereichs.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardabstand zwischen einem Aufgabenbereich und dem Rand des Clientbereichs ist 12 Pixel.  
  
##  <a name="a-namegetnextpagesa--cmfctaskspanegetnextpages"></a><a name="getnextpages"></a>CMFCTasksPane::GetNextPages  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void GetNextPages(CStringList& lstNextPages) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lstNextPages`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetpagebygroupa--cmfctaskspanegetpagebygroup"></a><a name="getpagebygroup"></a>CMFCTasksPane::GetPageByGroup  
 Ruft den Seitenindex für eine angegebene Gruppe ab.  
  
```  
BOOL GetPageByGroup(
    int nGroup,  
    int& nPage) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nGroup`  
 Gibt den nullbasierten Index der Aufgabengruppe.  
  
 [out] `nPage`  
 Enthält die Seitenindex für die angegebene Gruppe. Wenn die Aufgabengruppe, die nur eine Standardseite enthält, ist der Rückgabewert 0.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Gruppe `nGroup` vorhanden ist, andernfalls `FALSE`.  
  
##  <a name="a-namegetpagescounta--cmfctaskspanegetpagescount"></a><a name="getpagescount"></a>CMFCTasksPane::GetPagesCount  
 Gibt die Anzahl der Seiten zurück.  
  
```  
int GetPagesCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Seiten im Aufgabenbereich.  
  
##  <a name="a-namegetpreviouspagesa--cmfctaskspanegetpreviouspages"></a><a name="getpreviouspages"></a>CMFCTasksPane::GetPreviousPages  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void GetPreviousPages(CStringList& lstPrevPages) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lstPrevPages`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetscrollbarctrla--cmfctaskspanegetscrollbarctrl"></a><a name="getscrollbarctrl"></a>CMFCTasksPane::GetScrollBarCtrl  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CScrollBar* GetScrollBarCtrl(int nBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nBar`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegettaska--cmfctaskspanegettask"></a><a name="gettask"></a>CMFCTasksPane::GetTask  
 Ruft eine Aufgabe ab.  
  
```  
CMFCTasksPaneTask* GetTask(
    int nGroup,  
    int nTask) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nGroup`  
 Gibt den nullbasierten Index der Gruppe, die die Aufgabe enthält.  
  
 [in] `nTask`  
 Gibt den nullbasierten Index des Tasks in der Liste angegebenen `nGroup`.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Aufgabe am angegebenen Index.  
  
##  <a name="a-namegettaskcounta--cmfctaskspanegettaskcount"></a><a name="gettaskcount"></a>CMFCTasksPane::GetTaskCount  
 Gibt die Anzahl der Aufgaben in einer angegebenen Gruppe zurück.  
  
```  
int GetTaskCount(int nGroup) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nGroup`  
 Gibt den Index der Aufgabengruppe.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Aufgaben in der angegebenen Gruppe bzw. 0, wenn `nGroup` ist ungültig.  
  
##  <a name="a-namegettaskgroupa--cmfctaskspanegettaskgroup"></a><a name="gettaskgroup"></a>CMFCTasksPane::GetTaskGroup  
 Gibt eine Aufgabengruppe für einen Index für die angegebene Gruppe zurück.  
  
```  
CMFCTasksPaneTaskGroup* GetTaskGroup(int nGroup) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nGroup`  
 Gibt den nullbasierten Index des abzurufenden Gruppe.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Aufgabengruppe am angegebenen Index.  
  
##  <a name="a-namegettasklocationa--cmfctaskspanegettasklocation"></a><a name="gettasklocation"></a>CMFCTasksPane::GetTaskLocation  
 Gibt die Gruppe und den Index für den angegebenen Vorgang zurück.  
  
```  
BOOL GetTaskLocation(
    UINT uiCommandID,  
    int& nGroup,  
    int& nTask) const;  
  
BOOL GetTaskLocation(
    HWND hwndTask,  
    int& nGroup,  
    int& nTask) const;  
  
BOOL GetTaskLocation(
    CMFCTasksPaneTask* pTask,  
    int& nGroup,  
    int& nTask) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCommandID`  
 Gibt die Befehls-ID des Vorgangs zu suchen.  
  
 [out] `nGroup`  
 Enthält den gruppenindex der Aufgabe.  
  
 [out] `nTask`  
 Enthält den Index des Tasks in der Aufgabengruppe.  
  
 [in] `hwndTask`  
 Gibt das Fenster mit der Aufgabe verknüpft ist.  
  
 [in] `pTask`  
 Gibt die Aufgabe zu suchen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der taskspeicherort gefunden wurde; `FALSE` ist die angegebene Aufgabe ist nicht vorhanden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft die Gruppe und Taskindex für den angegebenen Vorgang. Wenn die Methode zurückgibt `FALSE`, `nGroup` und `nTask` auf-1 festgelegt sind.  
  
##  <a name="a-namegettaskshorzoffseta--cmfctaskspanegettaskshorzoffset"></a><a name="gettaskshorzoffset"></a>CMFCTasksPane::GetTasksHorzOffset  
 Gibt den horizontalen Offset des Tasks zurück.  
  
```  
int GetTasksHorzOffset() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der horizontale Offset von Aufgaben vom linken und rechten Rand ihre übergeordneten Gruppen.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardeinstellung horizontale Offset von Aufgaben ist 12 Pixel.  
  
##  <a name="a-namegettasksiconhorzoffseta--cmfctaskspanegettasksiconhorzoffset"></a><a name="gettasksiconhorzoffset"></a>CMFCTasksPane::GetTasksIconHorzOffset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetTasksIconHorzOffset() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegettasksiconvertoffseta--cmfctaskspanegettasksiconvertoffset"></a><a name="gettasksiconvertoffset"></a>CMFCTasksPane::GetTasksIconVertOffset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetTasksIconVertOffset() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetvertmargina--cmfctaskspanegetvertmargin"></a><a name="getvertmargin"></a>CMFCTasksPane::GetVertMargin  
 Gibt den vertikalen Rand zwischen einem Aufgabenbereich und den Rändern des Clientbereichs zurück.  
  
```  
int GetVertMargin() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der vertikalen Rand zwischen einem Aufgabenbereich und den Rändern des Clientbereichs.  
  
### <a name="remarks"></a>Hinweise  
 Die vertikale Rand ist der Abstand zwischen einem Aufgabenbereich und den Rändern des Clientbereichs. Der Standardwert des vertikalen Rands beträgt 12 Pixel.  
  
##  <a name="a-nameisaccessibilitycompatiblea--cmfctaskspaneisaccessibilitycompatible"></a><a name="isaccessibilitycompatible"></a>CMFCTasksPane::IsAccessibilityCompatible  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsAccessibilityCompatible();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameisanimationenableda--cmfctaskspaneisanimationenabled"></a><a name="isanimationenabled"></a>CMFCTasksPane::IsAnimationEnabled  
 Gibt an, ob die Animation aktiviert ist.  
  
```  
BOOL IsAnimationEnabled() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Animation, die auftritt, wenn ein Benutzer erweitert oder eine Gruppe reduziert aktiviert ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [CMFCTasksPane::EnableAnimation](#enableanimation) aktivieren oder Deaktivieren der Animation.  
  
##  <a name="a-nameisbackbuttonenableda--cmfctaskspaneisbackbuttonenabled"></a><a name="isbackbuttonenabled"></a>CMFCTasksPane::IsBackButtonEnabled  
 Gibt an, ob die Zurück-Schaltfläche aktiviert ist.  
  
```  
BOOL IsBackButtonEnabled() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die zurück-Schaltfläche aktiviert ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Benutzer die zurück-Schaltfläche klickt, zeigt das Framework die vorherigen Aufgabenseite.  
  
##  <a name="a-nameisforwardbuttonenableda--cmfctaskspaneisforwardbuttonenabled"></a><a name="isforwardbuttonenabled"></a>CMFCTasksPane::IsForwardButtonEnabled  
 Gibt an, ob die Weiter-Schaltfläche aktiviert ist.  
  
```  
BOOL IsForwardButtonEnabled() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Schaltfläche "Vorwärts" aktiviert ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die Schaltfläche "Vorwärts" ermöglicht die Vorwärtsnavigation im Verlauf des Task-Seiten.  
  
##  <a name="a-nameisgroupcollapseenableda--cmfctaskspaneisgroupcollapseenabled"></a><a name="isgroupcollapseenabled"></a>CMFCTasksPane::IsGroupCollapseEnabled  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsGroupCollapseEnabled() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameishistorymenubuttonsenableda--cmfctaskspaneishistorymenubuttonsenabled"></a><a name="ishistorymenubuttonsenabled"></a>CMFCTasksPane::IsHistoryMenuButtonsEnabled  
 Gibt an, ob die **Weiter** und **vorherige** Navigationsschaltflächen Dropdown-Menüs haben.  
  
```  
BOOL IsHistoryMenuButtonsEnabled() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die **Weiter** und **vorherige** Navigationsschaltflächen Dropdown-Menüs haben; andernfalls `FALSE`.  
  
##  <a name="a-nameisnavigationtoolbarenableda--cmfctaskspaneisnavigationtoolbarenabled"></a><a name="isnavigationtoolbarenabled"></a>CMFCTasksPane::IsNavigationToolbarEnabled  
 Gibt an, ob die Navigationssymbolleiste aktiviert ist.  
  
```  
BOOL IsNavigationToolbarEnabled() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Navigationssymbolleiste aktiviert ist; andernfalls `FALSE`.  
  
##  <a name="a-nameistoolboxa--cmfctaskspaneistoolbox"></a><a name="istoolbox"></a>CMFCTasksPane::IsToolBox  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsToolBox() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameiswraplabelsenableda--cmfctaskspaneiswraplabelsenabled"></a><a name="iswraplabelsenabled"></a>CMFCTasksPane::IsWrapLabelsEnabled  
 Gibt an, ob der Aufgabenbereich Wörter in Bezeichnungen umbricht.  
  
```  
BOOL IsWrapLabelsEnabled() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Sie Wörter in Bezeichnungen eingeschlossen werden; andernfalls `FALSE`.  
  
##  <a name="a-nameiswraptasksenableda--cmfctaskspaneiswraptasksenabled"></a><a name="iswraptasksenabled"></a>CMFCTasksPane::IsWrapTasksEnabled  
 Gibt an, ob das Framework die aufgabenzeichenfolge umschließt.  
  
```  
BOOL IsWrapTasksEnabled() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Zeichenfolge Task umschlossen ist; andernfalls `FALSE`.  
  
##  <a name="a-nameloadstatea--cmfctaskspaneloadstate"></a><a name="loadstate"></a>CMFCTasksPane::LoadState  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 [in] `nIndex`  
 [in] `uiID`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonactivatetaskspanepagea--cmfctaskspaneonactivatetaskspanepage"></a><a name="onactivatetaskspanepage"></a>CMFCTasksPane::OnActivateTasksPanePage  
 Vom Framework aufgerufen, wenn eine Aufgabenbereichsseite aktiv wird.  
  
```  
virtual void OnActivateTasksPanePage();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Anpassen der Darstellung der Seite im Bereich Task.  
  
##  <a name="a-nameoncancela--cmfctaskspaneoncancel"></a><a name="oncancel"></a>CMFCTasksPane::OnCancel  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnCancel();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonclicktaska--cmfctaskspaneonclicktask"></a><a name="onclicktask"></a>CMFCTasksPane::OnClickTask  
 Wird vom Framework aufgerufen, wenn der Benutzer auf ein Element im Aufgabenbereich klickt.  
  
```  
virtual void OnClickTask(
    int nGroupNumber,  
    int nTaskNumber,  
    UINT uiCommandID,  
    DWORD dwUserData);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nGroupNumber`  
 Gibt den nullbasierten Index der Gruppe, die den ausgewählten Task enthält.  
  
 [in] `nTaskNumber`  
 Gibt den nullbasierten Index des ausgewählten Tasks an.  
  
 [in] `uiCommandID`  
 Gibt die Befehls-ID, die dem Vorgang zugeordnet.  
  
 [in] `dwUserData`  
 Enthält benutzerdefinierte Daten, die dem ausgewählten Vorgang zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode klickt ein Benutzer eine Aufgabe. In der Standardeinstellung das Framework prüft die Befehls-ID, die dem ausgewählten Vorgang zugeordnet und ist er nicht NULL ist, sendet die `WM_COMMAND` Nachricht an den Besitzer des Aufgabenbereich-Steuerelements.  
  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, benutzerdefinierten Code auszuführen, wenn eine Aufgabe geklickt wird.  
  
##  <a name="a-nameonoka--cmfctaskspaneonok"></a><a name="onok"></a>CMFCTasksPane::OnOK  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonpressbackbuttona--cmfctaskspaneonpressbackbutton"></a><a name="onpressbackbutton"></a>CMFCTasksPane::OnPressBackButton  
 Wird vom Framework aufgerufen, wenn der Benutzer auf die Zurück-Schaltfläche klickt.  
  
```  
virtual void OnPressBackButton();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig zeigt das Framework die zuvor angezeigte Seite.  
  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, benutzerdefinierten Code auszuführen, wenn der Benutzer die zurück-Schaltfläche klickt.  
  
##  <a name="a-nameonpressforwardbuttona--cmfctaskspaneonpressforwardbutton"></a><a name="onpressforwardbutton"></a>CMFCTasksPane::OnPressForwardButton  
 Wird vom Framework aufgerufen, wenn der Benutzer auf die Navigationsschaltfläche Weiter klickt.  
  
```  
virtual void OnPressForwardButton();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig zeigt das Framework die Seite, die der Benutzer angezeigt, bevor Sie auf die **wieder** Schaltfläche.  
  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, benutzerdefinierten Code auszuführen, wenn der Benutzer auf die Schaltfläche "Vorwärts" klickt.  
  
##  <a name="a-nameonpresshomebuttona--cmfctaskspaneonpresshomebutton"></a><a name="onpresshomebutton"></a>CMFCTasksPane::OnPressHomeButton  
 Vom Framework aufgerufen, wenn der Benutzer auf die Navigationsschaltfläche Startseite klickt.  
  
```  
virtual void OnPressHomeButton();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig zeigt das Framework die Standardseite für die Aufgabengruppe.  
  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, benutzerdefinierten Code auszuführen, wenn der Benutzer auf die Navigationsschaltfläche Startseite klickt.  
  
##  <a name="a-nameonpressotherbuttona--cmfctaskspaneonpressotherbutton"></a><a name="onpressotherbutton"></a>CMFCTasksPane::OnPressOtherButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnPressOtherButton(
    CMFCCaptionMenuButton* pbtn,  
    CWnd* pWndOwner);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pbtn`  
 [in] `pWndOwner`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonsetaccdataa--cmfctaskspaneonsetaccdata"></a><a name="onsetaccdata"></a>CMFCTasksPane::OnSetAccData  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnSetAccData(long lVal);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lVal`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonupdatecmduia--cmfctaskspaneonupdatecmdui"></a><a name="onupdatecmdui"></a>CMFCTasksPane::OnUpdateCmdUI  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pTarget`  
 [in] `bDisableIfNoHndler`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namepretranslatemessagea--cmfctaskspanepretranslatemessage"></a><a name="pretranslatemessage"></a>CMFCTasksPane::PreTranslateMessage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMsg`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namerecalclayouta--cmfctaskspanerecalclayout"></a><a name="recalclayout"></a>CMFCTasksPane::RecalcLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void RecalcLayout(BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bRedraw`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameremoveallgroupsa--cmfctaskspaneremoveallgroups"></a><a name="removeallgroups"></a>CMFCTasksPane::RemoveAllGroups  
 Entfernt alle Gruppen auf der angegebenen Seite.  
  
```  
void RemoveAllGroups(int nPageIdx = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nPageIdx`  
 Gibt den nullbasierten Index der Seite.  
  
### <a name="remarks"></a>Hinweise  
 Entfernt alle Gruppen auf der angegebenen Seite `nPageIdx`, oder alle Gruppen, wenn nur eine Standardseite vorhanden ist.  
  
##  <a name="a-nameremoveallpagesa--cmfctaskspaneremoveallpages"></a><a name="removeallpages"></a>CMFCTasksPane::RemoveAllPages  
 Entfernt alle Seiten aus dem Aufgabenbereich mit Ausnahme der Standardseite (erste).  
  
```  
void RemoveAllPages();
```  
  
##  <a name="a-nameremovealltasksa--cmfctaskspaneremovealltasks"></a><a name="removealltasks"></a>CMFCTasksPane::RemoveAllTasks  
 Entfernt alle Aufgaben aus der angegebenen Gruppe.  
  
```  
void RemoveAllTasks(int nGroup);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nGroup`  
 Gibt den nullbasierten Index der Gruppe an.  
  
##  <a name="a-nameremovegroupa--cmfctaskspaneremovegroup"></a><a name="removegroup"></a>CMFCTasksPane::RemoveGroup  
 Entfernt eine Gruppe.  
  
```  
void RemoveGroup(int nGroup);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nGroup`  
 Gibt den nullbasierten Index der Gruppe entfernen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird eine einzelne Gruppe entfernt. Um alle Gruppen zu entfernen, rufen Sie [CMFCTasksPane::RemoveAllGroups](#removeallgroups) stattdessen.  
  
 Wenn das Framework eine Gruppe entfernt wird, werden alle Tasks und Benutzer Windows zugeordnet zerstört.  
  
##  <a name="a-nameremovepagea--cmfctaskspaneremovepage"></a><a name="removepage"></a>CMFCTasksPane::RemovePage  
 Entfernt eine angegebene Seite aus dem Aufgabenbereich.  
  
```  
void RemovePage(int nPageIdx);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nPageIdx`  
 Gibt den nullbasierten Index des zu entfernenden Seite.  
  
##  <a name="a-nameremovetaska--cmfctaskspaneremovetask"></a><a name="removetask"></a>CMFCTasksPane::RemoveTask  
 Entfernt eine Aufgabe aus einer Aufgabengruppe.  
  
```  
BOOL RemoveTask(
    int nGroup,  
    int nTask,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nGroup`  
 Gibt den nullbasierten Index der Aufgabengruppe mit der Aufgabe zu entfernen.  
  
 [in] `nTask`  
 Gibt den nullbasierten Index des Vorgangs zu entfernen.  
  
 [in] `bRedraw`  
 `TRUE`den Aufgabenbereich neu gezeichnet; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Funktion erfolgreich ist. `FALSE` Wenn `nGroup` oder `nTask` ist ungültig.  
  
##  <a name="a-namesavestatea--cmfctaskspanesavestate"></a><a name="savestate"></a>CMFCTasksPane::SaveState  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 [in] `nIndex`  
 [in] `uiID`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameserializea--cmfctaskspaneserialize"></a><a name="serialize"></a>CMFCTasksPane::Serialize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `ar`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetactivepagea--cmfctaskspanesetactivepage"></a><a name="setactivepage"></a>CMFCTasksPane::SetActivePage  
 Aktiviert die angegebene Seite im Aufgabenbereich.  
  
```  
void SetActivePage(int nPageIdx);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nPageIdx`  
 Gibt den nullbasierten Index des anzuzeigenden Seite.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überprüft, wenn die `nPageIdx` ist ungültig.  
  
##  <a name="a-namesetcaptiona--cmfctaskspanesetcaption"></a><a name="setcaption"></a>CMFCTasksPane::SetCaption  
 Legt den Beschriftungsnamen eines Aufgabenbereichs fest.  
  
```  
void SetCaption(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszName`  
 Gibt den Beschriftungsnamen.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Aufgabenbereich auf mehrere Seiten umfasst, hat die Standardseite die Beschriftung, die mit dieser Funktion festgelegt wurde.  
  
##  <a name="a-namesetgroupcaptionheighta--cmfctaskspanesetgroupcaptionheight"></a><a name="setgroupcaptionheight"></a>CMFCTasksPane::SetGroupCaptionHeight  
 Legt die Höhe einer Gruppenbeschriftung fest.  
  
```  
void SetGroupCaptionHeight(int n = -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `n`  
 Gibt die Höhe der Beschriftung.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Ränder der Elemente im Bereich Task anpassen.  
  
 Wenn `n` ist-1 und das Framework bestimmt den Wert für den Rand mit visuellen Manager ( `CMFCVisualManager::GetTasksPaneGroupCaptionHeight`). Die Überschriftenhöhe Standard ist 25 Pixel.  
  
##  <a name="a-namesetgroupcaptionhorzoffseta--cmfctaskspanesetgroupcaptionhorzoffset"></a><a name="setgroupcaptionhorzoffset"></a>CMFCTasksPane::SetGroupCaptionHorzOffset  
 Legt den horizontalen Offset einer Gruppenbeschriftung fest.  
  
```  
void SetGroupCaptionHorzOffset(int n = -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `n`  
 Gibt den horizontalen Offset die Beschriftung der Gruppe.  
  
##  <a name="a-namesetgroupcaptionvertoffseta--cmfctaskspanesetgroupcaptionvertoffset"></a><a name="setgroupcaptionvertoffset"></a>CMFCTasksPane::SetGroupCaptionVertOffset  
 Legt den vertikalen Offset einer Gruppenbeschriftung fest.  
  
```  
void SetGroupCaptionVertOffset(int n = -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `n`  
 Den vertikalen Offset angibt in Pixel der gruppenbeschriftung.  
  
##  <a name="a-namesetgroupnamea--cmfctaskspanesetgroupname"></a><a name="setgroupname"></a>CMFCTasksPane::SetGroupName  
 Legt einen Gruppennamen fest.  
  
```  
BOOL SetGroupName(
    int nGroup,  
    LPCTSTR lpszGroupName);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nGroup`  
 Gibt den nullbasierten Index der Gruppe an.  
  
 [in] `lpszGroupName`  
 Gibt den Namen der Gruppe an.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Gruppenname erfolgreich festgelegt wurde. andernfalls `FALSE`.  
  
##  <a name="a-namesetgrouptextcolora--cmfctaskspanesetgrouptextcolor"></a><a name="setgrouptextcolor"></a>CMFCTasksPane::SetGroupTextColor  
 Legt die Textfarbe für eine Gruppenbeschriftung fest.  
  
```  
BOOL SetGroupTextColor(
    int nGroup,  
    COLORREF color,  
    COLORREF colorHot = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nGroup`  
 Gibt den nullbasierten Index der Gruppe an.  
  
 [in] `color`  
 Gibt die Farbe des Texts an.  
  
 [in] `colorHot`  
 Gibt die Farbe des Texts für die markierte Gruppe an. Wenn&1;, wird die standardmäßige Hervorhebungsfarbe verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Textfarbe der Gruppe erfolgreich geändert wurde. andernfalls `FALSE`.  
  
##  <a name="a-namesetgroupvertoffseta--cmfctaskspanesetgroupvertoffset"></a><a name="setgroupvertoffset"></a>CMFCTasksPane::SetGroupVertOffset  
 Legt den vertikalen Offset für eine Gruppe fest.  
  
```  
void SetGroupVertOffset(int n = -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `n`  
 Gibt den vertikalen Offset.  
  
### <a name="remarks"></a>Hinweise  
 Der vertikale Offset ist der Abstand zwischen einer Aufgabengruppe und dem Rand des Aufgabenbereichs.  
  
 Rufen Sie diese Methode, um die Ränder der Elemente des Vorgangs anpassen. Wenn `n` ist-1 und das Framework bestimmt den Wert für den Rand mit visuellen Manager ( `CMFCVisualManager::GetTasksPaneGroupVertOffset`). Der Standardwert beträgt 15 Pixel.  
  
##  <a name="a-namesethorzmargina--cmfctaskspanesethorzmargin"></a><a name="sethorzmargin"></a>CMFCTasksPane::SetHorzMargin  
 Legt den horizontalen Rand fest.  
  
```  
void SetHorzMargin(int n = -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `n`  
 Gibt den Rand in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Der horizontale Rand ist der Abstand zwischen einem Aufgabenbereich und den oberen oder unteren Rand des Clientbereichs.  
  
 Wenn n -1, und das Framework bestimmt den Wert für den Rand mit visuellen Manager ( `CMFCVisualManager::GetTasksPaneHorzMargin`). Die horizontale Standardrand beträgt 12 Pixel.  
  
##  <a name="a-nameseticonslista--cmfctaskspaneseticonslist"></a><a name="seticonslist"></a>CMFCTasksPane::SetIconsList  
 Legt die Bildliste fest.  
  
```  
BOOL SetIconsList(
    UINT uiImageListResID,  
    int cx,  
    COLORREF clrTransparent = RGB(255, 0, 255));  
  
void SetIconsList(HIMAGELIST hIcons);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiImageListResID`  
 Gibt die Ressourcen-ID der Bildliste.  
  
 [in] `cx`  
 Gibt die Größe der Symbole in der Bildliste an.  
  
 [in] `clrTransparent`  
 Gibt die transparente Farbe.  
  
 [in] `hIcons`  
 Gibt die Liste der Images, die die Symbole für den Aufgabenbereich enthält.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework speichert die Symbole in einer Bildliste. Aufgaben sind Symbole, die in der Liste gespeichert werden zugeordnet.  
  
 Diese Methode ordnet eine Bildliste mit dem Aufgabenbereich-Steuerelement. Das Symbol für einen Vorgang festlegen, wenn Sie aufrufen [cmfctaskspane:: Addtask](#addtask)legen `nTaskIcon` auf den entsprechenden nullbasierten Index in der Liste dieses Images.  
  
##  <a name="a-namesetpagecaptiona--cmfctaskspanesetpagecaption"></a><a name="setpagecaption"></a>CMFCTasksPane::SetPageCaption  
 Legt den Beschriftungstext für eine Aufgabenbereichsseite fest.  
  
```  
void SetPageCaption(
    int nPageIdx,  
    LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nPageIdx`  
 Gibt den nullbasierten Index der Seite.  
  
 [in] `lpszName`  
 Gibt den Beschriftungstext, die auf der Seite angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Aufgabenbereich auf mehrere Seiten umfasst, hat die Standardseite die Beschriftung, die mit dieser Methode festgelegt wurde.  
  
##  <a name="a-namesettasknamea--cmfctaskspanesettaskname"></a><a name="settaskname"></a>CMFCTasksPane::SetTaskName  
 Legt den Namen für eine Aufgabe fest.  
  
```  
BOOL SetTaskName(
    int nGroup,  
    int nTask,  
    LPCTSTR lpszTaskName);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nGroup`  
 Gibt den nullbasierten Index der Aufgabengruppe.  
  
 [in] `nTask`  
 Gibt den nullbasierten Index des Tasks an.  
  
 [in] `lpszTaskName`  
 Gibt den Aufgabennamen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Vorgangsname erfolgreich festgelegt wurde; andernfalls `FALSE`.  
  
##  <a name="a-namesettaskshorzoffseta--cmfctaskspanesettaskshorzoffset"></a><a name="settaskshorzoffset"></a>CMFCTasksPane::SetTasksHorzOffset  
 Legt den horizontalen Offset für Aufgaben.  
  
```  
void SetTasksHorzOffset(int n = -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `n`  
 Gibt den horizontalen Offset.  
  
### <a name="remarks"></a>Hinweise  
 Der horizontale Offset ist der Abstand in Pixel vom linken und rechten Rand einer Gruppe.  
  
 Wenn `n` ist-1, diese Methode legt den horizontalen Offset auf den Rückgabewert von der `CMFCVisualManager::GetTasksPaneTaskHorzOffset` Methode.  
  
 Der horizontale Offset der Standardwert beträgt 12 Pixel.  
  
##  <a name="a-namesettasksiconhorzoffseta--cmfctaskspanesettasksiconhorzoffset"></a><a name="settasksiconhorzoffset"></a>CMFCTasksPane::SetTasksIconHorzOffset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetTasksIconHorzOffset(int n = -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `n`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesettasksiconvertoffseta--cmfctaskspanesettasksiconvertoffset"></a><a name="settasksiconvertoffset"></a>CMFCTasksPane::SetTasksIconVertOffset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetTasksIconVertOffset(int n = -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `n`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesettasktextcolora--cmfctaskspanesettasktextcolor"></a><a name="settasktextcolor"></a>CMFCTasksPane::SetTaskTextColor  
 Legt die Textfarbe für eine Aufgabe fest.  
  
```  
BOOL SetTaskTextColor(
    int nGroup,  
    int nTask,  
    COLORREF color,  
    COLORREF colorHot = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nGroup`  
 Gibt den nullbasierten Index der Aufgabengruppe, die die Aufgabe enthält.  
  
 [in] `nTask`  
 Gibt den nullbasierten Index des Tasks an.  
  
 [in] `color`  
 Gibt die Textfarbe für den Task an.  
  
 [in] `colorHot`  
 Gibt die Farbe des Texts für die markierte Gruppe an. Wenn-1 verwendet diese Methode die standardmäßige Hervorhebungsfarbe.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Textfarbe für die Aufgabe erfolgreich festgelegt wurde. andernfalls `FALSE`.  
  
##  <a name="a-namesetvertmargina--cmfctaskspanesetvertmargin"></a><a name="setvertmargin"></a>CMFCTasksPane::SetVertMargin  
 Legt den vertikalen Rand fest.  
  
```  
void SetVertMargin(int n = -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `n`  
 Gibt den vertikalen Rand festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Die vertikale Rand ist der Abstand zwischen einem Aufgabenbereich und den vertikalen Rändern des Clientbereichs.  
  
 Wenn `n` ist-1 und das Framework bestimmt den Wert für den Rand mit visuellen Manager ( `CMFCVisualManager::GetTasksPaneVertMargin`). Der Standardrand beträgt 12 Pixel.  
  
##  <a name="a-namesetwindowheighta--cmfctaskspanesetwindowheight"></a><a name="setwindowheight"></a>CMFCTasksPane::SetWindowHeight  
 Legt die Höhe für ein Fenstersteuerelement.  
  
```  
BOOL SetWindowHeight(
    int nGroup,  
    HWND hwndTask,  
    int nWndHeight);

 
BOOL SetWindowHeight(
    HWND hwndTask,  
    int nWndHeight);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nGroup`  
 Gibt den nullbasierten Index der Gruppe, die das Steuerelement enthält.  
  
 [in] `hwndTask`  
 Gibt das Handle für das Steuerelement.  
  
 [in] `nWndHeight`  
 Gibt die Höhe fest.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Höhe des Steuerelements Fenster erfolgreich festgelegt wurde. `FALSE` Wenn `nGroup` ist ungültig, oder wenn `hwndTask` ist nicht vorhanden.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [CMFCTasksPane::AddWindow](#addwindow) Aufgaben mit Windows-Steuerelemente hinzufügen.  
  
##  <a name="a-nameshowcommandmessagestringa--cmfctaskspaneshowcommandmessagestring"></a><a name="showcommandmessagestring"></a>CMFCTasksPane::ShowCommandMessageString  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void ShowCommandMessageString(UINT uiCmdId);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdId`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameshowtaska--cmfctaskspaneshowtask"></a><a name="showtask"></a>CMFCTasksPane::ShowTask  
 Blendet eine Aufgabe ein oder aus.  
  
```  
BOOL ShowTask(
    int nGroup,  
    int nTask,  
    BOOL bShow = TRUE,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nGroup`  
 Gibt den nullbasierten Index der Gruppe an.  
  
 [in] `nTask`  
 Gibt den nullbasierten Index des Vorgangs anzeigen oder ausblenden.  
  
 [in] `bShow`  
 `TRUE`den Task angezeigt; `FALSE` die Aufgabe ausgeblendet.  
  
 [in] `bRedraw`  
 `TRUE`den Aufgabenbereich neu gezeichnet; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Aufgabe wurde erfolgreich angezeigt oder ausgeblendet. `FALSE` Wenn die angegebene Gruppe oder eine Aufgabe nicht vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [CMFCTasksPane::ShowTaskByCmdId](#showtaskbycmdid) ein-oder Ausblenden eines Vorgangs, basierend auf der Befehls-ID.  
  
##  <a name="a-nameshowtaskbycmdida--cmfctaskspaneshowtaskbycmdid"></a><a name="showtaskbycmdid"></a>CMFCTasksPane::ShowTaskByCmdId  
 Blendet eine Aufgabe basierend auf der Befehls-ID ein oder aus.  
  
```  
BOOL ShowTaskByCmdId(
    UINT uiCommandID,  
    BOOL bShow = TRUE,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCommandID`  
 Gibt die Befehls-ID des Vorgangs zum ein- oder ausblenden.  
  
 [in] `bShow`  
 `TRUE`den Task angezeigt; `FALSE` die Aufgabe ausgeblendet.  
  
 [in] `bRedraw`  
 `TRUE`den Aufgabenbereich neu gezeichnet; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Aufgabe wurde erfolgreich angezeigt oder ausgeblendet. `FALSE` ist eine Aufgabe mit der angegebenen Befehls-ID nicht vorhanden.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [CMFCTasksPane::ShowTask](#showtask) ein-oder Ausblenden eines Vorgangs, basierend auf der Befehls-ID.  
  
##  <a name="a-nameupdatea--cmfctaskspaneupdate"></a><a name="update"></a>CMFCTasksPane::Update  
 Aktualisiert alle Steuerelemente in einem Aufgabenbereich.  
  
```  
virtual void Update();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode aktualisiert die Aufgabe Bereich Beschriftung, passt die Bildlaufleiste, verschiebt alle Aufgaben und zeichnet alle Steuerelemente im Bereich Task.  
  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, benutzerdefinierten Code auszuführen, wenn das Framework den Aufgabenbereich aktualisiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCTasksPaneTaskGroup-Klasse](../../mfc/reference/cmfctaskspanetaskgroup-class.md)   
 [Cmfctaskspanetask-Klasse](../../mfc/reference/cmfctaskspanetask-class.md)   
 [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCVisualManager-Klasse](../../mfc/reference/cmfcvisualmanager-class.md)

