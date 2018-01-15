---
title: CMFCRibbonPanel Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CMFCRibbonPanel [MFC], CMFCRibbonPanel
- CMFCRibbonPanel [MFC], Add
- CMFCRibbonPanel [MFC], AddSeparator
- CMFCRibbonPanel [MFC], AddToolBar
- CMFCRibbonPanel [MFC], FindByData
- CMFCRibbonPanel [MFC], FindByID
- CMFCRibbonPanel [MFC], GetCaptionHeight
- CMFCRibbonPanel [MFC], GetCount
- CMFCRibbonPanel [MFC], GetData
- CMFCRibbonPanel [MFC], GetDefaultButton
- CMFCRibbonPanel [MFC], GetDroppedDown
- CMFCRibbonPanel [MFC], GetElement
- CMFCRibbonPanel [MFC], GetElements
- CMFCRibbonPanel [MFC], GetElementsByID
- CMFCRibbonPanel [MFC], GetFocused
- CMFCRibbonPanel [MFC], GetGalleryRect
- CMFCRibbonPanel [MFC], GetHighlighted
- CMFCRibbonPanel [MFC], GetIndex
- CMFCRibbonPanel [MFC], GetItemIDsList
- CMFCRibbonPanel [MFC], GetName
- CMFCRibbonPanel [MFC], GetParentButton
- CMFCRibbonPanel [MFC], GetParentCategory
- CMFCRibbonPanel [MFC], GetParentMenuBar
- CMFCRibbonPanel [MFC], GetPreferedMenuLocation
- CMFCRibbonPanel [MFC], GetPressed
- CMFCRibbonPanel [MFC], GetRect
- CMFCRibbonPanel [MFC], GetVisibleElements
- CMFCRibbonPanel [MFC], HasElement
- CMFCRibbonPanel [MFC], HitTest
- CMFCRibbonPanel [MFC], HitTestEx
- CMFCRibbonPanel [MFC], Insert
- CMFCRibbonPanel [MFC], InsertSeparator
- CMFCRibbonPanel [MFC], IsCenterColumnVert
- CMFCRibbonPanel [MFC], IsCollapsed
- CMFCRibbonPanel [MFC], IsHighlighted
- CMFCRibbonPanel [MFC], IsJustifyColumns
- CMFCRibbonPanel [MFC], IsMainPanel
- CMFCRibbonPanel [MFC], IsMenuMode
- CMFCRibbonPanel [MFC], MakeGalleryItemVisible
- CMFCRibbonPanel [MFC], OnKey
- CMFCRibbonPanel [MFC], RecalcWidths
- CMFCRibbonPanel [MFC], Remove
- CMFCRibbonPanel [MFC], RemoveAll
- CMFCRibbonPanel [MFC], Replace
- CMFCRibbonPanel [MFC], ReplaceByID
- CMFCRibbonPanel [MFC], SetCenterColumnVert
- CMFCRibbonPanel [MFC], SetData
- CMFCRibbonPanel [MFC], SetElementMenu
- CMFCRibbonPanel [MFC], SetElementRTC
- CMFCRibbonPanel [MFC], SetElementRTCByID
- CMFCRibbonPanel [MFC], SetFocused
- CMFCRibbonPanel [MFC], SetJustifyColumns
- CMFCRibbonPanel [MFC], SetKeys
- CMFCRibbonPanel [MFC], ShowPopup
ms.assetid: 51d70749-1140-4386-b103-f14082049ba6
caps.latest.revision: "34"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b8c91cdd7b793195e0afb05acfe3fc33694fdb60
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcribbonpanel-class"></a>CMFCRibbonPanel-Klasse
Implementiert einen Bereich, der eine Anzahl von Menübandelementen enthält. Wenn der Bereich gezeichnet wird, werden darin so viele Elemente wie möglich angezeigt.  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
 
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonPanel : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonPanel::CMFCRibbonPanel](#cmfcribbonpanel)|Erstellt und initialisiert ein `CMFCRibbonPanel`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Cmfcribbonpanel:: Add](#add)|Fügt ein Menübandelement in den Bereich an.|  
|[CMFCRibbonPanel::AddSeparator](#addseparator)|Fügt ein Trennzeichen zum Menübandbereich an.|  
|[CMFCRibbonPanel::AddToolBar](#addtoolbar)|Der Menübandbereich hinzugefügt eine Symbolleiste.|  
|[CMFCRibbonPanel::FindByData](#findbydata)||  
|[CMFCRibbonPanel::FindByID](#findbyid)|Gibt ein Element, der durch einen angegebenen Befehls-ID identifiziert wird.|  
|[CMFCRibbonPanel::GetCaptionHeight](#getcaptionheight)||  
|[CMFCRibbonPanel::GetCount](#getcount)|Gibt die Anzahl der Elemente in der Menübandbereich zurück.|  
|[CMFCRibbonPanel::GetData](#getdata)|Gibt die benutzerdefinierten Daten, die im Bereich zugeordnet.|  
|[CMFCRibbonPanel::GetDefaultButton](#getdefaultbutton)||  
|[CMFCRibbonPanel::GetDroppedDown](#getdroppeddown)||  
|[CMFCRibbonPanel::GetElement](#getelement)|Gibt die Menübandelement am angegebenen Index zurück.|  
|[CMFCRibbonPanel::GetElements](#getelements)|Ruft alle Elemente, die in der Menübandbereich enthalten sind.|  
|[CMFCRibbonPanel::GetElementsByID](#getelementsbyid)||  
|[CMFCRibbonPanel::GetFocused](#getfocused)|Gibt ein Fokuselement zurück.|  
|[CMFCRibbonPanel::GetGalleryRect](#getgalleryrect)|Gibt ein umschließendes Rechteck Gallery Elements zurück.|  
|[CMFCRibbonPanel::GetHighlighted](#gethighlighted)||  
|[CMFCRibbonPanel::GetIndex](#getindex)||  
|[CMFCRibbonPanel::GetItemIDsList](#getitemidslist)||  
|[CMFCRibbonPanel::GetName](#getname)||  
|[CMFCRibbonPanel::GetParentButton](#getparentbutton)||  
|[CMFCRibbonPanel::GetParentCategory](#getparentcategory)|Gibt die übergeordnete Kategorie der Menübandbereich zurück.|  
|[CMFCRibbonPanel::GetParentMenuBar](#getparentmenubar)||  
|[CMFCRibbonPanel::GetPreferedMenuLocation](#getpreferedmenulocation)||  
|[CMFCRibbonPanel::GetPressed](#getpressed)||  
|[CMFCRibbonPanel::GetRect](#getrect)||  
|[CMFCRibbonPanel::GetVisibleElements](#getvisibleelements)|Ruft ein Array von sichtbaren Elemente ab.|  
|[CMFCRibbonPanel::HasElement](#haselement)||  
|[CMFCRibbonPanel::HitTest](#hittest)||  
|[CMFCRibbonPanel::HitTestEx](#hittestex)||  
|[CMFCRibbonPanel::Insert](#insert)|Fügt ein Menübandelement an der angegebenen Position.|  
|[CMFCRibbonPanel::InsertSeparator](#insertseparator)|Fügt ein Trennzeichen an der angegebenen Position ein.|  
|[CMFCRibbonPanel::IsCenterColumnVert](#iscentercolumnvert)|Gibt an, ob alle Bereichselementen zentriert werden soll (ausgerichtet) vertikal nach Spalte.|  
|[CMFCRibbonPanel::IsCollapsed](#iscollapsed)||  
|[CMFCRibbonPanel::IsHighlighted](#ishighlighted)||  
|[CMFCRibbonPanel::IsJustifyColumns](#isjustifycolumns)|Gibt an, ob alle Bereich Spalten die gleiche Breite aufweisen.|  
|[CMFCRibbonPanel::IsMainPanel](#ismainpanel)||  
|[CMFCRibbonPanel::IsMenuMode](#ismenumode)||  
|[CMFCRibbonPanel::MakeGalleryItemVisible](#makegalleryitemvisible)|Scrollt den Katalog für den angegebenen Menübandelement sichtbar zu machen.|  
|[CMFCRibbonPanel::OnKey](#onkey)||  
|[CMFCRibbonPanel::RecalcWidths](#recalcwidths)||  
|[CMFCRibbonPanel::Remove](#remove)|Entfernt, und löscht optional ein Element am angegebenen Index.|  
|[CMFCRibbonPanel::RemoveAll](#removeall)|Entfernt alle Elemente aus dem Menübandbereich.|  
|[CMFCRibbonPanel::Replace](#replace)|Ersetzt ein Element mit einem anderen basierend auf ihren Indexwerten der entsprechenden.|  
|[CMFCRibbonPanel::ReplaceByID](#replacebyid)|Ersetzt ein Element mit einem anderen basierend auf einer angegebenen Befehls-ID.|  
|[CMFCRibbonPanel::SetCenterColumnVert](#setcentercolumnvert)|Ordnet den Bereich Elemente nach Spalte vertikal auszurichten.|  
|[CMFCRibbonPanel::SetData](#setdata)|Ordnet eine benutzerdefinierte Daten mit dem Menübandbereich.|  
|[CMFCRibbonPanel::SetElementMenu](#setelementmenu)|Weist ein Popup-Menü auf das Element mit der angegebenen Befehls-ID.|  
|[CMFCRibbonPanel::SetElementRTC](#setelementrtc)|Fügt ein Menübandelement, das durch die bereitgestellten laufzeitklasseninformationen zum Menübandbereich angegeben.|  
|[CMFCRibbonPanel::SetElementRTCByID](#setelementrtcbyid)|Fügt ein Menübandelement, das durch die bereitgestellten laufzeitklasseninformationen zum Menübandbereich angegeben.|  
|[CMFCRibbonPanel::SetFocused](#setfocused)|Legt den Fokus auf das angegebene Menübandelement.|  
|[CMFCRibbonPanel::SetJustifyColumns](#setjustifycolumns)|Aktiviert oder deaktiviert die Ausrichtung der Spalte.|  
|[CMFCRibbonPanel::SetKeys](#setkeys)|Legt die Tastenkombination, die die Menübandbereich anzeigt.|  
|[CMFCRibbonPanel::ShowPopup](#showpopup)||  
  
## <a name="remarks"></a>Hinweise  
 Menübandbereichen sind logische Gruppierungen von Aufgaben, die Sie im menübandkategorien zu erstellen. Als die Größe des Menübands ändert wird der Bereichslayout automatisch so viele Elemente wie möglich angezeigt.  
  
 Sie erhalten ein Menüband Bereiche, die in einer Menübandkategorie enthalten ist, durch Aufrufen der [CMFCRibbonCategory::GetPanel](../../mfc/reference/cmfcribboncategory-class.md#getpanel) Methode.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Konfigurieren einer `CMFCRibbonPanel` -Objekt mithilfe verschiedener Methoden in der `CMFCRibbonPanel` Klasse. Das Beispiel zeigt, wie legen Sie die Tastenkombination, die die Menübandbereich anzeigt, Elemente in der Systemsteuerung vertikal ausrichten, indem Sie Spalten und Spalte Ausrichtung zu aktivieren. Dieser Codeausschnitt ist Teil der [MS Office 2007 Demobeispiel für](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#10](../../mfc/reference/codesnippet/cpp/cmfcribbonpanel-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxRibbonPanel.h  
  
##  <a name="add"></a>Cmfcribbonpanel:: Add  
 Fügt das angegebene Menübandelement in das Array von Menübandelementen, das in der Menübandbereich enthalten ist.  
  
```  
virtual void Add(CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `pElem`  
 Ein Zeiger auf ein Menübandelement.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="addseparator"></a>CMFCRibbonPanel::AddSeparator  
 Fügt ein Trennzeichen zum Menübandbereich an.  
  
```  
virtual void AddSeparator();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um ein Trennzeichen zum Menübandbereich hinzufügen. Das Trennzeichen wird neben der Menübandelement, das durch den vorhergehenden Aufruf von hinzugefügt wurde hinzugefügt [cmfcribbonpanel:: Add](#add). Rufen Sie zum Einfügen von Trennzeichen an einer bestimmten Position [CMFCRibbonPanel::InsertSeparator](#insertseparator).  
  
##  <a name="addtoolbar"></a>CMFCRibbonPanel::AddToolBar  
 Der Menübandbereich hinzugefügt eine Symbolleiste.  
  
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
 Gibt die Ressourcen-ID der kalten Symbolleistenbilder an.  
  
 [in] `uiHotResID`  
 Gibt die Ressourcen-ID des aktiven Symbolleistenbilder an.  
  
 [in] `uiDisabledResID`  
 Gibt die Ressourcen-ID der deaktivierten Symbolleistenbilder an.  
  
### <a name="return-value"></a>Rückgabewert  
 Rufen Sie diese Methode, um eine Symbolleiste zum Menübandbereich hinzufügen. Die Symbolleiste neben das Menübandelement hinzugefügt, durch den vorhergehenden Aufruf von hinzugefügt [cmfcribbonpanel:: Add](#add).  
  
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
 Der Name der Menübandbereich.  
  
 [in] `hIcon`  
 Handle für das Symbol ", der die Standardschaltfläche für das Menübandbereich.  
  
 [in] `pPaletteButton`  
 Zeiger auf einem Menübandkatalog für die Menübandbereich.  
  
##  <a name="findbydata"></a>CMFCRibbonPanel::FindByData  
 Ruft das Menübandelement, das die angegebenen Daten zugeordnet ist.  
  
```  
CMFCRibbonBaseElement* FindByData(DWORD_PTR dwData) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwData`  
 Die Daten, die ein Menübandelement zugeordnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf ein Menübandelement, wenn die Methode erfolgreich ausgeführt wurde; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="findbyid"></a>CMFCRibbonPanel::FindByID  
 Ruft das Menübandelement, das von der angegebenen Befehls-ID identifiziert wird  
  
```  
CMFCRibbonBaseElement* FindByID(UINT uiCmdID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdID`  
 Die Befehls-ID von einem Menübandelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Menübandelement, das durch die angegebene Befehls-ID gekennzeichnet ist; andernfalls `NULL` Wenn keine Menübandelement mit der angegebenen Befehls-ID identifiziert wird  
  
##  <a name="getcaptionheight"></a>CMFCRibbonPanel::GetCaptionHeight  
 Ruft die Höhe der Beschriftung für den Menübandbereich ab.  
  
```  
int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe in Pixel, der eine Beschriftung für die Menübandbereich.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcount"></a>CMFCRibbonPanel::GetCount  
 Ruft die Anzahl von Menübandelementen, die in der Menübandbereich enthalten sind.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl von Menübandelementen, die in der Menübandbereich enthalten sind.  
  
##  <a name="getdata"></a>CMFCRibbonPanel::GetData  
 Gibt die benutzerdefinierten Daten, die im Bereich zugeordnet.  
  
```  
DWORD_PTR GetData() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die benutzerdefinierten Daten im Bereich zugeordnet.  
  
##  <a name="getdefaultbutton"></a>CMFCRibbonPanel::GetDefaultButton  
 Ruft die Standardschaltfläche für das Menübandbereich ab.  
  
```  
CMFCRibbonButton& GetDefaultButton();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardschaltfläche für das Menübandbereich.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardschaltfläche ist angezeigt, wenn ein Menübandbereich nicht genügend Speicherplatz für die Menübandelemente anzeigen verfügt.  
  
##  <a name="getdroppeddown"></a>CMFCRibbonPanel::GetDroppedDown  
 Ruft einen Zeiger auf ein Menübandelement ab, wenn der Popup-Menü nach unten gelöscht wird.  
  
```  
CMFCRibbonBaseElement* GetDroppedDown() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf das Menübandelement, das seine Popupmenü unten gelöscht wurde; andernfalls `NULL` besitzt keine Menübandelement seine Popupmenü unten gelöscht.  
  
### <a name="remarks"></a>Hinweise  
 Nur Menübandelemente, die in der Menübandbereich enthalten sind, werden getestet.  
  
##  <a name="getelement"></a>CMFCRibbonPanel::GetElement  
 Gibt die Menübandelement am angegebenen Index zurück.  
  
```  
CMFCRibbonBaseElement* GetElement(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Gibt den nullbasierten Index des abzurufenden Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger Zeiger auf der Basis Menübandelement befindet sich an Position `nIndex` in der Menübandbereich oder `NULL` , wenn kein Element am angegebenen Index vorhanden ist.  
  
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
 Fügt Multifunktionsleisten-Elemente, die über die angegebene Befehls-ID in das angegebene Array.  
  
```  
void GetElementsByID(
UINT uiCmdID,  
CArray<CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdID`  
 Befehls-ID für ein Menübandelement.  
  
 [in] `arElements`  
 Ein Array von Menübandelementen.  
  
### <a name="remarks"></a>Hinweise  
 Nur Menübandelemente, die in der Menübandbereich enthalten sind, werden getestet.  
  
##  <a name="gethighlighted"></a>CMFCRibbonPanel::GetHighlighted  
 Ruft das Menübandelement, das im Menübandbereich hervorgehoben ist.  
  
```  
CMFCRibbonBaseElement* GetHighlighted() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Menübandelement, das im Menübandbereich hervorgehoben ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getindex"></a>CMFCRibbonPanel::GetIndex  
 Ruft den nullbasierten Index des angegebenen Menübandelements aus dem Array von Menübandelementen, die in der Menübandbereich enthalten sind.  
  
```  
virtual int GetIndex(CMFCRibbonBaseElement* pElem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pElem`  
 Ein Zeiger auf ein Menübandelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Nullbasierte Index des angegebenen Menübandelement, wenn die Methode erfolgreich ausgeführt wurde. andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getitemidslist"></a>CMFCRibbonPanel::GetItemIDsList  
 Ruft die Befehls-IDs für alle Menübandelemente im Menübandbereich ab.  
  
```  
void GetItemIDsList(CList<UINT, UINT>& lstItems) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `lstItems`  
 Die Liste der Befehls-IDs für Menübandelemente, die in der Menübandbereich enthalten sind.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getname"></a>CMFCRibbonPanel::GetName  
 Ruft den Namen der Menübandbereich ab.  
  
```  
LPCTSTR GetName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name der Menübandbereich.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getparentbutton"></a>CMFCRibbonPanel::GetParentButton  

  
```  
CMFCRibbonBaseElement* GetParentButton() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getparentcategory"></a>CMFCRibbonPanel::GetParentCategory  
 Gibt die übergeordnete Kategorie der Menübandbereich zurück.  
  
```  
CMFCRibbonCategory* GetParentCategory() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Menübandkategorie, die diese Menübandbereich enthält.  
  
##  <a name="getparentmenubar"></a>CMFCRibbonPanel::GetParentMenuBar  

  
```  
CMFCRibbonPanelMenuBar* GetParentMenuBar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getpreferedmenulocation"></a>CMFCRibbonPanel::GetPreferedMenuLocation  
 Ruft den Anzeigestil Rechteck für das Menü das Popupmenü Menübandbereich ab.  
  
```  
virtual BOOL GetPreferedMenuLocation(CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rect`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer `FALSE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt immer `FALSE` zurück. Überschreiben Sie diese Methode, um das bevorzugte Anzeigerechteck für das Menü das Popupmenü Menübandbereich abzurufen.  
  
##  <a name="getpressed"></a>CMFCRibbonPanel::GetPressed  
 Ruft einen Zeiger auf ein Menübandelement im Menübandbereich ab, wenn der Benutzer derzeit drückt.  
  
```  
CMFCRibbonBaseElement* GetPressed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Menübandelement, wenn der Benutzer derzeit drückt; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getrect"></a>CMFCRibbonPanel::GetRect  
 Ruft das Anzeigerechteck für die Menübandbereich ab.  
  
```  
const CRect& GetRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Anzeigerechteck der Menüband-Panels.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="haselement"></a>CMFCRibbonPanel::HasElement  
 Gibt an, ob die Menübandbereich angegebenen Menübandelements enthält.  
  
```  
BOOL HasElement(const CMFCRibbonBaseElement* pElem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pElem`  
 Ein Zeiger auf ein Menübandelement.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Menübandbereich angegebenen Menübandelements enthält. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="highlight"></a>CMFCRibbonPanel::Highlight  
 Legt die Hervorhebungsfarbe für die ausgewählte Menübandbereich und für das Menübandelement vom Punkt angegeben.  
  
```  
virtual void Highlight(
BOOL bHighlight,  
CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bHighlight`  
 `TRUE`auf der Menübandbereich zu markieren. `FALSE` zum Menübandbereich unhighlight.  
  
 [in] `point`  
 Die x- und y-Koordinaten des Zeigers, relativ zu der oberen linken Ecke des Fensters.  
  
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
 Die x- und y-Koordinaten des Zeigers, relativ zu der oberen linken Ecke des Fensters.  
  
 [in] `bCheckPanelCaption`  
 `TRUE`So testen Sie die Beschriftung der Menüband-Bereich; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf ein Menübandelement, wenn der angegebene Punkt darin befindet. andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Nur Menübandelemente, die in der Menübandbereich enthalten sind, werden getestet.  
  
##  <a name="hittestex"></a>CMFCRibbonPanel::HitTestEx  
 Ruft den nullbasierten Index des Menübandelements, die den angegebenen Punkt befindet sich im es hat.  
  
```  
virtual int HitTestEx(CPoint point) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Die x- und y-Koordinaten des Zeigers, relativ zu der oberen linken Ecke des Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des Menübandelements, das den angegebenen Punkt befindet sich im es hat; andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Nur Menübandelemente, die in der Menübandbereich enthalten sind, werden getestet.  
  
##  <a name="insert"></a>CMFCRibbonPanel::Insert  
 Fügt das angegebene Menübandelement an der angegebenen Position im Array von Menübandelementen, die in der Menübandbereich enthalten ist.  
  
```  
virtual BOOL Insert(
CMFCRibbonBaseElement* pElem,  
int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `pElem`  
 Ein Zeiger auf ein Menübandelement.  
  
 [in] `nIndex`  
 Nullbasierter Wert von-1 bis hin zu der Anzahl von Menübandelementen, die im Array enthalten sind.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Menübandelement erfolgreich eingefügt wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Wert der `nIndex` ist-1, oder wenn `nIndex` entspricht der Anzahl von Menübandelementen im Array, das angegebene Menübandelement wird bis zum Ende des Arrays hinzugefügt. Wenn der Wert des `nIndex` ist außerhalb des gültigen Bereichs, der die Methode schlägt fehl.  
  
##  <a name="insertseparator"></a>CMFCRibbonPanel::InsertSeparator  
 Fügt ein Trennzeichen an der angegebenen Position ein.  
  
```  
virtual BOOL InsertSeparator(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Gibt den nullbasierten Index, in dem das Trennzeichen eingefügt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Trennzeichen erfolgreich eingefügt wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um an der Position angegeben, die durch ein Trennzeichen einfügen `nIndex`. Rufen Sie zum Einfügen von Trennzeichen neben das zuletzt hinzugefügte Menübandelement [CMFCRibbonPanel::AddSeparator](#addseparator).  
  
##  <a name="iscentercolumnvert"></a>CMFCRibbonPanel::IsCenterColumnVert  
 Gibt an, ob die vertikale Position von Menübandelementen innerhalb ihrer Anzeigerechteck zentriert werden.  
  
```  
BOOL IsCenterColumnVert() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der vertikal positioniert sind Menübandelemente in ihre Anzeigerechteck zentriert; andernfalls `FALSE`.  
  
##  <a name="iscollapsed"></a>CMFCRibbonPanel::IsCollapsed  
 Gibt an, ob die Anzeigegröße der Menübandbereich in horizontaler Richtung minimiert wird.  
  
```  
BOOL IsCollapsed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Anzeigegröße der Menübandbereich in horizontaler Richtung; minimiert ist andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Menübandbereich reduziert wird, zeigt nur die Standardschaltfläche, den Namen und eine Dropdown-Pfeil.  
  
##  <a name="ishighlighted"></a>CMFCRibbonPanel::IsHighlighted  
 Gibt an, ob die Anzeige der Menübandbereich hervorgehoben ist.  
  
```  
BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Anzeige der Menübandbereich hervorgehoben ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die Anzeige von einem Menübandbereich wird hervorgehoben, wenn der Mauszeiger darüber befindet.  
  
##  <a name="isjustifycolumns"></a>CMFCRibbonPanel::IsJustifyColumns  
 Gibt an, ob der Anzeigegröße Menübandelemente, die in der gleichen Spalte in der Menübandbereich sind auf die gleiche Breite festgelegt werden.  
  
```  
BOOL IsJustifyColumns() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Anzeigegröße Menübandelemente, die in der gleichen Spalte in der Menübandbereich sind auf die gleiche Breite festgelegt werden andernfalls `FALSE`.  
  
##  <a name="ismainpanel"></a>CMFCRibbonPanel::IsMainPanel  
 Gibt an, ob die Menübandbereich der wichtigsten Menübandbereich ist.  
  
```  
virtual BOOL IsMainPanel() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer `FALSE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt immer `FALSE` zurück. Überschreiben Sie diese Methode, um anzugeben, ob die Menübandbereich der wichtigsten Menübandbereich ist.  
  
 Die wichtigsten Menübandbereich wird angezeigt, wenn der Benutzer die Schaltfläche auswählt.  
  
##  <a name="ismenumode"></a>CMFCRibbonPanel::IsMenuMode  

  
```  
BOOL IsMenuMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onkey"></a>CMFCRibbonPanel::OnKey  

  
```  
virtual BOOL OnKey(UINT nChar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nChar`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="recalcwidths"></a>CMFCRibbonPanel::RecalcWidths  
 Berechnet die Breite der Anzeige Layout Konfigurationen für die Menübandbereich neu.  
  
```  
virtual void RecalcWidths(
CDC* pDC,  
int nHeight);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext für das Menübandbereich.  
  
 [in] `nHeight`  
 Die Höhe der Menübandbereich.  
  
### <a name="remarks"></a>Hinweise  
 Einem Menübandbereich ändert seine Layout-Konfiguration, die verfügbare Breite ändert.  
  
##  <a name="remove"></a>CMFCRibbonPanel::Remove  
 Entfernt, und löscht optional ein Element am angegebenen Index.  
  
```  
BOOL Remove(
int nIndex,  
BOOL bDelete = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Gibt den nullbasierten Index des Elements, das aus der Menübandbereich entfernt wird.  
  
 [in] `bDelete`  
 `TRUE`So löschen Sie das Element entfernt wird; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Element entfernt und gelöscht wurde (Wenn `bDelete` ist `TRUE`); `FALSE` , wenn das Element nicht entfernt wurde oder es ist keine Menübandelement controllerarbeitsverzeichnis `nIndex`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um ein Element aus der Menübandbereich zu entfernen.  
  
##  <a name="removeall"></a>CMFCRibbonPanel::RemoveAll  
 Löscht alle Menübandelemente aus dem Menübandbereich an.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Alle Menübandelemente aus dem Menübandbereich gelöscht und zerstört.  
  
##  <a name="replace"></a>CMFCRibbonPanel::Replace  
 Ersetzt ein Element mit einem anderen basierend auf deren Indexwert.  
  
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
 `TRUE`Wenn das ursprüngliche Menübandelement erfolgreich durch das neue Menübandelement ersetzt wurde; `FALSE` Wenn das Menübandelement nicht ersetzt wurde oder kein Element am angegebenen Index vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufen, um ein Menübandelement von Befehls-ID zu ersetzen, [CMFCRibbonPanel::ReplaceByID](#replacebyid).  
  
##  <a name="replacebyid"></a>CMFCRibbonPanel::ReplaceByID  
 Ersetzt ein Element mit einem anderen basierend auf einer angegebenen Befehls-ID.  
  
```  
BOOL ReplaceByID(
UINT uiCmdID,  
CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdID`  
 Gibt die Befehls-ID des Elements ersetzt.  
  
 [in] [out]`pElem`  
 Ein gültiger Zeiger auf das Element, das das ursprüngliche Element ersetzt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das ursprüngliche Menübandelement erfolgreich durch das neue Menübandelement ersetzt wurde; `FALSE` Wenn das Menübandelement nicht ersetzt wurde oder kein Element mit der angegebenen Befehls-ID tatsächlich vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufen, um ein Menübandelement auf Grundlage der Position zu ersetzen, [CMFCRibbonPanel::Replace](#replace).  
  
##  <a name="setcentercolumnvert"></a>CMFCRibbonPanel::SetCenterColumnVert  
 Aktiviert oder deaktiviert die Zentrieren der vertikalen Positionen von Menübandelementen innerhalb ihrer Anzeigerechteck.  
  
```  
void SetCenterColumnVert(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bSet`  
 `TRUE`um die vertikale Position von Menübandelemente innerhalb ihrer Anzeigerechteck zentrieren; `FALSE` wird diese Funktion deaktiviert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setdata"></a>CMFCRibbonPanel::SetData  
 Ordnet eine benutzerdefinierte Daten mit dem Menübandbereich.  
  
```  
void SetData(DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwData`  
 Gibt die benutzerdefinierten Daten festlegen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um benutzerdefinierte Daten im Menübandbereich zuordnen.  
  
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
 Gibt die Befehls-ID des Menübandelements, wo Sie im Menü hinzugefügt wird.  
  
 [in] `hMenu`  
 Gibt das Handle für das Windows-Menü zum Menübandbereich hinzufügen.  
  
 [in] `bIsDefautCommand`  
 `TRUE`um anzugeben, dass das Menübandelement zugeordnete Befehl ausgeführt werden soll, wenn das Menübandelement geklickt wird. In diesem Fall wird das Menü nur geöffnet, klickt der Benutzer auf den Pfeil neben das Menübandelement. `FALSE`um anzugeben, dass das Menübandelement zugeordnete Befehl nicht ausgeführt werden soll, wenn das Menübandelement geklickt wird. In diesem Fall wird das Popupmenü angezeigt, unabhängig davon, wo der Benutzer auf das Element klickt.  
  
 [in] `bRightAlign`  
 `TRUE`um anzugeben, dass das Popupmenü rechts ausgerichtet wird; andernfalls `FALSE`.  
  
 [in] `uiMenuResID`  
 Gibt die Ressourcen-ID des Menüs zum Menübandbereich hinzufügen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Sie im Menü auf das Menübandelement zugewiesen wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um das Menübandelement ein Popupmenü zuweisen, die die angegebenen Befehls-ID.  
  
##  <a name="setelementrtc"></a>CMFCRibbonPanel::SetElementRTC  
 Fügt das Menübandelement, das durch die bereitgestellten laufzeitklasseninformationen zum Menübandbereich angegeben wird.  
  
```  
CMFCRibbonBaseElement* SetElementRTC(
int nIndex,  
CRuntimeClass* pRTC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Gibt den nullbasierten Index des hinzuzufügenden Menübandelements an.  
  
 [in] [out]`pRTC`  
 Ein Zeiger auf die laufzeitklasseninformationen für das Menübandelement, das zum Menübandbereich hinzugefügt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Menübandelement, das mit dem angegebenen Common Language Runtime-Klasseninformationen erstellt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein benutzerdefiniertes Element (z. B. eine farbenschaltfläche ") zum Menübandbereich hinzufügen möchten, müssen Sie das benutzerdefinierte Element Laufzeit-Klasseninformationen angeben. Das Menüband speichert diese Informationen, erstellt das benutzerdefinierte Element und ersetzt ein vorhandene Element, das sich befindet (identifiziert durch) die angegebenen Befehls-ID. Das Menüband gibt einen Zeiger auf das neu erstellte Element zurück.  
  
##  <a name="setelementrtcbyid"></a>CMFCRibbonPanel::SetElementRTCByID  
 Fügt ein Menübandelement, das durch die bereitgestellten laufzeitklasseninformationen zum Menübandbereich angegeben wird.  
  
```  
CMFCRibbonBaseElement* SetElementRTCByID(
UINT uiCmdID,  
CRuntimeClass* pRTC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdID`  
 Gibt die Befehls-ID des Menübandelements hinzufügen.  
  
 [in] [out]`pRTC`  
 Ein Zeiger auf die laufzeitklasseninformationen zugeordneten das Menübandelement, das zum Menübandbereich hinzugefügt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Menübandelement, das mit dem angegebenen Common Language Runtime-Klasseninformationen erstellt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein benutzerdefiniertes Element (z. B. eine farbenschaltfläche ") zum Menübandbereich hinzufügen möchten, müssen Sie das benutzerdefinierte Element Laufzeit-Klasseninformationen angeben. Das Menüband speichert diese Informationen, erstellt das benutzerdefinierte Element und ersetzt ein vorhandenes Element der angegebenen Befehls-ID nicht gefunden Anschließend wird einen Zeiger auf das neu erstellte Element zurückgegeben.  
  
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
 `TRUE`die Breite des Menübandelemente in der gleichen Spalte auf die Breite des größten Menübandelements in der Spalte anpassen; `FALSE` diese Anpassung Breite zu deaktivieren.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Funktion in einem Menübandbereich aktiviert ist, werden die Breiten der Menübandelemente in der gleichen Spalte, die Breite des größten Menübandelements in der gleichen Spalte angepasst.  
  
##  <a name="setkeys"></a>CMFCRibbonPanel::SetKeys  
 Legt die ZugriffstastenInfo für die Standardschaltfläche im Menüband-Bereich.  
  
```  
void SetKeys(LPCTSTR lpszKeys);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszKeys`  
 Der ZugriffstastenInfo für die Standardschaltfläche im Menüband-Bereich.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardschaltfläche ist angezeigt, wenn ein Menübandbereich nicht genügend Speicherplatz für die Menübandelemente anzeigen verfügt.  
  
##  <a name="showpopup"></a>CMFCRibbonPanel::ShowPopup  
 Erstellt und für die Menübandbereich ein Popupmenü anzeigt.  
  
```  
CMFCRibbonPanelMenu* ShowPopup(CMFCRibbonDefaultPanelButton* pButton = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pButton`  
 Ein Zeiger auf die Standardschaltfläche für das Menübandbereich.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf das Menü das Popupmenü für Menübandbereich, wenn die Methode erfolgreich ausgeführt wurde; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Im Popupmenü des Menüband-Panels ist nur verfügbar, wenn die Anzeige der Menübandbereich reduziert wird.  
  
##  <a name="setfocused"></a>CMFCRibbonPanel::SetFocused  
 Legt den Fokus auf das angegebene Menübandelement.  
  
```  
void SetFocused(CMFCRibbonBaseElement* pNewFocus);
```  
  
### <a name="parameters"></a>Parameter  
 `pNewFocus`  
 Ein Zeiger auf ein Menübandelement, das Fokus erhält.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="makegalleryitemvisible"></a>CMFCRibbonPanel::MakeGalleryItemVisible  
 Scrollt den Katalog für den angegebenen Menübandelement sichtbar zu machen.  
  
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
 `TRUE`Wenn das Menüband übergeordneten Windows 7, suchen Sie enthält. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getvisibleelements"></a>CMFCRibbonPanel::GetVisibleElements  
 Ruft ein Array von sichtbaren Elemente ab.  
  
```  
void GetVisibleElements(
CArray<CMFCRibbonBaseElement*,  
CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Parameter  
 `arElements`  
 Wenn die Funktion zurückgibt, enthält dieser Parameter ein Array von sichtbaren Elemente.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getgalleryrect"></a>CMFCRibbonPanel::GetGalleryRect  
 Gibt ein umschließendes Rechteck für ein Katalogelement zurück.  
  
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
