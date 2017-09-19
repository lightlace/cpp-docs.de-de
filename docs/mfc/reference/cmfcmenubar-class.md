---
title: Klasse CMFCMenuBar | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCMenuBar
- AFXMENUBAR/CMFCMenuBar
- AFXMENUBAR/CMFCMenuBar::AdjustLocations
- AFXMENUBAR/CMFCMenuBar::AllowChangeTextLabels
- AFXMENUBAR/CMFCMenuBar::AllowShowOnPaneMenu
- AFXMENUBAR/CMFCMenuBar::CalcFixedLayout
- AFXMENUBAR/CMFCMenuBar::CalcLayout
- AFXMENUBAR/CMFCMenuBar::CalcMaxButtonHeight
- AFXMENUBAR/CMFCMenuBar::CanBeClosed
- AFXMENUBAR/CMFCMenuBar::CanBeRestored
- AFXMENUBAR/CMFCMenuBar::Create
- AFXMENUBAR/CMFCMenuBar::CreateEx
- AFXMENUBAR/CMFCMenuBar::CreateFromMenu
- AFXMENUBAR/CMFCMenuBar::EnableHelpCombobox
- AFXMENUBAR/CMFCMenuBar::EnableMenuShadows
- AFXMENUBAR/CMFCMenuBar::GetAvailableExpandSize
- AFXMENUBAR/CMFCMenuBar::GetColumnWidth
- AFXMENUBAR/CMFCMenuBar::GetDefaultMenu
- AFXMENUBAR/CMFCMenuBar::GetDefaultMenuResId
- AFXMENUBAR/CMFCMenuBar::GetFloatPopupDirection
- AFXMENUBAR/CMFCMenuBar::GetForceDownArrows
- AFXMENUBAR/CMFCMenuBar::GetHelpCombobox
- AFXMENUBAR/CMFCMenuBar::GetHMenu
- AFXMENUBAR/CMFCMenuBar::GetMenuFont
- AFXMENUBAR/CMFCMenuBar::GetMenuItem
- AFXMENUBAR/CMFCMenuBar::GetRowHeight
- AFXMENUBAR/CMFCMenuBar::GetSystemButton
- AFXMENUBAR/CMFCMenuBar::GetSystemButtonsCount
- AFXMENUBAR/CMFCMenuBar::GetSystemMenu
- AFXMENUBAR/CMFCMenuBar::HighlightDisabledItems
- AFXMENUBAR/CMFCMenuBar::IsButtonExtraSizeAvailable
- AFXMENUBAR/CMFCMenuBar::IsHighlightDisabledItems
- AFXMENUBAR/CMFCMenuBar::IsMenuShadows
- AFXMENUBAR/CMFCMenuBar::IsRecentlyUsedMenus
- AFXMENUBAR/CMFCMenuBar::IsShowAllCommands
- AFXMENUBAR/CMFCMenuBar::IsShowAllCommandsDelay
- AFXMENUBAR/CMFCMenuBar::LoadState
- AFXMENUBAR/CMFCMenuBar::OnChangeHot
- AFXMENUBAR/CMFCMenuBar::OnDefaultMenuLoaded
- AFXMENUBAR/CMFCMenuBar::OnSendCommand
- AFXMENUBAR/CMFCMenuBar::OnSetDefaultButtonText
- AFXMENUBAR/CMFCMenuBar::OnToolHitTest
- AFXMENUBAR/CMFCMenuBar::PreTranslateMessage
- AFXMENUBAR/CMFCMenuBar::RestoreOriginalstate
- AFXMENUBAR/CMFCMenuBar::SaveState
- AFXMENUBAR/CMFCMenuBar::SetDefaultMenuResId
- AFXMENUBAR/CMFCMenuBar::SetForceDownArrows
- AFXMENUBAR/CMFCMenuBar::SetMaximizeMode
- AFXMENUBAR/CMFCMenuBar::SetMenuButtonRTC
- AFXMENUBAR/CMFCMenuBar::SetMenuFont
- AFXMENUBAR/CMFCMenuBar::SetRecentlyUsedMenus
- AFXMENUBAR/CMFCMenuBar::SetShowAllCommands
dev_langs:
- C++
helpviewer_keywords:
- CMFCMenuBar class
ms.assetid: 8a3ce4c7-b012-4dc0-b4f8-53c10b4b86b8
caps.latest.revision: 36
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
ms.openlocfilehash: ab2896f5ebab0df894f70e5ddb85bae3a5e1d5af
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcmenubar-class"></a>CMFCMenuBar-Klasse
Eine Menüleiste, die Andocken implementiert.  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCMenuBar : public CMFCToolbar  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCMenuBar::AdjustLocations](#adjustlocations)|(Überschreibt `CMFCToolBar::AdjustLocations`.)|  
|[CMFCMenuBar::AllowChangeTextLabels](#allowchangetextlabels)|Gibt an, ob die Beschriftungen unter Images auf die Symbolleisten-Schaltflächen angezeigt werden können. (Überschreibt [CMFCToolBar::AllowChangeTextLabels](../../mfc/reference/cmfctoolbar-class.md#allowchangetextlabels).)|  
|[CMFCMenuBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(Überschreibt `CPane::AllowShowOnPaneMenu`.)|  
|[CMFCMenuBar::CalcFixedLayout](#calcfixedlayout)|Berechnet die horizontale Größe der Symbolleiste. (Überschreibt [CMFCToolBar::CalcFixedLayout](../../mfc/reference/cmfctoolbar-class.md#calcfixedlayout).)|  
|[CMFCMenuBar::CalcLayout](#calclayout)|(Überschreibt `CMFCToolBar::CalcLayout`.)|  
|[CMFCMenuBar::CalcMaxButtonHeight](#calcmaxbuttonheight)|Berechnet die maximale Höhe von Schaltflächen auf der Symbolleiste. (Überschreibt [CMFCToolBar::CalcMaxButtonHeight](../../mfc/reference/cmfctoolbar-class.md#calcmaxbuttonheight).)|  
|[CMFCMenuBar::CanBeClosed](#canbeclosed)|Gibt an, ob ein Benutzer auf die Symbolleiste schließen kann. (Überschreibt [CMFCToolBar::CanBeClosed](../../mfc/reference/cmfctoolbar-class.md#canbeclosed).)|  
|[CMFCMenuBar::CanBeRestored](#canberestored)|Bestimmt, ob das System nach der Anpassung eine Symbolleiste in seinen ursprünglichen Zustand wiederherstellen können. (Überschreibt [CMFCToolBar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|  
|[CMFCMenuBar::Create](#create)|Erstellt ein Steuerelement und fügt es ein `CMFCMenuBar` Objekt.|  
|[CMFCMenuBar::CreateEx](#createex)|Erstellt ein `CMFCMenuBar` -Objekt mit zusätzlichen Optionen.|  
|[CMFCMenuBar::CreateFromMenu](#createfrommenu)|Initialisiert ein `CMFCMenuBar` Objekt. Akzeptiert ein `HMENU` -Parameter, der als Vorlage für ein gefülltes `CMFCMenuBar`.|  
|[CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox)|Ermöglicht eine **Hilfe** Kombinationsfeld, das auf der rechten Seite der Menüleiste befindet.|  
|[CMFCMenuBar::EnableMenuShadows](#enablemenushadows)|Gibt an, ob Schatten für Popup-Menüs angezeigt.|  
|[CMFCMenuBar::GetAvailableExpandSize](#getavailableexpandsize)|(Überschreibt [CPane::GetAvailableExpandSize](../../mfc/reference/cpane-class.md#getavailableexpandsize).)|  
|[CMFCMenuBar::GetColumnWidth](#getcolumnwidth)|Gibt die Breite der Symbolleisten-Schaltflächen. (Überschreibt [CMFCToolBar::GetColumnWidth](../../mfc/reference/cmfctoolbar-class.md#getcolumnwidth).)|  
|[CMFCMenuBar::GetDefaultMenu](#getdefaultmenu)|Gibt ein Handle zum ursprünglichen Menü in der Ressourcendatei.|  
|[CMFCMenuBar::GetDefaultMenuResId](#getdefaultmenuresid)|Gibt den Ressourcenbezeichner des ursprünglichen Menüs in der Ressourcendatei.|  
|[CMFCMenuBar::GetFloatPopupDirection](#getfloatpopupdirection)||  
|[CMFCMenuBar::GetForceDownArrows](#getforcedownarrows)||  
|[CMFCMenuBar::GetHelpCombobox](#gethelpcombobox)|Gibt einen Zeiger auf die **Hilfe** Kombinationsfeld.|  
|[CMFCMenuBar::GetHMenu](#gethmenu)|Gibt das Handle für das Menü, das zugeordnet ist die `CMFCMenuBar` Objekt.|  
|[CMFCMenuBar::GetMenuFont](#getmenufont)|Gibt die aktuelle globale Schriftart für Menu-Objekte zurück.|  
|[CMFCMenuBar::GetMenuItem](#getmenuitem)|Gibt die Symbolleisten-Schaltfläche zugeordneten Index des angegebenen Elements zurück.|  
|[CMFCMenuBar::GetRowHeight](#getrowheight)|Gibt die Höhe der Symbolleisten-Schaltflächen. (Überschreibt [CMFCToolBar::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|  
|[CMFCMenuBar::GetSystemButton](#getsystembutton)||  
|[CMFCMenuBar::GetSystemButtonsCount](#getsystembuttonscount)||  
|[CMFCMenuBar::GetSystemMenu](#getsystemmenu)||  
|[CMFCMenuBar::HighlightDisabledItems](#highlightdisableditems)|Gibt an, ob es sich bei deaktivierten Menüeinträgen hervorgehoben werden.|  
|[CMFCMenuBar::IsButtonExtraSizeAvailable](#isbuttonextrasizeavailable)|Bestimmt, ob die Symbolleiste Schaltflächen angezeigt werden kann, die Rahmen erweitert haben. (Überschreibt [CMFCToolBar::IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable).)|  
|[CMFCMenuBar::IsHighlightDisabledItems](#ishighlightdisableditems)|Gibt an, ob deaktivierte Elemente hervorgehoben werden.|  
|[CMFCMenuBar::IsMenuShadows](#ismenushadows)|Gibt an, ob bei Popupmenüs Schatten gezeichnet werden.|  
|[CMFCMenuBar::IsRecentlyUsedMenus](#isrecentlyusedmenus)|Gibt an, ob die zuletzt verwendeten Befehle in der Menüleiste angezeigt werden.|  
|[CMFCMenuBar::IsShowAllCommands](#isshowallcommands)|Gibt an, ob Popupmenüs alle Befehle anzuzeigen.|  
|[CMFCMenuBar::IsShowAllCommandsDelay](#isshowallcommandsdelay)|Zeigt an, ob Menüs alle Befehle nach einer kurzen Verzögerung.|  
|[CMFCMenuBar::LoadState](#loadstate)|Lädt den Zustand der `CMFCMenuBar` -Objekt aus der Registrierung.|  
|[CMFCMenuBar::OnChangeHot](#onchangehot)|Vom Framework aufgerufen, wenn ein Benutzer eine Schaltfläche auf der Symbolleiste aktiviert. (Überschreibt [CMFCToolBar::OnChangeHot](../../mfc/reference/cmfctoolbar-class.md#onchangehot).)|  
|[CMFCMenuBar::OnDefaultMenuLoaded](#ondefaultmenuloaded)|Vom Framework aufgerufen, wenn ein Rahmenfenster mit Standardmenü aus der Ressourcendatei geladen.|  
|[CMFCMenuBar::OnSendCommand](#onsendcommand)|(Überschreibt `CMFCToolBar::OnSendCommand`.)|  
|[CMFCMenuBar::OnSetDefaultButtonText](#onsetdefaultbuttontext)|Vom Framework aufgerufen, wenn ein Menü im Anpassungsmodus und der Benutzer Text des Menüelements ändert.|  
|[CMFCMenuBar::OnToolHitTest](#ontoolhittest)|(Überschreibt `CMFCToolBar::OnToolHitTest`.)|  
|[CMFCMenuBar::PreTranslateMessage](#pretranslatemessage)|(Überschreibt `CMFCToolBar::PreTranslateMessage`.)|  
|[CMFCMenuBar::RestoreOriginalstate](#restoreoriginalstate)|Vom Framework aufgerufen, wenn ein Menü im Anpassungsmodus und der Benutzer wählt **zurücksetzen** für eine Menüleiste.|  
|[CMFCMenuBar::SaveState](#savestate)|Speichert den Zustand der `CMFCMenuBar` Objekt in der Registrierung.|  
|[CMFCMenuBar::SetDefaultMenuResId](#setdefaultmenuresid)|Legt den ursprüngliche Menü in der Ressourcendatei.|  
|[CMFCMenuBar::SetForceDownArrows](#setforcedownarrows)||  
|[CMFCMenuBar::SetMaximizeMode](#setmaximizemode)|Wird vom Framework aufgerufen, wenn ein untergeordnetes MDI-Fenster den Anzeigemodus ändert. Wenn die untergeordneten MDI-Fensters neu maximiert oder wird nicht mehr maximiert, aktualisiert diese Methode die Menüleiste.|  
|[CMFCMenuBar::SetMenuButtonRTC](#setmenubuttonrtc)|Legt fest, die Common Language Runtime-Klasse, die generiert wird, wenn der Benutzer die Menüschaltflächen dynamisch erstellt.|  
|[CMFCMenuBar::SetMenuFont](#setmenufont)|Legt die Schriftart für alle Menüs in der Anwendung fest.|  
|[CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus)|Gibt an, ob eine Menüleiste zuletzt verwendeten Befehle.|  
|[CMFCMenuBar::SetShowAllCommands](#setshowallcommands)|Gibt an, ob alle Befehle die Menüleiste angezeigt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCMenuBar` -Klasse ist eine Menüleiste, andockbaren Funktionen implementiert. Es ähnelt eine Symbolleiste, jedoch nicht geschlossen werden kann – es wird immer angezeigt.  
  
 `CMFCMenuBar`unterstützt die Option Menü zuletzt verwendeten Objekte anzeigen. Wenn diese Option aktiviert ist, die `CMFCMenuBar` zeigt nur eine Teilmenge der verfügbaren Befehle auf den ersten. Danach werden die zuletzt verwendeten Befehle zusammen mit der ursprünglichen Teilmenge der Befehle angezeigt. Darüber hinaus kann der Benutzer immer das Menü, um alle verfügbaren Befehle anzeigen erweitern. Folglich wird jeden Befehl verfügbaren konfiguriert, um ständig anzuzeigen oder um nur angezeigt, wenn sie vor kurzem ausgewählt wurde.  
  
 Verwenden einer `CMFCMenuBar` Objekt, in das Hauptfenster Frame-Objekt einbetten. Bei der Verarbeitung der `WM_CREATE` angezeigt wird, rufen Sie `CMFCMenuBar::Create` oder `CMFCMenuBar::CreateEx`. Unabhängig von der Funktion erstellen verwenden, übergeben Sie einen Zeiger an das Hauptrahmenfenster. Aktivieren Sie dann durch Aufrufen von Andocken [CFrameWndEx::EnableDocking](../../mfc/reference/cframewndex-class.md#enabledocking). Andocken von diesem Menü durch Aufrufen von [CFrameWndEx::DockPane](../../mfc/reference/cframewndex-class.md#dockpane).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCMenuBar` Klasse. Das Beispiel zeigt die Vorgehensweise beim Festlegen des Formats des Bereichs, aktivieren die Schaltfläche "anpassen", aktivieren das Hilfe, Schatten bei Popupmenüs aktivieren und Aktualisieren der Menüleiste. Dieser Codeausschnitt ist Teil der [IE Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_IEDemo&#1;](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]  
[!code-cpp[NVC_MFC_IEDemo&3;](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 `CMFCMenuBar`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxmenubar.h  
  
##  <a name="adjustlocations"></a>CMFCMenuBar::AdjustLocations  
 Passt die Positionen der Menüelemente in der Menüleiste.  
  
```  
virtual void AdjustLocations();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="allowchangetextlabels"></a>CMFCMenuBar::AllowChangeTextLabels  
 Bestimmt, ob die Beschriftungen unter Images in der Menüleiste zulässig sind.  
  
```  
virtual BOOL AllowChangeTextLabels() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` , wenn der Benutzer auswählen kann, um Beschriftungen unter Images anzuzeigen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="allowshowonpanemenu"></a>CMFCMenuBar::AllowShowOnPaneMenu  

  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="calcfixedlayout"></a>CMFCMenuBar::CalcFixedLayout  

  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bStretch`  
 [in] `bHorz`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="calclayout"></a>CMFCMenuBar::CalcLayout  

  
```  
virtual CSize CalcLayout(
    DWORD dwMode,  
    int nLength = -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwMode`  
 [in] `nLength`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="calcmaxbuttonheight"></a>CMFCMenuBar::CalcMaxButtonHeight  

  
```  
virtual int CalcMaxButtonHeight();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="canbeclosed"></a>CMFCMenuBar::CanBeClosed  

  
```  
virtual BOOL CanBeClosed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="canberestored"></a>CMFCMenuBar::CanBeRestored  

  
```  
virtual BOOL CanBeRestored() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="create"></a>CMFCMenuBar::Create  
 Erstellt ein Steuerelement und fügt es einer [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) Objekt.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = AFX_DEFAULT_TOOLBAR_STYLE,  
    UINT nID = AFX_IDW_MENUBAR);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pParentWnd`  
 Zeiger auf das übergeordnete Fenster für die neue `CMFCMenuBar` Objekt.  
  
 [in] `dwStyle`  
 Der Stil der neuen Menüleiste.  
  
 [in] `nID`  
 Die ID für das untergeordnete Fenster der Menüleiste.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn erfolgreich, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Nach der Konstruktion einer `CMFCMenuBar` -Objekt, Sie müssen `Create`. Diese Methode erstellt die `CMFCMenuBar` steuern und fügt es der `CMFCMenuBar` Objekt.  
  
 Weitere Informationen über Toolbar-Stile finden Sie unter [CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle).  
  
##  <a name="createex"></a>CMFCMenuBar::CreateEx  
 Erstellt eine [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) -Objekt mit dem angegebenen erweiterten Stile.  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = TBSTYLE_FLAT,  
    DWORD dwStyle = AFX_DEFAULT_TOOLBAR_STYLE,  
    CRect rcBorders = CRect(1,
    1,
    1,
    1),  
    UINT nID =AFX_IDW_MENUBAR);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pParentWnd`  
 Zeiger auf das übergeordnete Fenster des neuen `CMFCMenuBar` Objekt.  
  
 [in] `dwCtrlStyle`  
 Weitere Formate für die neue Menüleiste.  
  
 [in] `dwStyle`  
 Der Hauptunterschied Stil der neuen Menüleiste.  
  
 [in] `rcBorders`  
 Ein `CRect` Parameter, der angibt, die Größen für die Rahmen der `CMFCMenuBar` Objekt.  
  
 [in] `nID`  
 Die ID für das untergeordnete Fenster der Menüleiste.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Methode erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie sollten diese Funktion nicht verwenden [CMFCMenuBar::Create](#create) Wenn Sie Formatvorlagen neben dem Stil angeben möchten. Einige häufig verwendete zusätzliche Formate sind `TBSTYLE_TRANSPARENT` und `CBRS_TOP`.  
  
 Listen der zusätzliche Formate finden Sie unter [Symbolleisten-Steuerelements und Schaltflächenstile](http://msdn.microsoft.com/library/windows/desktop/bb760439), [Steuerelementtypen für die allgemeine](http://msdn.microsoft.com/library/windows/desktop/bb775498), und [allgemeine Fensterstile](http://msdn.microsoft.com/library/windows/desktop/ms632600).  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `CreateEx` Methode der `CMFCMenuBar` Klasse. Dieser Codeausschnitt ist Teil der [IE Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_IEDemo&#1;](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]  
[!code-cpp[NVC_MFC_IEDemo&#2;](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_3.cpp)]  
  
##  <a name="createfrommenu"></a>CMFCMenuBar::CreateFromMenu  
 Initialisiert eine [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) Objekt. Diese Methode Modelle der `CMFCMenuBar` Objekts, nachdem ein `HMENU` Parameter.  
  
```  
virtual void CreateFromMenu(
    HMENU hMenu,  
    BOOL bDefaultMenu = FALSE,  
    BOOL bForceUpdate = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hMenu`  
 Ein Handle für eine Ressource. `CreateFromMenu`verwendet diese Ressource als Vorlage für die `CMFCMenuBar`.  
  
 [in] `bDefaultMenu`  
 Ein boolescher Wert, der angibt, ob das neue Menü Standardmenü ist.  
  
 [in] `bForceUpdate`  
 Ein boolescher Wert, der angibt, ob diese Methode erzwingt, ein Update im Menü dass.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, wenn Sie möchten, dass ein Menüsteuerelement haben die gleichen Menüelemente als Menüressource im. Sie rufen Sie diese Methode aufrufen, nachdem Sie entweder [CMFCMenuBar::Create](#create) oder [CMFCMenuBar::CreateEx](#createex).  
  
##  <a name="enablehelpcombobox"></a>CMFCMenuBar::EnableHelpCombobox  
 Ermöglicht eine **Hilfe** Kombinationsfeld, das auf der rechten Seite der Menüleiste befindet.  
  
```  
void EnableHelpCombobox(
    UINT uiID,  
    LPCTSTR lpszPrompt = NULL,  
    int nComboBoxWidth = 150);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiID`  
 Die Befehls-ID für die Schaltfläche für die **Hilfe** Kombinationsfeld.  
  
 [in] `lpszPrompt`  
 Eine Zeichenfolge, die den Text, den vom Framework im Kombinationsfeld angezeigt wird enthält, wenn er leer ist und nicht aktiv ist. Z. B. "Geben Sie hier den Text".  
  
 [in] `nComboBoxWidth`  
 Die Breite der Schaltfläche für das Kombinationsfeld in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Die **Hilfe** Kombinationsfeld ähnelt der **Hilfe** Kombinationsfeld in der Menüleiste des [!INCLUDE[ofprword](../../mfc/reference/includes/ofprword_md.md)].  
  
 Wenn Sie beim Aufrufen dieser Methode `uiID` auf 0 festgelegt wird, diese Methode blendet das Kombinationsfeld. Andernfalls zeigt diese Methode das Kombinationsfeld automatisch auf der rechten Seite der Menüleiste. Nachdem Sie diese Methode aufrufen, rufen Sie [CMFCMenuBar::GetHelpCombobox](#gethelpcombobox) ein Zeiger auf die eingefügten [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) Objekt.  
  
##  <a name="enablemenushadows"></a>CMFCMenuBar::EnableMenuShadows  
 Aktiviert Schatten bei Popupmenüs.  
  
```  
static void EnableMenuShadows(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 Ein boolescher Parameter, der angibt, ob bei Popupmenüs Schatten aktiviert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Der Algorithmus, den diese Methode verwendet, ist komplex und kann die Leistung Ihrer Anwendung auf langsameren Systemen verringern.  
  
##  <a name="getavailableexpandsize"></a>CMFCMenuBar::GetAvailableExpandSize  

  
```  
virtual int GetAvailableExpandSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcolumnwidth"></a>CMFCMenuBar::GetColumnWidth  

  
```  
virtual int GetColumnWidth() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getdefaultmenu"></a>CMFCMenuBar::GetDefaultMenu  
 Ruft ein Handle für das ursprüngliche Menü ab. Das Framework lädt im ursprüngliche Menü aus der Ressourcendatei.  
  
```  
HMENU GetDefaultMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für eine Ressource.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Ihre Anwendung ein Menü anpasst, können Sie diese Methode, um ein Handle für das ursprüngliche Menü abzurufen.  
  
##  <a name="getdefaultmenuresid"></a>CMFCMenuBar::GetDefaultMenuResId  
 Ruft den Ressourcenbezeichner für das Standardmenü ab.  
  
```  
UINT GetDefaultMenuResId() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Bezeichner für den Menü-Ressource.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework lädt das Standardmenü für die `CMFCMenuBar` Objekt aus der Ressourcendatei.  
  
##  <a name="getfloatpopupdirection"></a>CMFCMenuBar::GetFloatPopupDirection  

  
```  
int GetFloatPopupDirection(CMFCToolBarMenuButton* pButton);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pButton`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getforcedownarrows"></a>CMFCMenuBar::GetForceDownArrows  

  
```  
BOOL GetForceDownArrows();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gethelpcombobox"></a>CMFCMenuBar::GetHelpCombobox  
 Gibt einen Zeiger auf die **Hilfe** Kombinationsfeld.  
  
```  
CMFCToolBarComboBoxButton* GetHelpCombobox();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die **Hilfe** Kombinationsfeld. `NULL`Wenn die **Hilfe** Kombinationsfeld ausgeblendet oder nicht aktiviert.  
  
### <a name="remarks"></a>Hinweise  
 Die **Hilfe** Kombinationsfeld befindet sich auf der rechten Seite der Menüleiste. Rufen Sie die Methode [CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox) dieses Kombinationsfeld zu aktivieren.  
  
##  <a name="gethmenu"></a>CMFCMenuBar::GetHMenu  
 Ruft das Handle für das Menü an der der [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) Objekt.  
  
```  
HMENU GetHMenu() const;  
```  
  
##  <a name="getmenufont"></a>CMFCMenuBar::GetMenuFont  
 Ruft den aktuellen Menüschriftart ab.  
  
```  
static const CFont& GetMenuFont(BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bHorz`  
 Ein boolescher Parameter, der angibt, ob die horizontale oder vertikale Schriftart zurückgegeben. `TRUE`Gibt die horizontale Schriftart an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CFont](../../mfc/reference/cfont-class.md) Parameter, der die aktuelle Menüleiste Schriftart enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die zurückgegebene Schriftart ist ein globaler Parameter für die Anwendung. Zwei globale Schriftarten bleiben für alle `CMFCMenuBar` Objekte. Diese separaten Schriftarten werden für die horizontale und vertikale Menüleisten verwendet.  
  
##  <a name="getmenuitem"></a>CMFCMenuBar::GetMenuItem  
 Ruft eine [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) Objekt auf einer Menüleiste basierend auf den Index des Elements.  
  
```  
CMFCToolBarButton* GetMenuItem(int iItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iItem`  
 Der Index des zurückzugebenden Menüelements im.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `CMFCToolBarButton` -Objekt, das den angegebenen Index entspricht `iItem`. `NULL`Wenn der Index ungültig ist.  
  
##  <a name="getrowheight"></a>CMFCMenuBar::GetRowHeight  

  
```  
virtual int GetRowHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getsystembutton"></a>CMFCMenuBar::GetSystemButton  

  
```  
CMFCToolBarMenuButtonsButton* GetSystemButton(
    UINT uiBtn,  
    BOOL bByCommand = TRUE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiBtn`  
 [in] `bByCommand`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getsystembuttonscount"></a>CMFCMenuBar::GetSystemButtonsCount  

  
```  
int GetSystemButtonsCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getsystemmenu"></a>CMFCMenuBar::GetSystemMenu  

  
```  
CMFCToolBarSystemMenuButton* GetSystemMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="highlightdisableditems"></a>CMFCMenuBar::HighlightDisabledItems  
 Steuert, ob das Framework deaktivierten Menüeinträgen hervorgehoben.  
  
```  
static void HighlightDisabledItems(BOOL bHighlight = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bHighlight`  
 Ein boolescher Parameter, der angibt, ob das Framework nicht verfügbare Menüelemente hervorhebt.  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung markieren das Framework nicht Menüelemente nicht verfügbar, wenn der Benutzer den Mauszeiger darauf positioniert.  
  
##  <a name="isbuttonextrasizeavailable"></a>CMFCMenuBar::IsButtonExtraSizeAvailable  

  
```  
virtual BOOL IsButtonExtraSizeAvailable() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ishighlightdisableditems"></a>CMFCMenuBar::IsHighlightDisabledItems  
 Gibt an, ob das Framework nicht verfügbare Menüelemente hervorhebt.  
  
```  
static BOOL IsHighlightDisabledItems();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn nicht verfügbare Menüelemente hervorgehoben werden. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung markieren das Framework nicht Menüelemente nicht verfügbar, wenn der Benutzer den Mauszeiger darauf positioniert. Verwenden der [CMFCMenuBar::HighlightDisabledItems](#highlightdisableditems) Methode, um diese Funktion zu aktivieren.  
  
##  <a name="ismenushadows"></a>CMFCMenuBar::IsMenuShadows  
 Gibt an, ob das Framework Schatten bei Popupmenüs zeichnet.  
  
```  
static BOOL IsMenuShadows();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Framework Menü Schatten gezeichnet; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCMenuBar::EnableMenuShadows](#enablemenushadows) Methode, um diese Funktion aktivieren oder deaktivieren.  
  
##  <a name="isrecentlyusedmenus"></a>CMFCMenuBar::IsRecentlyUsedMenus  
 Gibt an, ob die zuletzt verwendeten Befehle in der Menüleiste angezeigt werden.  
  
```  
static BOOL IsRecentlyUsedMenus();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CMFCMenuBar` Objekt zeigt die zuletzt verwendeten Befehle im Menü, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie die Funktion [CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus) steuern, ob die Menüleiste vor kurzem zeigt Befehle im Menü verwendet.  
  
##  <a name="isshowallcommands"></a>CMFCMenuBar::IsShowAllCommands  
 Gibt an, ob Menüs alle Befehle anzuzeigen.  
  
```  
static BOOL IsShowAllCommands();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CMFCMenuBar` zeigt alle Befehle, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein `CMFCMenuBar` Objekt konfiguriert werden, um alle Befehle anzeigen oder nur eine Teilmenge der Befehle angezeigt. Weitere Informationen zu dieser Funktion finden Sie unter [CMFCMenuBar Klasse](../../mfc/reference/cmfcmenubar-class.md).  
  
 `IsShowAllCommands`informiert Sie darüber, wie dieses Feature konfiguriert ist, für die `CMFCMenuBar` Objekt. Um zu steuern, welche Befehle im Menü angezeigt werden, verwenden Sie die Methoden [CMFCMenuBar::SetShowAllCommands](#setshowallcommands) und [CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus).  
  
##  <a name="isshowallcommandsdelay"></a>CMFCMenuBar::IsShowAllCommandsDelay  
 Gibt an, ob die [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) Objekt zeigt alle Befehle nach einer kurzen Verzögerung.  
  
```  
static BOOL IsShowAllCommandsDelay();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Menüleiste Menüs nach einer kurzen Verzögerung angezeigt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie eine Menüleiste, um Anzeigeelemente, die zuletzt verwendeten konfigurieren, zeigt die Menüleiste das vollständige Menü auf zwei Arten:  
  
-   Das vollständige Menü nach programmierten verzögert, wenn der Benutzer den Cursor auf den Pfeil am unteren Rand des Menüs bewegt wird angezeigt.  
  
-   Zeigen Sie vollständige Menü an, nachdem der Benutzer auf den Pfeil nach unten im Menü klickt.  
  
 In der Standardeinstellung alle `CMFCMenuBar` Objekte verwenden Sie die Option nach einer kurzen Verzögerung das vollständige Menü angezeigt. Diese Option kann nicht geändert werden programmgesteuert in die `CMFCMenuBar` Klasse. Jedoch ein Benutzer kann ändern das Verhalten beim Anpassen von Symbolleisten mithilfe der **anpassen** Dialogfeld...  
  
##  <a name="loadstate"></a>CMFCMenuBar::LoadState  
 Lädt den Zustand der Menüleiste in der Windows-Registrierung.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT)-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Eine Zeichenfolge, die den Pfad der Windows-Registrierungsschlüssel enthält.  
  
 [in] `nIndex`  
 Die Steuerelement-ID für die Menüleiste.  
  
 [in] `uiID`  
 Ein reservierter Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich war; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCMenuBar::SaveState](#savestate) Methode, um den Status der Menüleiste in der Registrierung speichern. Die gespeicherte Informationen enthält die Menüelemente, die Dock-Status und die Position der Menüleiste.  
  
 In den meisten Fällen wird Ihre Anwendung nicht aufrufen `LoadState`. Das Framework ruft diese Methode auf, bei der Initialisierung des Arbeitsbereichs.  
  
##  <a name="onchangehot"></a>CMFCMenuBar::OnChangeHot  

  
```  
virtual void OnChangeHot(int iHot);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iHot`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondefaultmenuloaded"></a>CMFCMenuBar::OnDefaultMenuLoaded  
 Das Framework ruft diese Methode, wenn die Ressource aus der Ressourcendatei geladen.  
  
```  
virtual void OnDefaultMenuLoaded(HMENU hMenu);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hMenu`  
 Das Handle für das Menü angefügt, um die `CMFCMenuBar` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um benutzerdefinierten Code auszuführen, nachdem das Framework eine Ressource aus der Ressourcendatei geladen.  
  
##  <a name="onsendcommand"></a>CMFCMenuBar::OnSendCommand  

  
```  
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pButton`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onsetdefaultbuttontext"></a>CMFCMenuBar::OnSetDefaultButtonText  
 Das Framework ruft diese Methode auf, wenn der Benutzer den Text eines Elements in der Menüleiste ändert.  
  
```  
virtual BOOL OnSetDefaultButtonText(CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pButton`  
 Ein Zeiger auf die [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) -Objekt, das der Benutzer möchte anpassen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Framework die ändert der Menüleiste gilt. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung für diese Methode ändert den Text der Schaltfläche auf den Text, den der Benutzer bereitstellt.  
  
##  <a name="ontoolhittest"></a>CMFCMenuBar::OnToolHitTest  

  
```  
virtual INT_PTR OnToolHitTest(
    CPoint point,  
    TOOLINFO* pTI) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 [in] `pTI`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="pretranslatemessage"></a>CMFCMenuBar::PreTranslateMessage  

  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMsg`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="restoreoriginalstate"></a>CMFCMenuBar::RestoreOriginalstate  
 Vom Framework aufgerufen, wenn der Benutzer auswählt **zurücksetzen** aus der **anpassen** Dialogfeld.  
  
```  
virtual BOOL RestoreOriginalstate();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Methode erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, wenn der Benutzer auswählt **zurücksetzen** Menü anpassen. Sie können diese Methode, um programmgesteuert auf den Zustand der Menüleiste zurücksetzen auch manuell aufrufen. Diese Methode lädt den ursprünglichen Zustand aus der Ressourcendatei.  
  
 Diese Methode überschreiben, sollten Sie Verarbeitung bei der Auswahl der **zurücksetzen** Option.  
  
##  <a name="savestate"></a>CMFCMenuBar::SaveState  
 Speichert den Zustand der [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) Objekt, das die Windows-Registrierung.  
  
```  
virtual BOOL SaveState (
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT)-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Eine Zeichenfolge, die den Pfad der Windows-Registrierungsschlüssel enthält.  
  
 [in] `nIndex`  
 Die Steuerelement-ID für die Menüleiste.  
  
 [in] `uiID`  
 Ein reservierter Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Bei Erfolg; andernfalls `FALSE`;  
  
### <a name="remarks"></a>Hinweise  
 Die Anwendung wird in der Regel nicht aufgerufen `SaveState`. Das Framework ruft diese Methode, wenn der Arbeitsbereich serialisiert wird. Weitere Informationen finden Sie unter [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate).  
  
 Die gespeicherte Informationen enthält die Menüelemente, die Dock-Status und die Position der Menüleiste.  
  
##  <a name="setdefaultmenuresid"></a>CMFCMenuBar::SetDefaultMenuResId  
 Legt das Standardmenü für eine [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) -Objekts basierend auf den Ressourcen-ID.  
  
```  
void SetDefaultMenuResId(UINT uiResId);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiResId`  
 Die Ressourcen-ID für das neue Standardmenü.  
  
### <a name="remarks"></a>Hinweise  
 Die [CMFCMenuBar::RestoreOriginalstate](#restoreoriginalstate) Methode wiederherstellt Standardmenü aus der Ressourcendatei.  
  
 Verwenden der [CMFCMenuBar::GetDefaultMenuResId](#getdefaultmenuresid) Methode, um das Standardmenü abzurufen, ohne ihn wiederherzustellen.  
  
##  <a name="setforcedownarrows"></a>CMFCMenuBar::SetForceDownArrows  

  
```  
void SetForceDownArrows(BOOL bValue);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bValue`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setmaximizemode"></a>CMFCMenuBar::SetMaximizeMode  
 Das Framework ruft diese Methode auf, wenn eine MDI seine Darstellung ändert und die Menüleiste aktualisiert werden muss.  
  
```  
void SetMaximizeMode(
    BOOL bMax,  
    CWnd* pWnd = NULL,  
    BOOL bRecalcLayout = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bMax`  
 Ein boolescher Wert, der den Modus angibt. Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
 [in] `pWnd`  
 Ein Zeiger auf die untergeordneten MDI-Fensters, die geändert wird.  
  
 [in] `bRecalcLayout`  
 Ein boolescher Wert, der angibt, ob das Layout der Menüleiste sofort neu berechnet werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein untergeordnetes MDI-Fenster maximiert wird, an der das untergeordnete MDI-Hauptrahmenfenster Menüleiste das Systemmenü und die **Minimieren**, **Maximieren** und **schließen** Schaltflächen. Wenn `bMax` ist `TRUE` und `pWnd` nicht `NULL`, das untergeordnete MDI-Fenster wird maximiert und die Menüleiste muss die zusätzlichen Steuerelemente integrieren. Andernfalls gibt die Menüleiste auf den normalen Zustand.  
  
##  <a name="setmenubuttonrtc"></a>CMFCMenuBar::SetMenuButtonRTC  
 Legt die Laufzeit-Klasseninformationen, die das Framework verwendet wird, wenn der Benutzer Menüschaltflächen erstellt.  
  
```  
void SetMenuButtonRTC(CRuntimeClass* pMenuButtonRTC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMenuButtonRTC`  
 Die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) für eine Klasse, die von abgeleiteten der [CMFCMenuButton Klasse](../../mfc/reference/cmfcmenubutton-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Benutzer neue Schaltflächen auf der Menüleiste hinzufügt, erstellt das Framework die Schaltflächen dynamisch. Standardmäßig erstellt `CMFCMenuButton` Objekte. Überschreiben Sie diese Methode, um den Typ der Schaltflächenobjekte ändern, die das Framework erstellt.  
  
##  <a name="setmenufont"></a>CMFCMenuBar::SetMenuFont  
 Legt die Schriftart für alle Menüleisten in Ihrer Anwendung.  
  
```  
static BOOL SetMenuFont(
    LPLOGFONT lpLogFont,  
    BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpLogFont`  
 Ein Zeiger auf eine ["LogFont"](http://msdn.microsoft.com/library/windows/desktop/bb773327) -Struktur, die Schriftart fest definiert.  
  
 [in] `bHorz`  
 True, wenn Sie möchten die `lpLogFont` Parameter für die vertikale Schriftart FALSE verwendet werden, wenn für horizontale Schriftart verwendet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich war; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Zwei Schriftarten wird für alle `CMFCMenuBar` Objekte. Diese separaten Schriftarten werden für die horizontale und vertikale Menüleisten verwendet.  
  
 Schriftarten sind globale Variablen und wirken sich auf alle `CMFCMenuBar` Objekte.  
  
##  <a name="setrecentlyusedmenus"></a>CMFCMenuBar::SetRecentlyUsedMenus  
 Steuerelemente, die Befehle im Menü eine Menüleiste, ob vor kurzem zeigt verwendet werden.  
  
```  
static void SetRecentlyUsedMenus (BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bOn`  
 Ein boolescher Wert, der steuert, ob die zuletzt verwendeten Befehle angezeigt werden.  
  
##  <a name="setshowallcommands"></a>CMFCMenuBar::SetShowAllCommands  
 Steuert, ob ein Menü werden alle verfügbaren Befehle angezeigt.  
  
```  
static void SetShowAllCommands(BOOL bShowAllCommands = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShowAllCommands`  
 Ein boolescher Parameter, der angibt, ob die Menübefehle im Popupmenü angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
 Die Menübefehle in ein Menü nicht angezeigt wird, blendet die Befehle, die selten verwendet werden. Weitere Informationen zum Anzeigen von Menübefehlen, finden Sie unter [CMFCMenuBar Klasse](../../mfc/reference/cmfcmenubar-class.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)

