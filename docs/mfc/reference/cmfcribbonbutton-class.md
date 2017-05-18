---
title: Klasse CMFCRibbonButton | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonButton
- AFXRIBBONBUTTON/CMFCRibbonButton
- AFXRIBBONBUTTON/CMFCRibbonButton::CMFCRibbonButton
- AFXRIBBONBUTTON/CMFCRibbonButton::AddSubItem
- AFXRIBBONBUTTON/CMFCRibbonButton::CanBeStretched
- AFXRIBBONBUTTON/CMFCRibbonButton::CleanUpSizes
- AFXRIBBONBUTTON/CMFCRibbonButton::ClosePopupMenu
- AFXRIBBONBUTTON/CMFCRibbonButton::DrawBottomText
- AFXRIBBONBUTTON/CMFCRibbonButton::DrawImage
- AFXRIBBONBUTTON/CMFCRibbonButton::DrawRibbonText
- AFXRIBBONBUTTON/CMFCRibbonButton::FindSubItemIndexByID
- AFXRIBBONBUTTON/CMFCRibbonButton::GetCommandRect
- AFXRIBBONBUTTON/CMFCRibbonButton::GetCompactSize
- AFXRIBBONBUTTON/CMFCRibbonButton::GetIcon
- AFXRIBBONBUTTON/CMFCRibbonButton::GetImageIndex
- AFXRIBBONBUTTON/CMFCRibbonButton::GetImageSize
- AFXRIBBONBUTTON/CMFCRibbonButton::GetIntermediateSize
- AFXRIBBONBUTTON/CMFCRibbonButton::GetMenu
- AFXRIBBONBUTTON/CMFCRibbonButton::GetMenuRect
- AFXRIBBONBUTTON/CMFCRibbonButton::GetRegularSize
- AFXRIBBONBUTTON/CMFCRibbonButton::GetSubItems
- AFXRIBBONBUTTON/CMFCRibbonButton::GetTextRowHeight
- AFXRIBBONBUTTON/CMFCRibbonButton::GetToolTipText
- AFXRIBBONBUTTON/CMFCRibbonButton::HasCompactMode
- AFXRIBBONBUTTON/CMFCRibbonButton::HasIntermediateMode
- AFXRIBBONBUTTON/CMFCRibbonButton::HasLargeMode
- AFXRIBBONBUTTON/CMFCRibbonButton::HasMenu
- AFXRIBBONBUTTON/CMFCRibbonButton::IsAlwaysDrawBorder
- AFXRIBBONBUTTON/CMFCRibbonButton::IsAlwaysLargeImage
- AFXRIBBONBUTTON/CMFCRibbonButton::IsApplicationButton
- AFXRIBBONBUTTON/CMFCRibbonButton::IsCommandAreaHighlighted
- AFXRIBBONBUTTON/CMFCRibbonButton::IsDefaultCommand
- AFXRIBBONBUTTON/CMFCRibbonButton::IsDefaultPanelButton
- AFXRIBBONBUTTON/CMFCRibbonButton::IsDrawTooltipImage
- AFXRIBBONBUTTON/CMFCRibbonButton::IsLargeImage
- AFXRIBBONBUTTON/CMFCRibbonButton::IsMenuAreaHighlighted
- AFXRIBBONBUTTON/CMFCRibbonButton::IsMenuOnBottom
- AFXRIBBONBUTTON/CMFCRibbonButton::IsPopupDefaultMenuLook
- AFXRIBBONBUTTON/CMFCRibbonButton::IsRightAlignMenu
- AFXRIBBONBUTTON/CMFCRibbonButton::IsSingleLineText
- AFXRIBBONBUTTON/CMFCRibbonButton::OnCalcTextSize
- AFXRIBBONBUTTON/CMFCRibbonButton::OnDrawBorder
- AFXRIBBONBUTTON/CMFCRibbonButton::OnDraw
- AFXRIBBONBUTTON/CMFCRibbonButton::OnFillBackground
- AFXRIBBONBUTTON/CMFCRibbonButton::RemoveAllSubItems
- AFXRIBBONBUTTON/CMFCRibbonButton::RemoveSubItem
- AFXRIBBONBUTTON/CMFCRibbonButton::SetACCData
- AFXRIBBONBUTTON/CMFCRibbonButton::SetAlwaysLargeImage
- AFXRIBBONBUTTON/CMFCRibbonButton::SetDefaultCommand
- AFXRIBBONBUTTON/CMFCRibbonButton::SetDescription
- AFXRIBBONBUTTON/CMFCRibbonButton::SetImageIndex
- AFXRIBBONBUTTON/CMFCRibbonButton::SetMenu
- AFXRIBBONBUTTON/CMFCRibbonButton::SetParentCategory
- AFXRIBBONBUTTON/CMFCRibbonButton::SetRightAlignMenu
- AFXRIBBONBUTTON/CMFCRibbonButton::SetText
- AFXRIBBONBUTTON/CMFCRibbonButton::OnClick
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonButton class
ms.assetid: 732e941c-9504-4b83-a691-d18075965d53
caps.latest.revision: 42
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
ms.openlocfilehash: 08672f10cf67a773f2af8d12130c4e3f5b497e11
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonbutton-class"></a>CMFCRibbonButton-Klasse
Die `CMFCRibbonButton`-Klasse implementiert Schaltflächen, die auf Menübandleisten-Elementen wie Bereichen, Symbolleisten für den Schnellzugriff und Popupmenüs positioniert werde können.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonButton : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonButton::CMFCRibbonButton](#cmfcribbonbutton)|Erstellt ein Menüband-Schaltflächenobjekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonButton::AddSubItem](#addsubitem)|Fügt ein Menüelement zu dem Popup-Menü hinzu, dem die Schaltfläche zugeordnet ist.|  
|[CMFCRibbonButton::CanBeStretched](#canbestretched)|(Überschreibt [cmfcribbonbaseelement:: Canbestretched](../../mfc/reference/cmfcribbonbaseelement-class.md#canbestretched).)|  
|[CMFCRibbonButton::CleanUpSizes](#cleanupsizes)|(Überschreibt [cmfcribbonbaseelement:: Cleanupsizes](../../mfc/reference/cmfcribbonbaseelement-class.md#cleanupsizes).)|  
|[CMFCRibbonButton::ClosePopupMenu](#closepopupmenu)|(Überschreibt [cmfcribbonbaseelement:: Closepopupmenu](../../mfc/reference/cmfcribbonbaseelement-class.md#closepopupmenu).)|  
|[CMFCRibbonButton::DrawBottomText](#drawbottomtext)||  
|[CMFCRibbonButton::DrawImage](#drawimage)|(Überschreibt [cmfcribbonbaseelement:: DrawImage](../../mfc/reference/cmfcribbonbaseelement-class.md#drawimage).)|  
|[CMFCRibbonButton::DrawRibbonText](#drawribbontext)||  
|[CMFCRibbonButton::FindSubItemIndexByID](#findsubitemindexbyid)|Gibt den Index eines Popupmenü-Elements zurück, das der angegebenen Befehls-ID zugeordnet ist.|  
|[CMFCRibbonButton::GetCommandRect](#getcommandrect)||  
|[CMFCRibbonButton::GetCompactSize](#getcompactsize)|Gibt die komprimierte Größe des Menübandelements zurück. (Überschreibt [cmfcribbonbaseelement:: Getcompactsize](../../mfc/reference/cmfcribbonbaseelement-class.md#getcompactsize).)|  
|[CMFCRibbonButton::GetIcon](#geticon)||  
|[CMFCRibbonButton::GetImageIndex](#getimageindex)|Gibt den Index des Bilds zurück, das der Schaltfläche zugeordnet ist.|  
|[CMFCRibbonButton::GetImageSize](#getimagesize)|Gibt die Bildgröße des Menübandelements zurück. (Überschreibt [cmfcribbonbaseelement:: Getimagesize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize).)|  
|[CMFCRibbonButton::GetIntermediateSize](#getintermediatesize)|Gibt die Größe des Menübandelements im Zwischenstatus zurück. (Überschreibt [cmfcribbonbaseelement:: Getintermediatesize](../../mfc/reference/cmfcribbonbaseelement-class.md#getintermediatesize).)|  
|[CMFCRibbonButton::GetMenu](#getmenu)|Gibt ein Handle für ein Windows-Menü zurück, das der Menüband-Schaltfläche zugewiesen ist.|  
|[CMFCRibbonButton::GetMenuRect](#getmenurect)||  
|[CMFCRibbonButton::GetRegularSize](#getregularsize)|Gibt die reguläre Größe des Menübandelements zurück. (Überschreibt [cmfcribbonbaseelement:: Getregularsize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonButton::GetSubItems](#getsubitems)||  
|[CMFCRibbonButton::GetTextRowHeight](#gettextrowheight)||  
|[CMFCRibbonButton::GetToolTipText](#gettooltiptext)|Gibt den QuickInfo-Text des Menübandelements zurück. (Überschreibt [cmfcribbonbaseelement:: GetToolTipText](../../mfc/reference/cmfcribbonbaseelement-class.md#gettooltiptext).)|  
|[CMFCRibbonButton::HasCompactMode](#hascompactmode)|Gibt an, ob das Menübandelement über einen Komprimierungsmodus verfügt. (Überschreibt [cmfcribbonbaseelement:: Hascompactmode](../../mfc/reference/cmfcribbonbaseelement-class.md#hascompactmode).)|  
|[CMFCRibbonButton::HasIntermediateMode](#hasintermediatemode)|Gibt an, ob das Menübandelement über einen Zwischenstatus verfügt (Überschreibt [cmfcribbonbaseelement:: Hasintermediatemode](../../mfc/reference/cmfcribbonbaseelement-class.md#hasintermediatemode).)|  
|[CMFCRibbonButton::HasLargeMode](#haslargemode)|Legt fest, ob das Menübandelement über einen Großbildmodus verfügt. (Überschreibt [cmfcribbonbaseelement:: Haslargemode](../../mfc/reference/cmfcribbonbaseelement-class.md#haslargemode).)|  
|[CMFCRibbonButton::HasMenu](#hasmenu)|(Überschreibt [cmfcribbonbaseelement:: HasMenu](../../mfc/reference/cmfcribbonbaseelement-class.md#hasmenu).)|  
|[CMFCRibbonButton::IsAlwaysDrawBorder](#isalwaysdrawborder)||  
|[CMFCRibbonButton::IsAlwaysLargeImage](#isalwayslargeimage)|(Überschreibt [cmfcribbonbaseelement:: Isalwayslargeimage](../../mfc/reference/cmfcribbonbaseelement-class.md#isalwayslargeimage).)|  
|[CMFCRibbonButton::IsApplicationButton](#isapplicationbutton)||  
|[CMFCRibbonButton::IsCommandAreaHighlighted](#iscommandareahighlighted)||  
|[CMFCRibbonButton::IsDefaultCommand](#isdefaultcommand)|Legt fest, ob Sie den Standardbefehl für eine Menüband-Schaltfläche aktiviert haben.|  
|[CMFCRibbonButton::IsDefaultPanelButton](#isdefaultpanelbutton)||  
|[CMFCRibbonButton::IsDrawTooltipImage](#isdrawtooltipimage)||  
|[CMFCRibbonButton::IsLargeImage](#islargeimage)||  
|[CMFCRibbonButton::IsMenuAreaHighlighted](#ismenuareahighlighted)||  
|[CMFCRibbonButton::IsMenuOnBottom](#ismenuonbottom)||  
|[CMFCRibbonButton::IsPopupDefaultMenuLook](#ispopupdefaultmenulook)||  
|[CMFCRibbonButton::IsRightAlignMenu](#isrightalignmenu)|Legt fest, ob das Menü rechts ausgerichtet ist.|  
|[CMFCRibbonButton::IsSingleLineText](#issinglelinetext)||  
|[CMFCRibbonButton::OnCalcTextSize](#oncalctextsize)|(Überschreibt [cmfcribbonbaseelement:: Oncalctextsize](../../mfc/reference/cmfcribbonbaseelement-class.md#oncalctextsize).)|  
|[CMFCRibbonButton::OnDrawBorder](#ondrawborder)||  
|[CMFCRibbonButton::OnDraw](#ondraw)|Wird vom Framework aufgerufen, um das Menübandelement zu zeichnen. (Überschreibt [cmfcribbonbaseelement:: OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|  
|[CMFCRibbonButton::OnFillBackground](#onfillbackground)||  
|[CMFCRibbonButton::RemoveAllSubItems](#removeallsubitems)|Entfernt alle Menüelemente aus dem Popupmenü.|  
|[CMFCRibbonButton::RemoveSubItem](#removesubitem)|Entfernt ein Menüelement aus dem Popupmenü.|  
|[CMFCRibbonButton::SetACCData](#setaccdata)|(Überschreibt [cmfcribbonbaseelement:: Setaccdata](../../mfc/reference/cmfcribbonbaseelement-class.md#setaccdata).)|  
|[CMFCRibbonButton::SetAlwaysLargeImage](#setalwayslargeimage)|Gibt an, ob für die Schaltfläche ein großes oder ein kleines Bild angezeigt wird, wenn die Schaltfläche vom Benutzer reduziert wird.|  
|[CMFCRibbonButton::SetDefaultCommand](#setdefaultcommand)|Aktiviert den Standardbefehl für die Menübandschaltfläche.|  
|[CMFCRibbonButton::SetDescription](#setdescription)|Legt die Beschreibung für das Menübandelement fest. (Überschreibt [cmfcribbonbaseelement:: setDescription](../../mfc/reference/cmfcribbonbaseelement-class.md#setdescription).)|  
|[CMFCRibbonButton::SetImageIndex](#setimageindex)|Weist dem Schaltflächenbild einen Index zu.|  
|[CMFCRibbonButton::SetMenu](#setmenu)|Weist der Menüband-Schaltfläche ein Popupmenü zu.|  
|[CMFCRibbonButton::SetParentCategory](#setparentcategory)|(Überschreibt [cmfcribbonbaseelement:: Setparentcategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory).)|  
|[CMFCRibbonButton::SetRightAlignMenu](#setrightalignmenu)|Richtet das Popupmenü rechts neben der Schaltfläche aus.|  
|[CMFCRibbonButton::SetText](#settext)|Legt den Text für das Menübandelement fest. (Überschreibt [cmfcribbonbaseelement:: SetText](../../mfc/reference/cmfcribbonbaseelement-class.md#settext).)|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonButton::OnClick](#onclick)|Wird vom Framework aufgerufen, wenn der Benutzer auf die Schaltfläche klickt.|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Verwendung der unterschiedlichen Methoden in der `CMFCRibbonButton`-Klasse veranschaulicht. In dem Beispiel wird veranschaulicht, wie Sie ein Objekt der `CMFCRibbonButton`-Klasse erstellen, der Menüband-Schaltfläche ein Popupmenü zuweisen, die Beschreibung der Schaltfläche festlegen, ein Menüelement aus dem Popupmenü entfernen und das Popupmenü rechts an den Rand der Schaltfläche ausrichten können.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#7;](../../mfc/reference/codesnippet/cpp/cmfcribbonbutton-class_1.cpp)]  
  
## <a name="remarks"></a>Hinweise  
 Um eine Schaltfläche der Multifunktionsleiste in einer Anwendung zu verwenden, erstellen Sie das Button-Objekt und das entsprechende Menüband hinzufügen [Bereich](../../mfc/reference/cmfcribbonpanel-class.md).  
  
```  
CMFCRibbonPanel* pPanel = pCategory->AddPanel (
    _T("Clipboard"), // Panel name  
    m_PanelIcons.ExtractIcon (0)); // Panel icon  

// Create the first button ("Paste"):  
CMFCRibbonButton* pPasteButton = 
    new CMFCRibbonButton (ID_EDIT_PASTE, _T("Paste"), -1, 0);

// The third parameter (-1) disables small images for button.  
// This button is always displayed with a large image  
// Associate a pop-up menu with the "Paste" button:  
pPasteButton->SetMenu (IDR_CONTEXT_MENU);

// Add buttons to the panel. These buttons have only small images.  
pPanel->Add (new CMFCRibbonButton (ID_EDIT_CUT, _T("Cut"), 1));
pPanel->Add (new CMFCRibbonButton (ID_EDIT_COPY, _T("Copy"), 2));
pPanel->Add (new CMFCRibbonButton (ID_EDIT_PAINT, _T("Paint"), 9));
```  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxribbonbutton.h  
  
##  <a name="addsubitem"></a>CMFCRibbonButton::AddSubItem  
 Fügt ein Menüelement zu dem Popup-Menü hinzu, dem die Schaltfläche zugeordnet ist.  
  
```  
void AddSubItem(
    CMFCRibbonBaseElement* pSubItem,  
    int nIndex=-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pSubItem`  
 Gibt einen Zeiger auf das neue Element hinzufügen.  
  
 [in] `nIndex`  
 Gibt den Index, an dem das Element in das Array von Menüelementen der Schaltfläche hinzugefügt.&1;, um das Element am Ende des Arrays der Menüelemente hinzufügen.  
  
##  <a name="canbestretched"></a>CMFCRibbonButton::CanBeStretched  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CanBeStretched();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="cleanupsizes"></a>CMFCRibbonButton::CleanUpSizes  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void CleanUpSizes();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="closepopupmenu"></a>CMFCRibbonButton::ClosePopupMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void ClosePopupMenu();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="cmfcribbonbutton"></a>CMFCRibbonButton::CMFCRibbonButton  
 Erstellt ein Menüband-Schaltflächenobjekt.  
  
```  
CMFCRibbonButton(
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex=-1,  
    int nLargeImageIndex=-1,  
    BOOL bAlwaysShowDescription=FALSE);

CMFCRibbonButton(
    UINT nID,  
    LPCTSTR lpszText,  
    HICON hIcon,  
    BOOL bAlwaysShowDescription=FALSE,  
    HICON hIconSmall=NULL,  
    BOOL bAutoDestroyIcon=FALSE,  
    BOOL bAlphaBlendIcon=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 Gibt die Befehls-ID der Schaltfläche.  
  
 [in] `lpszText`  
 Gibt die Beschriftung der Schaltfläche.  
  
 [in] `nSmallImageIndex`  
 Gibt einen nullbasierten Index des kleines Bild der Schaltfläche in der Bildliste der übergeordneten Kategorie an.  
  
 [in] `nLargeImageIndex`  
 Gibt einen nullbasierten Index des großes Bild der Schaltfläche in der Bildliste der übergeordneten Kategorie an.  
  
 [in] `hIcon`  
 Gibt ein Handle für das Symbol, das die Anwendung als Bild der Schaltfläche verwendet.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCRibbonButton` Objekt.  
  
 [!code-cpp[NVC_MFC_RibbonApp&6;](../../mfc/reference/codesnippet/cpp/cmfcribbonbutton-class_2.cpp)]  
  
##  <a name="drawbottomtext"></a>CMFCRibbonButton::DrawBottomText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CSize DrawBottomText(
    CDC* pDC,  
    BOOL bCalcOnly);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 [in] `bCalcOnly`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="drawimage"></a>CMFCRibbonButton::DrawImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void DrawImage(
    CDC* pDC,  
    RibbonImageType type,  
    CRect rectImage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 [in] `type`  
 [in] `rectImage`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="drawribbontext"></a>CMFCRibbonButton::DrawRibbonText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int DrawRibbonText(
    CDC* pDC,  
    const CString& strText,  
    CRect rectText,  
    UINT uiDTFlags,  
    COLORREF clrText = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 [in] `strText`  
 [in] `rectText`  
 [in] `uiDTFlags`  
 [in] `clrText`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="findsubitemindexbyid"></a>CMFCRibbonButton::FindSubItemIndexByID  
 Gibt den Index eines Popupmenü-Elements zurück, das der angegebenen Befehls-ID zugeordnet ist.  
  
```  
int FindSubItemIndexByID(UINT uiID) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiID`  
 Gibt die Befehls-ID des Elements im Popupmenü.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des untergeordneten Elements, das zugeordnet ist die `uiID`. 1, wenn kein solcher untergeordnete Element vorhanden ist.  
  
##  <a name="getcommandrect"></a>CMFCRibbonButton::GetCommandRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CRect GetCommandRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcompactsize"></a>CMFCRibbonButton::GetCompactSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="geticon"></a>CMFCRibbonButton::GetIcon  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
HICON GetIcon(BOOL bLargeIcon = TRUE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bLargeIcon`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getimageindex"></a>CMFCRibbonButton::GetImageIndex  
 Gibt den Index des Bilds zurück, das der Schaltfläche zugeordnet ist.  
  
```  
int GetImageIndex(BOOL bLargeImage) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bLargeImage`  
 Wenn `TRUE`, gibt den Index des Bildes in der Bildliste, die große Bilder enthält, andernfalls gibt den Index des Bildes in der Bildliste, das der kleine Bilder enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index, der das Bild der Schaltfläche in der Liste zugeordnete Bild.  
  
##  <a name="getimagesize"></a>CMFCRibbonButton::GetImageSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetImageSize(RibbonImageType type) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `type`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getintermediatesize"></a>CMFCRibbonButton::GetIntermediateSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getmenu"></a>CMFCRibbonButton::GetMenu  
 Gibt ein Handle für ein Windows-Menü zurück, das der Menüband-Schaltfläche zugewiesen ist.  
  
```  
HMENU GetMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für ein Windows-Menü auf die Schaltfläche zugewiesen werden soll; `NULL` befindet sich kein Menü zugewiesen.  
  
##  <a name="getmenurect"></a>CMFCRibbonButton::GetMenuRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CRect GetMenuRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getregularsize"></a>CMFCRibbonButton::GetRegularSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getsubitems"></a>CMFCRibbonButton::GetSubItems  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
const CArray<CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& GetSubItems() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gettextrowheight"></a>CMFCRibbonButton::GetTextRowHeight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetTextRowHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gettooltiptext"></a>CMFCRibbonButton::GetToolTipText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CString GetToolTipText() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hascompactmode"></a>CMFCRibbonButton::HasCompactMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasCompactMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hasintermediatemode"></a>CMFCRibbonButton::HasIntermediateMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasIntermediateMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="haslargemode"></a>CMFCRibbonButton::HasLargeMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasLargeMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hasmenu"></a>CMFCRibbonButton::HasMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isalwaysdrawborder"></a>CMFCRibbonButton::IsAlwaysDrawBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsAlwaysDrawBorder() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isalwayslargeimage"></a>CMFCRibbonButton::IsAlwaysLargeImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsAlwaysLargeImage() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isapplicationbutton"></a>CMFCRibbonButton::IsApplicationButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsApplicationButton() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="iscommandareahighlighted"></a>CMFCRibbonButton::IsCommandAreaHighlighted  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsCommandAreaHighlighted() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isdefaultcommand"></a>CMFCRibbonButton::IsDefaultCommand  
 Gibt an, ob es sich bei der Standardbefehl für eine Schaltfläche der Multifunktionsleiste aktiviert ist.  
  
```  
BOOL IsDefaultCommand() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Sie den Standardbefehl für eine Schaltfläche der Multifunktionsleiste aktiviert haben. `FALSE` andernfalls.  
  
##  <a name="isdefaultpanelbutton"></a>CMFCRibbonButton::IsDefaultPanelButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsDefaultPanelButton() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isdrawtooltipimage"></a>CMFCRibbonButton::IsDrawTooltipImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsDrawTooltipImage() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="islargeimage"></a>CMFCRibbonButton::IsLargeImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsLargeImage() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ismenuareahighlighted"></a>CMFCRibbonButton::IsMenuAreaHighlighted  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsMenuAreaHighlighted() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ismenuonbottom"></a>CMFCRibbonButton::IsMenuOnBottom  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsMenuOnBottom() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ispopupdefaultmenulook"></a>CMFCRibbonButton::IsPopupDefaultMenuLook  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsPopupDefaultMenuLook() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isrightalignmenu"></a>CMFCRibbonButton::IsRightAlignMenu  
 Gibt an, ob das Menü rechts ausgerichtet ist.  
  
```  
BOOL IsRightAlignMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Sie im Menü rechts ausgerichtet ist. andernfalls `FALSE`.  
  
##  <a name="issinglelinetext"></a>CMFCRibbonButton::IsSingleLineText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsSingleLineText() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="oncalctextsize"></a>CMFCRibbonButton::OnCalcTextSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnCalcTextSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onclick"></a>CMFCRibbonButton::OnClick  
 Wird vom Framework aufgerufen, wenn der Benutzer auf die Schaltfläche klickt.  
  
```  
virtual void OnClick(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Gibt die Position des Mausklicks.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, wenn Sie dieses Ereignis behandeln möchten.  
  
##  <a name="ondraw"></a>CMFCRibbonButton::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondrawborder"></a>CMFCRibbonButton::OnDrawBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawBorder(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onfillbackground"></a>CMFCRibbonButton::OnFillBackground  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF OnFillBackground(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="removeallsubitems"></a>CMFCRibbonButton::RemoveAllSubItems  
 Entfernt alle Menüelemente aus dem Popupmenü.  
  
```  
void RemoveAllSubItems();
```  
  
##  <a name="removesubitem"></a>CMFCRibbonButton::RemoveSubItem  
 Entfernt ein Menüelement aus dem Popupmenü.  
  
```  
BOOL RemoveSubItem(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Gibt den nullbasierten Index des Menüelements, das Sie entfernen möchten.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das angegebene Element erfolgreich entfernt wurde; andernfalls `FALSE` Wenn `nIndex` ist negativ oder größer als die Anzahl der Menüelemente im Popup-Menü.  
  
##  <a name="setaccdata"></a>CMFCRibbonButton::SetACCData  
 Legt die Barrierefreiheitsdaten für die Menübandschaltfläche fest.  
  
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
 Gibt `TRUE` zurück, wenn erfolgreich; andernfalls FALSE.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setalwayslargeimage"></a>CMFCRibbonButton::SetAlwaysLargeImage  
 Gibt an, ob für die Schaltfläche ein großes oder ein kleines Bild angezeigt wird, wenn die Schaltfläche vom Benutzer reduziert wird.  
  
```  
void SetAlwaysLargeImage(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bSet`  
 Wenn `TRUE`, die Schaltfläche ein großes Bild anzeigt. Andernfalls wird die Schaltfläche ein kleines Bild angezeigt.  
  
##  <a name="setdefaultcommand"></a>CMFCRibbonButton::SetDefaultCommand  
 Aktiviert den Standardbefehl für die Menübandschaltfläche.  
  
```  
void SetDefaultCommand(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bSet`  
 Wenn `TRUE`, die Schaltfläche kann den Standardbefehl ausführen. Wenn `FALSE`, die Schaltfläche den Standardbefehl kann nicht ausgeführt werden.  
  
### <a name="remarks"></a>Hinweise  
 `bSet`trifft nur, wenn die Schaltfläche ein Menü aufweist. Wenn `bSet` ist `TRUE`, die Schaltfläche kann den Standardbefehl ausführen und im Popupmenü zugewiesenen erscheint nur, wenn ein Benutzer den Pfeil am rechten Rand der Schaltfläche klickt. Andernfalls die Schaltfläche den Standardbefehl kann nicht ausgeführt werden, und im Popupmenü angezeigt wird, unabhängig davon, welcher Bereich der Schaltfläche der Benutzer klickt.  
  
##  <a name="setdescription"></a>CMFCRibbonButton::SetDescription  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void SetDescription(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszText`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setimageindex"></a>CMFCRibbonButton::SetImageIndex  
 Weist dem Schaltflächenbild einen Index zu.  
  
```  
void SetImageIndex(
    int nIndex,  
    BOOL bLargeImage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Gibt den Index des Bildes an.  
  
 [in] `bLargeImage`  
 Wenn `TRUE`, der angegebene Index bezieht sich auf die Liste von Bildern. Andernfalls verweist der Index der Liste der kleine Bilder.  
  
##  <a name="setmenu"></a>CMFCRibbonButton::SetMenu  
 Weist der Menüband-Schaltfläche ein Popupmenü zu.  
  
```  
void SetMenu(
    HMENU hMenu,  
    BOOL bIsDefaultCommand=FALSE,  
    BOOL bRightAlign=FALSE);

void SetMenu(
    UINT uiMenuResID,  
    BOOL bIsDefaultCommand=FALSE,  
    BOOL bRightAlign=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `hMenu`  
 Ein Handle für ein Windows-Menü.  
  
 `bIsDefaultCommand`  
 Wenn `TRUE`, die Schaltfläche kann den Standardbefehl ausführen; andernfalls wird die Schaltfläche ein Popupmenü angezeigt.  
  
 `bRightAlign`  
 Wenn `TRUE`, klicken Sie im Menü wird rechts ausgerichtet. Andernfalls ist das Menü linksbündig ausgerichtet.  
  
 `uiMenuResID`  
 Ein Menü-Ressourcen-ID.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Anwendung im Menü die Schaltfläche zugewiesen wurde, zeigt die Schaltfläche einen Pfeil nach rechts. Wenn `bIsDefaultCommand` ist `TRUE`, klicken Sie im Menü erscheint nur, wenn der Benutzer die Taste klickt. Wenn der Benutzer auf die Schaltfläche klickt, wird der standardmäßige Befehl ausgeführt. Wenn `bIsDefaultCommand` ist `FALSE`, klicken Sie im Menü angezeigt wird, indem Sie auf die Schaltfläche klicken.  
  
##  <a name="setparentcategory"></a>CMFCRibbonButton::SetParentCategory  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void SetParentCategory(CMFCRibbonCategory* pParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pParent`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setrightalignmenu"></a>CMFCRibbonButton::SetRightAlignMenu  
 Richtet das Popupmenü an den Rand der Schaltfläche.  
  
```  
void SetRightAlignMenu(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bSet`  
 Wenn `TRUE`, klicken Sie im Menü wird rechts ausgerichtet. Andernfalls ist das Menü links ausgerichtete  
  
##  <a name="settext"></a>CMFCRibbonButton::SetText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszText`  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)

