---
title: Klasse CMFCOutlookBarPane | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::AddButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::CanBeAttached
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::ClearAll
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::Create
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnablePageScrollMode
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::GetRegularColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsBackgroundTexture
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsDrawShadedHighlight
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackImage
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetDefaultState
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetExtraSpace
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTextColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTransparentColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnableContextMenuItems
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveAllButtons
dev_langs:
- C++
helpviewer_keywords:
- Dock method
- IsChangeState method
- SmartUpdate method
- OnBeforeFloat method
- RestoreOriginalstate method
- CMFCOutlookBarPane class
- CanBeRestored method
ms.assetid: 094e2ef3-a118-487e-a4cc-27626108fe08
caps.latest.revision: 30
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
ms.openlocfilehash: da4fab1a6d94e962090f21414062dc2da0c9482c
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcoutlookbarpane-class"></a>CMFCOutlookBarPane-Klasse
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Ein Steuerelement abgeleitet [CMFCToolBar Klasse](../../mfc/reference/cmfctoolbar-class.md) in eine Outlook-Leiste eingefügt werden kann ( [CMFCOutlookBar Class](../../mfc/reference/cmfcoutlookbar-class.md)). Der Outlook-Leistenbereich enthält eine Spalte mit großen Schaltflächen. Der Benutzer kann einen Bildlauf durchführen, um die Liste der Schaltflächen nach oben bzw. unten zu verschieben, wenn sie größer ist als der Bereich. Wenn der Benutzer einen Outlook-Leistenbereich von der Outlook-Leiste trennt, ist er frei positionierbar oder kann im Hauptrahmenfenster andocken.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCOutlookBarPane : public CMFCToolBar  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCOutlookBarPane::CMFCOutlookBarPane`|Standardkonstruktor|  
|`CMFCOutlookBarPane::~CMFCOutlookBarPane`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCOutlookBarPane::AddButton](#addbutton)|Der Outlook-Leistenbereich hinzugefügt eine Schaltfläche.|  
|[CMFCOutlookBarPane::CanBeAttached](#canbeattached)|Bestimmt, ob der Bereich zu einem anderen Bereich oder Fenster angedockt werden kann. (Überschreibt [CBasePane::CanBeAttached](../../mfc/reference/cbasepane-class.md#canbeattached).)|  
|`CMFCOutlookBarPane::CanBeRestored`|Bestimmt, ob das System nach der Anpassung eine Symbolleiste in seinen ursprünglichen Zustand wiederherstellen können. (Überschreibt [CMFCToolBar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|  
|[CMFCOutlookBarPane::ClearAll](#clearall)|Gibt die von Bildern in der Outlook-Leistenbereich verwendeten Ressourcen frei.|  
|[CMFCOutlookBarPane::Create](#create)|Erstellt die Outlook-Leistenbereich.|  
|`CMFCOutlookBarPane::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CMFCOutlookBarPane::Dock`|Vom Framework aufgerufen, die Outlook-Leistenbereich andocken. (Überschreibt `CPane::Dock`.)|  
|[CMFCOutlookBarPane::EnablePageScrollMode](#enablepagescrollmode)|Gibt an, ob die Pfeile auf der Outlook-Leistenbereich die Liste der Schaltflächen für die Seite oder Schaltfläche wechseln.|  
|[CMFCOutlookBarPane::GetRegularColor](#getregularcolor)|Gibt die regulären (nicht ausgewählt) Textfarbe des Outlook-Leistenbereich zurück.|  
|`CMFCOutlookBarPane::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
|[CMFCOutlookBarPane::IsBackgroundTexture](#isbackgroundtexture)|Bestimmt, ob ein Hintergrundbild für das Outlook-Leistenbereich geladen ist.|  
|`CMFCOutlookBarPane::IsChangeState`|Bestimmt, ob ein nicht verankertes Fenster angedockt werden kann. (Überschreibt `CPane::IsChangeState`.)|  
|[CMFCOutlookBarPane::IsDrawShadedHighlight](#isdrawshadedhighlight)|Bestimmt, ob der Schaltflächenrahmen abgeblendet ist, wenn eine Schaltfläche hervorgehoben wird und ein Bild als Hintergrund angezeigt wird.|  
|`CMFCOutlookBarPane::OnBeforeFloat`|Wird vom Framework aufgerufen, wenn ein Bereich in einen Gleitkommawert ist. (Überschreibt [CPane::OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat).)|  
|[CMFCOutlookBarPane::RemoveButton](#removebutton)|Entfernt die Schaltfläche mit einem angegebenen Befehls-ID.|  
|`CMFCOutlookBarPane::RestoreOriginalstate`|Stellt den originalen Zustand einer Symbolleiste wieder her. (Überschreibt [CMFCToolBar::RestoreOriginalState](../../mfc/reference/cmfctoolbar-class.md#restoreoriginalstate).)|  
|[CMFCOutlookBarPane::SetBackColor](#setbackcolor)|Legt die Hintergrundfarbe fest.|  
|[CMFCOutlookBarPane::SetBackImage](#setbackimage)|Legt das Hintergrundbild fest.|  
|[CMFCOutlookBarPane::SetDefaultState](#setdefaultstate)|Setzt die Outlook-Leistenbereich auf die ursprüngliche Gruppe von Schaltflächen zurück.|  
|[CMFCOutlookBarPane::SetExtraSpace](#setextraspace)|Legt die Anzahl von Pixeln verwendet, um Schaltflächen im Outlook-Leiste.|  
|[CMFCOutlookBarPane::SetTextColor](#settextcolor)|Legt die regelmäßige und markierten Text in die Outlook-Leistenbereich fest.|  
|[CMFCOutlookBarPane::SetTransparentColor](#settransparentcolor)|Legt die transparente Farbe für die Outlook-Leistenbereich fest.|  
|`CMFCOutlookBarPane::SmartUpdate`|Intern verwendet, um die Outlook-Leiste zu aktualisieren. (Überschreibt `CMFCToolBar::SmartUpdate`.)|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCOutlookBarPane::EnableContextMenuItems](#enablecontextmenuitems)|Gibt an, welche Kontextmenüelemente im Anpassungsmodus angezeigt werden.|  
|[CMFCOutlookBarPane::RemoveAllButtons](#removeallbuttons)|Entfernt alle Schaltflächen aus dem Bereich der Outlook-Leiste. (Überschreibt [CMFCToolBar::RemoveAllButtons](../../mfc/reference/cmfctoolbar-class.md#removeallbuttons).)|  
  
## <a name="remarks"></a>Hinweise  
 Informationen dazu, wie Sie eine Outlook-Leiste zu implementieren, finden Sie unter [CMFCOutlookBar Class](../../mfc/reference/cmfcoutlookbar-class.md).  
  
 Ein Beispiel für eine Outlook-Leiste finden Sie unter das OutlookDemo-Beispielprojekt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden der `CMFCOutlookBarPane` Klasse. Das Beispiel zeigt, wie Sie einen Outlook-Leistenbereich zu erstellen, aktivieren Sie den Modus der Seite einen Bildlauf, aktivieren Sie das Andocken und Festlegen der Hintergrundfarbe der Outlook-Leiste. Dieser Codeausschnitt ist Teil der [Outlook mit mehreren Ansichten Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookMultiViews&3;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_1.h)]  
[!code-cpp[NVC_MFC_OutlookMultiViews&4;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxoutlookbarpane.h  
  
##  <a name="addbutton"></a>CMFCOutlookBarPane::AddButton  
 Der Outlook-Leistenbereich hinzugefügt eine Schaltfläche.  
  
```  
BOOL AddButton(
    UINT uiImage,  
    LPCTSTR lpszLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    UINT uiImage,  
    UINT uiLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    LPCTSTR szBmpFileName,  
    LPCTSTR szLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    HBITMAP hBmp,  
    LPCTSTR lpszLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    HICON hIcon,  
    LPCTSTR lpszLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1,  
    BOOL bAlphaBlend=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiImage`  
 Gibt den Ressourcenbezeichner der Bitmap an.  
  
 [in] `lpszLabel`  
 Gibt den Text der Schaltfläche.  
  
 [in] `iIdCommand`  
 Gibt das Schaltflächen-Steuerelement-ID an.  
  
 [in] `iInsertAt`  
 Gibt den nullbasierten Index auf der Outlook-Leiste unter der die Schaltfläche eingefügt.  
  
 [in] `uiLabel`  
 Eine Zeichenfolge-Ressourcen-ID  
  
 [in] `szBmpFileName`  
 Gibt den Namen der Abbilddatei geladen.  
  
 [in] `szLabel`  
 Gibt den Text der Schaltfläche.  
  
 [in] `hBmp`  
 Ein Handle für eine Schaltfläche Bitmap.  
  
 [in] `hIcon`  
 Ein Handle für ein Schaltflächen-Symbol.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn eine Schaltfläche erfolgreich hinzugefügt wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eine neue Schaltfläche in eine Outlook-Leiste Seite einzufügen. Das Bild der Schaltfläche kann aus den Anwendungsressourcen oder aus einer Datenträgerdatei geladen werden.  
  
 Wenn die Seiten-ID durch angegeben `uiPageID` -1 ist, wird die Schaltfläche in der ersten Seite eingefügt.  
  
 Wenn der Index von angegebenen `iInsertAt` ist-1, wird die Schaltfläche am Ende der Seite hinzugefügt.  
  
##  <a name="canbeattached"></a>CMFCOutlookBarPane::CanBeAttached  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="clearall"></a>CMFCOutlookBarPane::ClearAll  
 Gibt die Bilder auf der Outlook-Leistenbereich verwendeten Ressourcen frei.  
  
```  
void ClearAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft direkt [CMFCToolBarImages::Clear](../../mfc/reference/cmfctoolbarimages-class.md#clear), die aufgerufen wird, auf die Bilder, die von der Outlook-Leistenbereich verwendet werden.  
  
##  <a name="create"></a>CMFCOutlookBarPane::Create  
 Erstellt die Outlook-Leistenbereich.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle=AFX_DEFAULT_TOOLBAR_STYLE,  
    UINT uiID=(UINT)-1,  
    DWORD dwControlBarStyle=0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pParentWnd`  
 Gibt das übergeordnete Fenster des Outlook-Leiste-Steuerelements an. Dieser Wert darf nicht `NULL` sein.  
  
 [in] `dwStyle`  
 Der Fensterstil.  Eine Liste der Fensterstile, finden Sie unter [Fensterstile](../../mfc/reference/window-styles.md).  
  
 [in] `uiID`  
 Die Steuerelement-ID. Ist eindeutig zu speichern, der den Zustand des Steuerelements.  
  
 [in] `dwControlBarStyle`  
 Gibt spezielle Formate, die das Verhalten von der Outlook-Leistensteuerelement Bereich definieren, wenn sie von der Outlook-Leiste getrennt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich war; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen einer `CMFCOutlookBarPane` Objekt, rufen Sie zuerst den Konstruktor, und rufen Sie dann `Create`, das erstellt die Outlook-Leiste-Steuerelement und fügt es der `CMFCOutlookBarPane` Objekt.  
  
 Weitere Informationen zu `dwControlBarStyle` finden Sie unter [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
##  <a name="enablecontextmenuitems"></a>CMFCOutlookBarPane::EnableContextMenuItems  
 Gibt an, welche Kontextmenüelemente im Anpassungsmodus angezeigt werden.  
  
```  
virtual BOOL EnableContextMenuItems(
    CMFCToolBarButton* pButton,  
    CMenu* pPopup);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pButton`  
 Ein Zeiger auf eine Symbolleisten-Schaltfläche, die ein Benutzer geklickt hat.  
  
 [in] `pPopup`  
 Ein Zeiger auf das Kontextmenü.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` , wenn Sie im Kontextmenü angezeigt, andernfalls werden soll `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um das Framework-standard-Kontextmenü zu ändern, das vom Framework in den Anpassungsmodus angezeigt.  
  
 Die standardmäßige Implementierung überprüft den Anpassungsmodus ( [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)) festgelegt ist und `TRUE`, deaktiviert alle Kontextmenüs außer **löschen**. Klicken Sie dann einfach übergibt die Eingabeparameter für `CMFCToolBar::EnableContextMenuItems`.  
  
> [!NOTE]
> *Kontextmenü* ist ein Synonym für Kontextmenü.  
  
##  <a name="enablepagescrollmode"></a>CMFCOutlookBarPane::EnablePageScrollMode  
 Gibt an, ob die Pfeile auf der Outlook-Leistenbereich die Liste der Schaltflächen, die Seite oder durch Schaltfläche wechseln.  
  
```  
void EnablePageScrollMode(BOOL bPageScroll=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bPageScroll`  
 Wenn `TRUE`, aktivieren Sie den Modus der Seite einen Bildlauf. Wenn `FALSE`, deaktivieren Sie den Modus der Seite einen Bildlauf.  
  
##  <a name="getregularcolor"></a>CMFCOutlookBarPane::GetRegularColor  
 Gibt den regulären (d. h. nicht ausgewählt) Textfarbe des Outlook-Leistenbereich.  
  
```  
DECLARE_MESSAGE_MAPCOLORREF GetRegularColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Textfarbe als einen RGB-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [CMFCOutlookBarPane::SetTextColor](#settextcolor) die aktuelle (reguläre und ausgewählte) Textfarbe der Outlook-Leiste festlegen. Sie erhalten die Standardtextfarbe durch Aufrufen der [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) -Funktion mit der `COLOR_WINDOW` Index.  
  
##  <a name="isbackgroundtexture"></a>CMFCOutlookBarPane::IsBackgroundTexture  
 Bestimmt, ob ein Hintergrundbild für das Outlook-Leistenbereich geladen ist.  
  
```  
BOOL IsBackgroundTexture() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn enthält Hintergrundbild anzeigen. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Sie können ein Hintergrundbild hinzufügen, durch Aufrufen von [CMFCOutlookBarPane::SetBackImage](#setbackimage) Funktion.  
  
 Wenn kein Hintergrundbild vorhanden ist, wird der Hintergrund gezeichnet, mit einer Farbe, die mit angegebene [CMFCOutlookBarPane::SetBackColor](#setbackcolor).  
  
##  <a name="isdrawshadedhighlight"></a>CMFCOutlookBarPane::IsDrawShadedHighlight  
 Bestimmt, ob der Schaltflächenrahmen abgeblendet ist, wenn eine Schaltfläche hervorgehoben wird und ein Bild als Hintergrund angezeigt wird.  
  
```  
BOOL IsDrawShadedHighlight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Schaltfläche Rahmen schattiert sind. andernfalls `FALSE`.  
  
##  <a name="removeallbuttons"></a>CMFCOutlookBarPane::RemoveAllButtons  
 Entfernt alle Schaltflächen aus dem Bereich der Outlook-Leiste.  
  
```  
virtual void RemoveAllButtons();
```  
  
##  <a name="removebutton"></a>CMFCOutlookBarPane::RemoveButton  
 Entfernt die Schaltfläche mit einem angegebenen Befehls-ID.  
  
```  
BOOL RemoveButton(UINT iIdCommand);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iIdCommand`  
 Gibt die Befehls-ID einer Schaltfläche zu entfernen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Schaltfläche erfolgreich entfernt wurde. `FALSE` Wenn die angegebene Befehls-ID ungültig ist.  
  
##  <a name="setbackcolor"></a>CMFCOutlookBarPane::SetBackColor  
 Legt die Hintergrundfarbe der Outlook-Leiste.  
  
```  
void SetBackColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
 Gibt die neue Hintergrundfarbe an.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um die aktuelle Hintergrundfarbe für die Outlook-Leiste festlegen. Die Hintergrundfarbe wird nur verwendet, wenn kein Hintergrundbild vorhanden ist.  
  
##  <a name="setbackimage"></a>CMFCOutlookBarPane::SetBackImage  
 Legt das Hintergrundbild fest.  
  
```  
void SetBackImage(UINT uiImageID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiImageID`  
 Gibt die Bild-Ressourcen-ID.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Outlook Festlegen des Balkens Hintergrundbild. Die Liste der Hintergrundbilder wird verwaltet von eingebetteten [CMFCToolBarImages Klasse](../../mfc/reference/cmfctoolbarimages-class.md) Objekt.  
  
##  <a name="setdefaultstate"></a>CMFCOutlookBarPane::SetDefaultState  
 Setzt die Outlook-Leistenbereich auf die ursprüngliche Gruppe von Schaltflächen zurück.  
  
```  
void SetDefaultState();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode stellt die Outlook-Leiste Schaltflächen und die ursprünglichen wieder her. Diese Methode ist mit `CMFCOutlookBarPane::RestoreOriginalstate`, außer dass sie kein Neuzeichnen der Outlook-Leistenbereich auslöst.  
  
##  <a name="setextraspace"></a>CMFCOutlookBarPane::SetExtraSpace  
 Legt die Anzahl von Pixeln verwendet, um Schaltflächen im Outlook-Leiste.  
  
```  
void SetExtraSpace()  
```  
  
##  <a name="settextcolor"></a>CMFCOutlookBarPane::SetTextColor  
 Legt die regelmäßige und markierten Text in die Outlook-Leistenbereich fest.  
  
```  
void SetTextColor(
    COLORREF clrRegText,  
    COLORREF clrSelText=0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `clrRegText`  
 Gibt die neue Farbe für den Text nicht ausgewählt.  
  
 [in] `clrSelText`  
 Gibt die neue Farbe für den ausgewählten Text.  
  
##  <a name="settransparentcolor"></a>CMFCOutlookBarPane::SetTransparentColor  
 Legt die transparente Farbe für die Outlook-Leistenbereich fest.  
  
```  
void SetTransparentColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
 `color`  
 Gibt die neue transparente Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Die transparente Farbe ist erforderlich, um transparente Bilder anzuzeigen. Stattdessen wird jedes Vorkommen von Farbe in einem Bild mit der Hintergrundfarbe gezeichnet.  Es gibt keine Mischung von Hintergrund- und Vordergrundfarben Bildern.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCOutlookBarTabCtrl-Klasse](../../mfc/reference/cmfcoutlookbartabctrl-class.md)

