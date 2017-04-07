---
title: Klasse CMFCToolBarMenuButton | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarMenuButton class
ms.assetid: cfa50176-7e4b-4527-9904-86a1b48fc1bc
caps.latest.revision: 31
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
ms.openlocfilehash: a06fd323862c6869463b4db0977816b5707c3e18
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarmenubutton-class"></a>CMFCToolBarMenuButton-Klasse
Eine Symbolleisten-Schaltfläche, die ein Popupmenü enthält.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCToolBarMenuButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::CMFCToolBarMenuButton](#cmfctoolbarmenubutton)|Erstellt ein `CMFCToolBarMenuButton`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::CompareWith](#comparewith)|Vergleicht diese Instanz mit dem angegebenen `CMFCToolBarButton` Objekt. (Überschreibt [CMFCToolBarButton::CompareWith](../../mfc/reference/cmfctoolbarbutton-class.md#comparewith).)|  
|[CMFCToolBarMenuButton::CopyFrom](#copyfrom)|Kopiert die Eigenschaften des aktuellen Schaltfläche eine andere Symbolleisten-Schaltfläche. (Überschreibt [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|[CMFCToolBarMenuButton::CreateFromMenu](#createfrommenu)|Initialisiert das Symbolleistenmenü aus einem Windows-Menü-Handle.|  
|[CMFCToolBarMenuButton::CreateMenu](#createmenu)|Erstellt ein Windows-Menü, aus denen die Befehle im Symbolleistenmenü besteht. Gibt ein Handle an das Windows-Menü.|  
|[CMFCToolBarMenuButton::CreatePopupMenu](#createpopupmenu)|Erstellt ein Popupmenü-Objekt ( [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md)) auf der Symbolleiste anzuzeigen.|  
|[CMFCToolBarMenuButton::EnableQuickCustomize](#enablequickcustomize)||  
|[CMFCToolBarMenuButton::GetCommands](#getcommands)|Ermöglicht schreibgeschützten Zugriff auf die Liste der Befehle im Symbolleistenmenü.|  
|[CMFCToolBarMenuButton::GetImageRect](#getimagerect)|Ruft das umschließende Rechteck für das Bild der Schaltfläche ab.|  
|[CMFCToolBarMenuButton::GetPaletteRows](#getpaletterows)|Gibt die Anzahl der Zeilen im Popup-Menü zurück, wenn Sie im Menü im Palette ausgeführt wird.|  
|[CMFCToolBarMenuButton::GetPopupMenu](#getpopupmenu)|Gibt einen Zeiger auf das Popupmenü-Objekt, das die Schaltfläche zugeordnet ist.|  
|[CMFCToolBarMenuButton::HasButton](#hasbutton)||  
|[CMFCToolBarMenuButton::HaveHotBorder](#havehotborder)|Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer die Schaltfläche auswählt. (Überschreibt [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|  
|[CMFCToolBarMenuButton::IsBorder](#isborder)||  
|[CMFCToolBarMenuButton::IsClickedOnMenu](#isclickedonmenu)||  
|[CMFCToolBarMenuButton::IsDroppedDown](#isdroppeddown)|Bestimmt, ob im Popupmenü angezeigt wird.|  
|[CMFCToolBarMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|Aufgerufen, um zu bestimmen, ob ein Benutzer das ausgewählte Menüelement ein Untermenü öffnen kann.|  
|[CMFCToolBarMenuButton::IsExclusive](#isexclusive)|Bestimmt, ob die Schaltfläche im exklusiven Modus ist, ob im Popupmenü geöffnet bleibt, selbst wenn der Benutzer den Zeiger über eine andere Symbolleiste oder die Schaltfläche bewegt.|  
|[CMFCToolBarMenuButton::IsMenuPaletteMode](#ismenupalettemode)|Bestimmt, ob das Popupmenü im Palettenmodus befindet.|  
|[CMFCToolBarMenuButton::IsQuickMode](#isquickmode)||  
|[CMFCToolBarMenuButton::IsTearOffMenu](#istearoffmenu)|Bestimmt, ob das Popupmenü ein positionierbar wird.|  
|[CMFCToolBarMenuButton::OnAfterCreatePopupMenu](#onaftercreatepopupmenu)||  
|[CMFCToolBarMenuButton::OnBeforeDrag](#onbeforedrag)|Gibt an, ob die Schaltfläche gezogen werden kann. (Überschreibt [CMFCToolBarButton::OnBeforeDrag](../../mfc/reference/cmfctoolbarbutton-class.md#onbeforedrag).)|  
|[CMFCToolBarMenuButton::OnCalculateSize](#oncalculatesize)|Aufgerufen, um die Größe der Schaltfläche für den angegebenen Gerätekontext und Andockstatus berechnen. (Überschreibt [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|[CMFCToolBarMenuButton::OnCancelMode](#oncancelmode)|Aufgerufen, behandelt der [WM_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) Nachricht. (Überschreibt [CMFCToolBarButton::OnCancelMode](../../mfc/reference/cmfctoolbarbutton-class.md#oncancelmode).)|  
|[CMFCToolBarMenuButton::OnChangeParentWnd](#onchangeparentwnd)|Wird vom Framework aufgerufen, wenn eine neue Symbolleiste die Schaltfläche eingefügt wird. (Überschreibt [CMFCToolBarButton::OnChangeParentWnd](cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCToolBarMenuButton::OnClick](#onclick)|Vom Framework aufgerufen, wenn der Benutzer die Maustaste klickt. (Überschreibt [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCToolBarMenuButton::OnClickMenuItem](#onclickmenuitem)|Wird vom Framework aufgerufen, wenn der Benutzer ein Element im Popup-Menü auswählt.|  
|[CMFCToolBarMenuButton::OnContextHelp](#oncontexthelp)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste behandelt eine `WM_HELPHITTEST` Nachricht. (Überschreibt [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp).)|  
|[CMFCToolBarMenuButton::OnDraw](#ondraw)|Vom Framework aufgerufen wird die Schaltfläche gezeichnet werden soll, mithilfe der angegebenen Formate und -Optionen. (Überschreibt [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|[CMFCToolBarMenuButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Aufgerufen, um das Zeichnen der Schaltfläche die **Befehle** im Bereich der **anpassen** Dialogfeld. (Überschreibt [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCToolBarMenuButton::OpenPopupMenu](#openpopupmenu)|Wird vom Framework aufgerufen, wenn der Benutzer das Popup-Menü wird geöffnet.|  
|[CMFCToolBarMenuButton::ResetImageToDefault](#resetimagetodefault)|Legt das Bild, das der Schaltfläche zugeordnet ist, auf den Standardwert fest. (Überschreibt [CMFCToolBarButton::ResetImageToDefault](../../mfc/reference/cmfctoolbarbutton-class.md#resetimagetodefault).)|  
|[CMFCToolBarMenuButton::SaveBarState](#savebarstate)|Speichert den Zustand der Symbolleisten-Schaltfläche. (Überschreibt [CMFCToolBarButton::SaveBarState](../../mfc/reference/cmfctoolbarbutton-class.md#savebarstate).)|  
|[CMFCToolBarMenuButton::Serialize](#serialize)|Dieses Objekt aus dem Archiv liest oder schreibt dieses in ein Archiv. (Überschreibt [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|[CMFCToolBarMenuButton::SetACCData](#setaccdata)|Füllt die angegebene `CAccessibilityData` Objekt mit Zugriff auf Daten aus der Symbolleisten-Schaltfläche. (Überschreibt [CMFCToolBarButton::SetACCData](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata).)|  
|[CMFCToolBarMenuButton::SetMenuOnly](#setmenuonly)|Gibt an, ob die Schaltfläche zu einer Symbolleiste hinzugefügt werden kann.|  
|[CMFCToolBarMenuButton::SetMenuPaletteMode](#setmenupalettemode)|Gibt an, ob das Popupmenü im Palettenmodus.|  
|[CMFCToolBarMenuButton::SetMessageWnd](#setmessagewnd)||  
|[CMFCToolBarMenuButton::SetRadio](#setradio)|Erzwingt die Menüschaltfläche Symbolleiste um ein Symbol gibt an, dass es aktiviert ist.|  
|[CMFCToolBarMenuButton::SetTearOff](#settearoff)|Gibt eine Tearoff-ID für das Popupmenü Leiste.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::DrawDocumentIcon](#drawdocumenticon)|Zeichnet ein Symbol auf die Schaltfläche.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::m_bAlwaysCallOwnerDraw](#m_balwayscallownerdraw)|Wenn `TRUE`, ruft das Framework immer [CFrameWndEx::OnDrawMenuImage](../../mfc/reference/cframewndex-class.md#ondrawmenuimage) bei eine Schaltfläche gezeichnet wird.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `CMFCToolBarMenuButton` angezeigt werden, ein Menü, ein Menüelement, das ein Untermenü verfügt, eine Schaltfläche, die Ausführung eines Befehls oder zeigt ein Menü oder eine Schaltfläche, die nur ein Menü angezeigt. Sie bestimmen das Verhalten und die Darstellung der Menüschaltfläche durch Angeben von Parametern wie das Image, Text, Menü-Handle und Befehls-ID, die mit der Schaltfläche im Konstruktor verknüpft ist `CMFCToolbarMenuButton::CMFCToolbarMenuButton`.  
  
 Eine benutzerdefinierte abgeleitete Klasse der `CMFCToolbarMenuButton` Klasse verwenden, muss die [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) Makro. Die [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate) Makro wird ein Fehler generiert, wenn die Anwendung geschlossen wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie so konfigurieren Sie ein `CMFCToolBarMenuButton` Objekt. Der Code veranschaulicht die angeben, dass Sie im Dropdown Menü im Palettenmodus, und geben Sie die ID für den abtrennbare Balken, der erstellt wird, wenn der Benutzer die Schaltfläche aus einer Menüleiste zieht. Dieser Codeausschnitt ist Teil der [WordPad-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad&#10;](../../mfc/reference/codesnippet/cpp/cmfctoolbarmenubutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](cobject-class.md)  
  
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
 Ein Handle zu einem Menü oder `NULL` , wenn die Schaltfläche ein Menü nicht verfügt.  
  
 [in] `iImage`  
 Der Index des Bilds für die Schaltfläche. oder -1, wenn diese Schaltfläche verfügt nicht über ein Symbol oder verwendet das Symbol für den angegebenen Befehl `uiID`. Der Index wird für jedes `CMFCToolBarImages` Objekt in der Anwendung.  
  
 [in] `lpszText`  
 Der Text der Menüschaltfläche Symbolleiste.  
  
 [in] `bUserButton`  
 `TRUE`Wenn die Schaltfläche ein benutzerdefiniertes Bild angezeigt werden; `FALSE` wird die Schaltfläche eine vordefinierte mit den angegebenen Befehl verknüpfte Bild angezeigt `uiID`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `uiID` ist eine gültige Befehls-ID, die Schaltfläche führt den Befehl aus, wenn der Benutzer darauf klickt. Wenn `hMenu` ist ein Handle gültig Menü die Schaltfläche bietet ein Dropdown Menü aus, wenn es in einer Symbolleiste oder ein Untermenü angezeigt wird, wenn es in einem Menü angezeigt wird. Wenn beide `uiID` und `hMenu` gültig sind, die Schaltfläche wird eine Trennschaltfläche mit einem Teil, der den Befehl ausgeführt wird, wenn der Benutzer darauf klickt und einen Teil mit einem Abwärtspfeil angezeigt, die ein Menü Dropdownliste wird der Benutzer darauf klickt. Jedoch wenn `hMenu` gültig ist, ein Benutzer wird nicht in der Lage, klicken Sie auf die Schaltfläche, um einen Befehl auszuführen, wenn die Schaltfläche in einem Menü eingefügt wird.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Objekt vom Erstellen der `CMFCToolBarMenuButton` Klasse. Dieser Codeausschnitt ist Teil der [WordPad-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad&#9;](../../mfc/reference/codesnippet/cpp/cmfctoolbarmenubutton-class_2.cpp)]  
  
##  <a name="comparewith"></a>CMFCToolBarMenuButton::CompareWith  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CompareWith(const CMFCToolBarButton& other) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `other`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="copyfrom"></a>CMFCToolBarMenuButton::CopyFrom  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `src`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="createfrommenu"></a>CMFCToolBarMenuButton::CreateFromMenu  
 Initialisiert das Symbolleistenmenü aus einem Windows-Menü-Handle.  
  
```  
virtual void CreateFromMenu(HMENU hMenu);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hMenu`  
 Ein Handle für ein Menü.  
  
### <a name="remarks"></a>Hinweise  
 Eine Menüschaltfläche Symbolleiste kann ein Dropdown-Untermenü angezeigt.  
  
 Das Framework ruft diese Methode, um die Befehle im Untermenü aus einem Menü zu initialisieren.  
  
##  <a name="createmenu"></a>CMFCToolBarMenuButton::CreateMenu  
 Erstellt ein Menü, aus denen die Befehle im Symbolleistenmenü besteht. Gibt ein Handle auf das Menü an.  
  
```  
virtual HMENU CreateMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Handle für das Menü Wenn Erfolg. `NULL`Wenn die Liste der Befehle, die die Menüschaltfläche Symbolleiste zugeordneten leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Sie können angeben, überschreiben diese Methode in einer abgeleiteten Klasse die Art und Weise anpassen, wenn, die Sie im Menü generiert wird.  
  
##  <a name="createpopupmenu"></a>CMFCToolBarMenuButton::CreatePopupMenu  
 Erstellt ein `CMFCPopupMenu` Objekt, um das Symbolleistenmenü anzuzeigen.  
  
```  
virtual CMFCPopupMenu* CreatePopupMenu();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein `CMFCPopupMenu` -Objekt, das im Dropdown-Menü die Menüschaltfläche Symbolleiste zugeordnet angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework So bereiten Sie die Anzeige des Dropdown-Menüs mit der Schaltfläche verknüpften vor aufgerufen.  
  
 Die standardmäßige Implementierung einfach erstellt und gibt eine neue `CMFCPopupMenu` Objekt. Überschreiben Sie diese Methode, wenn Sie einen abgeleiteten Typ verwenden möchten [CMFCPopupMenu Klasse](cmfcpopupmenu-class.md) oder zusätzliche Initialisierung auszuführen.  
  
##  <a name="drawdocumenticon"></a>CMFCToolBarMenuButton::DrawDocumentIcon  
 Zeichnet das Symbol eines Dokuments auf die Schaltfläche.  
  
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
 Ein Handle für das Symbol.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode akzeptiert ein Dokumentsymbol und zeichnet es auf die Menüschaltfläche, die im angegebenen Bereich zentriert `rectImage`.  
  
##  <a name="enablequickcustomize"></a>CMFCToolBarMenuButton::EnableQuickCustomize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void EnableQuickCustomize();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hasbutton"></a>CMFCToolBarMenuButton::HasButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasButton() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="havehotborder"></a>CMFCToolBarMenuButton::HaveHotBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HaveHotBorder() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isborder"></a>CMFCToolBarMenuButton::IsBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsBorder() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isclickedonmenu"></a>CMFCToolBarMenuButton::IsClickedOnMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsClickedOnMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isquickmode"></a>CMFCToolBarMenuButton::IsQuickMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
 Ein konstanter Verweis auf eine [CObList-Klasse](../../mfc/reference/coblist-class.md) -Objekt, das eine Auflistung von enthält [CMFCToolBarButton Klasse](../../mfc/reference/cmfctoolbarbutton-class.md) Objekte.  
  
### <a name="remarks"></a>Hinweise  
 Eine Menüschaltfläche Symbolleiste kann ein Untermenü angezeigt. Sie können die Liste der Befehle im Untermenü im Konstruktor oder im Bereitstellen [CMFCToolBarMenuButton::CreateFromMenu](#createfrommenu) wie ein Handle zu einem Menü ( `HMENU`). Klicken Sie im Menü wird konvertiert, um eine Liste von Objekten, die von abgeleitet sind [CMFCToolBarButton Klasse](../../mfc/reference/cmfctoolbarbutton-class.md) und gespeichert, die in der internen `CObList` Objekt. Sie können diese Liste durch Aufrufen dieser Methode zugreifen.  
  
##  <a name="getimagerect"></a>CMFCToolBarMenuButton::GetImageRect  
 Ruft das umschließende Rechteck für das Bild der Schaltfläche ab.  
  
```  
void GetImageRect(CRect& rectImage);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rectImage`  
 Ein Verweis auf ein `CRect` Objekt, das die Koordinaten des umschließenden Rechtecks Bild empfängt.  
  
##  <a name="getpaletterows"></a>CMFCToolBarMenuButton::GetPaletteRows  
 Gibt die Anzahl der Zeilen im Dropdown-Menü zurück, wenn Sie im Menü im Palette ausgeführt wird.  
  
```  
int GetPaletteRows() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeilen in der Palette.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Schaltfläche auf der Palettenmodus festgelegt ist, werden die Menüelemente in mehreren Spalten mit nur einer begrenzten Anzahl von Zeilen angezeigt. Rufen Sie diese Methode, um die Anzahl der Zeilen zu erhalten. Aktivieren oder deaktivieren Palettenmodus und geben Sie die Anzahl der Zeilen, die mit [CMFCToolBarMenuButton::SetMenuPaletteMode](#setmenupalettemode).  
  
##  <a name="getpopupmenu"></a>CMFCToolBarMenuButton::GetPopupMenu  
 Gibt einen Zeiger auf die [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md) -Objekt, das im Dropdownmenü der Schaltfläche darstellt.  
  
```  
CMFCPopupMenu* GetPopupMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md) -Objekt, das erstellt wurde, wenn das Framework das Untermenü der Menüschaltfläche Symbolleiste; gezeichnet wurde. `NULL` , wenn keine Untermenü angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Menüschaltfläche Symbolleiste ein Dropdown Menü angezeigt wird, wird die Schaltfläche erstellt eine [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md) -Objekt, das Menü darstellen. Rufen Sie diese Methode, um einen Zeiger auf die `CMFCPopupMenu` Objekt. Den zurückgegebenen Zeiger, sollten Sie nicht speichern, da es temporär ist und wird ungültig, wenn der Benutzer im Dropdown-Menü geschlossen wird.  
  
##  <a name="isdroppeddown"></a>CMFCToolBarMenuButton::IsDroppedDown  
 Gibt an, ob derzeit im Popupmenü angezeigt wird.  
  
```  
virtual BOOL IsDroppedDown() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Menüschaltfläche Symbolleiste deren Untermenü angezeigt werden; andernfalls `FALSE`.  
  
##  <a name="isemptymenuallowed"></a>CMFCToolBarMenuButton::IsEmptyMenuAllowed  
 Gibt an, ob leere Untermenüs Menüelemente angezeigt wird.  
  
```  
virtual BOOL IsEmptyMenuAllowed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Framework des aktuell ausgewählten Menüelements ein Untermenü geöffnet, auch wenn das Untermenü leer ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn ein Benutzer versucht, das Untermenü des aktuell ausgewählten Menüelements zu öffnen. Wenn das Untermenü leer ist und `IsEmptyMenuAllowed` gibt `FALSE`, das Untermenü kann nicht geöffnet werden.  
  
 Die Standardimplementierung gibt `FALSE` zurück. Überschreiben Sie diese Methode, um dieses Verhalten anzupassen.  
  
##  <a name="isexclusive"></a>CMFCToolBarMenuButton::IsExclusive  
 Gibt an, ob die Schaltfläche im exklusiven Modus ist.  
  
```  
virtual BOOL IsExclusive() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Schaltfläche im exklusiven Modus verwendet werden kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Benutzer ein Popupmenü für eine Schaltfläche öffnet, und klicken Sie dann den Mauszeiger über einem anderen Symbolleiste oder Schaltfläche, schließt das Popupmenü, wenn die Schaltfläche im exklusiven Modus befindet.  
  
 Die standardmäßige Implementierung gibt immer `FALSE`. Überschreiben Sie diese Methode in einer abgeleiteten Klasse, wenn Sie im exklusiven Modus aktivieren möchten.  
  
##  <a name="ismenupalettemode"></a>CMFCToolBarMenuButton::IsMenuPaletteMode  
 Bestimmt, ob das Dropdown-Menü im Palette ausgeführt wird.  
  
```  
BOOL IsMenuPaletteMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Palettenmodus, andernfalls aktiviert ist `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Schaltfläche auf der Palettenmodus festgelegt ist, werden die Menüelemente in mehreren Spalten mit nur einer begrenzten Anzahl von Zeilen angezeigt. Rufen Sie diese Methode, um die Anzahl der Zeilen zu erhalten. Sie können aktivieren oder deaktivieren Sie den Palettenmodus durch Aufrufen von [CMFCToolBarMenuButton::SetMenuPaletteMode](#setmenupalettemode).  
  
##  <a name="istearoffmenu"></a>CMFCToolBarMenuButton::IsTearOffMenu  
 Gibt an, ob Sie im Dropdown Menü ein positionierbar wird.  
  
```  
virtual BOOL IsTearOffMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Menüschaltfläche Symbolleiste ein abtrennbare wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die abtrennbare-Funktion aktivieren und Festlegen der abtrennbare Balken-ID Aufrufen [CMFCToolBarMenuButton::SetTearOff](#settearoff).  
  
##  <a name="m_balwayscallownerdraw"></a>CMFCToolBarMenuButton::m_bAlwaysCallOwnerDraw  
 Gibt an, ob das Framework immer ruft [CFrameWndEx::OnDrawMenuImage](../../mfc/reference/cframewndex-class.md#ondrawmenuimage) bei eine Schaltfläche gezeichnet wird.  
  
```  
static BOOL m_bAlwaysCallOwnerDraw;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Membervariable auf festgelegt ist `TRUE`, ruft Sie die Schaltfläche immer [CFrameWndEx::OnDrawMenuImage](../../mfc/reference/cframewndex-class.md#ondrawmenuimage) Methode, um das Bild auf der Schaltfläche angezeigt. Wenn `m_bAlwaysCallOwnerDraw` ist `FALSE`, die Schaltfläche selbst zeichnet das Bild aus, wenn das Bild vordefiniert ist. Andernfalls ruft sie `OnDrawMenuImage`.  
  
##  <a name="onaftercreatepopupmenu"></a>CMFCToolBarMenuButton::OnAfterCreatePopupMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnAfterCreatePopupMenu();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onbeforedrag"></a>CMFCToolBarMenuButton::OnBeforeDrag  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnBeforeDrag() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="oncalculatesize"></a>CMFCToolBarMenuButton::OnCalculateSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnCancelMode();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onchangeparentwnd"></a>CMFCToolBarMenuButton::OnChangeParentWnd  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParent`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onclick"></a>CMFCToolBarMenuButton::OnClick  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
 Wird vom Framework aufgerufen, wenn der Benutzer ein Element im Dropdown-Menü auswählt.  
  
```  
virtual BOOL OnClickMenuItem();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `FALSE`Wenn das Framework das Standardmenü Element Verarbeitung fortzusetzen. andernfalls `TRUE`. Die standardmäßige Implementierung gibt immer `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer auf ein Menüelement klickt, führt das Framework einen Befehl, der dieses Element zugeordnet ist.  
  
 Um die Verarbeitung im Menü anzupassen, überschreiben `OnClickMenuItem` in einer abgeleiteten Klasse `CMFCToolBarMenuButton` Klasse. Sie müssen auch überschreiben, [CFrameWndEx::OnShowPopupMenu](../../mfc/reference/cframewndex-class.md#onshowpopupmenu) , und Ersetzen Sie die Schaltflächen, die eine spezielle Verarbeitung mit Instanzen der abgeleiteten Klasse erfordern.  
  
##  <a name="oncontexthelp"></a>CMFCToolBarMenuButton::OnContextHelp  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnContextHelp(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondraw"></a>CMFCToolBarMenuButton::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
 Vom Framework aufgerufen, wenn der Benutzer im Dropdown-Menü einer Menüschaltfläche Symbolleiste geöffnet wird.  
  
```  
virtual BOOL OpenPopupMenu(CWnd* pWnd=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Gibt das Fenster, das die Befehle im Dropdownmenü empfängt. Es kann sein `NULL` nur, wenn die Menüschaltfläche Symbolleiste ein übergeordnetes Fenster.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn ein [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md) Objekt erstellt wurde, und erfolgreich geöffnet; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird vom Framework aufgerufen, wenn der Benutzer ein Dropdown Menü auf einer Menüschaltfläche Symbolleiste geöffnet wird.  
  
##  <a name="resetimagetodefault"></a>CMFCToolBarMenuButton::ResetImageToDefault  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void ResetImageToDefault();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="savebarstate"></a>CMFCToolBarMenuButton::SaveBarState  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void SaveBarState();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn es eine Symbolleisten-Schaltfläche als Ergebnis eines Drag & Drop-Vorgangs erstellt. Diese Methode ruft die [CMFCPopupMenu::SaveState](../../mfc/reference/cmfcpopupmenu-class.md#savestate) Methode der obersten Ebene im Popupmenü, wodurch die übergeordnete Schaltfläche im Popupmenü auf das Menü neu zu erstellen.  
  
##  <a name="serialize"></a>CMFCToolBarMenuButton::Serialize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
 Gibt an, ob die Schaltfläche als Menüschaltfläche oder einer Trennschaltfläche gezeichnet wird, wenn sie eine gültige Befehls-ID und ein Untermenü verfügt.  
  
```  
void SetMenuOnly(BOOL bMenuOnly);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bMenuOnly`  
 `TRUE`Diese Schaltfläche als eine Schaltfläche angezeigt, wenn es sich um eine gültige Befehls-ID und ein Untermenü besitzt `FALSE` , diese Schaltfläche als eine Trennschaltfläche anzeigen, wenn sie eine gültige Befehls-ID und ein Untermenü verfügt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Menüschaltfläche Symbolleiste sowohl eine Befehls-ID als auch ein Untermenü verfügt, wird das Menü in der Regel eine Trennschaltfläche sein, die eine main-Schaltfläche und eine angefügte nach-unten-Taste. Wenn Sie diese Methode aufrufen und `bMenuOnly` ist `TRUE`, die Schaltfläche stattdessen eine einzelne Menüschaltfläche mit einem Abwärtspfeil in der Schaltfläche werden angezeigt. Klickt der Benutzer auf den Pfeil in beiden Modi, das Untermenü wird geöffnet, und klickt der Benutzer wird der Teil nicht Pfeil der Schaltfläche in beiden Modi das Framework der Befehl ausgeführt.  
  
##  <a name="setmenupalettemode"></a>CMFCToolBarMenuButton::SetMenuPaletteMode  
 Gibt an, ob Sie im Dropdown Menü in der Palettenmodus.  
  
```  
void SetMenuPaletteMode(
    BOOL bMenuPaletteMode=TRUE,  
    int nPaletteRows=1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bMenuPaletteMode`  
 Gibt an, ob Sie im Dropdown Menü in der Palettenmodus.  
  
 [in] `nPaletteRows`  
 Anzahl der Zeilen in der Palette.  
  
### <a name="remarks"></a>Hinweise  
 In der Palettenmodus werden alle Menüelemente als eine mehrspaltige Palette angezeigt. Sie geben die Anzahl der Zeilen mit `nPaletteRows`.  
  
##  <a name="setmessagewnd"></a>CMFCToolBarMenuButton::SetMessageWnd  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetMessageWnd(CWnd* pWndMessage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndMessage`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setradio"></a>CMFCToolBarMenuButton::SetRadio  
 Legt die Menüschaltfläche Symbolleiste ein Optionsfeld Stil Schaltflächensymbol an, wenn diese Option aktiviert ist.  
  
```  
virtual void SetRadio();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Schaltfläche gezeichnet wird, während es ausgecheckt ist, ruft er [CMFCVisualManager::OnDrawMenuCheck](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenucheck) einem Häkchen zu zeichnen. In der Standardeinstellung `OnDrawMenuCheck` fordert an, dass die aktuelle visuelle Manager ein Kontrollkästchen zeichnet Häkchen auf die Schaltfläche Format. Nach dem Aufruf dieser Methode zeichnet die aktuelle visuelle Manager ein Optionsfeld Schaltfläche Stil Häkchen stattdessen auf die Schaltfläche. Diese Änderung kann nicht rückgängig gemacht werden.  
  
 Wenn Sie diese Methode aufrufen und die Schaltfläche gerade angezeigt wird, wird es aktualisiert.  
  
##  <a name="settearoff"></a>CMFCToolBarMenuButton::SetTearOff  
 Gibt die ID des Balkens abtrennbare für das Dropdown-Menü.  
  
```  
virtual void SetTearOff(UINT uiBarID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiBarID`  
 Gibt eine neue abtrennbare Leiste ID.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die ID für den Balken abtrennbare angeben, die erstellt wird, wenn der Benutzer die Schaltfläche aus einer Menüleiste zieht. Wenn die `uiBarID` Parameter gleich 0 ist, der Benutzer kann nicht deaktiviert die Schaltfläche entfernen.  
  
 Rufen Sie [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus) der Menü-Funktion in Ihrer Anwendung aktiviert.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCPopupMenu-Klasse](../../mfc/reference/cmfcpopupmenu-class.md)
