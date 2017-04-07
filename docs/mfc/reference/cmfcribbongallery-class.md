---
title: Klasse CMFCRibbonGallery | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonGallery
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::CMFCRibbonGallery
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::AddGroup
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::AddSubItem
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::Clear
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::EnableMenuResize
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::EnableMenuSideBar
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetCompactSize
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetDroppedDown
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetGroupName
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetGroupOffset
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetIconsInRow
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetItemToolTip
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetLastSelectedItem
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetPaletteID
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetRegularSize
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::GetSelectedItem
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::HasMenu
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::IsButtonMode
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::IsMenuResizeEnabled
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::IsMenuResizeVertical
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::IsMenuSideBar
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::OnAfterChangeRect
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::OnDraw
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::OnEnable
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::OnRTLChanged
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::RedrawIcons
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::RemoveItemToolTips
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SelectItem
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SetACCData
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SetButtonMode
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SetGroupName
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SetIconsInRow
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SetItemToolTip
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SetPalette
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::SetPaletteID
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGallery::OnDrawPaletteIcon
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonGallery class
ms.assetid: 9734c9c9-981c-4b3f-8c59-264fd41811b4
caps.latest.revision: 28
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
ms.openlocfilehash: c4eadb9820f2d7318131cc4d197dbe28d65491c0
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbongallery-class"></a>CMFCRibbonGallery-Klasse
Implementiert Menübandkataloge im Stil von Office 2007.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonGallery : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonGallery::CMFCRibbonGallery](#cmfcribbongallery)|Erstellt und initialisiert ein `CMFCRibbonGallery`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonGallery::AddGroup](#addgroup)|Fügt eine neue Gruppe im Katalog.|  
|[CMFCRibbonGallery::AddSubItem](#addsubitem)|Klicken Sie im Dropdown-Menü hinzugefügt ein neues Menüelement.|  
|[CMFCRibbonGallery::Clear](#clear)|Löscht den Inhalt des Katalogs.|  
|[CMFCRibbonGallery::EnableMenuResize](#enablemenuresize)|Aktiviert oder deaktiviert, Ändern der Größe des Bereichs im Menü.|  
|[CMFCRibbonGallery::EnableMenuSideBar](#enablemenusidebar)|Aktiviert oder deaktiviert die Seitenleiste links neben dem Popup-Menü.|  
|[CMFCRibbonGallery::GetCompactSize](#getcompactsize)|(Überschreibt [CMFCRibbonButton::GetCompactSize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).)|  
|[CMFCRibbonGallery::GetDroppedDown](#getdroppeddown)|(Überschreibt [CMFCRibbonBaseElement::GetDroppedDown](../../mfc/reference/cmfcribbonbaseelement-class.md#getdroppeddown).)|  
|[CMFCRibbonGallery::GetGroupName](#getgroupname)|Gibt den Namen der Gruppe, die am angegebenen Index befindet.|  
|[CMFCRibbonGallery::GetGroupOffset](#getgroupoffset)||  
|[CMFCRibbonGallery::GetIconsInRow](#geticonsinrow)|Gibt die Anzahl der Elemente in einer Zeile das Menüband zurück.|  
|[CMFCRibbonGallery::GetItemToolTip](#getitemtooltip)|Gibt den QuickInfo-Text, der ein Element im Katalog zugeordnet ist.|  
|[CMFCRibbonGallery::GetLastSelectedItem](#getlastselecteditem)|Gibt den Index des letzten Elements in der Galerie, die vom Benutzer ausgewählte zurück.|  
|[CMFCRibbonGallery::GetPaletteID](#getpaletteid)|Gibt die Befehls-ID des aktuellen Katalogs zurück.|  
|[CMFCRibbonGallery::GetRegularSize](#getregularsize)|(Überschreibt [CMFCRibbonButton::GetRegularSize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).)|  
|[CMFCRibbonGallery::GetSelectedItem](#getselecteditem)||  
|[CMFCRibbonGallery::HasMenu](#hasmenu)|(Überschreibt [CMFCRibbonButton::HasMenu](../../mfc/reference/cmfcribbonbutton-class.md#hasmenu).)|  
|[CMFCRibbonGallery::IsButtonMode](#isbuttonmode)|Gibt an, ob der Katalog in einer Schaltfläche Katalog enthalten ist.|  
|[CMFCRibbonGallery::IsMenuResizeEnabled](#ismenuresizeenabled)|Gibt an, ob die Größe im Menü aktiviert oder deaktiviert ist.|  
|[CMFCRibbonGallery::IsMenuResizeVertical](#ismenuresizevertical)||  
|[CMFCRibbonGallery::IsMenuSideBar](#ismenusidebar)|Gibt an, ob die Seitenleiste aktiviert oder deaktiviert ist.|  
|[CMFCRibbonGallery::OnAfterChangeRect](#onafterchangerect)|(Überschreibt `CMFCRibbonButton::OnAfterChangeRect`.)|  
|[CMFCRibbonGallery::OnDraw](#ondraw)|(Überschreibt [CMFCRibbonButton::OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw).)|  
|[CMFCRibbonGallery::OnEnable](#onenable)|(Überschreibt `CMFCRibbonBaseElement::OnEnable`.)|  
|[CMFCRibbonGallery::OnRTLChanged](#onrtlchanged)|(Überschreibt [CMFCRibbonBaseElement::OnRTLChanged](../../mfc/reference/cmfcribbonbaseelement-class.md#onrtlchanged).)|  
|[CMFCRibbonGallery::RedrawIcons](#redrawicons)|Zeichnet den Katalog neu.|  
|[CMFCRibbonGallery::RemoveItemToolTips](#removeitemtooltips)|Entfernt die QuickInfos aus allen Elementen in der Galerie.|  
|[CMFCRibbonGallery::SelectItem](#selectitem)||  
|[CMFCRibbonGallery::SetACCData](#setaccdata)|(Überschreibt [CMFCRibbonButton::SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|  
|[CMFCRibbonGallery::SetButtonMode](#setbuttonmode)|Gibt an, ob das Menüband als Dropdown-Schaltfläche oder eine Palette direkt auf dem Menüband angezeigt werden soll.|  
|[CMFCRibbonGallery::SetGroupName](#setgroupname)|Legt den Namen einer Gruppe.|  
|[CMFCRibbonGallery::SetIconsInRow](#seticonsinrow)|Definiert die Anzahl der Elemente pro Zeile in der Galerie.|  
|[CMFCRibbonGallery::SetItemToolTip](#setitemtooltip)|Legt den QuickInfo-Text für ein Element in der Galerie.|  
|[CMFCRibbonGallery::SetPalette](#setpalette)|Fügt eine Palette an einem Menüband an.|  
|[CMFCRibbonGallery::SetPaletteID](#setpaletteid)|Definiert die Befehls-ID, die gesendet wird, in der `WM_COMMAND` angezeigt wird, wenn ein Galerieelement ausgewählt wurde.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonGallery::OnDrawPaletteIcon](#ondrawpaletteicon)|Wird vom Framework aufgerufen, wenn ein Katalog Symbol gezeichnet wird.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Schaltfläche Katalog verhält sich wie eine normale Schaltfläche, eine Sammlung angezeigt, wenn ein Benutzer geöffnet wird. Wenn Sie ein Element in einem Katalog auswählen, um das Framework sendet die `WM_COMMAND` Nachricht zusammen mit den Befehls-ID der Schaltfläche. Wenn Sie die Nachricht behandeln, sollten Sie aufrufen [CMFCRibbonGallery::GetLastSelectedItem](#getlastselecteditem) um zu bestimmen, welches Element aus der Galerie ausgewählt wurde.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCRibbonGallery` Klasse zum Konfigurieren einer `CMFCRibbonGallery` Objekt. Im Beispiel wird veranschaulicht, wie Geben Sie die Anzahl der Elemente pro Zeile in der Galerie, aktivieren, Ändern der Größe des Bereichs im Menü, Aktivieren der Seitenleiste links neben dem Popup-Menü, und zeigen das Menüband als eine Palette direkt in der menübandleiste. Dieser Codeausschnitt ist Teil der [zeichnen Clientbeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient&6;](../../mfc/reference/codesnippet/cpp/cmfcribbongallery-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md) [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md) [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxRibbonPaletteGallery.h  
  
##  <a name="addgroup"></a>CMFCRibbonGallery::AddGroup  
 Fügt eine neue Gruppe im Katalog.  
  
```  
void AddGroup(
    LPCTSTR lpszGroupName,  
    UINT uiImagesPaletteResID,  
    int cxPaletteImage);

 
void AddGroup(
    LPCTSTR lpszGroupName,  
    CMFCToolBarImages& imagesGroup);

 
void AddGroup(
    LPCTSTR lpszGroupName,  
    int nIconsNum);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszGroupName`  
 Gibt den Namen der Gruppe an.  
  
 [in] `uiImagesPaletteResID`  
 Gibt die Ressourcen-ID der Bildliste, die die Bilder für die Gruppe enthält.  
  
 [in] `cxPaletteImage`  
 Gibt die Breite in Pixel eines Bilds.  
  
 [in] `imagesGroup`  
 Ein Verweis auf die Bildliste mit Gruppieren von Images.  
  
 [in] `nIconsNum`  
 Gibt die Anzahl der Symbole in der Gruppe. Dieser Parameter sollte nur für benutzerdefinierte (Ownerdrawn) angegeben werden Gruppen.  
  
### <a name="remarks"></a>Hinweise  
 Sie können Elemente in einem Menüband in mehrere Gruppen unterteilen, durch Aufrufen dieser Methode. Jede Gruppe kann eine Beschriftung verfügen.  
  
##  <a name="addsubitem"></a>CMFCRibbonGallery::AddSubItem  
 Klicken Sie im Dropdown-Menü hinzugefügt ein neues Menüelement.  
  
```  
void AddSubItem(
    CMFCRibbonBaseElement* pSubItem,  
    int nIndex=-1,  
    BOOL bOnTop=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pSubItem`  
 Ein Zeiger auf das Element, auf das Menü hinzugefügt.  
  
 [in] `nIndex`  
 Gibt dem nullbasierten Index des einen Speicherort, wo das Element eingefügt werden.  
  
 [in] `bOnTop`  
 `TRUE`um anzugeben, dass das Element vor dem Menüband eingefügt werden sollen; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Sie können Popup-Katalogen mit Popupmenüelemente kombinieren, durch Aufrufen dieser Methode. Menüelemente können vor oder nach der Gallery eingefügt werden.  
  
 Wenn das Element vor dem Katalog einfügen möchten, legen Sie `bOnTop` auf `TRUE`. Legen Sie `bOnTop` auf `FALSE` das Element unterhalb des Katalogs eingefügt.  
  
> [!NOTE]
>  Der Parameter `nIndex` gibt den Einfügeindex am oberen Rand der Galerie sowohl am unteren Rand der Galerie. Wenn Sie eine Element eine Position vor dem Katalog einfügen müssen, z. B. festgelegt `nIndex` auf 1 und `bOnTop` auf `TRUE`. Wenn Sie eine Element eine Position unterhalb des Katalogs einfügen müssen, auf ähnliche Weise festlegen `nIndex` auf 1 und `bOnTop` auf `FALSE`.  
  
##  <a name="clear"></a>CMFCRibbonGallery::Clear  
 Löscht den Inhalt des Katalogs.  
  
```  
virtual void Clear();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um alle Inhalte aus dem Menüband entfernen. Dies muss erfolgen, bevor Sie dem Menüband eine neue Menüband oder eine Gruppe von Gruppen zuordnen.  
  
##  <a name="cmfcribbongallery"></a>CMFCRibbonGallery::CMFCRibbonGallery  
 Erstellt und initialisiert ein [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md) Objekt.  
  
```  
CMFCRibbonGallery (
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex,  
    int nLargeImageIndex,  
    CMFCToolBarImages& imagesPalette);

 
CMFCRibbonGallery (
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex,  
    int nLargeImageIndex,  
    UINT uiImagesPaletteResID=0,  
    int cxPaletteImage=0);

 
CMFCRibbonGallery (
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex,  
    int nLargeImageIndex,  
    CSize sizeIcon,  
    int nIconsNum,  
    BOOL bDefaultButtonStyle=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Gibt die Befehls-ID des Befehls ausführen, wenn ein Benutzer auf die Schaltfläche klickt.  
  
 `lpszText`  
 Gibt den Text auf der Schaltfläche angezeigt werden sollen.  
  
 `nSmallImageIndex`  
 Der nullbasierte Index des kleinen Bilds auf der Schaltfläche angezeigt werden.  
  
 `nLargeImageIndex`  
 Der nullbasierte Index des großen Bilds auf der Schaltfläche angezeigt werden.  
  
 `imagesPalette`  
 Ein Verweis auf die [CMFCToolBarImages](../../mfc/reference/cmfctoolbarimages-class.md) -Objekt, das den Bildern in der Sammlung angezeigt werden sollen.  
  
 `uiImagesPaletteResID`  
 Die Ressourcen-ID der Liste der Bilder in der Sammlung angezeigt.  
  
 `cxPaletteImage`  
 Gibt die Breite in Pixel des Bilds in der Sammlung an.  
  
 `sizeIcon`  
 Gibt die Größe des Images aus dem Katalog in Pixel an.  
  
 `nIconsNum`  
 Gibt die Anzahl der Symbole in der Galerie.  
  
 `bDefaultButtonStyle`  
 Gibt an, ob der Standard-oder der Ownerdrawn-Schaltflächen-Formatvorlage.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enablemenuresize"></a>CMFCRibbonGallery::EnableMenuResize  
 Aktiviert oder deaktiviert, Ändern der Größe des Bereichs im Menü.  
  
```  
void EnableMenuResize(
    BOOL bEnable = TRUE,  
    BOOL bVertcalOnly = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`So aktivieren Sie die Größe im Menüs; andernfalls `FALSE`.  
  
 [in] `bVertcalOnly`  
 `TRUE`um anzugeben, dass der Katalog nur vertikal angepasst werden kann; `FALSE` um anzugeben, dass die Galerie kann Bildfelds horizontal und vertikal.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode zum Aktivieren oder deaktivieren, Ändern der Größe der Menüband. Beim Ändern der Größe aktiviert ist, zeigt das Menüband ein Ziehpunkte, die ein Benutzer verwenden können, um seine Größe anzupassen.  
  
##  <a name="enablemenusidebar"></a>CMFCRibbonGallery::EnableMenuSideBar  
 Aktiviert oder deaktiviert die Seitenleiste links neben dem Popup-Menü.  
  
```  
void EnablMenuSideBar(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`um anzugeben, dass die Seitenleiste aktiviert ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Aktivieren oder deaktivieren die Office XP-Stil Seitenleiste auf der linken Seite des Menüs.  
  
##  <a name="getcompactsize"></a>CMFCRibbonGallery::GetCompactSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getdroppeddown"></a>CMFCRibbonGallery::GetDroppedDown  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CMFCRibbonBaseElement* GetDroppedDown();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getgroupname"></a>CMFCRibbonGallery::GetGroupName  
 Gibt den Namen der Gruppe, die am angegebenen Index befindet.  
  
```  
LPCTSTR GetGroupName(int nGroupIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nGroupIndex`  
 Gibt den nullbasierten Index für die Gruppe, deren Name abgerufen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name der Gruppe am angegebenen Index. Übergeben einen ungültigen Index führt eine fehlgeschlagene Assertion.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getgroupoffset"></a>CMFCRibbonGallery::GetGroupOffset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetGroupOffset() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="geticonsinrow"></a>CMFCRibbonGallery::GetIconsInRow  
 Gibt die Anzahl der Elemente in einer Zeile das Menüband zurück.  
  
```  
int GetIconsInRow() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in einer Zeile.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getitemtooltip"></a>CMFCRibbonGallery::GetItemToolTip  
 Gibt den QuickInfo-Text, der ein Element im Katalog zugeordnet ist.  
  
```  
LPCTSTR GetItemToolTip(int nItemIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nItemIndex`  
 Gibt den nullbasierten Index des Elements, für die QuickInfo-Text abzurufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die QuickInfo-Zeichenfolge, die auf ein Element auf dem Menüband zugewiesen. Es kann sein `NULL` Wenn dieses Element keine QuickInfo zugewiesen wird.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getlastselecteditem"></a>CMFCRibbonGallery::GetLastSelectedItem  
 Gibt den Index des letzten Elements in dem Menüband, die der Benutzer ausgewählt.  
  
```  
static int GetLastSelectedItem(UINT uiCmdID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdID`  
 Gibt die Befehls-ID des Menüelements, das die Menüband-Galerie geöffnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Benutzer ein Element in der Menüband-Galerie auswählt, sendet die Bibliothek der `WM_COMMAND` Nachricht zusammen mit den Befehls-ID der Menüschaltfläche, die das Menüband geöffnet.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getpaletteid"></a>CMFCRibbonGallery::GetPaletteID  
 Gibt die Befehls-ID der aktuellen Palette zurück.  
  
```  
int GetPaletteID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Befehls-ID der aktuell ausgewählten Palette.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getregularsize"></a>CMFCRibbonGallery::GetRegularSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getselecteditem"></a>CMFCRibbonGallery::GetSelectedItem  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetSelectedItem() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hasmenu"></a>CMFCRibbonGallery::HasMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isbuttonmode"></a>CMFCRibbonGallery::IsButtonMode  
 Gibt an, ob die Palette in eine Schaltfläche Katalog enthalten ist.  
  
```  
BOOL IsButtonMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Palette als eine Dropdown-Schaltfläche angezeigt wird. `FALSE` Wenn die Palette direkt auf dem Menüband angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ismenuresizeenabled"></a>CMFCRibbonGallery::IsMenuResizeEnabled  
 Gibt an, ob das Ändern der Größe von Menüs aktiviert ist.  
  
```  
BOOL IsMenuResizeEnabled() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Ändern der Größe von Menüs aktiviert wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ismenuresizevertical"></a>CMFCRibbonGallery::IsMenuResizeVertical  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsMenuResizeVertical() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ismenusidebar"></a>CMFCRibbonGallery::IsMenuSideBar  
 Gibt an, ob die Seitenleiste aktiviert oder deaktiviert ist.  
  
```  
BOOL IsMenuSideBar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Office XP-Stil Seitenleiste auf der linken Seite des Popupmenüs gezeichnet wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onafterchangerect"></a>CMFCRibbonGallery::OnAfterChangeRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnAfterChangeRect(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondraw"></a>CMFCRibbonGallery::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondrawpaletteicon"></a>CMFCRibbonGallery::OnDrawPaletteIcon  
 Wird vom Framework aufgerufen, wenn ein Katalog Symbol gezeichnet wird.  
  
```  
virtual void OnDrawPaletteIcon(
    CDC* pDC,  
    CRect rectIcon,  
    int nIconIndex,  
    CMFCRibbonGalleryIcon* pIcon,  
    COLORREF clrText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext, der zum Zeichnen verwendet wird.  
  
 [in] `rectIcon`  
 Gibt das umschließende Rechteck des Symbols zu zeichnen.  
  
 [in] `nIconIndex`  
 Gibt den nullbasierten Index in der Bildliste Katalog Symbole für das Symbol gezeichnet.  
  
 [in] `pIcon`  
 Ein Zeiger auf das Symbol gezeichnet wird.  
  
 [in] `clrText`  
 Gibt die Farbe für den Text des Elements, das gezeichnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode in einer abgeleiteten Klasse zum Anpassen der Darstellung von einem Menüband überschreiben.  
  
##  <a name="onenable"></a>CMFCRibbonGallery::OnEnable  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnEnable(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onrtlchanged"></a>CMFCRibbonGallery::OnRTLChanged  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bIsRTL`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="redrawicons"></a>CMFCRibbonGallery::RedrawIcons  
 Zeichnet den Katalog neu.  
  
```  
void RedrawIcons();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um den Katalog neu zu zeichnen. Wenn Sie den Inhalt des Katalogs zur Laufzeit geändert haben, müssen Sie diese Methode aufrufen.  
  
##  <a name="removeitemtooltips"></a>CMFCRibbonGallery::RemoveItemToolTips  
 Entfernt die QuickInfos aus allen Elementen in der Galerie.  
  
```  
void RemoveItemToolTips();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="selectitem"></a>CMFCRibbonGallery::SelectItem  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SelectItem(int nItemIndex);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nItemIndex`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setaccdata"></a>CMFCRibbonGallery::SetACCData  
 Füllt das angegebene `CAccessibilityData` -Objekt mithilfe von Barrierefreiheitsdaten aus dem Menübandkatalog.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,   
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pParent`  
 Das übergeordnete Fenster des Menübandkatalogfensters.  
  
 [out] `data`  
 Ein `CAccessibilityData` -Objekt, das die Barrierefreiheitsdaten aus dem Menübandkatalog erhält.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 `TRUE`Wenn die Methode erfolgreich ist; andernfalls `FALSE`.  
  
##  <a name="setbuttonmode"></a>CMFCRibbonGallery::SetButtonMode  
 Bestimmt, ob das Menüband als Dropdown-Schaltfläche oder eine Palette direkt auf dem Menüband angezeigt.  
  
```  
void SetButtonMode(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bSet`  
 `TRUE`auf dem Menüband als eine Dropdown-Schaltfläche angezeigt werden. `FALSE` den Inhalt der Menüband direkt auf dem Menüband angezeigt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setgroupname"></a>CMFCRibbonGallery::SetGroupName  
 Legt den Namen einer Gruppe.  
  
```  
void SetGroupName(
    int nGroupIndex,  
    LPCTSTR lpszGroupName);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nGroupIndex`  
 Gibt den nullbasierten Index für die Gruppe, für die der Name geändert wurde.  
  
 [in] `lpszGroupName`  
 Gibt den neuen Namen für die Gruppe an.  
  
### <a name="remarks"></a>Hinweise  
 Die Gruppe, deren Name geändert werden, muss hinzugefügten mithilfe der [CMFCRibbonGallery::AddGroup](#addgroup) Methode.  
  
##  <a name="seticonsinrow"></a>CMFCRibbonGallery::SetIconsInRow  
 Gibt die Anzahl der Elemente pro Zeile in der Galerie.  
  
```  
void SetIconsInRow(int nIconsInRow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIconsInRow`  
 Gibt die Anzahl der Elemente in jeder Zeile des Katalogs angezeigt werden.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um die Breite der Menüband anzugeben.  
  
##  <a name="setitemtooltip"></a>CMFCRibbonGallery::SetItemToolTip  
 Legt den QuickInfo-Text für ein Element in der Galerie.  
  
```  
void SetItemToolTip(
    int nItemIndex,  
    LPCTSTR lpszToolTip);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nItemIndex`  
 Der nullbasierte Index des Elements Palette mit dem die QuickInfo zugeordnet werden soll.  
  
 [in] `lpszToolTip`  
 Der Text der QuickInfo angezeigt werden.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpalette"></a>CMFCRibbonGallery::SetPalette  
 Fügt eine Palette an einem Menüband an.  
  
```  
void SetPalette(CMFCToolBarImages& imagesPalette);

 
void SetPalette(
    UINT uiImagesPaletteResID,  
    int cxPaletteImage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `imagesPalette`  
 Gibt die Liste der Images, die die Symbole in der Sammlung angezeigt werden sollen.  
  
 [in] `uiImagesPaletteResID`  
 Gibt die Ressourcen-ID der Bildliste, die die Symbole in der Sammlung angezeigt werden sollen.  
  
 [in] `cxPaletteImage`  
 Gibt die Breite in Pixel eines Bilds in der Sammlung an.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpaletteid"></a>CMFCRibbonGallery::SetPaletteID  
 Definiert die Befehls-ID, die gesendet wird, in der **WM_COMMAND** angezeigt wird, wenn ein Benutzer ein Galerieelement auswählt.  
  
```  
void SetPaletteID(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 Gibt die Befehls-ID, die gesendet wird, in der **WM_COMMAND** angezeigt wird, wenn ein Benutzer ein Galerieelement auswählt.  
  
### <a name="remarks"></a>Hinweise  
 Um das Element zu bestimmen, die ein Benutzer aus der Galerie ausgewählt, rufen Sie die [CMFCRibbonGallery::GetLastSelectedItem](#getlastselecteditem) statische Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton-Klasse](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonGalleryMenuButton-Klasse](../../mfc/reference/cmfcribbongallerymenubutton-class.md)

