---
title: CMFCOutlookBarPane Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CMFCOutlookBarPane [MFC], AddButton
- CMFCOutlookBarPane [MFC], CanBeAttached
- CMFCOutlookBarPane [MFC], ClearAll
- CMFCOutlookBarPane [MFC], Create
- CMFCOutlookBarPane [MFC], EnablePageScrollMode
- CMFCOutlookBarPane [MFC], GetRegularColor
- CMFCOutlookBarPane [MFC], IsBackgroundTexture
- CMFCOutlookBarPane [MFC], IsDrawShadedHighlight
- CMFCOutlookBarPane [MFC], RemoveButton
- CMFCOutlookBarPane [MFC], SetBackColor
- CMFCOutlookBarPane [MFC], SetBackImage
- CMFCOutlookBarPane [MFC], SetDefaultState
- CMFCOutlookBarPane [MFC], SetExtraSpace
- CMFCOutlookBarPane [MFC], SetTextColor
- CMFCOutlookBarPane [MFC], SetTransparentColor
- CMFCOutlookBarPane [MFC], EnableContextMenuItems
- CMFCOutlookBarPane [MFC], RemoveAllButtons
ms.assetid: 094e2ef3-a118-487e-a4cc-27626108fe08
caps.latest.revision: "30"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 59eb92e44a26577866a797243f3a32d53b854365
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcoutlookbarpane-class"></a>CMFCOutlookBarPane-Klasse
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Ein Steuerelement abgeleitet [CMFCToolBar Klasse](../../mfc/reference/cmfctoolbar-class.md) , die in eine Outlook-Leiste eingefügt werden können ( [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)). Der Outlook-Leistenbereich enthält eine Spalte mit großen Schaltflächen. Der Benutzer kann einen Bildlauf durchführen, um die Liste der Schaltflächen nach oben bzw. unten zu verschieben, wenn sie größer ist als der Bereich. Wenn der Benutzer einen Outlook-Leistenbereich von der Outlook-Leiste trennt, ist er frei positionierbar oder kann im Hauptrahmenfenster andocken.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCOutlookBarPane : public CMFCToolBar  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCOutlookBarPane::CMFCOutlookBarPane`|Standardkonstruktor|  
|`CMFCOutlookBarPane::~CMFCOutlookBarPane`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCOutlookBarPane::AddButton](#addbutton)|Das Outlook-Leistenbereich hinzugefügt eine Schaltfläche.|  
|[CMFCOutlookBarPane::CanBeAttached](#canbeattached)|Bestimmt, ob der Bereich in einem anderen Bereich oder der Zielframe, Fenster angedockt werden kann. (Überschreibt [CBasePane::CanBeAttached](../../mfc/reference/cbasepane-class.md#canbeattached).)|  
|`CMFCOutlookBarPane::CanBeRestored`|Bestimmt, ob das System nach dem Anpassen eine Symbolleiste in seinen ursprünglichen Zustand wiederherstellen können. (Überschreibt [CMFCToolBar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|  
|[CMFCOutlookBarPane::ClearAll](#clearall)|Gibt die von der Bilder in der Outlook-Leistenbereich verwendeten Ressourcen frei.|  
|[CMFCOutlookBarPane::Create](#create)|Erstellt die Outlook-Leistenbereich an.|  
|`CMFCOutlookBarPane::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CMFCOutlookBarPane::Dock`|Vom Framework aufgerufen, die Outlook-Leistenbereich andocken. (Überschreibt `CPane::Dock`.)|  
|[CMFCOutlookBarPane::EnablePageScrollMode](#enablepagescrollmode)|Gibt an, ob die Pfeile auf der Outlook-Leistenbereich die Liste der Schaltflächen, indem Seite oder Schaltfläche wechseln.|  
|[CMFCOutlookBarPane::GetRegularColor](#getregularcolor)|Gibt die regulären (nicht ausgewählt) Textfarbe des Outlook-Leistenbereich zurück.|  
|`CMFCOutlookBarPane::GetThisClass`|Durch das Framework verwendet wird, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CMFCOutlookBarPane::IsBackgroundTexture](#isbackgroundtexture)|Bestimmt, ob es ein Hintergrundbild für das Outlook-Leistenbereich geladen.|  
|`CMFCOutlookBarPane::IsChangeState`|Bestimmt, ob ein Gleitkommazahl im Bereich angedockt werden kann. (Überschreibt `CPane::IsChangeState`.)|  
|[CMFCOutlookBarPane::IsDrawShadedHighlight](#isdrawshadedhighlight)|Bestimmt, ob die Schaltflächenrahmen abgeblendet ist, wenn eine Schaltfläche wird hervorgehoben, und ein Hintergrundbild angezeigt wird.|  
|`CMFCOutlookBarPane::OnBeforeFloat`|Vom Framework aufgerufen, wenn ein Bereich zu "float" befindet. (Überschreibt [CPane::OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat).)|  
|[CMFCOutlookBarPane::RemoveButton](#removebutton)|Entfernt die Schaltfläche mit einem angegebenen Befehls-ID.|  
|`CMFCOutlookBarPane::RestoreOriginalstate`|Stellt den originalen Zustand einer Symbolleiste wieder her. (Überschreibt [CMFCToolBar::RestoreOriginalState](../../mfc/reference/cmfctoolbar-class.md#restoreoriginalstate).)|  
|[CMFCOutlookBarPane::SetBackColor](#setbackcolor)|Legt die Hintergrundfarbe fest.|  
|[CMFCOutlookBarPane::SetBackImage](#setbackimage)|Legt das Hintergrundbild an.|  
|[CMFCOutlookBarPane::SetDefaultState](#setdefaultstate)|Setzt die Outlook-Leistenbereich auf den ursprünglichen Satz an Schaltflächen zurück.|  
|[CMFCOutlookBarPane::SetExtraSpace](#setextraspace)|Legt die Anzahl von Pixeln verwendet, um Schaltflächen in der Outlook-Leistenbereich Abstand fest.|  
|[CMFCOutlookBarPane::SetTextColor](#settextcolor)|Legt die Farben der regulären und markierten Text in der Outlook-Leistenbereich fest.|  
|[CMFCOutlookBarPane::SetTransparentColor](#settransparentcolor)|Legt die transparente Farbe für den Outlook-Leistenbereich fest.|  
|`CMFCOutlookBarPane::SmartUpdate`|Wird intern verwendet, um die Outlook-Leiste zu aktualisieren. (Überschreibt `CMFCToolBar::SmartUpdate`.)|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCOutlookBarPane::EnableContextMenuItems](#enablecontextmenuitems)|Gibt an, welche Tastenkombinations-Menüelemente im Anpassungsmodus angezeigt werden.|  
|[CMFCOutlookBarPane::RemoveAllButtons](#removeallbuttons)|Entfernt alle Schaltflächen aus dem Outlook-Leistenbereich an. (Überschreibt [CMFCToolBar::RemoveAllButtons](../../mfc/reference/cmfctoolbar-class.md#removeallbuttons).)|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen dazu, wie eine Outlook-Leiste zu implementieren, finden Sie unter [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md).  
  
 Ein Beispiel für eine Outlook-Leiste finden Sie das Beispielprojekt OutlookDemo.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden der `CMFCOutlookBarPane` Klasse. Im Beispiel veranschaulicht das Erstellen eines Outlook-Leistenbereich, den Seite einen Bildlauf-Modus zu aktivieren, aktivieren Sie das Andocken und Festlegen der Hintergrundfarbe der Outlook-Leiste. Dieser Codeausschnitt ist Teil der [Outlook mehreren Ansichten Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookMultiViews#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_1.h)]  
[!code-cpp[NVC_MFC_OutlookMultiViews#4](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
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
 Das Outlook-Leistenbereich hinzugefügt eine Schaltfläche.  
  
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
 Gibt den Ressourcenbezeichner einer Bitmap an.  
  
 [in] `lpszLabel`  
 Gibt an, der Text der Schaltfläche.  
  
 [in] `iIdCommand`  
 Gibt das Schaltflächen-Steuerelement-ID an.  
  
 [in] `iInsertAt`  
 Gibt den nullbasierten Index auf Seite "der Outlook-Leiste" auf die Schaltfläche mit den eingefügt.  
  
 [in] `uiLabel`  
 Eine Zeichenfolge-Ressourcen-ID.  
  
 [in] `szBmpFileName`  
 Gibt den Namen der Abbilddatei zu laden.  
  
 [in] `szLabel`  
 Gibt an, der Text der Schaltfläche.  
  
 [in] `hBmp`  
 Ein Handle für eine Schaltfläche mithilfe einer Bitmap.  
  
 [in] `hIcon`  
 Ein Handle für ein Schaltflächen-Symbol.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn eine Schaltfläche erfolgreich hinzugefügt wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eine Schaltfläche "Neu" in eine Outlook-Leiste Seite einfügen. Bild der Schaltfläche kann aus den Anwendungsressourcen oder von einer Datenträgerdatei geladen werden.  
  
 Wenn die Seiten-ID, wird angegeben `uiPageID` ist-1, wird die Schaltfläche mit der in der ersten Seite eingefügt.  
  
 Wenn der Index von angegebenen `iInsertAt` ist-1, wird die Schaltfläche am Ende der Seite hinzugefügt.  
  
##  <a name="canbeattached"></a>CMFCOutlookBarPane::CanBeAttached  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="clearall"></a>CMFCOutlookBarPane::ClearAll  
 Gibt die von der Bilder für die Outlook-Leistenbereich verwendeten Ressourcen frei.  
  
```  
void ClearAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft direkt [CMFCToolBarImages::Clear](../../mfc/reference/cmfctoolbarimages-class.md#clear), was genannt wird, auf die Bilder, die von der Outlook-Leistenbereich verwendet werden.  
  
##  <a name="create"></a>CMFCOutlookBarPane::Create  
 Erstellt die Outlook-Leistenbereich an.  
  
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
 Der Fensterstil.  Eine Liste der Fensterstile, finden Sie unter [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] `uiID`  
 Die Steuerelement-ID. Muss eindeutig sein, um aktivieren Speichern des Status des Steuerelements.  
  
 [in] `dwControlBarStyle`  
 Gibt spezielle Formate, die das Verhalten des Steuerelements Outlook-Leiste definieren, wenn sie von der Outlook-Leiste getrennt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich ausgeführt wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 So erstellen Sie eine `CMFCOutlookBarPane` Objekt, rufen Sie zunächst den Konstruktor, und rufen Sie anschließend `Create`, der das Outlook-Leiste Bereichssteuerelement erstellt, und fügt es der `CMFCOutlookBarPane` Objekt.  
  
 Weitere Informationen zu `dwControlBarStyle` finden Sie unter [cbasepane:: CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
##  <a name="enablecontextmenuitems"></a>CMFCOutlookBarPane::EnableContextMenuItems  
 Gibt an, welche Tastenkombinations-Menüelemente im Anpassungsmodus angezeigt werden.  
  
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
 Gibt `TRUE` , wenn Sie im Kontextmenü, andernfalls angezeigten werden soll `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um das standardmäßige Kontextmenü Framework zu ändern, das vom Framework in Anpassungsmodus angezeigt.  
  
 Die standardmäßige Implementierung überprüft die Anpassungsmodus ( [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)) und wenn sie, um festgelegt ist `TRUE`, deaktiviert alle Tastenkombinations-Menüelemente außer **löschen**. Klicken Sie dann einfach übergibt die Eingabeparameter für `CMFCToolBar::EnableContextMenuItems`.  
  
> [!NOTE]
> *Kontextmenü* ist ein Synonym für Kontextmenü.  
  
##  <a name="enablepagescrollmode"></a>CMFCOutlookBarPane::EnablePageScrollMode  
 Gibt an, ob die Liste der Schaltflächen Seite oder der Schaltfläche durch die Pfeile auf der Outlook-Leistenbereich zu gelangen.  
  
```  
void EnablePageScrollMode(BOOL bPageScroll=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bPageScroll`  
 Wenn `TRUE`, den Seite einen Bildlauf-Modus zu aktivieren. Wenn `FALSE`, deaktivieren Sie die Bildlaufleiste Page-Modus.  
  
##  <a name="getregularcolor"></a>CMFCOutlookBarPane::GetRegularColor  
 Gibt die regulären (d. h. nicht ausgewählt) Textfarbe der Outlook-Leistenbereich.  
  
```  
DECLARE_MESSAGE_MAPCOLORREF GetRegularColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Textfarbe als eine RGB-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [CMFCOutlookBarPane::SetTextColor](#settextcolor) aktuellen (regulären und ausgewählte) Textfarbe der Outlook-Leiste festlegen. Sie erhalten die Farbe des Textes durch Aufrufen der [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) -Funktion mit der `COLOR_WINDOW` Index.  
  
##  <a name="isbackgroundtexture"></a>CMFCOutlookBarPane::IsBackgroundTexture  
 Bestimmt, ob es ein Hintergrundbild für das Outlook-Leistenbereich geladen.  
  
```  
BOOL IsBackgroundTexture() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn enthält Hintergrundbild angezeigt. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Sie können ein Hintergrundbild hinzufügen, durch den Aufruf [CMFCOutlookBarPane::SetBackImage](#setbackimage) Funktion.  
  
 Ist kein Hintergrundbild, wird der Hintergrund gezeichnet, mit einer Farbe mit angegeben [CMFCOutlookBarPane::SetBackColor](#setbackcolor).  
  
##  <a name="isdrawshadedhighlight"></a>CMFCOutlookBarPane::IsDrawShadedHighlight  
 Bestimmt, ob die Schaltflächenrahmen abgeblendet ist, wenn eine Schaltfläche wird hervorgehoben, und ein Hintergrundbild angezeigt wird.  
  
```  
BOOL IsDrawShadedHighlight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Schaltfläche Rahmen schattiert sind. andernfalls `FALSE`.  
  
##  <a name="removeallbuttons"></a>CMFCOutlookBarPane::RemoveAllButtons  
 Entfernt alle Schaltflächen aus dem Outlook-Leistenbereich an.  
  
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
 `TRUE`Wenn die Schaltfläche "" wurde erfolgreich entfernt wurde; `FALSE` , wenn die angegebene Befehls-ID ungültig ist.  
  
##  <a name="setbackcolor"></a>CMFCOutlookBarPane::SetBackColor  
 Legt die Hintergrundfarbe der Outlook-Leiste.  
  
```  
void SetBackColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
 Die neue Hintergrundfarbe angibt.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Festlegen der aktuellen Background-Farbe für die Outlook-Leiste. Die Farbe des Hintergrunds wird nur verwendet, wenn kein Hintergrundbild vorhanden ist.  
  
##  <a name="setbackimage"></a>CMFCOutlookBarPane::SetBackImage  
 Legt das Hintergrundbild an.  
  
```  
void SetBackImage(UINT uiImageID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiImageID`  
 Gibt die Bild-Ressourcen-ID.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Festlegen der Outlook Leiste Hintergrundbild. Die Liste der Hintergrundbilder wird verwaltet von eingebetteten [CMFCToolBarImages Klasse](../../mfc/reference/cmfctoolbarimages-class.md) Objekt.  
  
##  <a name="setdefaultstate"></a>CMFCOutlookBarPane::SetDefaultState  
 Setzt die Outlook-Leistenbereich auf den ursprünglichen Satz an Schaltflächen zurück.  
  
```  
void SetDefaultState();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode stellt die Outlook-Leiste Schaltflächen auf den ursprünglichen Satz wieder her. Diese Methode entspricht `CMFCOutlookBarPane::RestoreOriginalstate`, außer dass sie kein Neuzeichnen der Outlook-Leistenbereich auslöst.  
  
##  <a name="setextraspace"></a>CMFCOutlookBarPane::SetExtraSpace  
 Legt die Anzahl von Pixeln verwendet, um Schaltflächen in der Outlook-Leistenbereich Abstand fest.  
  
```  
void SetExtraSpace()  
```  
  
##  <a name="settextcolor"></a>CMFCOutlookBarPane::SetTextColor  
 Legt die Farben der regulären und markierten Text in der Outlook-Leistenbereich fest.  
  
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
 Legt die transparente Farbe für den Outlook-Leistenbereich fest.  
  
```  
void SetTransparentColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
 `color`  
 Gibt die neue transparente Farbe an.  
  
### <a name="remarks"></a>Hinweise  
 Die transparente Farbe ist erforderlich, um transparente Bilder anzuzeigen. Alle Vorkommen dieser Farbe eines Bildes wird mit der Hintergrundfarbe stattdessen gezeichnet.  Es gibt keine Mischung von Hintergrund- und Vordergrundfarben Bildern.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCOutlookBarTabCtrl-Klasse](../../mfc/reference/cmfcoutlookbartabctrl-class.md)
