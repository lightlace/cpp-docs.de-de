---
title: Klasse CMFCRibbonPanel | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonPanel
- AFXRIBBONPANEL/CMFCRibbonPanel
- AFXRIBBONPANEL/CMFCRibbonPanel::CMFCRibbonPanel
- AFXRIBBONPANEL/CMFCRibbonPanel::Add
- AFXRIBBONPANEL/CMFCRibbonPanel::AddSeparator
- AFXRIBBONPANEL/CMFCRibbonPanel::AddToolBar
- AFXRIBBONPANEL/CMFCRibbonPanel::FindByData
- AFXRIBBONPANEL/CMFCRibbonPanel::FindByID
- AFXRIBBONPANEL/CMFCRibbonPanel::GetCaptionHeight
- AFXRIBBONPANEL/CMFCRibbonPanel::GetCount
- AFXRIBBONPANEL/CMFCRibbonPanel::GetData
- AFXRIBBONPANEL/CMFCRibbonPanel::GetDefaultButton
- AFXRIBBONPANEL/CMFCRibbonPanel::GetDroppedDown
- AFXRIBBONPANEL/CMFCRibbonPanel::GetElement
- AFXRIBBONPANEL/CMFCRibbonPanel::GetElements
- AFXRIBBONPANEL/CMFCRibbonPanel::GetElementsByID
- AFXRIBBONPANEL/CMFCRibbonPanel::GetFocused
- AFXRIBBONPANEL/CMFCRibbonPanel::GetGalleryRect
- AFXRIBBONPANEL/CMFCRibbonPanel::GetHighlighted
- AFXRIBBONPANEL/CMFCRibbonPanel::GetIndex
- AFXRIBBONPANEL/CMFCRibbonPanel::GetItemIDsList
- AFXRIBBONPANEL/CMFCRibbonPanel::GetName
- AFXRIBBONPANEL/CMFCRibbonPanel::GetParentButton
- AFXRIBBONPANEL/CMFCRibbonPanel::GetParentCategory
- AFXRIBBONPANEL/CMFCRibbonPanel::GetParentMenuBar
- AFXRIBBONPANEL/CMFCRibbonPanel::GetPreferedMenuLocation
- AFXRIBBONPANEL/CMFCRibbonPanel::GetPressed
- AFXRIBBONPANEL/CMFCRibbonPanel::GetRect
- AFXRIBBONPANEL/CMFCRibbonPanel::GetVisibleElements
- AFXRIBBONPANEL/CMFCRibbonPanel::HasElement
- AFXRIBBONPANEL/CMFCRibbonPanel::HitTest
- AFXRIBBONPANEL/CMFCRibbonPanel::HitTestEx
- AFXRIBBONPANEL/CMFCRibbonPanel::Insert
- AFXRIBBONPANEL/CMFCRibbonPanel::InsertSeparator
- AFXRIBBONPANEL/CMFCRibbonPanel::IsCenterColumnVert
- AFXRIBBONPANEL/CMFCRibbonPanel::IsCollapsed
- AFXRIBBONPANEL/CMFCRibbonPanel::IsHighlighted
- AFXRIBBONPANEL/CMFCRibbonPanel::IsJustifyColumns
- AFXRIBBONPANEL/CMFCRibbonPanel::IsMainPanel
- AFXRIBBONPANEL/CMFCRibbonPanel::IsMenuMode
- AFXRIBBONPANEL/CMFCRibbonPanel::MakeGalleryItemVisible
- AFXRIBBONPANEL/CMFCRibbonPanel::OnKey
- AFXRIBBONPANEL/CMFCRibbonPanel::RecalcWidths
- AFXRIBBONPANEL/CMFCRibbonPanel::Remove
- AFXRIBBONPANEL/CMFCRibbonPanel::RemoveAll
- AFXRIBBONPANEL/CMFCRibbonPanel::Replace
- AFXRIBBONPANEL/CMFCRibbonPanel::ReplaceByID
- AFXRIBBONPANEL/CMFCRibbonPanel::SetCenterColumnVert
- AFXRIBBONPANEL/CMFCRibbonPanel::SetData
- AFXRIBBONPANEL/CMFCRibbonPanel::SetElementMenu
- AFXRIBBONPANEL/CMFCRibbonPanel::SetElementRTC
- AFXRIBBONPANEL/CMFCRibbonPanel::SetElementRTCByID
- AFXRIBBONPANEL/CMFCRibbonPanel::SetFocused
- AFXRIBBONPANEL/CMFCRibbonPanel::SetJustifyColumns
- AFXRIBBONPANEL/CMFCRibbonPanel::SetKeys
- AFXRIBBONPANEL/CMFCRibbonPanel::ShowPopup
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonPanel class
ms.assetid: 51d70749-1140-4386-b103-f14082049ba6
caps.latest.revision: 34
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
ms.openlocfilehash: 1f833e1fa59f733734da321718d5db73377fa4bd
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonpanel-class"></a>CMFCRibbonPanel-Klasse
Implementiert einen Bereich, der eine Anzahl von Menübandelementen enthält. Wenn der Bereich gezeichnet wird, werden darin so viele Elemente wie möglich angezeigt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonPanel : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonPanel::CMFCRibbonPanel](#cmfcribbonpanel)|Erstellt und initialisiert ein `CMFCRibbonPanel`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonPanel::Add](#add)|Im Bereich hinzugefügt ein Menübandelement.|  
|[CMFCRibbonPanel::AddSeparator](#addseparator)|Fügt ein Trennzeichen zum Menübandbereich.|  
|[CMFCRibbonPanel::AddToolBar](#addtoolbar)|Die Menübandbereich hinzugefügt eine Symbolleiste.|  
|[CMFCRibbonPanel::FindByData](#findbydata)||  
|[CMFCRibbonPanel::FindByID](#findbyid)|Gibt ein Element anhand einer angegebenen Befehls-ID.|  
|[CMFCRibbonPanel::GetCaptionHeight](#getcaptionheight)||  
|[CMFCRibbonPanel::GetCount](#getcount)|Gibt die Anzahl der Elemente in der Menübandbereich zurück.|  
|[CMFCRibbonPanel::GetData](#getdata)|Gibt die benutzerdefinierten Daten, die dem Bereich zugeordnet.|  
|[CMFCRibbonPanel::GetDefaultButton](#getdefaultbutton)||  
|[CMFCRibbonPanel::GetDroppedDown](#getdroppeddown)||  
|[CMFCRibbonPanel::GetElement](#getelement)|Gibt die Multifunktionsleisten-Element am angegebenen Index zurück.|  
|[CMFCRibbonPanel::GetElements](#getelements)|Ruft alle Elemente, die in der Menübandbereich enthalten sind.|  
|[CMFCRibbonPanel::GetElementsByID](#getelementsbyid)||  
|[CMFCRibbonPanel::GetFocused](#getfocused)|Gibt ein Fokuselement zurück.|  
|[CMFCRibbonPanel::GetGalleryRect](#getgalleryrect)|Gibt ein umschließendes Rechteck Gallery-Elements zurück.|  
|[CMFCRibbonPanel::GetHighlighted](#gethighlighted)||  
|[CMFCRibbonPanel::GetIndex](#getindex)||  
|[CMFCRibbonPanel::GetItemIDsList](#getitemidslist)||  
|[CMFCRibbonPanel::GetName](#getname)||  
|[CMFCRibbonPanel::GetParentButton](#getparentbutton)||  
|[CMFCRibbonPanel::GetParentCategory](#getparentcategory)|Gibt die übergeordnete Kategorie Menübandbereich zurück.|  
|[CMFCRibbonPanel::GetParentMenuBar](#getparentmenubar)||  
|[CMFCRibbonPanel::GetPreferedMenuLocation](#getpreferedmenulocation)||  
|[CMFCRibbonPanel::GetPressed](#getpressed)||  
|[CMFCRibbonPanel::GetRect](#getrect)||  
|[CMFCRibbonPanel::GetVisibleElements](#getvisibleelements)|Ruft ein Array von Elementen angezeigt.|  
|[CMFCRibbonPanel::HasElement](#haselement)||  
|[CMFCRibbonPanel::HitTest](#hittest)||  
|[CMFCRibbonPanel::HitTestEx](#hittestex)||  
|[CMFCRibbonPanel::Insert](#insert)|Fügt eine Multifunktionsleisten-Element an der angegebenen Position.|  
|[CMFCRibbonPanel::InsertSeparator](#insertseparator)|Fügt ein Trennzeichen an der angegebenen Position ein.|  
|[CMFCRibbonPanel::IsCenterColumnVert](#iscentercolumnvert)|Gibt an, ob alle Panel-Elemente zentriert werden soll (Ausrichtung) und/oder vertikal nach Spalte.|  
|[CMFCRibbonPanel::IsCollapsed](#iscollapsed)||  
|[CMFCRibbonPanel::IsHighlighted](#ishighlighted)||  
|[CMFCRibbonPanel::IsJustifyColumns](#isjustifycolumns)|Gibt an, ob alle Bereich Spalten die gleiche Breite aufweisen.|  
|[CMFCRibbonPanel::IsMainPanel](#ismainpanel)||  
|[CMFCRibbonPanel::IsMenuMode](#ismenumode)||  
|[CMFCRibbonPanel::MakeGalleryItemVisible](#makegalleryitemvisible)|Führt einen Bildlauf durch den Katalog für die angegebene Multifunktionsleisten-Element sichtbar zu machen.|  
|[CMFCRibbonPanel::OnKey](#onkey)||  
|[CMFCRibbonPanel::RecalcWidths](#recalcwidths)||  
|[CMFCRibbonPanel::Remove](#remove)|Entfernt und löscht optional ein Element am angegebenen Index.|  
|[CMFCRibbonPanel::RemoveAll](#removeall)|Entfernt alle Elemente im Menüband.|  
|[CMFCRibbonPanel::Replace](#replace)|Ersetzt ein Element mit einem anderen basierend auf den Indexwerten der entsprechenden.|  
|[CMFCRibbonPanel::ReplaceByID](#replacebyid)|Ersetzt ein Element mit einer anderen basierend auf einer angegebenen Befehls-ID.|  
|[CMFCRibbonPanel::SetCenterColumnVert](#setcentercolumnvert)|Ordnet das Panel, um Elemente nach Spalte vertikal auszurichten.|  
|[CMFCRibbonPanel::SetData](#setdata)|Ordnet mit der benutzerdefinierten Datentyps an.|  
|[CMFCRibbonPanel::SetElementMenu](#setelementmenu)|Weist ein Popup-Menü auf das Element mit der angegebenen Befehls-ID.|  
|[CMFCRibbonPanel::SetElementRTC](#setelementrtc)|Fügt ein Menübandelement, das durch die angegebene Laufzeit-Klasseninformationen zum Menübandbereich angegeben.|  
|[CMFCRibbonPanel::SetElementRTCByID](#setelementrtcbyid)|Fügt ein Menübandelement, das durch die angegebene Laufzeit-Klasseninformationen zum Menübandbereich angegeben.|  
|[CMFCRibbonPanel::SetFocused](#setfocused)|Setzt den Fokus auf das angegebene Element der Multifunktionsleiste.|  
|[CMFCRibbonPanel::SetJustifyColumns](#setjustifycolumns)|Aktiviert oder deaktiviert die Ausrichtung der Spalte.|  
|[CMFCRibbonPanel::SetKeys](#setkeys)|Legt die Tastenkombination, die im Menüband-Fenster wird angezeigt.|  
|[CMFCRibbonPanel::ShowPopup](#showpopup)||  
  
## <a name="remarks"></a>Hinweise  
 Menübandbereichen sind logische Gruppen von verwandten Aufgaben, die Sie im menübandkategorien erstellen. Die Größe des Menübands ändert wird das Panellayout automatisch so viele Elemente wie möglich angezeigt.  
  
 Sie erhalten ein Menüband Bereiche, die in einer Menübandkategorie enthalten ist, durch Aufrufen der [CMFCRibbonCategory::GetPanel](../../mfc/reference/cmfcribboncategory-class.md#getpanel) Methode.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie so konfigurieren Sie eine `CMFCRibbonPanel` Objekt mit verschiedenen Methoden in der `CMFCRibbonPanel` Klasse. Das Beispiel zeigt, wie legen Sie die Tastenkombination, die im Menüband-Fenster wird angezeigt, Elemente im Bereich vertikal ausrichten, indem Sie Spalte und Spalte Begründung zu aktivieren. Dieser Codeausschnitt ist Teil der [MS Office 2007-Demo-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo&#10;](../../mfc/reference/codesnippet/cpp/cmfcribbonpanel-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxRibbonPanel.h  
  
##  <a name="add"></a>CMFCRibbonPanel::Add  
 Fügt den angegebenen Multifunktionsleisten-Element in das Array von Menübandelemente, das in der Menübandbereich enthalten ist.  
  
```  
virtual void Add(CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `pElem`  
 Ein Zeiger auf ein Menübandelement.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="addseparator"></a>CMFCRibbonPanel::AddSeparator  
 Fügt ein Trennzeichen zum Menübandbereich.  
  
```  
virtual void AddSeparator();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um ein Trennzeichen zum Menübandbereich hinzufügen. Das Trennzeichen wird neben der Multifunktionsleisten-Element, das vom vorherigen Aufruf hinzugefügt wurde hinzugefügt [CMFCRibbonPanel::Add](#add). Rufen Sie an einer angegebenen Position eine Trennzeichen einfügen [CMFCRibbonPanel::InsertSeparator](#insertseparator).  
  
##  <a name="addtoolbar"></a>CMFCRibbonPanel::AddToolBar  
 Die Menübandbereich hinzugefügt eine Symbolleiste.  
  
```  
CMFCRibbonButtonsGroup* AddToolBar(
UINT uiToolbarResID,  
UINT uiColdResID = 0,  
UINT uiHotResID = 0,  
UINT uiDisabledResID = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiToolbarResID`  
 Gibt die Ressourcen-ID der Symbolleiste hinzufügen.  
  
 [in] `uiColdResID`  
 Gibt die Ressourcen-ID des kalten Bilder auf der Symbolleiste.  
  
 [in] `uiHotResID`  
 Gibt die Ressourcen-ID der Symbolleiste hot-Images.  
  
 [in] `uiDisabledResID`  
 Gibt die Ressourcen-ID auf der Symbolleiste deaktiviert Images.  
  
### <a name="return-value"></a>Rückgabewert  
 Rufen Sie diese Methode, um eine Symbolleiste zum Menübandbereich hinzufügen. Die Symbolleiste wird neben der Multifunktionsleisten-Element hinzugefügt, die vom vorherigen Aufruf von hinzugefügt [CMFCRibbonPanel::Add](#add).  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen über Symbolleisten, hervorgehobenen Bilder, kalte Bilder und deaktivierte Bilder finden Sie unter [CMFCToolBar Klasse](../../mfc/reference/cmfctoolbar-class.md).  
  
##  <a name="cmfcribbonpanel"></a>CMFCRibbonPanel::CMFCRibbonPanel  
 Erstellt und initialisiert ein [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md) Objekt.  
  
```  
CMFCRibbonPanel(
LPCTSTR lpszName = NULL,  
HICON hIcon = NULL);  
  
CMFCRibbonPanel(CMFCRibbonGallery* pPaletteButton);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszName`  
 Der Name des Bereichs Menüband.  
  
 [in] `hIcon`  
 Handle für das Symbol als Standardschaltfläche des Menüband-Panels.  
  
 [in] `pPaletteButton`  
 Ein Zeiger auf ein Menüband für das Menüband-Panel.  
  
##  <a name="findbydata"></a>CMFCRibbonPanel::FindByData  
 Ruft das Menübandelement, das die angegebenen Daten zugeordnet ist.  
  
```  
CMFCRibbonBaseElement* FindByData(DWORD_PTR dwData) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwData`  
 Die Daten, die ein Menübandelement zugeordnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf ein Menübandelement, wenn die Methode erfolgreich war; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="findbyid"></a>CMFCRibbonPanel::FindByID  
 Ruft die Multifunktionsleisten-Element, das von der angegebenen Befehls-ID identifiziert wird  
  
```  
CMFCRibbonBaseElement* FindByID(UINT uiCmdID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdID`  
 Befehls-ID der Multifunktionsleisten-Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Menübandelement, das von der angegebenen Befehls-ID angegeben wird; andernfalls `NULL` Wenn keine Multifunktionsleisten-Element mit der angegebenen Befehls-ID identifiziert wird  
  
##  <a name="getcaptionheight"></a>CMFCRibbonPanel::GetCaptionHeight  
 Ruft die Höhe einer Beschriftung für das Menüband Panel ab.  
  
```  
int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe der Beschriftung für den Menübandbereich in Pixel.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcount"></a>CMFCRibbonPanel::GetCount  
 Ruft die Anzahl der Menübandelemente, die klicken Sie im Menüband enthalten sind.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Menübandelemente, die klicken Sie im Menüband enthalten sind.  
  
##  <a name="getdata"></a>CMFCRibbonPanel::GetData  
 Gibt die benutzerdefinierten Daten, die dem Bereich zugeordnet.  
  
```  
DWORD_PTR GetData() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die benutzerdefinierten Daten im Bereich zugeordnet.  
  
##  <a name="getdefaultbutton"></a>CMFCRibbonPanel::GetDefaultButton  
 Ruft die Standardschaltfläche für das Menüband Panel ab.  
  
```  
CMFCRibbonButton& GetDefaultButton();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardschaltfläche für das Menüband-Panel.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardschaltfläche wird angezeigt, wenn ein Menübandbereich nicht genügend Platz zum Anzeigen von dessen Menübandelemente hat.  
  
##  <a name="getdroppeddown"></a>CMFCRibbonPanel::GetDroppedDown  
 Ruft einen Zeiger auf ein Menübandelement ab, wenn das Popup-Menü sichtbar ist.  
  
```  
CMFCRibbonBaseElement* GetDroppedDown() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf das Menübandelement, das das Popup-Menü unten gelöscht wurde; andernfalls `NULL` besitzt keine Multifunktionsleisten-Element seine Popupmenü eingetragen.  
  
### <a name="remarks"></a>Hinweise  
 Nur im Menübandbereich enthaltenen Menübandelemente werden getestet.  
  
##  <a name="getelement"></a>CMFCRibbonPanel::GetElement  
 Gibt die Multifunktionsleisten-Element am angegebenen Index zurück.  
  
```  
CMFCRibbonBaseElement* GetElement(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Gibt den nullbasierten Index des abzurufenden Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger Zeiger auf der Basis der Multifunktionsleisten-Element befindet sich an Position `nIndex` klicken Sie im Menüband oder `NULL` Wenn am angegebenen Index kein Element vorhanden ist.  
  
##  <a name="getelements"></a>CMFCRibbonPanel::GetElements  
 Ruft alle Menübandelemente, die in der Menübandbereich enthalten sind.  
  
```  
void GetElements(CArray<CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `arElements`  
 Ein Array mit alle Menübandelemente zu füllen, die in der Menübandbereich enthalten sind.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getelementsbyid"></a>CMFCRibbonPanel::GetElementsByID  
 Fügt die Multifunktionsleistenelemente mit der angegebenen Befehls-ID in das angegebene Array.  
  
```  
void GetElementsByID(
UINT uiCmdID,  
CArray<CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdID`  
 Befehls-ID für ein Menübandelement.  
  
 [in] `arElements`  
 Array von Menübandelementen.  
  
### <a name="remarks"></a>Hinweise  
 Nur im Menübandbereich enthaltenen Menübandelemente werden getestet.  
  
##  <a name="gethighlighted"></a>CMFCRibbonPanel::GetHighlighted  
 Ruft das Menübandelement, das im Menübandbereich markiert ist.  
  
```  
CMFCRibbonBaseElement* GetHighlighted() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Multifunktionsleisten-Element, das im Menübandbereich markiert ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getindex"></a>CMFCRibbonPanel::GetIndex  
 Ruft den nullbasierten Index des angegebenen Menübandelements aus dem Array von Menübandelemente, die klicken Sie im Menüband enthalten sind.  
  
```  
virtual int GetIndex(CMFCRibbonBaseElement* pElem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pElem`  
 Ein Zeiger auf ein Menübandelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Nullbasierte Index des angegebenen Menübandelement, wenn die Methode erfolgreich war. andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getitemidslist"></a>CMFCRibbonPanel::GetItemIDsList  
 Ruft die Befehls-IDs für alle Menübandelemente im Menübandbereich ab.  
  
```  
void GetItemIDsList(CList<UINT, UINT>& lstItems) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `lstItems`  
 Die Liste der Befehls-IDs für Menübandelemente, die klicken Sie im Menüband enthalten sind.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getname"></a>CMFCRibbonPanel::GetName  
 Ruft den Namen des Panels Menüband.  
  
```  
LPCTSTR GetName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name des Bereichs Menüband.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getparentbutton"></a>CMFCRibbonPanel::GetParentButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCRibbonBaseElement* GetParentButton() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getparentcategory"></a>CMFCRibbonPanel::GetParentCategory  
 Gibt die übergeordnete Kategorie Menübandbereich zurück.  
  
```  
CMFCRibbonCategory* GetParentCategory() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Menübandkategorie, die dieses Menüband-Steuerelement enthält.  
  
##  <a name="getparentmenubar"></a>CMFCRibbonPanel::GetParentMenuBar  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCRibbonPanelMenuBar* GetParentMenuBar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getpreferedmenulocation"></a>CMFCRibbonPanel::GetPreferedMenuLocation  
 Ruft die bevorzugte Anzeigerechteck für das Popupmenü im Menüband-Bereich ab.  
  
```  
virtual BOOL GetPreferedMenuLocation(CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rect`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer `FALSE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt immer `FALSE` zurück. Überschreiben Sie diese Methode, um das Rechteck Anzeigestil für die Popup-Menü im Menüband-Bereich abgerufen.  
  
##  <a name="getpressed"></a>CMFCRibbonPanel::GetPressed  
 Ruft einen Zeiger auf ein Menübandelement im Menübandbereich ab, wenn der Benutzer derzeit drückt.  
  
```  
CMFCRibbonBaseElement* GetPressed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Menübandelement, wenn der Benutzer derzeit drückt; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getrect"></a>CMFCRibbonPanel::GetRect  
 Ruft das Anzeigerechteck für das Menüband Panel ab.  
  
```  
const CRect& GetRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Anzeigerechteck für den Menübandbereich.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="haselement"></a>CMFCRibbonPanel::HasElement  
 Gibt an, ob der Menübandbereich der angegebenen Multifunktionsleisten-Element enthält.  
  
```  
BOOL HasElement(const CMFCRibbonBaseElement* pElem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pElem`  
 Ein Zeiger auf ein Menübandelement.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Menübandbereich der angegebenen Multifunktionsleisten-Element enthält. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="highlight"></a>CMFCRibbonPanel::Highlight  
 Legt die Hervorhebungsfarbe für den ausgewählten Menübandbereich und für das Menübandelement vom Punkt angegeben.  
  
```  
virtual void Highlight(
BOOL bHighlight,  
CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bHighlight`  
 `TRUE`auf der Menübandbereich zu markieren. `FALSE` auf Menübandbereich unhighlight.  
  
 [in] `point`  
 Die x- und y-Koordinaten des Mauszeigers, in Bezug auf die linke obere Ecke des Fensters.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hittest"></a>CMFCRibbonPanel::HitTest  
 Ruft ein Menübandelement ab, wenn der angegebene Punkt darin befindet.  
  
```  
virtual CMFCRibbonBaseElement* HitTest(
CPoint point,  
BOOL bCheckPanelCaption = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Die x- und y-Koordinaten des Mauszeigers, in Bezug auf die linke obere Ecke des Fensters.  
  
 [in] `bCheckPanelCaption`  
 `TRUE`So testen Sie die Beschriftung der Menüband-Bereich; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf ein Menübandelement, wenn der angegebene Punkt darin enthalten ist; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Nur im Menübandbereich enthaltenen Menübandelemente werden getestet.  
  
##  <a name="hittestex"></a>CMFCRibbonPanel::HitTestEx  
 Ruft den nullbasierten Index des Multifunktionsleisten-Element, das den angegebenen Punkt darin verfügt.  
  
```  
virtual int HitTestEx(CPoint point) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Die x- und y-Koordinaten des Mauszeigers, in Bezug auf die linke obere Ecke des Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des Menübandelements, die den angegebenen Punkt darin verfügt; andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Nur im Menübandbereich enthaltenen Menübandelemente werden getestet.  
  
##  <a name="insert"></a>CMFCRibbonPanel::Insert  
 Fügt den angegebenen Multifunktionsleisten-Element an der angegebenen Position im Array von Menübandelementen, die in der Menübandbereich enthalten ist.  
  
```  
virtual BOOL Insert(
CMFCRibbonBaseElement* pElem,  
int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `pElem`  
 Ein Zeiger auf ein Menübandelement.  
  
 [in] `nIndex`  
 Nullbasierter Wert von-1 bis zu der Anzahl der Menübandelemente, die im Array enthalten sind.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Menübandelement erfolgreich eingefügt wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Wert der `nIndex` ist-1, oder wenn `nIndex` gleich der Anzahl der Menübandelemente im Array, das angegebene Menübandelement wird bis zum Ende des Arrays hinzugefügt. Wenn der Wert des `nIndex` ist außerhalb des Bereichs, der die Methode schlägt fehl.  
  
##  <a name="insertseparator"></a>CMFCRibbonPanel::InsertSeparator  
 Fügt ein Trennzeichen an der angegebenen Position ein.  
  
```  
virtual BOOL InsertSeparator(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Gibt den nullbasierten Index, an dem das Trennzeichen eingefügt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Trennzeichen erfolgreich eingefügt wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um ein Trennzeichen einzufügen, an der angegebenen Position `nIndex`. Rufen Sie zum Einfügen von Trennzeichen neben das zuletzt hinzugefügte Menübandelement [CMFCRibbonPanel::AddSeparator](#addseparator).  
  
##  <a name="iscentercolumnvert"></a>CMFCRibbonPanel::IsCenterColumnVert  
 Gibt an, ob die vertikale Position von Menübandelemente innerhalb ihrer Anzeigerechteck zentriert werden.  
  
```  
BOOL IsCenterColumnVert() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die vertikale von positioniert Menübandelemente innerhalb ihrer Anzeigerechteck zentriert; andernfalls `FALSE`.  
  
##  <a name="iscollapsed"></a>CMFCRibbonPanel::IsCollapsed  
 Gibt an, ob die Größe des Bereichs Menüband in horizontaler Richtung minimiert wird.  
  
```  
BOOL IsCollapsed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Größe des Bereichs Menüband, in horizontaler Richtung minimiert wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Menübandbereich reduziert ist, wird nur die Standardschaltfläche, den Namen und ein Dropdown Pfeil.  
  
##  <a name="ishighlighted"></a>CMFCRibbonPanel::IsHighlighted  
 Gibt an, ob die Anzeige der Menübandbereich hervorgehoben wird.  
  
```  
BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Anzeige des Bereichs Menüband hervorgehoben ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die Anzeige von einem Menübandbereich wird hervorgehoben, wenn der Mauszeiger darüber befindet.  
  
##  <a name="isjustifycolumns"></a>CMFCRibbonPanel::IsJustifyColumns  
 Gibt an, ob die Anzeige Dimensionen Menübandelemente, die in der gleichen Spalte klicken Sie im Menüband auf die gleiche Breite festgelegt werden.  
  
```  
BOOL IsJustifyColumns() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Anzeige Dimensionen Menübandelemente, die in der gleichen Spalte klicken Sie im Menüband auf die gleiche Breite festgelegt werden; andernfalls `FALSE`.  
  
##  <a name="ismainpanel"></a>CMFCRibbonPanel::IsMainPanel  
 Gibt an, ob Menübandbereich der Multifunktionsleiste-Bereich ist.  
  
```  
virtual BOOL IsMainPanel() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer `FALSE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt immer `FALSE` zurück. Überschreiben Sie diese Methode, um anzugeben, ob der Menübandbereich im Bereich der Multifunktionsleiste ist.  
  
 Die Multifunktionsleiste wird eingeblendet, wenn der Benutzer die Schaltfläche auswählt.  
  
##  <a name="ismenumode"></a>CMFCRibbonPanel::IsMenuMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsMenuMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onkey"></a>CMFCRibbonPanel::OnKey  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnKey(UINT nChar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nChar`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="recalcwidths"></a>CMFCRibbonPanel::RecalcWidths  
 Berechnet die Breite der Konfiguration jedes Layout für den Menübandbereich.  
  
```  
virtual void RecalcWidths(
CDC* pDC,  
int nHeight);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf einen Gerätekontext für das Menüband-Panel.  
  
 [in] `nHeight`  
 Die Höhe des Bereichs Menüband.  
  
### <a name="remarks"></a>Hinweise  
 Ein Menüband-Panel ändert seine Konfiguration Layout die verfügbare Breite geändert.  
  
##  <a name="remove"></a>CMFCRibbonPanel::Remove  
 Entfernt und löscht optional ein Element am angegebenen Index.  
  
```  
BOOL Remove(
int nIndex,  
BOOL bDelete = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Gibt den nullbasierten Index des Elements, das aus dem Menübandbereich entfernt wird.  
  
 [in] `bDelete`  
 `TRUE`So löschen Sie das Element entfernt wird; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Element entfernt und gelöscht wurde (Wenn `bDelete` ist `TRUE`); `FALSE` Wenn das Element nicht entfernt wurde oder ist es befindet sich kein Multifunktionsleisten-Element am `nIndex`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um ein Element aus der Menübandbereich zu entfernen.  
  
##  <a name="removeall"></a>CMFCRibbonPanel::RemoveAll  
 Löscht alle Menübandelemente aus dem Menübandbereich.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Alle Menübandelemente aus Menübandbereich gelöscht und zerstört.  
  
##  <a name="replace"></a>CMFCRibbonPanel::Replace  
 Ersetzt ein Element mit einem anderen basierend auf ihrer Indexwert.  
  
```  
BOOL Replace(
int nIndex,  
CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Gibt den nullbasierten Index des zu ersetzenden Elements.  
  
 [in] [out]`pElem`  
 Ein gültiger Zeiger auf das Element, das das ursprüngliche Element ersetzt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die ursprüngliche-Element Multifunktionsleisten wurde erfolgreich durch die neue Multifunktionsleisten-Element ersetzt. `FALSE` Wenn das Menübandelement nicht ersetzt wurde oder wenn kein Element am angegebenen Index vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Um ein Menübandelement von Befehls-ID zu ersetzen, rufen Sie [CMFCRibbonPanel::ReplaceByID](#replacebyid).  
  
##  <a name="replacebyid"></a>CMFCRibbonPanel::ReplaceByID  
 Ersetzt ein Element mit einer anderen basierend auf einer angegebenen Befehls-ID.  
  
```  
BOOL ReplaceByID(
UINT uiCmdID,  
CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdID`  
 Gibt die Befehls-ID des Elements zu ersetzen.  
  
 [in] [out]`pElem`  
 Ein gültiger Zeiger auf das Element, das das ursprüngliche Element ersetzt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die ursprüngliche-Element Multifunktionsleisten wurde erfolgreich durch die neue Multifunktionsleisten-Element ersetzt. `FALSE` Wenn das Menübandelement nicht ersetzt wurde oder wenn kein Element mit der angegebenen Befehls-ID tatsächlich vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Um ein Menübandelement je nach Position zu ersetzen, rufen Sie [CMFCRibbonPanel::Replace](#replace).  
  
##  <a name="setcentercolumnvert"></a>CMFCRibbonPanel::SetCenterColumnVert  
 Aktiviert oder deaktiviert die Zentrieren der vertikalen Positionen von Menübandelementen innerhalb ihrer Anzeigerechteck.  
  
```  
void SetCenterColumnVert(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bSet`  
 `TRUE`So zentrieren Sie die vertikale Position von Menübandelemente innerhalb ihrer Anzeigerechteck; `FALSE` wird diese Funktion deaktiviert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setdata"></a>CMFCRibbonPanel::SetData  
 Ordnet mit der benutzerdefinierten Datentyps an.  
  
```  
void SetData(DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwData`  
 Gibt die benutzerdefinierten Daten festlegen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um benutzerdefinierte Daten mit dem zuordnen.  
  
##  <a name="setelementmenu"></a>CMFCRibbonPanel::SetElementMenu  
 Weist ein Popup-Menü auf das Element mit der angegebenen Befehls-ID.  
  
```  
BOOL SetElementMenu(
UINT uiCmdID,  
HMENU hMenu,  
BOOL bIsDefautCommand = FALSE,  
BOOL bRightAlign = FALSE);

 
BOOL SetElementMenu(
UINT uiCmdID,  
UINT uiMenuResID,  
BOOL bIsDefautCommand = FALSE,  
BOOL bRightAlign = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdID`  
 Gibt die Befehls-ID des Menübandelements, klicken Sie im Menü hinzugefügt wird.  
  
 [in] `hMenu`  
 Gibt das Handle für das Windows-Menü im Menübandbereich hinzu.  
  
 [in] `bIsDefautCommand`  
 `TRUE`um festzulegen, das Menübandelement zugeordnete Befehl ausgeführt werden soll, wenn das Menübandelement geklickt wird. In diesem Fall wird im Menü nur geöffnet, wenn der Benutzer auf den Pfeil neben der Multifunktionsleisten-Element klickt. `FALSE`um anzugeben, dass die Multifunktionsleisten-Element zugeordnete Befehl nicht ausgeführt werden soll, wenn das Menübandelement geklickt wird. In diesem Fall wird im Popupmenü angezeigt, unabhängig davon, wo der Benutzer auf das Element klickt.  
  
 [in] `bRightAlign`  
 `TRUE`um anzugeben, dass das Popupmenü rechts ausgerichtet; andernfalls `FALSE`.  
  
 [in] `uiMenuResID`  
 Gibt die Ressourcen-ID des Menüs zu dem Bereich der Multifunktionsleiste hinzuzufügen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Sie im Menü auf das Menübandelement zugewiesen wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um ein Popup-Menü auf das Menübandelement zuweisen, die die angegebene Befehls-ID.  
  
##  <a name="setelementrtc"></a>CMFCRibbonPanel::SetElementRTC  
 Fügt das Menübandelement, das durch die angegebene Laufzeit-Klasseninformationen zum Menübandbereich angegeben wird.  
  
```  
CMFCRibbonBaseElement* SetElementRTC(
int nIndex,  
CRuntimeClass* pRTC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Gibt den nullbasierten Index des Menübandelements hinzufügen.  
  
 [in] [out]`pRTC`  
 Ein Zeiger auf die Laufzeit-Klasseninformationen für das Menübandelement, das zum Menübandbereich hinzugefügt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Multifunktionsleisten-Element, das mit dem angegebenen Common Language Runtime-Klasse erstellt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein benutzerdefiniertes Element (z. B. eine farbenschaltfläche "), wenn der Menübandbereich hinzufügen möchten, müssen Sie das benutzerdefinierte Element Laufzeit-Klasseninformationen angeben. Die Multifunktionsleiste speichert diese Informationen, erstellt das benutzerdefinierte Element und ersetzt ein vorhandenes Element, das sich befindet (identifiziert durch) der angegebenen Befehls-ID. Die Multifunktionsleiste gibt einen Zeiger auf das neu erstellte Element zurück.  
  
##  <a name="setelementrtcbyid"></a>CMFCRibbonPanel::SetElementRTCByID  
 Fügt ein Menübandelement, das durch die angegebene Laufzeit-Klasseninformationen zum Menübandbereich angegeben wird.  
  
```  
CMFCRibbonBaseElement* SetElementRTCByID(
UINT uiCmdID,  
CRuntimeClass* pRTC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdID`  
 Gibt die Befehls-ID des Menübandelements hinzufügen.  
  
 [in] [out]`pRTC`  
 Ein Zeiger auf die Laufzeit-Klasseninformationen zugeordnete Multifunktionsleisten-Element, das den Menübandbereich hinzugefügt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Multifunktionsleisten-Element, das mit dem angegebenen Common Language Runtime-Klasse erstellt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein benutzerdefiniertes Element (z. B. eine farbenschaltfläche "), wenn der Menübandbereich hinzufügen möchten, müssen Sie das benutzerdefinierte Element Laufzeit-Klasseninformationen angeben. Die Multifunktionsleiste speichert diese Informationen, erstellt das benutzerdefinierte Element und ersetzt ein vorhandenes Element anhand der angegebenen Befehls-ID. Es gibt einen Zeiger auf das neu erstellte Element zurück.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die `SetElementRTCByID` Methode:  
  
```  
 
// Load and add toolbar with standard buttons. This toolbar  
// should display a custom color button with id ID_CHAR_COLOR:  
 
pPanel->AddToolBar(IDR_MAINFRAME,
    IDB_MAINFRAME256);

CMFCRibbonColorButton* pColorButton = 
(CMFCRibbonColorButton*)pPanel->SetElementRTCByID(
ID_CHAR_COLOR,
    RUNTIME_CLASS (CMFCRibbonColorButton));

 
// SetElementRTCByID sets runtime class and returns a pointer  
// to the newly created custom button,
    which can be set up immediately:  
pColorButton->EnableAutomaticButton(_T("Automatic"),
    RGB (0,
    0,
    0));  
```  
  
##  <a name="setjustifycolumns"></a>CMFCRibbonPanel::SetJustifyColumns  
 Aktiviert oder deaktiviert die Anpassung der Breite des Menübandelemente in der gleichen Spalte.  
  
```  
void SetJustifyColumns(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bSet`  
 `TRUE`um die Breite des Menübandelemente in der gleichen Spalte an die Breite des größten Menübandelements in der Spalte anpassen. `FALSE` diese Anpassung der Breite zu deaktivieren.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Funktion in einem Menübandbereich aktiviert ist, werden die Breiten der Menübandelemente in der gleichen Spalte an die Breite des größten Elements in der gleichen Spalte Multifunktionsleiste angepasst.  
  
##  <a name="setkeys"></a>CMFCRibbonPanel::SetKeys  
 Legt die ZugriffstastenInfo für die Standardschaltfläche des Menüband-Bedienfelds fest.  
  
```  
void SetKeys(LPCTSTR lpszKeys);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszKeys`  
 Der ZugriffstastenInfo für die Standardschaltfläche des Menüband-Bereichs.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardschaltfläche wird angezeigt, wenn ein Menübandbereich nicht genügend Platz zum Anzeigen von dessen Menübandelemente hat.  
  
##  <a name="showpopup"></a>CMFCRibbonPanel::ShowPopup  
 Erstellt und ein Popup-Menü für den Bereich der Multifunktionsleiste angezeigt.  
  
```  
CMFCRibbonPanelMenu* ShowPopup(CMFCRibbonDefaultPanelButton* pButton = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pButton`  
 Ein Zeiger auf die Standardschaltfläche für das Menüband-Panel.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf das Popupmenü für das Menüband-Panel, wenn die Methode erfolgreich war; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Im Popupmenü Menübandbereich ist nur verfügbar, wenn die Anzeige des Bereichs Menüband reduziert wird.  
  
##  <a name="setfocused"></a>CMFCRibbonPanel::SetFocused  
 Setzt den Fokus auf das angegebene Element der Multifunktionsleiste.  
  
```  
void SetFocused(CMFCRibbonBaseElement* pNewFocus);
```  
  
### <a name="parameters"></a>Parameter  
 `pNewFocus`  
 Ein Zeiger auf ein Menübandelement, das Fokus erhält.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="makegalleryitemvisible"></a>CMFCRibbonPanel::MakeGalleryItemVisible  
 Führt einen Bildlauf durch den Katalog für die angegebene Multifunktionsleisten-Element sichtbar zu machen.  
  
```  
void MakeGalleryItemVisible(CMFCRibbonBaseElement* pItem);
```  
  
### <a name="parameters"></a>Parameter  
 `pItem`  
 Ein Zeiger auf ein Menübandelement angezeigt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="iswindows7look"></a>CMFCRibbonPanel::IsWindows7Look  
 Gibt an, ob der übergeordnete Menüband verfügt über ein Windows 7 (kleine rechteckige Anwendungsschaltfläche) zu suchen.  
  
```  
BOOL IsWindows7Look() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die übergeordnete Multifunktionsleiste Aussehen von Windows 7 enthält. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getvisibleelements"></a>CMFCRibbonPanel::GetVisibleElements  
 Ruft ein Array von Elementen angezeigt.  
  
```  
void GetVisibleElements(
CArray<CMFCRibbonBaseElement*,  
CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Parameter  
 `arElements`  
 Wenn die Funktion zurückgibt, enthält dieser Parameter ein Array von Elementen angezeigt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getgalleryrect"></a>CMFCRibbonPanel::GetGalleryRect  
 Gibt ein umschließende Rechteck von einem Galerieelement.  
  
```  
CRect GetGalleryRect();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Größe und Position des Elements Katalog innerhalb dieses Bereichs.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getfocused"></a>CMFCRibbonPanel::GetFocused  
 Gibt ein Fokuselement zurück.  
  
```  
CMFCRibbonBaseElement* GetFocused() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Fokuselement oder `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [CMFCRibbonCategory-Klasse](../../mfc/reference/cmfcribboncategory-class.md)   
 [CMFCRibbonBaseElement-Klasse](../../mfc/reference/cmfcribbonbaseelement-class.md)

