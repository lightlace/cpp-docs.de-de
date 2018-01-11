---
title: CMFCToolBarMenuButton Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarMenuButton
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::CMFCToolBarMenuButton
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::CompareWith
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::CopyFrom
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::CreateFromMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::CreateMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::CreatePopupMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::EnableQuickCustomize
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::GetCommands
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::GetImageRect
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::GetPaletteRows
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::GetPopupMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::HasButton
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::HaveHotBorder
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsBorder
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsClickedOnMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsDroppedDown
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsEmptyMenuAllowed
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsExclusive
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsMenuPaletteMode
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsQuickMode
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsTearOffMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnAfterCreatePopupMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnBeforeDrag
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnCalculateSize
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnCancelMode
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnChangeParentWnd
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnClick
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnClickMenuItem
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnContextHelp
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnDraw
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnDrawOnCustomizeList
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OpenPopupMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::ResetImageToDefault
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::SaveBarState
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::Serialize
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::SetACCData
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::SetMenuOnly
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::SetMenuPaletteMode
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::SetMessageWnd
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::SetRadio
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::SetTearOff
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::DrawDocumentIcon
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::m_bAlwaysCallOwnerDraw
dev_langs: C++
helpviewer_keywords:
- CMFCToolBarMenuButton [MFC], CMFCToolBarMenuButton
- CMFCToolBarMenuButton [MFC], CompareWith
- CMFCToolBarMenuButton [MFC], CopyFrom
- CMFCToolBarMenuButton [MFC], CreateFromMenu
- CMFCToolBarMenuButton [MFC], CreateMenu
- CMFCToolBarMenuButton [MFC], CreatePopupMenu
- CMFCToolBarMenuButton [MFC], EnableQuickCustomize
- CMFCToolBarMenuButton [MFC], GetCommands
- CMFCToolBarMenuButton [MFC], GetImageRect
- CMFCToolBarMenuButton [MFC], GetPaletteRows
- CMFCToolBarMenuButton [MFC], GetPopupMenu
- CMFCToolBarMenuButton [MFC], HasButton
- CMFCToolBarMenuButton [MFC], HaveHotBorder
- CMFCToolBarMenuButton [MFC], IsBorder
- CMFCToolBarMenuButton [MFC], IsClickedOnMenu
- CMFCToolBarMenuButton [MFC], IsDroppedDown
- CMFCToolBarMenuButton [MFC], IsEmptyMenuAllowed
- CMFCToolBarMenuButton [MFC], IsExclusive
- CMFCToolBarMenuButton [MFC], IsMenuPaletteMode
- CMFCToolBarMenuButton [MFC], IsQuickMode
- CMFCToolBarMenuButton [MFC], IsTearOffMenu
- CMFCToolBarMenuButton [MFC], OnAfterCreatePopupMenu
- CMFCToolBarMenuButton [MFC], OnBeforeDrag
- CMFCToolBarMenuButton [MFC], OnCalculateSize
- CMFCToolBarMenuButton [MFC], OnCancelMode
- CMFCToolBarMenuButton [MFC], OnChangeParentWnd
- CMFCToolBarMenuButton [MFC], OnClick
- CMFCToolBarMenuButton [MFC], OnClickMenuItem
- CMFCToolBarMenuButton [MFC], OnContextHelp
- CMFCToolBarMenuButton [MFC], OnDraw
- CMFCToolBarMenuButton [MFC], OnDrawOnCustomizeList
- CMFCToolBarMenuButton [MFC], OpenPopupMenu
- CMFCToolBarMenuButton [MFC], ResetImageToDefault
- CMFCToolBarMenuButton [MFC], SaveBarState
- CMFCToolBarMenuButton [MFC], Serialize
- CMFCToolBarMenuButton [MFC], SetACCData
- CMFCToolBarMenuButton [MFC], SetMenuOnly
- CMFCToolBarMenuButton [MFC], SetMenuPaletteMode
- CMFCToolBarMenuButton [MFC], SetMessageWnd
- CMFCToolBarMenuButton [MFC], SetRadio
- CMFCToolBarMenuButton [MFC], SetTearOff
- CMFCToolBarMenuButton [MFC], DrawDocumentIcon
- CMFCToolBarMenuButton [MFC], m_bAlwaysCallOwnerDraw
ms.assetid: cfa50176-7e4b-4527-9904-86a1b48fc1bc
caps.latest.revision: "31"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e6c752d1b9570ce11e232020393cc6d7982baa80
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfctoolbarmenubutton-class"></a>CMFCToolBarMenuButton-Klasse
Eine Symbolleisten-Schaltfläche, die ein Popupmenü enthält.  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCToolBarMenuButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::CMFCToolBarMenuButton](#cmfctoolbarmenubutton)|Erstellt ein `CMFCToolBarMenuButton`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::CompareWith](#comparewith)|Vergleicht diese Instanz mit der bereitgestellten `CMFCToolBarButton` Objekt. (Überschreibt [CMFCToolBarButton::CompareWith](../../mfc/reference/cmfctoolbarbutton-class.md#comparewith).)|  
|[Cmfctoolbarmenubutton:: CopyFrom](#copyfrom)|Kopiert die Eigenschaften von einer anderen Symbolleistenschaltfläche auf die Schaltfläche mit den aktuellen. (Überschreibt [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|[CMFCToolBarMenuButton::CreateFromMenu](#createfrommenu)|Initialisiert das workflowsymbolleisten-Menü aus einem Windows-Menü-Handle.|  
|[CMFCToolBarMenuButton::CreateMenu](#createmenu)|Erstellt ein Windows-Menü, aus denen die Befehle in der Symbolleistenmenüs besteht. Gibt ein Handle für das Windows-Menü zurück.|  
|[Cmfctoolbarmenubutton:: CreatePopupMenu](#createpopupmenu)|Erstellt ein Popupmenü-Objekt ( [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md)) auf das workflowsymbolleisten-Menü anzuzeigen.|  
|[CMFCToolBarMenuButton::EnableQuickCustomize](#enablequickcustomize)||  
|[CMFCToolBarMenuButton::GetCommands](#getcommands)|Ermöglicht schreibgeschützten Zugriff auf die Liste der Befehle im Symbolleistenmenü.|  
|[CMFCToolBarMenuButton::GetImageRect](#getimagerect)|Ruft das umschließende Rechteck für das Schaltflächenbild ab.|  
|[CMFCToolBarMenuButton::GetPaletteRows](#getpaletterows)|Gibt die Anzahl der Zeilen im Popupmenü zurück, wenn das Menü im Palettenmodus befindet.|  
|[CMFCToolBarMenuButton::GetPopupMenu](#getpopupmenu)|Gibt einen Zeiger auf das Popupmenü-Objekt, das der Schaltfläche zugeordnet ist.|  
|[CMFCToolBarMenuButton::HasButton](#hasbutton)||  
|[CMFCToolBarMenuButton::HaveHotBorder](#havehotborder)|Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer die Schaltfläche auswählt. (Überschreibt [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|  
|[CMFCToolBarMenuButton::IsBorder](#isborder)||  
|[CMFCToolBarMenuButton::IsClickedOnMenu](#isclickedonmenu)||  
|[CMFCToolBarMenuButton::IsDroppedDown](#isdroppeddown)|Bestimmt, ob das Menü das Popupmenü angezeigt wird.|  
|[Cmfctoolbarmenubutton:: Isemptymenuallowed](#isemptymenuallowed)|Wird aufgerufen, durch das Framework, um zu bestimmen, ob ein Benutzer ein Untermenü des ausgewählten Menüelements öffnen kann.|  
|[CMFCToolBarMenuButton::IsExclusive](#isexclusive)|Bestimmt, ob die Schaltfläche mit der im exklusiven Modus, d. h. gibt an, ob das Menü das Popupmenü geöffnet bleibt, selbst wenn der Benutzer den Zeiger auf eine andere Symbolleiste oder die Schaltfläche richtet.|  
|[CMFCToolBarMenuButton::IsMenuPaletteMode](#ismenupalettemode)|Bestimmt, ob das Menü das Popupmenü im Palettenmodus befindet.|  
|[CMFCToolBarMenuButton::IsQuickMode](#isquickmode)||  
|[CMFCToolBarMenuButton::IsTearOffMenu](#istearoffmenu)|Bestimmt, ob das Menü das Popupmenü eine abtrennbarer Leiste verfügt.|  
|[CMFCToolBarMenuButton::OnAfterCreatePopupMenu](#onaftercreatepopupmenu)||  
|[CMFCToolBarMenuButton::OnBeforeDrag](#onbeforedrag)|Gibt an, ob die Schaltfläche gezogen werden kann. (Überschreibt [CMFCToolBarButton::OnBeforeDrag](../../mfc/reference/cmfctoolbarbutton-class.md#onbeforedrag).)|  
|[CMFCToolBarMenuButton::OnCalculateSize](#oncalculatesize)|Wird aufgerufen, durch das Framework die Größe der Schaltfläche für den angegebenen Gerätekontext und andockzustand berechnet. (Überschreibt [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|[CMFCToolBarMenuButton::OnCancelMode](#oncancelmode)|Wird aufgerufen, durch das Framework behandelt die [WM_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) Nachricht. (Überschreibt [CMFCToolBarButton::OnCancelMode](../../mfc/reference/cmfctoolbarbutton-class.md#oncancelmode).)|  
|[CMFCToolBarMenuButton::OnChangeParentWnd](#onchangeparentwnd)|Vom Framework aufgerufen, wenn die Schaltfläche "" in eine neue Symbolleiste eingefügt wird. (Überschreibt [CMFCToolBarButton::OnChangeParentWnd](cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCToolBarMenuButton::OnClick](#onclick)|Wird vom Framework aufgerufen, klickt der Benutzer die Maustaste los. (Überschreibt [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCToolBarMenuButton::OnClickMenuItem](#onclickmenuitem)|Wird vom Framework aufgerufen, wenn der Benutzer ein Element im Popupmenü auswählt.|  
|[CMFCToolBarMenuButton::OnContextHelp](#oncontexthelp)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste verarbeitet eine `WM_HELPHITTEST` Nachricht. (Überschreibt [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp).)|  
|[CMFCToolBarMenuButton::OnDraw](#ondraw)|Wird aufgerufen, durch das Framework der Schaltfläche gezeichnet werden soll, mithilfe des angegebenen Stile und Optionen. (Überschreibt [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|[CMFCToolBarMenuButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Wird aufgerufen, durch das Framework der Schaltfläche gezeichnet werden soll, der **Befehle** im Bereich der **anpassen** (Dialogfeld). (Überschreibt [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCToolBarMenuButton::OpenPopupMenu](#openpopupmenu)|Wird vom Framework aufgerufen, wenn der Benutzer über das Menü das Popupmenü öffnet.|  
|[CMFCToolBarMenuButton::ResetImageToDefault](#resetimagetodefault)|Legt das Bild, das der Schaltfläche zugeordnet ist, auf den Standardwert fest. (Überschreibt [CMFCToolBarButton::ResetImageToDefault](../../mfc/reference/cmfctoolbarbutton-class.md#resetimagetodefault).)|  
|[CMFCToolBarMenuButton::SaveBarState](#savebarstate)|Speichert den Zustand der Symbolleisten-Schaltfläche. (Überschreibt [CMFCToolBarButton::SaveBarState](../../mfc/reference/cmfctoolbarbutton-class.md#savebarstate).)|  
|[CMFCToolBarMenuButton::Serialize](#serialize)|Dieses Objekt aus einem Archiv liest oder schreibt sie in ein Archiv. (Überschreibt [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|[CMFCToolBarMenuButton::SetACCData](#setaccdata)|Füllt die angegebene `CAccessibilityData` Objekt mit Zugriff auf Daten aus der Symbolleisten-Schaltfläche. (Überschreibt [CMFCToolBarButton::SetACCData](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata).)|  
|[CMFCToolBarMenuButton::SetMenuOnly](#setmenuonly)|Gibt an, ob die Schaltfläche eine Symbolleiste hinzugefügt werden kann.|  
|[CMFCToolBarMenuButton::SetMenuPaletteMode](#setmenupalettemode)|Gibt an, ob das Menü das Popupmenü im Palettenmodus befindet.|  
|[CMFCToolBarMenuButton::SetMessageWnd](#setmessagewnd)||  
|[CMFCToolBarMenuButton::SetRadio](#setradio)|Erzwingt die Symbolleistenschaltfläche Menü, um ein Symbol gibt an, dass diese Option ausgewählt ist.|  
|[CMFCToolBarMenuButton::SetTearOff](#settearoff)|Gibt eine abtrennbare Leiste ID für das Menü das Popupmenü.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::DrawDocumentIcon](#drawdocumenticon)|Zeichnet ein Symbol auf die Schaltfläche.|  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::m_bAlwaysCallOwnerDraw](#m_balwayscallownerdraw)|Wenn `TRUE`, immer das Framework ruft [CFrameWndEx::OnDrawMenuImage](../../mfc/reference/cframewndex-class.md#ondrawmenuimage) bei eine Schaltfläche gezeichnet wird.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `CMFCToolBarMenuButton` angezeigt werden, ein Menü, ein Menüelement, das über ein Untermenü verfügt, eine Schaltfläche, die entweder einen Befehl ausführt, oder ein Menü zeigt oder eine Schaltfläche, die nur ein Menü angezeigt. Sie bestimmen das Verhalten und die Darstellung der Menüschaltfläche durch Angeben von Parametern, wie das Image, Text, Menü-Handle und Befehls-ID, die mit der Schaltfläche in den Konstruktor anfallen `CMFCToolbarMenuButton::CMFCToolbarMenuButton`.  
  
 Eine benutzerdefinierte abgeleitete Klasse die `CMFCToolbarMenuButton` Klasse verwenden, muss die [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) Makro. Die [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate) Makro wird ein Fehler generiert, wenn die Anwendung geschlossen wird.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Konfigurieren einer `CMFCToolBarMenuButton` Objekt. Im Code wird veranschaulicht, wie Sie angeben, dass das Dropdown-Menü im Palettenmodus befindet, und geben Sie die ID für die abtrennbarer Leiste, die erstellt wird, wenn der Benutzer auf die Menüschaltfläche aus einer Menüleiste zieht. Dieser Codeausschnitt ist Teil des [WordPad-Beispiels](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#10](../../mfc/reference/codesnippet/cpp/cmfctoolbarmenubutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtoolbarmenubutton.h  
  
##  <a name="cmfctoolbarmenubutton"></a>CMFCToolBarMenuButton::CMFCToolBarMenuButton  
 Erstellt ein `CMFCToolBarMenuButton`-Objekt.  
  
```  
CMFCToolBarMenuButton();
CMFCToolBarMenuButton(const CMFCToolBarMenuButton& src);

CMFCToolBarMenuButton(
    UINT uiID,  
    HMENU hMenu,  
    int iImage,  
    LPCTSTR lpszText=NULL,  
    BOOL bUserButton=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `src`  
 Eine vorhandene `CMFCToolBarMenuButton` Objekt in diese kopiert werden `CMFCToolBarMenuButton` Objekt.  
  
 [in] `uiID`  
 Die ID des Befehls ausführen, wenn ein Benutzer auf die Schaltfläche klickt. oder ( `UINT`)-1 für eine Menüschaltfläche, die nicht direkt einen Befehl ausgeführt wird.  
  
 [in] `hMenu`  
 Ein Handle zu einem Menü; oder `NULL` , wenn die Schaltfläche ein Menü nicht verfügt.  
  
 [in] `iImage`  
 Der Index des Bilds für die Schaltfläche ""; oder -1, wenn diese Schaltfläche verfügt nicht über ein Symbol oder das Symbol für den Befehl gemäß verwendet `uiID`. Der Index gilt für jede `CMFCToolBarImages` Objekten in der Anwendung.  
  
 [in] `lpszText`  
 Der Text der Symbolleisten-Schaltfläche im Menü.  
  
 [in] `bUserButton`  
 `TRUE`Wenn die Schaltfläche zeigt ein benutzerdefiniertes Image an. `FALSE` wird die Schaltfläche ein vordefiniertes Image mit dem Befehl angegeben werden, indem Sie verknüpfte angezeigt `uiID`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `uiID` ist eine gültige Befehls-ID, die Schaltfläche "" führt den Befehl aus, wenn der Benutzer darauf klickt. Wenn `hMenu` ist ein Handle gültige im Menü der Schaltfläche bietet ein Dropdown-Menü aus, wenn es in einer Symbolleiste oder ein Untermenü angezeigt wird, wenn es in einem Menü angezeigt wird. Wenn beide `uiID` und `hMenu` sind gültig ist, wird die Schaltfläche wird eine unterteilte Schaltfläche mit einem Teil, der der Befehl ausgeführt wird, wenn der Benutzer darauf klickt und einen Teil mit einem Pfeil nach unten, die ein Menü Dropdownelement wird der Benutzer darauf klickt. Jedoch wenn `hMenu` gültig ist, ein Benutzer wird nicht in der Lage, klicken Sie auf die Schaltfläche, um einen Befehl auszuführen, wenn die Schaltfläche in einem Menü eingefügt wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen von ein Objekt von der `CMFCToolBarMenuButton` Klasse. Dieser Codeausschnitt ist Teil des [WordPad-Beispiels](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#9](../../mfc/reference/codesnippet/cpp/cmfctoolbarmenubutton-class_2.cpp)]  
  
##  <a name="comparewith"></a>CMFCToolBarMenuButton::CompareWith  

  
```  
virtual BOOL CompareWith(const CMFCToolBarButton& other) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `other`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="copyfrom"></a>Cmfctoolbarmenubutton:: CopyFrom  

  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `src`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="createfrommenu"></a>CMFCToolBarMenuButton::CreateFromMenu  
 Initialisiert das workflowsymbolleisten-Menü aus einem Windows-Menü-Handle.  
  
```  
virtual void CreateFromMenu(HMENU hMenu);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hMenu`  
 Ein Handle für ein Menü.  
  
### <a name="remarks"></a>Hinweise  
 Eine Symbolleisten-Schaltfläche im Menü kann ein Dropdown-Untermenü angezeigt.  
  
 Das Framework ruft diese Methode, um die Befehle im Untermenü in einem Menü zu initialisieren.  
  
##  <a name="createmenu"></a>CMFCToolBarMenuButton::CreateMenu  
 Erstellt ein Menü, aus denen die Befehle in der Symbolleistenmenüs besteht. Gibt ein Handle für das Menü zurück.  
  
```  
virtual HMENU CreateMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein handle für klicken Sie im Menü, wenn erfolgreich. `NULL`Wenn die Liste der Befehle, die im Menü Symbolleistenschaltfläche zugeordnet leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode in einer abgeleiteten Klasse die Art und Weise anpassen, die generiert wird, klicken Sie im Menü überschreiben.  
  
##  <a name="createpopupmenu"></a>Cmfctoolbarmenubutton:: CreatePopupMenu  
 Erstellt eine `CMFCPopupMenu` -Objekt, das workflowsymbolleisten-Menü anzuzeigen.  
  
```  
virtual CMFCPopupMenu* CreatePopupMenu();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CMFCPopupMenu` -Objekt, das zeigt das Dropdown-Menü die Menüschaltfläche Symbolleiste zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework So bereiten Sie die Anzeige des Dropdown-Menüs mit der Schaltfläche verknüpften vor aufgerufen.  
  
 Die standardmäßige Implementierung einfach erstellt und gibt eine neue `CMFCPopupMenu` Objekt. Überschreiben Sie diese Methode, wenn einen abgeleiteten Typ von verwenden möchten [CMFCPopupMenu Klasse](cmfcpopupmenu-class.md) oder um eine zusätzliche Initialisierung auszuführen.  
  
##  <a name="drawdocumenticon"></a>CMFCToolBarMenuButton::DrawDocumentIcon  
 Zeichnet ein Symbol "Dokument" auf die Schaltfläche.  
  
```  
void DrawDocumentIcon(
    CDC* pDC,  
    const CRect& rectImage,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext.  
  
 [in] `rectImage`  
 Die Koordinaten des umschließenden Rechtecks Bilds.  
  
 [in] `hIcon`  
 Ein Handle für das Symbol ".  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode nimmt ein Symbol "Dokument" und zeichnet Sie es auf die Menüschaltfläche, die in den vom angegebenen Bereich zentriert `rectImage`.  
  
##  <a name="enablequickcustomize"></a>CMFCToolBarMenuButton::EnableQuickCustomize  

  
```  
void EnableQuickCustomize();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hasbutton"></a>CMFCToolBarMenuButton::HasButton  

  
```  
virtual BOOL HasButton() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="havehotborder"></a>CMFCToolBarMenuButton::HaveHotBorder  

  
```  
virtual BOOL HaveHotBorder() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isborder"></a>CMFCToolBarMenuButton::IsBorder  

  
```  
virtual BOOL IsBorder() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isclickedonmenu"></a>CMFCToolBarMenuButton::IsClickedOnMenu  

  
```  
BOOL IsClickedOnMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isquickmode"></a>CMFCToolBarMenuButton::IsQuickMode  

  
```  
BOOL IsQuickMode();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcommands"></a>CMFCToolBarMenuButton::GetCommands  
 Ermöglicht schreibgeschützten Zugriff auf die Liste der Befehle im Symbolleistenmenü.  
  
```  
const CObList& GetCommands() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein konstanter Verweis auf eine [CObList Klasse](../../mfc/reference/coblist-class.md) Objekt, das eine Auflistung von enthält [CMFCToolBarButton Klasse](../../mfc/reference/cmfctoolbarbutton-class.md) Objekte.  
  
### <a name="remarks"></a>Hinweise  
 Eine Symbolleisten-Schaltfläche im Menü kann ein Untermenü angezeigt. Sie können die Liste der Befehle im Untermenü im Konstruktor oder im Bereitstellen [CMFCToolBarMenuButton::CreateFromMenu](#createfrommenu) als ein Handle zu einem Menü ( `HMENU`). Klicken Sie im Menü wird konvertiert, um eine Liste von Objekten, die von der abgeleiteten [CMFCToolBarButton Klasse](../../mfc/reference/cmfctoolbarbutton-class.md) und gespeichert, in der internen `CObList` Objekt. Sie können diese Liste zugreifen, durch Aufruf dieser Methode.  
  
##  <a name="getimagerect"></a>CMFCToolBarMenuButton::GetImageRect  
 Ruft das umschließende Rechteck für das Schaltflächenbild ab.  
  
```  
void GetImageRect(CRect& rectImage);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rectImage`  
 Ein Verweis auf ein `CRect` Objekt, das die Koordinaten des umschließenden Rechtecks Bilds empfängt.  
  
##  <a name="getpaletterows"></a>CMFCToolBarMenuButton::GetPaletteRows  
 Gibt die Anzahl der Zeilen in der Dropdown-Menü zurück, wenn das Menü im Palettenmodus befindet.  
  
```  
int GetPaletteRows() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeilen in der Palette.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Menüschaltfläche Palette Modus festgelegt ist, werden der Menüelemente in mehreren Spalten mit nur einer begrenzten Anzahl von Zeilen angezeigt. Rufen Sie diese Methode, um die Anzahl der Zeilen zu erhalten. Aktivieren oder deaktivieren Palettenmodus und geben Sie die Anzahl der Zeilen, die mit [CMFCToolBarMenuButton::SetMenuPaletteMode](#setmenupalettemode).  
  
##  <a name="getpopupmenu"></a>CMFCToolBarMenuButton::GetPopupMenu  
 Gibt einen Zeiger auf die [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md) -Objekt, das Dropdownmenü neben der Schaltfläche darstellt.  
  
```  
CMFCPopupMenu* GetPopupMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md) -Objekt, das erstellt wurde, wenn das Framework das Untermenü der Symbolleiste Menüschaltfläche; gezeichnet wurde. `NULL` , wenn keine Untermenü angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Dropdown-Menü eine Menüschaltfläche Symbolleiste angezeigt wird, erstellt die Schaltfläche eine [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md) -Objekt, das Menü darstellen. Rufen Sie diese Methode, um einen Zeiger auf die `CMFCPopupMenu` Objekt. Da es temporär ist und wird ungültig, wenn der Benutzer im Dropdown-Menü geschlossen wird, sollten Sie nicht den zurückgegebenen Zeiger speichern.  
  
##  <a name="isdroppeddown"></a>CMFCToolBarMenuButton::IsDroppedDown  
 Gibt an, ob das Menü das Popupmenü derzeit angezeigt wird.  
  
```  
virtual BOOL IsDroppedDown() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Symbolleiste Menüschaltfläche seine Untermenü angezeigt werden; andernfalls `FALSE`.  
  
##  <a name="isemptymenuallowed"></a>Cmfctoolbarmenubutton:: Isemptymenuallowed  
 Gibt an, ob leere Untermenüs Menüelemente angezeigt wird.  
  
```  
virtual BOOL IsEmptyMenuAllowed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Framework ein Untermenü des aktuell ausgewählten Menüelements, öffnet selbst wenn das Untermenü leer ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn ein Benutzer versucht, das Untermenü des aktuell ausgewählten Menüelements zu öffnen. Wenn im Untermenü leer ist und `IsEmptyMenuAllowed` gibt `FALSE`, das Untermenü die Option kann nicht geöffnet werden.  
  
 Die Standardimplementierung gibt `FALSE` zurück. Überschreiben Sie diese Methode, um dieses Verhalten anzupassen.  
  
##  <a name="isexclusive"></a>CMFCToolBarMenuButton::IsExclusive  
 Gibt an, ob die Schaltfläche mit der im exklusiven Modus befindet.  
  
```  
virtual BOOL IsExclusive() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Schaltfläche im exklusiven Modus verwendet werden kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Benutzer ein Popupmenü für eine Schaltfläche öffnet, und klicken Sie dann den Mauszeiger über einem anderen Symbolleiste oder im Menü-Schaltfläche bewegt, schließt das Popupmenü, wenn die Schaltfläche im exklusiven Modus ist.  
  
 Gibt die standardmäßige Implementierung immer `FALSE`. Überschreiben Sie diese Methode in einer abgeleiteten Klasse, wenn Sie im exklusiven Modus aktivieren möchten.  
  
##  <a name="ismenupalettemode"></a>CMFCToolBarMenuButton::IsMenuPaletteMode  
 Bestimmt, ob der Dropdown-Menü im Palettenmodus befindet.  
  
```  
BOOL IsMenuPaletteMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Palettenmodus, andernfalls aktiviert ist `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Menüschaltfläche Palette Modus festgelegt ist, werden die Menüelemente in mehreren Spalten mit nur einer begrenzten Anzahl von Zeilen angezeigt. Rufen Sie diese Methode, um die Anzahl der Zeilen zu erhalten. Sie aktivieren oder deaktivieren Sie die Palettenmodus durch Aufrufen [CMFCToolBarMenuButton::SetMenuPaletteMode](#setmenupalettemode).  
  
##  <a name="istearoffmenu"></a>CMFCToolBarMenuButton::IsTearOffMenu  
 Gibt an, ob der Dropdown-Menü eine abtrennbarer Leiste verfügt.  
  
```  
virtual BOOL IsTearOffMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Symbolleiste Menüschaltfläche eine abtrennbarer Leiste enthält. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die abtrennbare-Funktion aktivieren und Festlegen der abtrennbare Strich-ID rufen [CMFCToolBarMenuButton::SetTearOff](#settearoff).  
  
##  <a name="m_balwayscallownerdraw"></a>CMFCToolBarMenuButton::m_bAlwaysCallOwnerDraw  
 Gibt an, ob das Framework immer ruft [CFrameWndEx::OnDrawMenuImage](../../mfc/reference/cframewndex-class.md#ondrawmenuimage) bei eine Schaltfläche gezeichnet wird.  
  
```  
static BOOL m_bAlwaysCallOwnerDraw;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Membervariable auf festgelegt ist `TRUE`, ruft Sie die Schaltfläche immer [CFrameWndEx::OnDrawMenuImage](../../mfc/reference/cframewndex-class.md#ondrawmenuimage) Methode zur Anzeige des Bilds auf der Schaltfläche. Wenn `m_bAlwaysCallOwnerDraw` ist `FALSE`, die Schaltfläche "selbst" zeichnet das Bild aus, wenn das Bild vordefiniert ist. Andernfalls ruft `OnDrawMenuImage`.  
  
##  <a name="onaftercreatepopupmenu"></a>CMFCToolBarMenuButton::OnAfterCreatePopupMenu  

  
```  
virtual void OnAfterCreatePopupMenu();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onbeforedrag"></a>CMFCToolBarMenuButton::OnBeforeDrag  

  
```  
virtual BOOL OnBeforeDrag() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="oncalculatesize"></a>CMFCToolBarMenuButton::OnCalculateSize  

  
```  
virtual SIZE OnCalculateSize(
    CDC* pDC,  
    const CSize& sizeDefault,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 [in] `sizeDefault`  
 [in] `bHorz`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="oncancelmode"></a>CMFCToolBarMenuButton::OnCancelMode  

  
```  
virtual void OnCancelMode();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onchangeparentwnd"></a>CMFCToolBarMenuButton::OnChangeParentWnd  

  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParent`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onclick"></a>CMFCToolBarMenuButton::OnClick  

  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 [in] `bDelay`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onclickmenuitem"></a>CMFCToolBarMenuButton::OnClickMenuItem  
 Wird vom Framework aufgerufen, wenn der Benutzer ein Element in der Dropdown-Menü auswählt.  
  
```  
virtual BOOL OnClickMenuItem();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `FALSE`Wenn das Framework das Standardmenü Element Verarbeitung fortgesetzt werden soll; andernfalls `TRUE`. Gibt die standardmäßige Implementierung immer `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer ein Menüelement klickt, führt das Framework einen Befehl, der dieses Element zugeordnet ist.  
  
 Um die Verarbeitung der Arbeitsaufgabe Menü anzupassen, überschreiben `OnClickMenuItem` in einer abgeleiteten Klasse `CMFCToolBarMenuButton` Klasse. Sie müssen auch überschreiben [CFrameWndEx::OnShowPopupMenu](../../mfc/reference/cframewndex-class.md#onshowpopupmenu) , und Ersetzen Sie die Menüschaltflächen, die mit Instanzen der abgeleiteten Klasse besondere Verarbeitung erforderlich ist.  
  
##  <a name="oncontexthelp"></a>CMFCToolBarMenuButton::OnContextHelp  

  
```  
virtual BOOL OnContextHelp(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondraw"></a>CMFCToolBarMenuButton::OnDraw  

  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    CMFCToolBarImages* pImages,  
    BOOL bHorz = TRUE,  
    BOOL bCustomizeMode = FALSE,  
    BOOL bHighlight = FALSE,  
    BOOL bDrawBorder = TRUE,  
    BOOL bGrayDisabledButtons = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 [in] `rect`  
 [in] `pImages`  
 [in] `bHorz`  
 [in] `bCustomizeMode`  
 [in] `bHighlight`  
 [in] `bDrawBorder`  
 [in] `bGrayDisabledButtons`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondrawoncustomizelist"></a>CMFCToolBarMenuButton::OnDrawOnCustomizeList  

  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 [in] `rect`  
 [in] `bSelected`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="openpopupmenu"></a>CMFCToolBarMenuButton::OpenPopupMenu  
 Wird vom Framework aufgerufen, wenn der Benutzer auf die Dropdown-Menü einer Menüschaltfläche Symbolleiste öffnet.  
  
```  
virtual BOOL OpenPopupMenu(CWnd* pWnd=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Gibt an, das Fenster, das die Befehle im Dropdownmenü empfängt. Es kann sein `NULL` nur dann, wenn die Symbolleiste Menüschaltfläche ein übergeordnetes Fenster.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn eine [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md) Objekt wurde erstellt und geöffnet wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird vom Framework aufgerufen, wenn der Benutzer ein Dropdown-Menü aus einer Symbolleisten-Schaltfläche im Menü geöffnet wird.  
  
##  <a name="resetimagetodefault"></a>CMFCToolBarMenuButton::ResetImageToDefault  

  
```  
virtual void ResetImageToDefault();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="savebarstate"></a>CMFCToolBarMenuButton::SaveBarState  

  
```  
virtual void SaveBarState();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn es eine Symbolleisten-Schaltfläche als Ergebnis eines Drag-and-Drop-Vorgangs erstellt. Diese Methode ruft die [CMFCPopupMenu::SaveState](../../mfc/reference/cmfcpopupmenu-class.md#savestate) Methode von der obersten Ebene im Popupmenü, wodurch die übergeordnete Schaltfläche im Popupmenü Menüs neu zu erstellen.  
  
##  <a name="serialize"></a>CMFCToolBarMenuButton::Serialize  

  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `ar`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setaccdata"></a>CMFCToolBarMenuButton::SetACCData  
 Legt die Barrierefreiheitsdaten für das Menübandelement fest.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parameter  
 `pParent`  
 Das übergeordnete Fenster für die Menübandelement.  
  
 `data`  
 Die Barrierefreiheitsdaten für das Menübandelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig legt diese Methode die Barrierefreiheitsdaten für das Menübandelement fest und gibt immer `TRUE`zurück. Setzen Sie diese Methode außer Kraft, um die Barrierefreiheitsdaten festzulegen und einen Wert zurückzugeben, der den Erfolg oder einen Fehler angibt.  
  
##  <a name="setmenuonly"></a>CMFCToolBarMenuButton::SetMenuOnly  
 Gibt an, ob die Schaltfläche "" als einer Menüschaltfläche oder eine unterteilte Schaltfläche gezeichnet wird, wenn sie eine gültige Befehls-ID und ein Untermenü verfügt.  
  
```  
void SetMenuOnly(BOOL bMenuOnly);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bMenuOnly`  
 `TRUE`Diese Schaltfläche als einer Menüschaltfläche angezeigt, wenn sie eine gültige Befehls-ID und ein Untermenü verfügt `FALSE` auf diese Schaltfläche als eine unterteilte Schaltfläche anzeigen, wenn sie eine gültige Befehls-ID und ein Untermenü verfügt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Symbolleisten-Schaltfläche im Menü ein Untermenü und eine Befehls-ID aufweist, wird das Menü in der Regel eine unterteilte Schaltfläche sein, die eine Hauptschaltfläche und eine angefügte nach-unten-Taste. Wenn Sie diese Methode aufrufen und `bMenuOnly` ist `TRUE`, die Schaltfläche stattdessen zu einer einzelnen Menüschaltfläche mit einem Pfeil in der Schaltfläche angezeigt. Klickt der Benutzer auf den Pfeil in beiden Modi, das Untermenü wird geöffnet, und klickt der Benutzer wird der nicht-Pfeil Teil der Schaltfläche in beiden Modi das Framework der Befehl ausgeführt.  
  
##  <a name="setmenupalettemode"></a>CMFCToolBarMenuButton::SetMenuPaletteMode  
 Gibt an, ob der Dropdown-Menü im Palettenmodus befindet.  
  
```  
void SetMenuPaletteMode(
    BOOL bMenuPaletteMode=TRUE,  
    int nPaletteRows=1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bMenuPaletteMode`  
 Gibt an, ob der Dropdown-Menü im Palettenmodus befindet.  
  
 [in] `nPaletteRows`  
 Anzahl der Zeilen in der Palette.  
  
### <a name="remarks"></a>Hinweise  
 In der Palettenmodus werden alle Menüelemente als einen mehrspaltigen Palette angezeigt. Sie geben die Anzahl der Zeilen mit `nPaletteRows`.  
  
##  <a name="setmessagewnd"></a>CMFCToolBarMenuButton::SetMessageWnd  

  
```  
void SetMessageWnd(CWnd* pWndMessage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndMessage`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setradio"></a>CMFCToolBarMenuButton::SetRadio  
 Legt die Symbolleistenschaltfläche-Menü auf das Symbol "Bildschaltfläche Stil" ein Optionsfeld angezeigt wird, wenn diese Option aktiviert ist.  
  
```  
virtual void SetRadio();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Schaltfläche gezeichnet wird, während diese Option aktiviert ist, ruft er [CMFCVisualManager::OnDrawMenuCheck](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenucheck) ein Häkchen gezeichnet werden soll. Standardmäßig `OnDrawMenuCheck` fordert an, dass die aktuellen visuelle Manager ein Kontrollkästchen zeichnet Häkchen auf die Schaltfläche "im Menü" formatieren. Nachdem Sie diese Methode aufrufen, zeichnet der aktuellen visuelle Manager stattdessen ein Optionsfeld Schaltfläche Stil Häkchen auf die Schaltfläche. Diese Änderung kann nicht rückgängig gemacht werden.  
  
 Wenn Sie diese Methode aufrufen, und die Menüschaltfläche gerade angezeigt wird, werden sie aktualisiert.  
  
##  <a name="settearoff"></a>CMFCToolBarMenuButton::SetTearOff  
 Gibt die ID des Balkens abtrennbare für das Dropdown-Menü.  
  
```  
virtual void SetTearOff(UINT uiBarID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiBarID`  
 Gibt eine neue abtrennbare Leiste ID.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die ID für die abtrennbarer Leiste angeben, die erstellt wird, wenn der Benutzer auf die Menüschaltfläche aus einer Menüleiste zieht. Wenn die `uiBarID` Parameter gleich 0 ist, der Benutzer kann nicht deaktiviert die Menüschaltfläche entfernen.  
  
 Rufen Sie [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus) das Feature abtrennbares Menü in der Anwendung aktiviert.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCPopupMenu-Klasse](../../mfc/reference/cmfcpopupmenu-class.md)