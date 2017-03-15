---
title: CMFCRibbonCategory-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonCategory
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCategory class
ms.assetid: 99ba25b6-d060-4fdd-bfab-3c46c22981bb
caps.latest.revision: 38
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
ms.openlocfilehash: dccbaac6450985f0d5255a790d83f374b52f06f9
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribboncategory-class"></a>CMFCRibbonCategory-Klasse
Die `CMFCRibbonCategory` -Klasse implementiert eine Menübandregisterkarte, eine Gruppe von enthält [Multifunktionsleisten-Panels](../../mfc/reference/cmfcribbonpanel-class.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonCategory : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
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
|[CMFCRibbonCategory::GetFirstVisibleElement](#getfirstvisibleelement)|Erhalten Sie ein ersten visible-Element, die die Menübandkategorie angehören.|  
|[CMFCRibbonCategory::GetFocused](#getfocused)|Gibt ein Fokuselement zurück.|  
|[CMFCRibbonCategory::GetHighlighted](#gethighlighted)|Gibt eine markierte Element.|  
|[CMFCRibbonCategory::GetImageCount](#getimagecount)||  
|[CMFCRibbonCategory::GetImageSize](#getimagesize)||  
|[CMFCRibbonCategory::GetItemIDsList](#getitemidslist)||  
|[CMFCRibbonCategory::GetLastVisibleElement](#getlastvisibleelement)|Abrufen der letzten sichtbares Element, die die Menübandkategorie angehören|  
|[CMFCRibbonCategory::GetLargeImages](#getlargeimages)|Gibt einen Verweis auf die Liste der große Bilder, die die Menübandkategorie verwendet.|  
|[CMFCRibbonCategory::GetMaxHeight](#getmaxheight)||  
|[CMFCRibbonCategory::GetName](#getname)||  
|[CMFCRibbonCategory::GetPanel](#getpanel)|Gibt einen Zeiger zum Menübandbereich, das sich am angegebenen Index befindet.|  
|[CMFCRibbonCategory::GetPanelCount](#getpanelcount)|Gibt die Anzahl der menübandbereiche in die Menübandkategorie zurück.|  
|[CMFCRibbonCategory::GetPanelFromPoint](#getpanelfrompoint)||  
|[CMFCRibbonCategory::GetPanelIndex](#getpanelindex)|Gibt den Index des angegebenen Menübandbereich zurück.|  
|[CMFCRibbonCategory::GetParentButton](#getparentbutton)||  
|[CMFCRibbonCategory::GetParentMenuBar](#getparentmenubar)||  
|[CMFCRibbonCategory::GetParentRibbonBar](#getparentribbonbar)||  
|[CMFCRibbonCategory::GetRect](#getrect)||  
|[CMFCRibbonCategory::GetSmallImages](#getsmallimages)|Gibt einen Verweis auf die Liste der kleine Bilder, die die Kategorie verwendet.|  
|[CMFCRibbonCategory::GetTabColor](#gettabcolor)|Gibt die aktuelle Farbe des Menübands Kategorie zurück.|  
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
|[CMFCRibbonCategory::OnKey](#onkey)|Vom Framework aufgerufen, wenn ein Benutzer eine Taste drückt.|  
|[CMFCRibbonCategory::OnLButtonDown](#onlbuttondown)||  
|[CMFCRibbonCategory::OnLButtonUp](#onlbuttonup)||  
|[CMFCRibbonCategory::OnMouseMove](#onmousemove)||  
|[CMFCRibbonCategory::OnRTLChanged](#onrtlchanged)||  
|[CMFCRibbonCategory::OnScrollHorz](#onscrollhorz)||  
|[CMFCRibbonCategory::OnUpdateCmdUI](#onupdatecmdui)||  
|[CMFCRibbonCategory::RecalcLayout](#recalclayout)||  
|[CMFCRibbonCategory::RemovePanel](#removepanel)||  
|[CMFCRibbonCategory::ReposPanels](#repospanels)||  
|[CMFCRibbonCategory::SetCollapseOrder](#setcollapseorder)|Definiert die Reihenfolge Reduzieren der menübandbereiche, die in der Menübandkategorie vorhanden sind.|  
|[CMFCRibbonCategory::SetData](#setdata)|Speichert die benutzerdefinierten Daten in der Menübandkategorie.|  
|[CMFCRibbonCategory::SetKeys](#setkeys)|Die Menübandkategorie eine Zugriffstasteninfo zugewiesen.|  
|[CMFCRibbonCategory::SetName](#setname)||  
|[CMFCRibbonCategory::SetTabColor](#settabcolor)|Legt die Farbe der Menübandkategorie fest.|  
  
## <a name="remarks"></a>Hinweise  
 Normalerweise erstellen Sie eine Menübandkategorie indirekt durch Aufrufen von [CMFCRibbonBar::AddCategory](../../mfc/reference/cmfcribbonbar-class.md#addcategory), die einen Zeiger auf die neu erstellte Menübandkategorie zurückgibt. Hinzufügen von Bereichen in der Kategorie durch Aufrufen von [CMFCRibbonCategory::AddPanel](#addpanel).  
  
 Die `CMFCRibbonTab` menübandkategorien zeichnen. Es stammt von [CMFCRibbonBaseElement Klasse](../../mfc/reference/cmfcribbonbaseelement-class.md).  
  
 Im folgenden Beispiel wird veranschaulicht, wie eine Menübandkategorie erstellen, und fügen ein Panel hinzu.  
  
 `// Create a new ribbon category and get a pointer to it`  
  
 `CMFCRibbonCategory* pCategory = m_wndRibbonBar.AddCategory`  
  
 `(_T("&Write"),           // Category name`  
  
 `IDB_WRITE,              // Category small images (16 x 16)`  
  
 `IDB_WRITE_LARGE);   // Category large images (32 x 32)`  
  
 `// Add a panel to the new category`  
  
 `CMFCRibbonPanel* pPanel = pCategory->AddPanel (`  
  
 `_T("Clipboard"),                       // Panel name`  
  
 `m_PanelIcons.ExtractIcon (0));  // Panel icon`  
  
 Das folgende Diagramm zeigt eine Abbildung der Startseite Kategorie aus der RibbonApp-beispielanwendung.  
  
 ![CMFCRibbonCategory-Bild](../../mfc/reference/media/cmfcribboncategory.png "Cmfcribboncategory")  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCRibbonCategory`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxribboncategory.h  
  
##  <a name="a-nameaddhiddena--cmfcribboncategoryaddhidden"></a><a name="addhidden"></a>CMFCRibbonCategory::AddHidden  
 Das Array der Menübandelemente, die im Dialogfeld "anpassen" angezeigt werden hinzugefügt die angegebenen Multifunktionsleisten-Element.  
  
```  
void AddHidden(CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pElem`  
 Ein Zeiger auf ein Menübandelement.  
  
### <a name="remarks"></a>Hinweise  
 Menübandelemente im Dialogfeld "anpassen" werden die Befehle, die Sie auf der Symbolleiste für den Schnellzugriff hinzufügen können.  
  
##  <a name="a-nameaddpanela--cmfcribboncategoryaddpanel"></a><a name="addpanel"></a>CMFCRibbonCategory::AddPanel  
 Erstellt einen Menübandbereich für die Menübandkategorie.  
  
```  
CMFCRibbonPanel* AddPanel(
    LPCTSTR lpszPanelName,  
    HICON hIcon = 0,  
    CRuntimeClass* pRTI = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszPanelName`  
 Zeiger auf den Namen des neuen Menübands Panels.  
  
 [in] `hIcon`  
 Handle für das Standardsymbol für den neuen Menübandbereich ein.  
  
 [in] `pRTI`  
 Ein Zeiger auf die Laufzeit-Klasseninformationen für eine benutzerdefinierte Multifunktionsleiste Fläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf die neue Menübandbereich, wenn die Methode erfolgreich war; andernfalls `NULL` Wenn der Bereich nicht erstellt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen Bereich für die benutzerdefinierte Multifunktionsleiste erstellen möchten, müssen Sie angeben, dass die Laufzeit-Klasseninformationen in `pRTI`. Die benutzerdefinierte Multifunktionsleiste Panel-Klasse abgeleitet werden muss die `CMFCRibbonPanel` Klasse.  
  
 Das Standardsymbol für das Menüband-Fenster wird angezeigt, wenn nicht genügend zum Menübandelemente anzeigen Speicherplatz.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `AddPanel` -Methode in der `CMFCRibbonCategory` Klasse.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#10;](../../mfc/reference/codesnippet/cpp/cmfcribboncategory-class_1.cpp)]  
  
##  <a name="a-namecmfcribboncategorya--cmfcribboncategorycmfcribboncategory"></a><a name="cmfcribboncategory"></a>CMFCRibbonCategory::CMFCRibbonCategory  
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
 Ein Zeiger auf die übergeordnete-Menübands der Menübandkategorie.  
  
 [in] `lpszName`  
 Der Name der Menübandkategorie.  
  
 [in] `uiSmallImagesResID`  
 Ressourcen-ID, der die Bildliste für kleine Bilder, die von Menübandelementen in der Menübandkategorie verwendet werden.  
  
 [in] `uiLargeImagesResID`  
 Ressourcen-ID, der die Bildliste für große Bilder, die von Menübandelementen in der Menübandkategorie verwendet werden.  
  
 [in] `sizeSmallImage`  
 Die Standardgröße für kleine Bilder für die Menübandelemente in der Menübandkategorie.  
  
 [in] `sizeLargeImage`  
 Die Standardgröße für große Bilder für die Menübandelemente in der Menübandkategorie.  
  
##  <a name="a-namecopyfroma--cmfcribboncategorycopyfrom"></a><a name="copyfrom"></a>CMFCRibbonCategory::CopyFrom  
 Kopiert den Zustand des angegebenen [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md) mit dem aktuellen [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md) Objekt.  
  
```  
virtual void CopyFrom(CMFCRibbonCategory& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `src`  
 Das `CMFCRibbonCategory`-Quellobjekt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namefindbydataa--cmfcribboncategoryfindbydata"></a><a name="findbydata"></a>CMFCRibbonCategory::FindByData  
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
 `TRUE`Schnellzugriff Menübandelemente in die Suche eingeschlossen; `FALSE` Schnellzugriff Menübandelemente in der Suche ausgeschlossen.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf ein Menübandelement, wenn die Methode erfolgreich war; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namefindbyida--cmfcribboncategoryfindbyid"></a><a name="findbyid"></a>CMFCRibbonCategory::FindByID  
 Ruft die Multifunktionsleisten-Element, das der angegebenen Befehls-ID zugeordnet ist  
  
```  
CMFCRibbonBaseElement* FindByID(
    UINT uiCmdID,  
    BOOL bVisibleOnly = TRUE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdID`  
 Befehls-ID, die ein Menübandelement zugeordnet.  
  
 [in] `bVisibleOnly`  
 `TRUE`Schnellzugriff Menübandelemente in die Suche eingeschlossen; `FALSE` Schnellzugriff Menübandelemente in der Suche ausgeschlossen.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf ein Menübandelement, wenn die Methode erfolgreich war; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namefindpanelwithelema--cmfcribboncategoryfindpanelwithelem"></a><a name="findpanelwithelem"></a>CMFCRibbonCategory::FindPanelWithElem  
 Ruft die Menübandbereich, der der angegebenen Multifunktionsleisten-Element enthält.  
  
```  
CMFCRibbonPanel* FindPanelWithElem(const CMFCRibbonBaseElement* pElement);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pElement`  
 Ein Zeiger auf ein Menübandelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf einen Menübandbereich, wenn die Methode erfolgreich war; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetcontextida--cmfcribboncategorygetcontextid"></a><a name="getcontextid"></a>CMFCRibbonCategory::GetContextID  
 Ruft die Kontext-ID der Menübandkategorie ab.  
  
```  
UINT GetContextID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Kontext-ID der Menübandkategorie.  
  
### <a name="remarks"></a>Hinweise  
 Die Kontext-ID ist 0, wenn die Menübandkategorie keine Menübandkategorie Kontext ist.  
  
##  <a name="a-namegetdataa--cmfcribboncategorygetdata"></a><a name="getdata"></a>CMFCRibbonCategory::GetData  
 Ruft die benutzerdefinierten Daten, die die Menübandkategorie zugeordnet ist.  
  
```  
DWORD_PTR GetData() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die benutzerdefinierten Daten, die die Menübandkategorie zugeordnet ist.  
  
##  <a name="a-namegetdroppeddowna--cmfcribboncategorygetdroppeddown"></a><a name="getdroppeddown"></a>CMFCRibbonCategory::GetDroppedDown  
 Ruft einen Zeiger auf das Menübandelement, das momentan den Popupmenü angezeigt hat.  
  
```  
CMFCRibbonBaseElement* GetDroppedDown();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf ein Menübandelement, wenn die Methode erfolgreich war; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetelementsa--cmfcribboncategorygetelements"></a><a name="getelements"></a>CMFCRibbonCategory::GetElements  
 Ruft alle Menübandelemente in der Menübandkategorie ab.  
  
```  
void GetElements(
    CArray <CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `arElements`  
 Ein Verweis auf eine [CArray](../../mfc/reference/carray-class.md) von Menübandelementen.  
  
### <a name="remarks"></a>Hinweise  
 Menübandelemente, die für die Verwendung auf der Symbolleiste für den Schnellzugriff entwickelt wurden, sind im Array enthalten.  
  
##  <a name="a-namegetelementsbyida--cmfcribboncategorygetelementsbyid"></a><a name="getelementsbyid"></a>CMFCRibbonCategory::GetElementsByID  
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
 Menübandelemente, die für die Verwendung auf der Symbolleiste für den Schnellzugriff entwickelt wurden, sind im Array enthalten.  
  
##  <a name="a-namegetfirstvisibleelementa--cmfcribboncategorygetfirstvisibleelement"></a><a name="getfirstvisibleelement"></a>CMFCRibbonCategory::GetFirstVisibleElement  
 Ruft das erste sichtbare Element, zu dem die Menübandkategorie gehört.  
  
```  
CMFCRibbonBaseElement* GetFirstVisibleElement() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf das erste sichtbare Element. möglicherweise `NULL` Kategorie keinen keine sichtbaren Elemente.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetfocuseda--cmfcribboncategorygetfocused"></a><a name="getfocused"></a>CMFCRibbonCategory::GetFocused  
 Gibt ein Fokuselement zurück.  
  
```  
CMFCRibbonBaseElement* GetFocused();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Fokuselement oder `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegethighlighteda--cmfcribboncategorygethighlighted"></a><a name="gethighlighted"></a>CMFCRibbonCategory::GetHighlighted  
 Gibt eine markierte Element.  
  
```  
CMFCRibbonBaseElement* GetHighlighted();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine hervorgehobene Element oder `NULL` Wenn keine Elemente markiert sind.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetimagecounta--cmfcribboncategorygetimagecount"></a><a name="getimagecount"></a>CMFCRibbonCategory::GetImageCount  
 Ruft die Anzahl der Bilder in der angegebenen Bildliste, die in der Menübandkategorie enthalten sind.  
  
```  
int GetImageCount(BOOL bIsLargeImage) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bIsLargeImage`  
 `TRUE`die Anzahl der Bilder in der Liste großes Bild; `FALSE` für die Anzahl der Bilder in der Miniaturansicht-Liste.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bilder in der Liste angegebenen Bild.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetimagesizea--cmfcribboncategorygetimagesize"></a><a name="getimagesize"></a>CMFCRibbonCategory::GetImageSize  
 Ruft die Größe eines Bilds in der angegebenen Bildliste, die in der Menübandkategorie enthalten sind.  
  
```  
CSize GetImageSize(BOOL bIsLargeImage) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bIsLargeImage`  
 `TRUE`für die Größe von Bildern. `FALSE` für kleine Bilder.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe eines Bilds in der Liste angegebenen Bild.  
  
### <a name="remarks"></a>Hinweise  
 Die Größe abgerufen enthält den Skalierungsfaktor globales Image.  
  
##  <a name="a-namegetitemidslista--cmfcribboncategorygetitemidslist"></a><a name="getitemidslist"></a>CMFCRibbonCategory::GetItemIDsList  
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
 `TRUE`auszuschließende Menübandelemente, die auf der Multifunktionsleiste in der Menübandkategorie angezeigt; `FALSE` die Menübandkategorie alle Menübandelemente einschließt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetlargeimagesa--cmfcribboncategorygetlargeimages"></a><a name="getlargeimages"></a>CMFCRibbonCategory::GetLargeImages  
 Ruft die Liste der große Bilder, die in der Menübandkategorie enthalten sind.  
  
```  
CMFCToolBarImages& GetLargeImages();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Liste der große Bilder, die in der Menübandkategorie enthalten sind.  
  
##  <a name="a-namegetlastvisibleelementa--cmfcribboncategorygetlastvisibleelement"></a><a name="getlastvisibleelement"></a>CMFCRibbonCategory::GetLastVisibleElement  
 Ruft das letzte sichtbare Element, zu der die Menübandkategorie gehört.  
  
```  
CMFCRibbonBaseElement* GetLastVisibleElement() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf das letzte sichtbare Element. möglicherweise `NULL` Kategorie keinen keine sichtbaren Elemente.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetmaxheighta--cmfcribboncategorygetmaxheight"></a><a name="getmaxheight"></a>CMFCRibbonCategory::GetMaxHeight  
 Ruft die maximale Höhe der menübandbereiche, die in der Menübandkategorie enthalten sind.  
  
```  
int GetMaxHeight(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf einen Gerätekontext für die Multifunktionsleiste geändert wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Höhe der menübandbereiche, die in der Menübandkategorie enthalten sind.  
  
### <a name="remarks"></a>Hinweise  
 Der abgerufene Wert enthält die Höhe der oberen und unteren Ränder für die Multifunktionsleiste geändert wurde.  
  
##  <a name="a-namegetnamea--cmfcribboncategorygetname"></a><a name="getname"></a>CMFCRibbonCategory::GetName  
 Ruft den Namen der Menübandkategorie ein.  
  
```  
LPCTSTR GetName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name der Menübandkategorie.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetpanela--cmfcribboncategorygetpanel"></a><a name="getpanel"></a>CMFCRibbonCategory::GetPanel  
 Gibt einen Zeiger zum Menübandbereich, das sich am angegebenen Index befindet.  
  
```  
CMFCRibbonPanel* GetPanel(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Der nullbasierte Index von einem Menübandbereich.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Menübandbereich, die sich am angegebenen Index befindet.  
  
### <a name="remarks"></a>Hinweise  
 Eine Ausnahme wird ausgelöst, wenn `nIndex` liegt außerhalb des Bereichs.  
  
##  <a name="a-namegetpanelcounta--cmfcribboncategorygetpanelcount"></a><a name="getpanelcount"></a>CMFCRibbonCategory::GetPanelCount  
 Gibt die Anzahl der menübandbereiche in die Menübandkategorie zurück.  
  
```  
int GetPanelCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der menübandbereichen in der Menübandkategorie.  
  
##  <a name="a-namegetpanelfrompointa--cmfcribboncategorygetpanelfrompoint"></a><a name="getpanelfrompoint"></a>CMFCRibbonCategory::GetPanelFromPoint  
 Ruft einen Zeiger auf ein Menübandbereich ab, wenn der angegebene Punkt darin befindet.  
  
```  
CMFCRibbonPanel* GetPanelFromPoint(CPoint point) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Die x- und y-Koordinaten des Mauszeigers, in Bezug auf die linke obere Ecke des Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf einen Menübandbereich, wenn die Methode erfolgreich war; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Nur menübandbereiche, die in der Menübandkategorie enthalten sind, werden getestet.  
  
##  <a name="a-namegetpanelindexa--cmfcribboncategorygetpanelindex"></a><a name="getpanelindex"></a>CMFCRibbonCategory::GetPanelIndex  
 Ruft den nullbasierten Index des angegebenen Menübandbereich ab.  
  
```  
int GetPanelIndex(const CMFCRibbonPanel* pPanel) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pPanel`  
 Ein Zeiger auf ein Menüband-Panel.  
  
### <a name="return-value"></a>Rückgabewert  
 Nullbasierte Index des angegebenen Menübandbereich, wenn die Methode erfolgreich war. andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Durchsucht nur menübandbereiche, die in der Menübandkategorie enthalten sind.  
  
##  <a name="a-namegetparentbuttona--cmfcribboncategorygetparentbutton"></a><a name="getparentbutton"></a>CMFCRibbonCategory::GetParentButton  
 Ruft das übergeordnete Element der Menübandkategorie Menüband ab.  
  
```  
CMFCRibbonBaseElement* GetParentButton() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf das Menübandelement übergeordneten oder `NULL` , wenn kein übergeordnetes Element vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetparentmenubara--cmfcribboncategorygetparentmenubar"></a><a name="getparentmenubar"></a>CMFCRibbonCategory::GetParentMenuBar  
 Gibt einen Zeiger auf die übergeordnete Menüleiste des der `CMFCRibbonCategory` Objekt.  
  
```  
CMFCRibbonPanelMenuBar* GetParentMenuBar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Inhalt der `m_pParentMenuBar` geschützte Member.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetparentribbonbara--cmfcribboncategorygetparentribbonbar"></a><a name="getparentribbonbar"></a>CMFCRibbonCategory::GetParentRibbonBar  
 Ruft die übergeordnete-Menübands für die Menübandkategorie ab.  
  
```  
CMFCRibbonBar* GetParentRibbonBar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die übergeordnete-Menübands für die Menübandkategorie.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetrecta--cmfcribboncategorygetrect"></a><a name="getrect"></a>CMFCRibbonCategory::GetRect  
 Ruft das Anzeigerechteck der Menüband-Kategorie ab.  
  
```  
CRect GetRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Anzeigerechteck der Menüband-Kategorie.  
  
### <a name="remarks"></a>Hinweise  
 Das Anzeigerechteck der Menüband-Kategorie umfasst nicht die kategorienregisterkarte.  
  
##  <a name="a-namegetsmallimagesa--cmfcribboncategorygetsmallimages"></a><a name="getsmallimages"></a>CMFCRibbonCategory::GetSmallImages  
 Ruft die Liste der kleine Bilder, die in der Menübandkategorie enthalten sind.  
  
```  
CMFCToolBarImages& GetSmallImages();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Liste der kleine Bilder, die in der Menübandkategorie enthalten sind.  
  
##  <a name="a-namegettabcolora--cmfcribboncategorygettabcolor"></a><a name="gettabcolor"></a>CMFCRibbonCategory::GetTabColor  
 Gibt die aktuelle Farbe des Menübands Kategorie zurück.  
  
```  
AFX_RibbonCategoryColor GetTabColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Farbe des Menübands Kategorie.  
  
### <a name="remarks"></a>Hinweise  
 Der zurückgegebene Wert kann eine der folgenden Enumerationswerte:  
  
-   AFX_CategoryColor_Red  
  
-   AFX_CategoryColor_Orange  
  
-   AFX_CategoryColor_Yellow  
  
-   AFX_CategoryColor_Green  
  
-   AFX_CategoryColor_Blue  
  
-   AFX_CategoryColor_Indigo  
  
-   AFX_CategoryColor_Violet  
  
##  <a name="a-namegettabrecta--cmfcribboncategorygettabrect"></a><a name="gettabrect"></a>CMFCRibbonCategory::GetTabRect  
 Ruft das Anzeigerechteck für die Multifunktionsleisten-kategorienregisterkarte ab.  
  
```  
CRect GetTabRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Anzeigerechteck für die Multifunktionsleisten-kategorienregisterkarte.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegettexttoplinea--cmfcribboncategorygettexttopline"></a><a name="gettexttopline"></a>CMFCRibbonCategory::GetTextTopLine  
 Ruft die vertikale Position von Text in der Multifunktionsleisten-Schaltflächen in der Menübandkategorie, die große Bilder anzeigen.  
  
```  
int GetTextTopLine() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die vertikale Position des Texts in Pixel auf Menübandschaltflächen, die große Bilder anzuzeigen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetvisibleelementsa--cmfcribboncategorygetvisibleelements"></a><a name="getvisibleelements"></a>CMFCRibbonCategory::GetVisibleElements  
 Ruft alle sichtbaren Elemente, die die Menübandkategorie angehören.  
  
```  
void GetVisibleElements(
    CArray <CMFCRibbonBaseElement*,  
    CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Parameter  
 `arElements`  
 Ein Array aller sichtbaren Elemente.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namehighlightpanela--cmfcribboncategoryhighlightpanel"></a><a name="highlightpanel"></a>CMFCRibbonCategory::HighlightPanel  
 Markiert die angegebene Menübandbereich.  
  
```  
CMFCRibbonPanel* HighlightPanel(
    CMFCRibbonPanel* pHLPanel,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pHLPanel`  
 Zeiger zum Menübandbereich zu markieren.  
  
 [in] `point`  
 Die x- und y-Koordinaten des Mauszeigers, in Bezug auf die linke obere Ecke des Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf die zuvor markierten Menübandbereich; andernfalls `NULL` Wenn keine Menübandbereich markiert ist, wenn diese Methode aufgerufen wird.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu einem Menübandbereich hervorheben, finden Sie unter [CMFCRibbonPanel::Highlight](../../mfc/reference/cmfcribbonpanel-class.md#highlight).  
  
##  <a name="a-namehittesta--cmfcribboncategoryhittest"></a><a name="hittest"></a>CMFCRibbonCategory::HitTest  
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
 Zeiger auf ein Menübandelement, wenn die Methode erfolgreich war; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Es werden nur Menübandelemente, die in der Menübandkategorie enthalten sind getestet.  
  
##  <a name="a-namehittestexa--cmfcribboncategoryhittestex"></a><a name="hittestex"></a>CMFCRibbonCategory::HitTestEx  
 Ruft den nullbasierten Index des Multifunktionsleisten-Element ab, wenn der angegebene Punkt darin befindet.  
  
```  
int HitTestEx(CPoint point) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Die x- und y-Koordinaten des Mauszeigers relativ zu der oberen linken Ecke des Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 Nullbasierte Index des ein Menübandelement, wenn die Methode erfolgreich war. andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Es werden nur Menübandelemente, die in der Menübandkategorie enthalten sind getestet.  
  
##  <a name="a-namehittestscrollbuttonsa--cmfcribboncategoryhittestscrollbuttons"></a><a name="hittestscrollbuttons"></a>CMFCRibbonCategory::HitTestScrollButtons  
 Wenn ein Punkt innerhalb einer Menübandkategorie nach links oder rechts Bildlaufschaltfläche liegt, gibt einen Zeiger auf diese Schaltfläche.  
  
```  
CMFCRibbonBaseElement* HitTestScrollButtons(CPoint point) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Der zu überprüfende Punkt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn `point` das umschließende Rechteck von der linken oder rechten Bildlaufschaltfläche der Menübandkategorie fällt, gibt einen Zeiger auf die Schaltfläche oder andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameisactivea--cmfcribboncategoryisactive"></a><a name="isactive"></a>CMFCRibbonCategory::IsActive  
 Gibt an, ob die Menübandkategorie aktiven Kategorie in der menübandleiste ist.  
  
```  
BOOL IsActive() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Menübandkategorie aktiven Kategorie ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die aktive Menübandkategorie zeigt den menübandbereichen an.  
  
##  <a name="a-nameisvisiblea--cmfcribboncategoryisvisible"></a><a name="isvisible"></a>CMFCRibbonCategory::IsVisible  
 Gibt an, ob die Menübandkategorie sichtbar ist.  
  
```  
BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Menübandkategorie sichtbar ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Menübandkategorien, die sichtbar sind anzeigen eine kategorienregisterkarte  
  
##  <a name="a-nameiswindows7looka--cmfcribboncategoryiswindows7look"></a><a name="iswindows7look"></a>CMFCRibbonCategory::IsWindows7Look  
 Gibt an, ob der übergeordnete Menüband verfügt über ein Windows 7 (kleine rechteckige Anwendungsschaltfläche) zu suchen.  
  
```  
BOOL IsWindows7Look() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die übergeordnete Multifunktionsleiste Aussehen von Windows 7 enthält. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namenotifycontrolcommanda--cmfcribboncategorynotifycontrolcommand"></a><a name="notifycontrolcommand"></a>CMFCRibbonCategory::NotifyControlCommand  
 Übermittelt die Nachricht eine WM_NOTIFY-Befehl an alle `CMFCRibbonPanel` Elemente in der `CMFCRibbonCategory` bis die Nachricht behandelt wird.  
  
```  
virtual BOOL NotifyControlCommand(
    BOOL bAccelerator,  
    int nNotifyCode,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bAccelerator`  
 `TRUE`Wenn dieser Befehl von einer Zugriffstaste stammt oder `FALSE` andernfalls.  
  
 [in] `nNotifyCode`  
 Der Benachrichtigungscode.  
  
 [in] `wParam`  
 Der WPARAM-Feld der Nachricht.  
  
 [in] `lParam`  
 Das LPARAM-Feld der Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` , wenn die Meldung verarbeitet wurde, oder `FALSE` ist dies nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameoncancelmodea--cmfcribboncategoryoncancelmode"></a><a name="oncancelmode"></a>CMFCRibbonCategory::OnCancelMode  
 Ruft die Cancel-Modus in allen der `CMFCRibbonPanel` Elemente der `CMFCRibbonCategory`.  
  
```  
virtual void OnCancelMode();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameondrawa--cmfcribboncategoryondraw"></a><a name="ondraw"></a>CMFCRibbonCategory::OnDraw  
 Aufgerufen, um die Menübandkategorie zu zeichnen.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf einen Gerätekontext für die Menübandkategorie.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameondrawimagea--cmfcribboncategoryondrawimage"></a><a name="ondrawimage"></a>CMFCRibbonCategory::OnDrawImage  
 Aufgerufen, um das Abbild auf die Menübandkategorie zu zeichnen.  
  
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
 Ein Zeiger auf einen Gerätekontext für das Bild.  
  
 [in] `rect`  
 Rechteck für das Bild wird angezeigt.  
  
 [in] `pElement`  
 Ein Zeiger auf die Multifunktionsleisten-Element, das das Bild enthält.  
  
 [in] `bIsLargeImage`  
 `TRUE`Wenn das Bild sehr groß ist. `FALSE` Wenn das Bild der Größe klein ist.  
  
 [in] `nImageIndex`  
 Nullbasierte Index des Bilds in das Image-Array, das in der Menübandkategorie enthalten ist.  
  
 [in] `bCenter`  
 `TRUE`So zentrieren Sie das Bild in das Anzeigerechteck; `FALSE` zum Zeichnen des Bilds in der oberen linken Ecke des Rechtecks angezeigt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich war; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameondrawmenubordera--cmfcribboncategoryondrawmenuborder"></a><a name="ondrawmenuborder"></a>CMFCRibbonCategory::OnDrawMenuBorder  
 Vom Framework aufgerufen wird zum Zeichnen des Rahmens für ein Popup-Menü.  
  
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
 Standardmäßig bewirkt diese Methode nichts. Überschreiben Sie diese Methode zum Zeichnen des Rahmens für ein Popup-Menü.  
  
##  <a name="a-nameonkeya--cmfcribboncategoryonkey"></a><a name="onkey"></a>CMFCRibbonCategory::OnKey  
 Vom Framework aufgerufen, wenn ein Benutzer eine Taste drückt.  
  
```  
virtual BOOL OnKey(UINT nChar);
```  
  
### <a name="parameters"></a>Parameter  
 `nChar`  
 Virtueller Tastencode für den Schlüssel, den ein Benutzer geklickt hat.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonlbuttondowna--cmfcribboncategoryonlbuttondown"></a><a name="onlbuttondown"></a>CMFCRibbonCategory::OnLButtonDown  
 Aufgerufen, um die Multifunktionsleisten-Element unter dem angegebenen Punkt abzurufen, wenn der Benutzer die linke Maustaste drückt.  
  
```  
virtual CMFCRibbonBaseElement* OnLButtonDown(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Die x- und y-Koordinaten des Mauszeigers relativ zu der oberen linken Ecke des Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf ein Menübandelement, wenn die Methode erfolgreich war; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonlbuttonupa--cmfcribboncategoryonlbuttonup"></a><a name="onlbuttonup"></a>CMFCRibbonCategory::OnLButtonUp  
 Wird vom Framework aufgerufen, wenn der Benutzer die linke Maustaste loslässt und der Mauszeiger über die Menübandkategorie.  
  
```  
virtual void OnLButtonUp(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Die x- und y-Koordinaten des Mauszeigers, in Bezug auf die linke obere Ecke des Fensters.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonmousemovea--cmfcribboncategoryonmousemove"></a><a name="onmousemove"></a>CMFCRibbonCategory::OnMouseMove  
 Wird vom Framework aufgerufen, wenn der Zeiger in der menübandleiste bewegt, um die Multifunktionsleiste Kategorie Anzeige zu aktualisieren.  
  
```  
virtual void OnMouseMove(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Die x- und y-Koordinaten des Mauszeigers, in Bezug auf die linke obere Ecke des Fensters.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonrtlchangeda--cmfcribboncategoryonrtlchanged"></a><a name="onrtlchanged"></a>CMFCRibbonCategory::OnRTLChanged  
 Wird vom Framework aufgerufen, wenn das Layout Richtung ändert.  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bIsRTL`  
 `TRUE`Wenn der rechts-nach-links wird; `FALSE` ist das Layout links nach rechts.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode passt das Layout aller menübandbereichen und Menübandelemente, die in der Menübandkategorie enthalten sind.  
  
##  <a name="a-nameonscrollhorza--cmfcribboncategoryonscrollhorz"></a><a name="onscrollhorz"></a>CMFCRibbonCategory::OnScrollHorz  
 Führt einen Bildlauf durch die Menübandkategorie in horizontaler Richtung.  
  
```  
virtual BOOL OnScrollHorz(
    BOOL bScrollLeft,  
    int nScrollOffset = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bScrollLeft`  
 `TRUE`zum Ausführen eines Bildlaufs nach links `FALSE` einen Bildlauf nach rechts durchführen.  
  
 [in] `nScrollOffset`  
 Die Bildlaufleiste Abstand in Pixel.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Menübandkategorie in horizontaler Richtung verschoben. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonupdatecmduia--cmfcribboncategoryonupdatecmdui"></a><a name="onupdatecmdui"></a>CMFCRibbonCategory::OnUpdateCmdUI  
 Aufrufe der `OnUpdateCmdUI` Member-Funktion in jedem der `CMFCRibbonPanel` Elemente der `CMFCRibbonCategory` aktivieren oder deaktivieren die Elemente der Benutzeroberfläche werden.  
  
```  
virtual void OnUpdateCmdUI(
    CMFCRibbonCmdUI* pCmdUI,  
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pCmdUI`  
 Zeiger auf die `CMFCRibbonCmdUI` Objekt, das angibt, welche Elemente der Benutzeroberfläche aktiviert werden sollen und welche deaktiviert werden soll.  
  
 [in] `pTarget`  
 Ein Zeiger auf die Aktivierung oder Deaktivierung der Elemente der Benutzeroberfläche steuert.  
  
 [in] `bDisableIfNoHndler`  
 `TRUE`zum Deaktivieren der Benutzeroberflächen-Element, wenn kein Handler ist eine Nachricht Zuordnung definiert. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namerecalclayouta--cmfcribboncategoryrecalclayout"></a><a name="recalclayout"></a>CMFCRibbonCategory::RecalcLayout  
 Passt das Layout aller Steuerelemente auf der Multifunktionsleiste-Kategorie.  
  
```  
virtual void RecalcLayout(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf einen Gerätekontext für die Menübandkategorie.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameremovepanela--cmfcribboncategoryremovepanel"></a><a name="removepanel"></a>CMFCRibbonCategory::RemovePanel  
 Entfernt ein Menübandbereich aus der Menübandkategorie.  
  
```cpp  
BOOL RemovePanel(
    int nIndex,  
    BOOL bDelete = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Die Indexnummer des zu entfernenden. Durch den Aufruf der [CMFCRibbonCategory::GetPanelIndex](#getpanelindex) Methode.  
  
 [in] `bDelete`  
 `TRUE`Das Panelobjekt aus dem Speicher zu löschen; `FALSE` das Panelobjekt zu entfernen, ohne sie zu löschen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn die Methode erfolgreich ausgeführt wurde, andernfalls `FALSE`.  
  
##  <a name="a-namerepospanelsa--cmfcribboncategoryrepospanels"></a><a name="repospanels"></a>CMFCRibbonCategory::ReposPanels  
 Passt das Layout aller Steuerelemente auf der Multifunktionsleiste, die in der Menübandkategorie enthalten sind.  
  
```  
virtual void ReposPanels(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf einen Gerätekontext für die menübandbereiche, die in der Menübandkategorie enthalten sind.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetcollapseordera--cmfcribboncategorysetcollapseorder"></a><a name="setcollapseorder"></a>CMFCRibbonCategory::SetCollapseOrder  
 Definiert die Reihenfolge, in der die Multifunktionsleiste Bereiche der Menübandkategorie reduzieren.  
  
```  
void SetCollapseOrder(const CArray<int,int>& arCollapseOrder);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `arCollapseOrder`  
 Gibt die Reihenfolge reduzieren. Das Array enthält nullbasierten Indizes ein Menübandbereich enthalten.  
  
### <a name="remarks"></a>Hinweise  
 Die Bibliothek definiert die Reihenfolge, reduzieren. Allerdings können Sie dieses Verhalten anpassen, durch die Bereitstellung der Kategorie mit der Liste der Indizes, die die Reihenfolge reduzieren angibt.  
  
 Wenn die Kategorie erkennt, dass er mit einem Menübandbereich zu reduzieren muss, sucht er das nächste Element in der angegebenen Liste. Wenn die Liste leer ist oder nicht genügend Elemente angegeben haben, wird die Kategorie der internen Algorithmus verwendet.  
  
 Z. B. die Kategorie verfügt über drei menübandbereiche und kann reduziert werden mehrere Male, bis alle Bereiche in vollständig reduzierten Zustand befinden. Sie können die folgenden reduzieren Reihenfolge festlegen: 0, 0, 2, 2. In diesem Fall die Kategorie wird im Bereich 0 zweimal reduzieren, Bereich 2 zwei Mal. Der Bereich mit dem Index 1 bleibt angezeigt.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `SetCollapseOrder` -Methode in der `CMFCRibbonCategory` Klasse. Das Beispiel zeigt, wie ein Array für die Bestellung reduzieren und wie die reduzieren Reihenfolge auf die Menübandkategorie festgelegt.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#13;](../../mfc/reference/codesnippet/cpp/cmfcribboncategory-class_2.cpp)]  
  
##  <a name="a-namesetdataa--cmfcribboncategorysetdata"></a><a name="setdata"></a>CMFCRibbonCategory::SetData  
 Legt die benutzerdefinierten Daten die Menübandkategorie zugeordnet werden soll.  
  
```  
void SetData(DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwData`  
 Die benutzerdefinierten Daten.  
  
##  <a name="a-namesetkeysa--cmfcribboncategorysetkeys"></a><a name="setkeys"></a>CMFCRibbonCategory::SetKeys  
 Die Menübandkategorie eine Zugriffstasteninfo zugewiesen.  
  
```  
void SetKeys(LPCTSTR lpszKeys);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszKeys`  
 Der Text Zugriffstasteninfo.  
  
### <a name="remarks"></a>Hinweise  
 KeyTips werden angezeigt, wenn der Benutzer die Alt-Taste oder die F10-TASTE drückt.  
  
##  <a name="a-namesetnamea--cmfcribboncategorysetname"></a><a name="setname"></a>CMFCRibbonCategory::SetName  
 Weist einen Namen und eine Zugriffstasteninfo der Menüband-Kategorie.  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszName`  
 Der Name und der Menübandkategorie Zugriffstasteninfo.  
  
### <a name="remarks"></a>Hinweise  
 Fügen Sie zum Festlegen der ZugriffstastenInfo für die Menübandkategorie eine neue-Zeile-Escape-Sequenz gefolgt von den Zeichen Zugriffstasteninfo zu `lpszName`.  
  
##  <a name="a-namesettabcolora--cmfcribboncategorysettabcolor"></a><a name="settabcolor"></a>CMFCRibbonCategory::SetTabColor  
 Legt die Farbe der Menübandkategorie fest.  
  
```  
void SetTabColor(AFX_RibbonCategoryColor color);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
 Gibt die neue Farbe der Menübandkategorie.  
  
### <a name="remarks"></a>Hinweise  
 Farbe kann einen der folgenden Werte sein:  
  
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

