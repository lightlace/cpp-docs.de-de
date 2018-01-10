---
title: CMFCRibbonCategory-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonCategory
- AFXRIBBONCATEGORY/CMFCRibbonCategory
- AFXRIBBONCATEGORY/CMFCRibbonCategory::CMFCRibbonCategory
- AFXRIBBONCATEGORY/CMFCRibbonCategory::AddHidden
- AFXRIBBONCATEGORY/CMFCRibbonCategory::AddPanel
- AFXRIBBONCATEGORY/CMFCRibbonCategory::CopyFrom
- AFXRIBBONCATEGORY/CMFCRibbonCategory::FindByData
- AFXRIBBONCATEGORY/CMFCRibbonCategory::FindByID
- AFXRIBBONCATEGORY/CMFCRibbonCategory::FindPanelWithElem
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetContextID
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetData
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetDroppedDown
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetElements
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetElementsByID
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetFirstVisibleElement
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetFocused
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetHighlighted
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetImageCount
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetImageSize
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetItemIDsList
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetLastVisibleElement
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetLargeImages
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetMaxHeight
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetName
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetPanel
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetPanelCount
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetPanelFromPoint
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetPanelIndex
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetParentButton
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetParentMenuBar
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetParentRibbonBar
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetRect
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetSmallImages
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetTabColor
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetTabRect
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetTextTopLine
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetVisibleElements
- AFXRIBBONCATEGORY/CMFCRibbonCategory::HighlightPanel
- AFXRIBBONCATEGORY/CMFCRibbonCategory::HitTest
- AFXRIBBONCATEGORY/CMFCRibbonCategory::HitTestEx
- AFXRIBBONCATEGORY/CMFCRibbonCategory::HitTestScrollButtons
- AFXRIBBONCATEGORY/CMFCRibbonCategory::IsActive
- AFXRIBBONCATEGORY/CMFCRibbonCategory::IsVisible
- AFXRIBBONCATEGORY/CMFCRibbonCategory::IsWindows7Look
- AFXRIBBONCATEGORY/CMFCRibbonCategory::NotifyControlCommand
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnCancelMode
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnDraw
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnDrawImage
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnDrawMenuBorder
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnKey
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnLButtonDown
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnLButtonUp
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnMouseMove
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnRTLChanged
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnScrollHorz
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnUpdateCmdUI
- AFXRIBBONCATEGORY/CMFCRibbonCategory::RecalcLayout
- AFXRIBBONCATEGORY/CMFCRibbonCategory::RemovePanel
- AFXRIBBONCATEGORY/CMFCRibbonCategory::ReposPanels
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetCollapseOrder
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetData
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetKeys
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetName
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetTabColor
dev_langs: C++
helpviewer_keywords:
- CMFCRibbonCategory [MFC], CMFCRibbonCategory
- CMFCRibbonCategory [MFC], AddHidden
- CMFCRibbonCategory [MFC], AddPanel
- CMFCRibbonCategory [MFC], CopyFrom
- CMFCRibbonCategory [MFC], FindByData
- CMFCRibbonCategory [MFC], FindByID
- CMFCRibbonCategory [MFC], FindPanelWithElem
- CMFCRibbonCategory [MFC], GetContextID
- CMFCRibbonCategory [MFC], GetData
- CMFCRibbonCategory [MFC], GetDroppedDown
- CMFCRibbonCategory [MFC], GetElements
- CMFCRibbonCategory [MFC], GetElementsByID
- CMFCRibbonCategory [MFC], GetFirstVisibleElement
- CMFCRibbonCategory [MFC], GetFocused
- CMFCRibbonCategory [MFC], GetHighlighted
- CMFCRibbonCategory [MFC], GetImageCount
- CMFCRibbonCategory [MFC], GetImageSize
- CMFCRibbonCategory [MFC], GetItemIDsList
- CMFCRibbonCategory [MFC], GetLastVisibleElement
- CMFCRibbonCategory [MFC], GetLargeImages
- CMFCRibbonCategory [MFC], GetMaxHeight
- CMFCRibbonCategory [MFC], GetName
- CMFCRibbonCategory [MFC], GetPanel
- CMFCRibbonCategory [MFC], GetPanelCount
- CMFCRibbonCategory [MFC], GetPanelFromPoint
- CMFCRibbonCategory [MFC], GetPanelIndex
- CMFCRibbonCategory [MFC], GetParentButton
- CMFCRibbonCategory [MFC], GetParentMenuBar
- CMFCRibbonCategory [MFC], GetParentRibbonBar
- CMFCRibbonCategory [MFC], GetRect
- CMFCRibbonCategory [MFC], GetSmallImages
- CMFCRibbonCategory [MFC], GetTabColor
- CMFCRibbonCategory [MFC], GetTabRect
- CMFCRibbonCategory [MFC], GetTextTopLine
- CMFCRibbonCategory [MFC], GetVisibleElements
- CMFCRibbonCategory [MFC], HighlightPanel
- CMFCRibbonCategory [MFC], HitTest
- CMFCRibbonCategory [MFC], HitTestEx
- CMFCRibbonCategory [MFC], HitTestScrollButtons
- CMFCRibbonCategory [MFC], IsActive
- CMFCRibbonCategory [MFC], IsVisible
- CMFCRibbonCategory [MFC], IsWindows7Look
- CMFCRibbonCategory [MFC], NotifyControlCommand
- CMFCRibbonCategory [MFC], OnCancelMode
- CMFCRibbonCategory [MFC], OnDraw
- CMFCRibbonCategory [MFC], OnDrawImage
- CMFCRibbonCategory [MFC], OnDrawMenuBorder
- CMFCRibbonCategory [MFC], OnKey
- CMFCRibbonCategory [MFC], OnLButtonDown
- CMFCRibbonCategory [MFC], OnLButtonUp
- CMFCRibbonCategory [MFC], OnMouseMove
- CMFCRibbonCategory [MFC], OnRTLChanged
- CMFCRibbonCategory [MFC], OnScrollHorz
- CMFCRibbonCategory [MFC], OnUpdateCmdUI
- CMFCRibbonCategory [MFC], RecalcLayout
- CMFCRibbonCategory [MFC], RemovePanel
- CMFCRibbonCategory [MFC], ReposPanels
- CMFCRibbonCategory [MFC], SetCollapseOrder
- CMFCRibbonCategory [MFC], SetData
- CMFCRibbonCategory [MFC], SetKeys
- CMFCRibbonCategory [MFC], SetName
- CMFCRibbonCategory [MFC], SetTabColor
ms.assetid: 99ba25b6-d060-4fdd-bfab-3c46c22981bb
caps.latest.revision: "38"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0c4e78017946ef335e04c8190b6ec4cd20e74ca2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcribboncategory-class"></a>CMFCRibbonCategory-Klasse
Die `CMFCRibbonCategory` Klasse implementiert eine Menübandregisterkarte, die eine Gruppe enthält [Bereiche des Menübands](../../mfc/reference/cmfcribbonpanel-class.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonCategory : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonCategory::CMFCRibbonCategory](#cmfcribboncategory)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonCategory::AddHidden](#addhidden)|Die Menübandkategorie hinzugefügt ein ausgeblendetes Element.|  
|[CMFCRibbonCategory::AddPanel](#addpanel)|Fügt einen neuen Bereich die Menübandkategorie hinzu.|  
|[CMFCRibbonCategory::CopyFrom](#copyfrom)||  
|[CMFCRibbonCategory::FindByData](#findbydata)||  
|[CMFCRibbonCategory::FindByID](#findbyid)||  
|[CMFCRibbonCategory::FindPanelWithElem](#findpanelwithelem)||  
|[CMFCRibbonCategory::GetContextID](#getcontextid)|Gibt die Kontext-ID der Menübandkategorie zurück.|  
|[CMFCRibbonCategory::GetData](#getdata)|Gibt die benutzerdefinierten Daten, die die Menübandkategorie zugeordnet ist.|  
|[CMFCRibbonCategory::GetDroppedDown](#getdroppeddown)||  
|[CMFCRibbonCategory::GetElements](#getelements)||  
|[CMFCRibbonCategory::GetElementsByID](#getelementsbyid)||  
|[CMFCRibbonCategory::GetFirstVisibleElement](#getfirstvisibleelement)|Rufen Sie ein erste visible-Element, die die Menübandkategorie angehören.|  
|[CMFCRibbonCategory::GetFocused](#getfocused)|Gibt ein Fokuselement zurück.|  
|[CMFCRibbonCategory::GetHighlighted](#gethighlighted)|Gibt eine markierte Element zurück.|  
|[CMFCRibbonCategory::GetImageCount](#getimagecount)||  
|[CMFCRibbonCategory::GetImageSize](#getimagesize)||  
|[CMFCRibbonCategory::GetItemIDsList](#getitemidslist)||  
|[CMFCRibbonCategory::GetLastVisibleElement](#getlastvisibleelement)|Abrufen eines letzten sichtbaren Elements, die die Menübandkategorie angehören|  
|[CMFCRibbonCategory::GetLargeImages](#getlargeimages)|Gibt einen Verweis auf die Liste der große Bilder, die die Menübandkategorie verwendet.|  
|[CMFCRibbonCategory::GetMaxHeight](#getmaxheight)||  
|[CMFCRibbonCategory::GetName](#getname)||  
|[CMFCRibbonCategory::GetPanel](#getpanel)|Gibt einen Zeiger zum Menübandbereich, das sich am angegebenen Index befindet.|  
|[CMFCRibbonCategory::GetPanelCount](#getpanelcount)|Gibt die Anzahl der menübandbereichen in die Menübandkategorie zurück.|  
|[CMFCRibbonCategory::GetPanelFromPoint](#getpanelfrompoint)||  
|[CMFCRibbonCategory::GetPanelIndex](#getpanelindex)|Gibt den Index der angegebenen Menübandbereich zurück.|  
|[CMFCRibbonCategory::GetParentButton](#getparentbutton)||  
|[CMFCRibbonCategory::GetParentMenuBar](#getparentmenubar)||  
|[CMFCRibbonCategory::GetParentRibbonBar](#getparentribbonbar)||  
|[CMFCRibbonCategory::GetRect](#getrect)||  
|[CMFCRibbonCategory::GetSmallImages](#getsmallimages)|Gibt einen Verweis auf die Liste der kleine Bilder, die die Kategorie verwendet.|  
|[CMFCRibbonCategory::GetTabColor](#gettabcolor)|Gibt die aktuelle Farbe von der Registerkarte des Menübands Kategorie zurück.|  
|[CMFCRibbonCategory::GetTabRect](#gettabrect)||  
|[CMFCRibbonCategory::GetTextTopLine](#gettexttopline)||  
|[CMFCRibbonCategory::GetVisibleElements](#getvisibleelements)|Rufen Sie alle sichtbaren Elemente, die die Menübandkategorie angehören.|  
|[CMFCRibbonCategory::HighlightPanel](#highlightpanel)||  
|[CMFCRibbonCategory::HitTest](#hittest)||  
|[CMFCRibbonCategory::HitTestEx](#hittestex)||  
|[CMFCRibbonCategory::HitTestScrollButtons](#hittestscrollbuttons)||  
|[CMFCRibbonCategory::IsActive](#isactive)||  
|[CMFCRibbonCategory::IsVisible](#isvisible)|Bestimmt, ob die Menübandkategorie sichtbar ist.|  
|[CMFCRibbonCategory::IsWindows7Look](#iswindows7look)|Gibt an, ob der übergeordnete Menüband verfügt über ein Windows 7-Format (kleine rechteckige Anwendungsschaltfläche)|  
|[CMFCRibbonCategory::NotifyControlCommand](#notifycontrolcommand)||  
|[CMFCRibbonCategory::OnCancelMode](#oncancelmode)||  
|[CMFCRibbonCategory::OnDraw](#ondraw)||  
|[CMFCRibbonCategory::OnDrawImage](#ondrawimage)||  
|[CMFCRibbonCategory::OnDrawMenuBorder](#ondrawmenuborder)||  
|[CMFCRibbonCategory::OnKey](#onkey)|Wird vom Framework aufgerufen, wenn ein Benutzer eine Taste drückt.|  
|[CMFCRibbonCategory::OnLButtonDown](#onlbuttondown)||  
|[CMFCRibbonCategory::OnLButtonUp](#onlbuttonup)||  
|[CMFCRibbonCategory::OnMouseMove](#onmousemove)||  
|[CMFCRibbonCategory::OnRTLChanged](#onrtlchanged)||  
|[CMFCRibbonCategory::OnScrollHorz](#onscrollhorz)||  
|[CMFCRibbonCategory::OnUpdateCmdUI](#onupdatecmdui)||  
|[CMFCRibbonCategory::RecalcLayout](#recalclayout)||  
|[CMFCRibbonCategory::RemovePanel](#removepanel)||  
|[CMFCRibbonCategory::ReposPanels](#repospanels)||  
|[CMFCRibbonCategory::SetCollapseOrder](#setcollapseorder)|Definiert die Reihenfolge reduzieren, der die menübandbereiche, die in der Menübandkategorie vorhanden sind.|  
|[CMFCRibbonCategory::SetData](#setdata)|Speichert die benutzerdefinierten Daten in der Menübandkategorie an.|  
|[CMFCRibbonCategory::SetKeys](#setkeys)|Die Menübandkategorie eine Zugriffstasteninfo zugewiesen.|  
|[CMFCRibbonCategory::SetName](#setname)||  
|[CMFCRibbonCategory:: Settabcolor](#settabcolor)|Legt die Farbe der Menübandkategorie fest.|  
  
## <a name="remarks"></a>Hinweise  
 Normalerweise erstellen Sie eine Menübandkategorie indirekt durch Aufrufen von [CMFCRibbonBar::AddCategory](../../mfc/reference/cmfcribbonbar-class.md#addcategory), die einen Zeiger auf die neu erstellte Menübandkategorie zurückgibt. Hinzufügen von Bereichen in der Kategorie durch Aufrufen von [CMFCRibbonCategory::AddPanel](#addpanel).  
  
 Die `CMFCRibbonTab` menübandkategorien zeichnen. Abgeleitet aus [CMFCRibbonBaseElement Klasse](../../mfc/reference/cmfcribbonbaseelement-class.md).  
  
 Im folgenden Beispiel wird veranschaulicht, wie zum Erstellen einer Menübandkategorie, und fügen Sie einen Bereich hinzu.  
  
 `// Create a new ribbon category and get a pointer to it`  
  
 `CMFCRibbonCategory* pCategory = m_wndRibbonBar.AddCategory`  
  
 `(_T("&Write"),           // Category name`  
  
 `IDB_WRITE,              // Category small images (16 x 16)`  
  
 `IDB_WRITE_LARGE);   // Category large images (32 x 32)`  
  
 `// Add a panel to the new category`  
  
 `CMFCRibbonPanel* pPanel = pCategory->AddPanel (`  
  
 `_T("Clipboard"),                       // Panel name`  
  
 `m_PanelIcons.ExtractIcon (0));  // Panel icon`  
  
 Das folgende Diagramm zeigt eine Abbildung der Kategorie "Startseite" aus der RibbonApp-beispielanwendung.  
  
 ![CMFCRibbonCategory-Bild](../../mfc/reference/media/cmfcribboncategory.png "Cmfcribboncategory")  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCRibbonCategory`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxribboncategory.h  
  
##  <a name="addhidden"></a>CMFCRibbonCategory::AddHidden  
 Fügt das angegebene Menübandelement auf das Array von Menübandelemente, die im Dialogfeld "anpassen" angezeigt werden.  
  
```  
void AddHidden(CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pElem`  
 Ein Zeiger auf ein Menübandelement.  
  
### <a name="remarks"></a>Hinweise  
 Menübandelemente im Dialogfeld "anpassen" werden die Befehle, die Sie auf der Symbolleiste für den Schnellzugriff hinzufügen können.  
  
##  <a name="addpanel"></a>CMFCRibbonCategory::AddPanel  
 Erstellt ein Menübandbereich für die Menübandkategorie an.  
  
```  
CMFCRibbonPanel* AddPanel(
    LPCTSTR lpszPanelName,  
    HICON hIcon = 0,  
    CRuntimeClass* pRTI = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszPanelName`  
 Ein Zeiger auf den Namen des neuen Menübandbereich.  
  
 [in] `hIcon`  
 Handle für das Standardsymbol für das neue Menübandbereich.  
  
 [in] `pRTI`  
 Ein Zeiger auf die laufzeitklasseninformationen für ein benutzerdefiniertes Menüband-Bereich.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf die neue Menübandbereich, wenn die Methode erfolgreich ausgeführt wurde; andernfalls `NULL` , wenn der Bereich nicht erstellt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen benutzerdefinierte Menüband-Bereich erstellen möchten, müssen Sie angeben, dass die Laufzeit-Klasseninformationen in `pRTI`. Benutzerdefiniertes Menüband Panel-Klasse abgeleitet werden muss die `CMFCRibbonPanel` Klasse.  
  
 Das Standardsymbol für das Menübandbereich wird angezeigt, wenn nicht genügend Speicherplatz, das Menübandelemente anzeigen.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `AddPanel` Methode in der `CMFCRibbonCategory` Klasse.  
  
 [!code-cpp[NVC_MFC_RibbonApp#10](../../mfc/reference/codesnippet/cpp/cmfcribboncategory-class_1.cpp)]  
  
##  <a name="cmfcribboncategory"></a>CMFCRibbonCategory::CMFCRibbonCategory  
 Erstellt und initialisiert ein [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md) Objekt.  
  
```  
CMFCRibbonCategory(
    CMFCRibbonBar* pParenrRibbonBar,  
    LPCTSTR lpszName,  
    UINT uiSmallImagesResID,  
    UINT uiLargeImagesResID,  
    CSize sizeSmallImage = CSize(16,
    16),  
    CSize sizeLargeImage = CSize(32,
    32));
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pParenrRibbonBar`  
 Ein Zeiger auf die übergeordnete menübandleiste der Menübandkategorie.  
  
 [in] `lpszName`  
 Der Name der Menübandkategorie.  
  
 [in] `uiSmallImagesResID`  
 Ressourcen-ID, der die Bildliste für kleine Bilder, die von Menübandelementen in die Menübandkategorie verwendet werden.  
  
 [in] `uiLargeImagesResID`  
 Ressourcen-ID, der die Bildliste für große Bilder, die von Menübandelementen in die Menübandkategorie verwendet werden.  
  
 [in] `sizeSmallImage`  
 Die Standardgröße des kleine Bilder für die Menübandelemente in der Menübandkategorie.  
  
 [in] `sizeLargeImage`  
 Die Standardgröße von Bildern für Menübandelemente in der Menübandkategorie.  
  
##  <a name="copyfrom"></a>CMFCRibbonCategory::CopyFrom  
 Kopiert den Status des angegebenen [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md) mit dem aktuellen [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md) Objekt.  
  
```  
virtual void CopyFrom(CMFCRibbonCategory& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `src`  
 Das `CMFCRibbonCategory`-Quellobjekt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="findbydata"></a>CMFCRibbonCategory::FindByData  
 Ruft das Menübandelement, das den angegebenen Daten zugeordnet.  
  
```  
CMFCRibbonBaseElement* FindByData(
    DWORD_PTR dwData,  
    BOOL bVisibleOnly = TRUE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwData`  
 Die Daten, die ein Menübandelement zugeordnet.  
  
 [in] `bVisibleOnly`  
 `TRUE`die Suche Schnellzugriff Menübandelemente einschließt; `FALSE` Schnellzugriff Menübandelemente in der Suche ausgeschlossen.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf ein Menübandelement, wenn die Methode erfolgreich ausgeführt wurde; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="findbyid"></a>CMFCRibbonCategory::FindByID  
 Ruft das Menübandelement, das der angegebenen Befehls-ID zugeordnet ist  
  
```  
CMFCRibbonBaseElement* FindByID(
    UINT uiCmdID,  
    BOOL bVisibleOnly = TRUE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdID`  
 Befehls-ID, die ein Menübandelement zugeordnet.  
  
 [in] `bVisibleOnly`  
 `TRUE`die Suche Schnellzugriff Menübandelemente einschließt; `FALSE` Schnellzugriff Menübandelemente in der Suche ausgeschlossen.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf ein Menübandelement, wenn die Methode erfolgreich ausgeführt wurde; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="findpanelwithelem"></a>CMFCRibbonCategory::FindPanelWithElem  
 Ruft die Menübandbereich, die das angegebene Menübandelement enthält.  
  
```  
CMFCRibbonPanel* FindPanelWithElem(const CMFCRibbonBaseElement* pElement);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pElement`  
 Ein Zeiger auf ein Menübandelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger zu einem Menübandbereich, wenn die Methode erfolgreich ausgeführt wurde. andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcontextid"></a>CMFCRibbonCategory::GetContextID  
 Ruft die Kontext-ID der Menübandkategorie ab.  
  
```  
UINT GetContextID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Kontext-ID der Menübandkategorie.  
  
### <a name="remarks"></a>Hinweise  
 Die Kontext-ID ist 0, wenn die Menübandkategorie keiner Menübandkategorie Kontext ist.  
  
##  <a name="getdata"></a>CMFCRibbonCategory::GetData  
 Ruft die benutzerdefinierten Daten, die die Menübandkategorie zugeordnet ist.  
  
```  
DWORD_PTR GetData() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die benutzerdefinierten Daten, die die Menübandkategorie zugeordnet ist.  
  
##  <a name="getdroppeddown"></a>CMFCRibbonCategory::GetDroppedDown  
 Ruft einen Zeiger auf die Menübandelement, das derzeit die Popupmenü angezeigt wurde.  
  
```  
CMFCRibbonBaseElement* GetDroppedDown();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf ein Menübandelement, wenn die Methode erfolgreich ausgeführt wurde; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getelements"></a>CMFCRibbonCategory::GetElements  
 Ruft alle Menübandelemente in der Menübandkategorie ab.  
  
```  
void GetElements(
    CArray <CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `arElements`  
 Ein Verweis auf eine [CArray](../../mfc/reference/carray-class.md) von Menübandelementen.  
  
### <a name="remarks"></a>Hinweise  
 Menübandelemente, die für die Verwendung bei der schnellen zugriffssymbolleiste entwickelt wurden, sind im Array enthalten.  
  
##  <a name="getelementsbyid"></a>CMFCRibbonCategory::GetElementsByID  
 Ruft alle Menübandelemente, die der angegebenen Befehls-ID zugeordnet sind.  
  
```  
void GetElementsByID(
    UINT uiCmdID,  
    CArray <CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdID`  
 Befehls-ID, die ein Menübandelement zugeordnet.  
  
 [in, out] `arElements`  
 Ein Verweis auf eine [CArray](../../mfc/reference/carray-class.md) von Menübandelementen.  
  
### <a name="remarks"></a>Hinweise  
 Menübandelemente, die für die Verwendung bei der schnellen zugriffssymbolleiste entwickelt wurden, sind im Array enthalten.  
  
##  <a name="getfirstvisibleelement"></a>CMFCRibbonCategory::GetFirstVisibleElement  
 Ruft das erste sichtbare Element, das die Menübandkategorie angehört.  
  
```  
CMFCRibbonBaseElement* GetFirstVisibleElement() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf das erste sichtbare Element; möglicherweise `NULL` Wenn Kategorie keine sichtbaren Elemente verfügt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getfocused"></a>CMFCRibbonCategory::GetFocused  
 Gibt ein Fokuselement zurück.  
  
```  
CMFCRibbonBaseElement* GetFocused();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Fokuselement oder `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gethighlighted"></a>CMFCRibbonCategory::GetHighlighted  
 Gibt eine markierte Element zurück.  
  
```  
CMFCRibbonBaseElement* GetHighlighted();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Element hervorgehoben oder `NULL` , wenn keine Elemente hervorgehoben sind.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getimagecount"></a>CMFCRibbonCategory::GetImageCount  
 Ruft die Anzahl von Bildern in der angegebenen Bildliste, die in der Menübandkategorie enthalten sind.  
  
```  
int GetImageCount(BOOL bIsLargeImage) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bIsLargeImage`  
 `TRUE`für die Anzahl von Bildern in das große Bildliste; `FALSE` für die Anzahl der Bilder in der Liste der Miniaturansicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bilder in der Liste angegebenen Bild.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getimagesize"></a>CMFCRibbonCategory::GetImageSize  
 Ruft die Größe eines Bilds in der angegebenen Bildliste, die in der Menübandkategorie enthalten sind.  
  
```  
CSize GetImageSize(BOOL bIsLargeImage) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bIsLargeImage`  
 `TRUE`für die Größe von Bildern. `FALSE` für die Größe der kleine Bilder.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe eines Bilds in der Liste angegebenen Bild.  
  
### <a name="remarks"></a>Hinweise  
 Die Größe abgerufen enthält den Skalierungsfaktor für die globale Bild.  
  
##  <a name="getitemidslist"></a>CMFCRibbonCategory::GetItemIDsList  
 Ruft die Befehls-IDs für die Menübandelemente, die in der Menübandkategorie enthalten sind.  
  
```  
void GetItemIDsList(
    CList<UINT, UINT>& lstItems,  
    BOOL bHiddenOnly = FALSE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `lstItems`  
 Die Liste der Befehls-IDs für die Menübandelemente in der Menübandkategorie.  
  
 [in] `bHiddenOnly`  
 `TRUE`auszuschließende Menübandelemente, die auf den menübandbereichen in die Menübandkategorie angezeigt; `FALSE` die Menübandkategorie alle Menübandelemente einschließt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getlargeimages"></a>CMFCRibbonCategory::GetLargeImages  
 Ruft die Liste der große Bilder, die in der Menübandkategorie enthalten sind.  
  
```  
CMFCToolBarImages& GetLargeImages();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Liste der große Bilder, die in der Menübandkategorie enthalten sind.  
  
##  <a name="getlastvisibleelement"></a>CMFCRibbonCategory::GetLastVisibleElement  
 Ruft den letzte sichtbare Element, das der Menüband-Kategorie gehört.  
  
```  
CMFCRibbonBaseElement* GetLastVisibleElement() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger zum letzten sichtbaren Element; möglicherweise `NULL` , wenn die Kategorie keine sichtbaren Elemente verfügt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getmaxheight"></a>CMFCRibbonCategory::GetMaxHeight  
 Ruft die maximale Höhe des menübandbereiche, die in der Menübandkategorie enthalten sind.  
  
```  
int GetMaxHeight(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext für das ein Menübandbereich enthalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Höhe der menübandbereiche, die in der Menübandkategorie enthalten sind.  
  
### <a name="remarks"></a>Hinweise  
 Der abgerufene Wert enthält die Höhe des oberen und unteren Rands für die menübandbereiche.  
  
##  <a name="getname"></a>CMFCRibbonCategory::GetName  
 Ruft den Namen der Menübandkategorie ab.  
  
```  
LPCTSTR GetName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name der Menübandkategorie.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getpanel"></a>CMFCRibbonCategory::GetPanel  
 Gibt einen Zeiger zum Menübandbereich, das sich am angegebenen Index befindet.  
  
```  
CMFCRibbonPanel* GetPanel(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Der nullbasierte Index von einem Menübandbereich.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger zum Menübandbereich, das sich am angegebenen Index befindet.  
  
### <a name="remarks"></a>Hinweise  
 Eine Ausnahme wird ausgelöst, wenn `nIndex` liegt außerhalb des gültigen Bereichs.  
  
##  <a name="getpanelcount"></a>CMFCRibbonCategory::GetPanelCount  
 Gibt die Anzahl der menübandbereichen in die Menübandkategorie zurück.  
  
```  
int GetPanelCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der in die Menübandkategorie ein Menübandbereich enthalten.  
  
##  <a name="getpanelfrompoint"></a>CMFCRibbonCategory::GetPanelFromPoint  
 Ruft einen Zeiger zu einem Menübandbereich ab, wenn der angegebene Punkt darin befindet.  
  
```  
CMFCRibbonPanel* GetPanelFromPoint(CPoint point) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Die x- und y-Koordinaten des Zeigers, relativ zu der oberen linken Ecke des Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger zu einem Menübandbereich, wenn die Methode erfolgreich ausgeführt wurde. andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Nur ein Menübandbereich enthalten, die in der Menübandkategorie enthalten sind, werden getestet.  
  
##  <a name="getpanelindex"></a>CMFCRibbonCategory::GetPanelIndex  
 Ruft den nullbasierten Index des angegebenen Menübandbereich ab.  
  
```  
int GetPanelIndex(const CMFCRibbonPanel* pPanel) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pPanel`  
 Zeiger zu einem Menübandbereich.  
  
### <a name="return-value"></a>Rückgabewert  
 Nullbasierte Index des angegebenen Menübandbereich, wenn die Methode erfolgreich ausgeführt wurde. andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Durchsucht nur menübandbereiche, die in der Menübandkategorie enthalten sind.  
  
##  <a name="getparentbutton"></a>CMFCRibbonCategory::GetParentButton  
 Ruft das übergeordnete Menübandelement der Menübandkategorie ab.  
  
```  
CMFCRibbonBaseElement* GetParentButton() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf das Menübandelement übergeordneten oder `NULL` , wenn kein übergeordnetes Element vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getparentmenubar"></a>CMFCRibbonCategory::GetParentMenuBar  
 Gibt einen Zeiger auf die übergeordnete Menüleiste des der `CMFCRibbonCategory` Objekt.  
  
```  
CMFCRibbonPanelMenuBar* GetParentMenuBar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Inhalt der `m_pParentMenuBar` geschützte Member.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getparentribbonbar"></a>CMFCRibbonCategory::GetParentRibbonBar  
 Ruft die übergeordnete menübandleiste für die Menübandkategorie ab.  
  
```  
CMFCRibbonBar* GetParentRibbonBar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die übergeordnete menübandleiste für die Menübandkategorie.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getrect"></a>CMFCRibbonCategory::GetRect  
 Ruft das Anzeigerechteck der Menüband-Kategorie ab.  
  
```  
CRect GetRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Anzeigerechteck der Menüband-Kategorie.  
  
### <a name="remarks"></a>Hinweise  
 Das Anzeigerechteck für die Menübandkategorie schließt sich nicht auf die Registerkarte "Kategorie" aus.  
  
##  <a name="getsmallimages"></a>CMFCRibbonCategory::GetSmallImages  
 Ruft die Liste der kleine Bilder, die in der Menübandkategorie enthalten sind.  
  
```  
CMFCToolBarImages& GetSmallImages();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Liste der kleine Bilder, die in der Menübandkategorie enthalten sind.  
  
##  <a name="gettabcolor"></a>CMFCRibbonCategory::GetTabColor  
 Gibt die aktuelle Farbe von der Registerkarte des Menübands Kategorie zurück.  
  
```  
AFX_RibbonCategoryColor GetTabColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Farbe der Menüband-kategorieregisterkarte.  
  
### <a name="remarks"></a>Hinweise  
 Der zurückgegebene Wert kann eine der folgenden Enumerationswerte:  
  
-   AFX_CategoryColor_Red  
  
-   AFX_CategoryColor_Orange  
  
-   AFX_CategoryColor_Yellow  
  
-   AFX_CategoryColor_Green  
  
-   AFX_CategoryColor_Blue  
  
-   AFX_CategoryColor_Indigo  
  
-   AFX_CategoryColor_Violet  
  
##  <a name="gettabrect"></a>CMFCRibbonCategory::GetTabRect  
 Ruft das Anzeigerechteck für die Registerkarte des Menübands Kategorie ab.  
  
```  
CRect GetTabRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Anzeigerechteck für die Menüband-kategorieregisterkarte.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gettexttopline"></a>CMFCRibbonCategory::GetTextTopLine  
 Ruft die vertikale Position von Text in Menübandschaltflächen, in denen große Bilder angezeigt, in der Menübandkategorie ab.  
  
```  
int GetTextTopLine() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die vertikale Position des Texts an, in Pixel auf Menübandschaltflächen, in denen große Bilder angezeigt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getvisibleelements"></a>CMFCRibbonCategory::GetVisibleElements  
 Ruft alle sichtbaren Elemente, die Menübandkategorie gehören, ab.  
  
```  
void GetVisibleElements(
    CArray <CMFCRibbonBaseElement*,  
    CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Parameter  
 `arElements`  
 Ein Array aller sichtbaren Elemente.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="highlightpanel"></a>CMFCRibbonCategory::HighlightPanel  
 Werden die angegebenen Menübandbereich hervorgehoben.  
  
```  
CMFCRibbonPanel* HighlightPanel(
    CMFCRibbonPanel* pHLPanel,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pHLPanel`  
 Zeiger zum Menübandbereich zu markieren.  
  
 [in] `point`  
 Die x- und y-Koordinaten des Zeigers, relativ zu der oberen linken Ecke des Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf die zuvor markierten Menübandbereich; andernfalls `NULL` Wenn keine Menübandbereich markiert ist, wenn diese Methode aufgerufen wird.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu einem Menübandbereich Hervorhebung, finden Sie unter [CMFCRibbonPanel::Highlight](../../mfc/reference/cmfcribbonpanel-class.md#highlight).  
  
##  <a name="hittest"></a>CMFCRibbonCategory::HitTest  
 Ruft einen Zeiger auf ein Menübandelement ab, wenn der angegebene Punkt darin befindet.  
  
```  
CMFCRibbonBaseElement* HitTest(
    CPoint point,  
    BOOL bCheckPanelCaption = FALSE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Die x- und y-Koordinaten des Mauszeigers relativ zu der oberen linken Ecke des Fensters.  
  
 [in] `bCheckPanelCaption`  
 `TRUE`So testen Sie die Beschriftung der Menüband-Bereich; `FALSE` die Beschriftung der Menüband-Bereich ausgeschlossen.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf ein Menübandelement, wenn die Methode erfolgreich ausgeführt wurde; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Nur Menübandelemente, die in der Menübandkategorie enthalten sind, werden getestet.  
  
##  <a name="hittestex"></a>CMFCRibbonCategory::HitTestEx  
 Ruft den nullbasierten Index des ein Menübandelement ab, wenn der angegebene Punkt darin befindet.  
  
```  
int HitTestEx(CPoint point) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Die x- und y-Koordinaten des Mauszeigers relativ zu der oberen linken Ecke des Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 Nullbasierte Index des ein Menübandelement, wenn die Methode erfolgreich ausgeführt wurde. andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Nur Menübandelemente, die in der Menübandkategorie enthalten sind, werden getestet.  
  
##  <a name="hittestscrollbuttons"></a>CMFCRibbonCategory::HitTestScrollButtons  
 Wenn ein Punkt innerhalb einer Menübandkategorie nach links oder rechts Bildlaufschaltfläche fällt, gibt einen Zeiger auf die Schaltfläche zurück.  
  
```  
CMFCRibbonBaseElement* HitTestScrollButtons(CPoint point) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Der Punkt zu testen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn `point` innerhalb des umschließenden Rechtecks des entweder links oder rechts Bildlaufschaltfläche der Menübandkategorie liegt, gibt einen Zeiger auf die Schaltfläche oder, andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isactive"></a>CMFCRibbonCategory::IsActive  
 Gibt an, ob die Menübandkategorie aktiven Kategorie auf der menübandleiste ist.  
  
```  
BOOL IsActive() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Menübandkategorie aktive Kategorie ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die aktive Menübandkategorie zeigt die menübandbereiche an.  
  
##  <a name="isvisible"></a>CMFCRibbonCategory::IsVisible  
 Gibt an, ob die Menübandkategorie sichtbar ist.  
  
```  
BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Menübandkategorie sichtbar ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Menübandkategorien, die sichtbar sind anzeigen eine kategorieregisterkarte  
  
##  <a name="iswindows7look"></a>CMFCRibbonCategory::IsWindows7Look  
 Gibt an, ob der übergeordnete Menüband verfügt über ein Windows 7 (kleine rechteckige Anwendungsschaltfläche) zu suchen.  
  
```  
BOOL IsWindows7Look() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Menüband übergeordneten Windows 7, suchen Sie enthält. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="notifycontrolcommand"></a>CMFCRibbonCategory::NotifyControlCommand  
 Übermittelt eine Befehl WM_NOTIFY-Meldung an alle `CMFCRibbonPanel` Elemente in der `CMFCRibbonCategory` , bis die Nachricht verarbeitet wird.  
  
```  
virtual BOOL NotifyControlCommand(
    BOOL bAccelerator,  
    int nNotifyCode,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bAccelerator`  
 `TRUE`Wenn dieser Befehl eine Zugriffstaste stammt oder `FALSE` andernfalls.  
  
 [in] `nNotifyCode`  
 Benachrichtigungscode.  
  
 [in] `wParam`  
 Das WPARAM-Feld der Nachricht.  
  
 [in] `lParam`  
 Das LPARAM-Feld der Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` , wenn die Meldung verarbeitet wurde, oder `FALSE` Wenn dies nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="oncancelmode"></a>CMFCRibbonCategory::OnCancelMode  
 Ruft "Abbrechen"-Modus in allen der `CMFCRibbonPanel` Elemente der `CMFCRibbonCategory`.  
  
```  
virtual void OnCancelMode();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondraw"></a>CMFCRibbonCategory::OnDraw  
 Wird aufgerufen, durch das Framework die Menübandkategorie gezeichnet werden soll.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext für die Menübandkategorie.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondrawimage"></a>CMFCRibbonCategory::OnDrawImage  
 Wird aufgerufen, durch das Framework das angegebene Image auf die Menübandkategorie gezeichnet werden soll.  
  
```  
virtual BOOL OnDrawImage(
    CDC* pDC,  
    CRect rect,  
    CMFCRibbonBaseElement* pElement,  
    BOOL bIsLargeImage,  
    BOOL nImageIndex,  
    BOOL bCenter);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext für das Bild.  
  
 [in] `rect`  
 Das Anzeigerechteck für das Bild.  
  
 [in] `pElement`  
 Ein Zeiger auf das Menübandelement, das das Bild enthält.  
  
 [in] `bIsLargeImage`  
 `TRUE`Wenn das Bild sehr groß ist; `FALSE` Wenn das Bild die kleine Größe ist.  
  
 [in] `nImageIndex`  
 Nullbasierte Index des Bilds in das Image-Array, das in der Menübandkategorie enthalten ist.  
  
 [in] `bCenter`  
 `TRUE`Zentrieren Sie das Bild in das Anzeigerechteck; `FALSE` zum Zeichnen des Bilds in der oberen linken Ecke des Rechtecks angezeigt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich ausgeführt wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondrawmenuborder"></a>CMFCRibbonCategory::OnDrawMenuBorder  
 Wird aufgerufen, durch das Framework zum Zeichnen des Rahmens für ein Popup-Menü.  
  
```  
virtual void OnDrawMenuBorder(
    CDC* pDC,  
    CMFCRibbonPanelMenuBar* pMenuBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Dieser Parameter wird nicht verwendet.  
  
 [in] `pMenuBar`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird diese Methode keine Aktion ausgeführt. Überschreiben Sie diese Methode, um den Rahmen des ein Popupmenü zu zeichnen.  
  
##  <a name="onkey"></a>CMFCRibbonCategory::OnKey  
 Wird vom Framework aufgerufen, wenn ein Benutzer eine Taste drückt.  
  
```  
virtual BOOL OnKey(UINT nChar);
```  
  
### <a name="parameters"></a>Parameter  
 `nChar`  
 Den virtueller Tastencode für den Schlüssel, den ein Benutzer gedrückt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onlbuttondown"></a>CMFCRibbonCategory::OnLButtonDown  
 Wird aufgerufen, durch das Framework das Menübandelement unter der angegebenen Position abrufen, wenn der Benutzer die linke Maustaste drückt.  
  
```  
virtual CMFCRibbonBaseElement* OnLButtonDown(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Die x- und y-Koordinaten des Mauszeigers relativ zu der oberen linken Ecke des Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf ein Menübandelement, wenn die Methode erfolgreich ausgeführt wurde; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onlbuttonup"></a>CMFCRibbonCategory::OnLButtonUp  
 Vom Framework aufgerufen, wenn der Benutzer die linke Maustaste loslässt, und der Mauszeiger über die Menübandkategorie ist.  
  
```  
virtual void OnLButtonUp(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Die x- und y-Koordinaten des Zeigers, relativ zu der oberen linken Ecke des Fensters.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onmousemove"></a>CMFCRibbonCategory::OnMouseMove  
 Vom Framework aufgerufen, wenn der Zeiger auf der menübandleiste bewegt werden, um die Anzeige der Menüband-Kategorie zu aktualisieren.  
  
```  
virtual void OnMouseMove(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Die x- und y-Koordinaten des Zeigers, relativ zu der oberen linken Ecke des Fensters.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onrtlchanged"></a>CMFCRibbonCategory::OnRTLChanged  
 Vom Framework aufgerufen, wenn das Layout Richtung ändert.  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bIsRTL`  
 `TRUE`Wenn das Layout rechts-nach-links wird; `FALSE` ist das Layout links nach rechts.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode passt das Layout aller menübandbereichen und Menübandelemente, die in der Menübandkategorie enthalten sind.  
  
##  <a name="onscrollhorz"></a>CMFCRibbonCategory::OnScrollHorz  
 Scrollt durch die Menübandkategorie in horizontaler Richtung.  
  
```  
virtual BOOL OnScrollHorz(
    BOOL bScrollLeft,  
    int nScrollOffset = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bScrollLeft`  
 `TRUE`auf der linken Seite einen Bildlauf durchführen; `FALSE` einen Bildlauf nach rechts durchführen.  
  
 [in] `nScrollOffset`  
 Das Scroll-Abstand in Pixel.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Menübandkategorie in horizontaler Richtung verschoben. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onupdatecmdui"></a>CMFCRibbonCategory::OnUpdateCmdUI  
 Aufrufe der `OnUpdateCmdUI` Memberfunktion in jedem der `CMFCRibbonPanel` Elemente der `CMFCRibbonCategory` aktivieren oder deaktivieren die Elemente der Benutzeroberfläche in ihnen.  
  
```  
virtual void OnUpdateCmdUI(
    CMFCRibbonCmdUI* pCmdUI,  
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pCmdUI`  
 Zeiger auf die `CMFCRibbonCmdUI` Objekt, das angibt, welche Elemente der Benutzeroberfläche werden aktiviert werden und welche deaktiviert werden soll.  
  
 [in] `pTarget`  
 Ein Zeiger auf das Fenster, das die Aktivierung oder Deaktivierung der Elemente der Benutzeroberfläche steuert.  
  
 [in] `bDisableIfNoHndler`  
 `TRUE`in einer meldungszuordnung werden zum Deaktivieren von Benutzeroberflächen-Elements, wenn kein Handler definiert. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="recalclayout"></a>CMFCRibbonCategory::RecalcLayout  
 Passt das Layout der alle Steuerelemente auf die Menübandkategorie an.  
  
```  
virtual void RecalcLayout(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext für die Menübandkategorie.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="removepanel"></a>CMFCRibbonCategory::RemovePanel  
 Entfernt ein Menübandbereich aus "Menüband".  
  
```cpp  
BOOL RemovePanel(
    int nIndex,  
    BOOL bDelete = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Die Indexnummer des Bereichs zu entfernen. Durch den Aufruf der [CMFCRibbonCategory::GetPanelIndex](#getpanelindex) Methode.  
  
 [in] `bDelete`  
 `TRUE`Das Panelobjekt aus dem Arbeitsspeicher gelöscht; `FALSE` jedoch stattdessen das Fenster zu entfernen, ohne Sie zu löschen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn die Methode erfolgreich ausgeführt wurde, andernfalls `FALSE`.  
  
##  <a name="repospanels"></a>CMFCRibbonCategory::ReposPanels  
 Passt das Layout von allen Steuerelementen für die menübandbereiche, die in der Menübandkategorie enthalten sind.  
  
```  
virtual void ReposPanels(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext für die menübandbereiche, die in der Menübandkategorie enthalten sind.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setcollapseorder"></a>CMFCRibbonCategory::SetCollapseOrder  
 Definiert die Reihenfolge, in der die menübandbereiche der Menübandkategorie reduzieren.  
  
```  
void SetCollapseOrder(const CArray<int,int>& arCollapseOrder);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `arCollapseOrder`  
 Gibt die Reihenfolge reduzieren. Das Array enthält nullbasierten Indizes ein Menübandbereich enthalten.  
  
### <a name="remarks"></a>Hinweise  
 Die Bibliothek definiert die Reihenfolge, reduzieren. Allerdings können Sie dieses Verhalten anpassen, durch die Bereitstellung der Kategorie mit der Liste der Indizes, die die Reihenfolge reduzieren angibt.  
  
 Wenn die Kategorie erkennt, dass er mit einem Menübandbereich zu reduzieren muss, sucht er das nächste Element in der angegebenen Liste. Wenn die Liste leer ist, oder Sie haben nicht genügend Elemente angegeben, verwendet die Kategorie der internen Algorithmus.  
  
 Z. B. die Kategorie verfügt über drei menübandbereiche und kann reduziert werden, mehrmals bis sich alle Panels im vollständig reduzierten Zustand befinden. Sie können die folgenden reduzieren Reihenfolge festlegen: 0, 0, 2, 2. In diesem Fall die Kategorie wird im Bereich 0 zweimal reduzieren, im Bereich 2 zwei Mal. Im Bereich mit dem Index 1 bleibt angezeigt.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `SetCollapseOrder` Methode in der `CMFCRibbonCategory` Klasse. Im Beispiel wird gezeigt, wie ein Array für die Bestellung reduzieren erstellt und zum Festlegen die Reihenfolge reduzieren auf die Menübandkategorie.  
  
 [!code-cpp[NVC_MFC_RibbonApp#13](../../mfc/reference/codesnippet/cpp/cmfcribboncategory-class_2.cpp)]  
  
##  <a name="setdata"></a>CMFCRibbonCategory::SetData  
 Legt die benutzerdefinierten Daten die Menübandkategorie zugeordnet werden soll.  
  
```  
void SetData(DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwData`  
 Die benutzerdefinierten Daten.  
  
##  <a name="setkeys"></a>CMFCRibbonCategory::SetKeys  
 Die Menübandkategorie eine Zugriffstasteninfo zugewiesen.  
  
```  
void SetKeys(LPCTSTR lpszKeys);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszKeys`  
 Der Text Zugriffstasteninfo.  
  
### <a name="remarks"></a>Hinweise  
 Zugriffstasteninfos werden angezeigt, wenn der Benutzer die Alt-Taste oder F10-TASTE drückt.  
  
##  <a name="setname"></a>CMFCRibbonCategory::SetName  
 Weist einen Namen und eine Zugriffstasteninfo die Menübandkategorie.  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszName`  
 Der Name und der Menübandkategorie Zugriffstasteninfo.  
  
### <a name="remarks"></a>Hinweise  
 Fügen Sie zum Festlegen der ZugriffstastenInfo für die Menübandkategorie ein neue-Zeile-Escape-Zeichenfolge gefolgt von den Zeichen Zugriffstasteninfo zu `lpszName`.  
  
##  <a name="settabcolor"></a>CMFCRibbonCategory:: Settabcolor  
 Legt die Farbe der Menübandkategorie fest.  
  
```  
void SetTabColor(AFX_RibbonCategoryColor color);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
 Gibt an, die neu ausgewählte Farbe der Menübandkategorie.  
  
### <a name="remarks"></a>Hinweise  
 Farbe der folgenden Werte sind möglich:  
  
-   AFX_CategoryColor_None  
  
-   AFX_CategoryColor_Red  
  
-   AFX_CategoryColor_Orange  
  
-   AFX_CategoryColor_Yellow  
  
-   AFX_CategoryColor_Green  
  
-   AFX_CategoryColor_Blue  
  
-   AFX_CategoryColor_Indigo  
  
-   AFX_CategoryColor_Violet  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)
