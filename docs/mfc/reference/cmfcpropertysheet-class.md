---
title: Cmfcpropertysheet-Klasse
ms.date: 11/19/2018
f1_keywords:
- CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet::CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet::AddPage
- AFXPROPERTYSHEET/CMFCPropertySheet::AddPageToTree
- AFXPROPERTYSHEET/CMFCPropertySheet::AddTreeCategory
- AFXPROPERTYSHEET/CMFCPropertySheet::EnablePageHeader
- AFXPROPERTYSHEET/CMFCPropertySheet::GetHeaderHeight
- AFXPROPERTYSHEET/CMFCPropertySheet::GetLook
- AFXPROPERTYSHEET/CMFCPropertySheet::GetNavBarWidth
- AFXPROPERTYSHEET/CMFCPropertySheet::GetTab
- AFXPROPERTYSHEET/CMFCPropertySheet::InitNavigationControl
- AFXPROPERTYSHEET/CMFCPropertySheet::OnActivatePage
- AFXPROPERTYSHEET/CMFCPropertySheet::OnDrawPageHeader
- AFXPROPERTYSHEET/CMFCPropertySheet::OnRemoveTreePage
- AFXPROPERTYSHEET/CMFCPropertySheet::RemoveCategory
- AFXPROPERTYSHEET/CMFCPropertySheet::RemovePage
- AFXPROPERTYSHEET/CMFCPropertySheet::SetIconsList
- AFXPROPERTYSHEET/CMFCPropertySheet::SetLook
helpviewer_keywords:
- CMFCPropertySheet [MFC], CMFCPropertySheet
- CMFCPropertySheet [MFC], AddPage
- CMFCPropertySheet [MFC], AddPageToTree
- CMFCPropertySheet [MFC], AddTreeCategory
- CMFCPropertySheet [MFC], EnablePageHeader
- CMFCPropertySheet [MFC], GetHeaderHeight
- CMFCPropertySheet [MFC], GetLook
- CMFCPropertySheet [MFC], GetNavBarWidth
- CMFCPropertySheet [MFC], GetTab
- CMFCPropertySheet [MFC], InitNavigationControl
- CMFCPropertySheet [MFC], OnActivatePage
- CMFCPropertySheet [MFC], OnDrawPageHeader
- CMFCPropertySheet [MFC], OnRemoveTreePage
- CMFCPropertySheet [MFC], RemoveCategory
- CMFCPropertySheet [MFC], RemovePage
- CMFCPropertySheet [MFC], SetIconsList
- CMFCPropertySheet [MFC], SetLook
ms.assetid: 01d93573-9698-440f-a6a4-5bebbee879dc
ms.openlocfilehash: f7c9d2b472a443d8bf556d0b12dfe202ea8607a1
ms.sourcegitcommit: 389c559918d9bfaf303d262ee5430d787a662e92
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "69505046"
---
# <a name="cmfcpropertysheet-class"></a>Cmfcpropertysheet-Klasse

Die Klasse `CMFCPropertySheet` unterstützt ein Eigenschaftenblatt, in dem jede Eigenschaftenseite durch eine Seitenregisterkarte, eine Symbolleisten-Schaltfläche, einen Strukturansichtsknoten oder ein Listenelement angegeben wird.

## <a name="syntax"></a>Syntax

```
class CMFCPropertySheet : public CPropertySheet
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[Cmfcpropertysheet:: cmfcpropertysheet](#cmfcpropertysheet)|Erstellt ein `CMFCPropertySheet`-Objekt.|
|`CMFCPropertySheet::~CMFCPropertySheet`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCPropertySheet::AddPage](#addpage)|Fügt dem Eigenschaftsblatt eine Seite hinzu.|
|[CMFCPropertySheet::AddPageToTree](#addpagetotree)|Fügt dem Struktursteuerelement eine neue Eigenschaftsseite hinzu.|
|[CMFCPropertySheet::AddTreeCategory](#addtreecategory)|Fügt dem Struktursteuerelement einen neuen Knoten hinzu.|
|[CMFCPropertySheet::EnablePageHeader](#enablepageheader)|Reserviert oben auf jeder Seite Platz, um einen benutzerdefinierten Header zu zeichnen.|
|[CMFCPropertySheet::GetHeaderHeight](#getheaderheight)|Ruft die Höhe des aktuellen Headers ab.|
|[CMFCPropertySheet::GetLook](#getlook)|Ruft einen Enumerationswert ab, der das Erscheinungsbild des aktuellen Eigenschaftsblatts angibt.|
|[CMFCPropertySheet::GetNavBarWidth](#getnavbarwidth)|Ruft die Breite der Navigationsleiste in Pixel ab.|
|[CMFCPropertySheet::GetTab](#gettab)|Ruft das interne Registerkarten-Steuerelementobjekt ab, das das aktuelle Eigenschaftsblatt-Steuerelement unterstützt.|
|`CMFCPropertySheet::GetThisClass`|Wird vom Framework verwendet, um einen Zeiger auf das [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|
|[CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol)|Initialisiert das Erscheinungsbild des aktuellen Eigenschaftsblatt-Steuerelements.|
|[CMFCPropertySheet::OnActivatePage](#onactivatepage)|Wird durch das Framework aufgerufen, wenn eine Eigenschaftsseite aktiviert wird.|
|[CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader)|Wird durch das Framework aufgerufen, um einen benutzerdefinierten Eigenschaftsseitenheader zu zeichnen.|
|`CMFCPropertySheet::OnInitDialog`|Verarbeitet die [WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog) -Meldung. (Überschreibt [CPropertySheet:: OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|
|[CMFCPropertySheet::OnRemoveTreePage](#onremovetreepage)|Wird durch das Framework aufgerufen, um eine Eigenschaftsseite aus einem Struktursteuerelement zu entfernen.|
|`CMFCPropertySheet::PreTranslateMessage`|Übersetzt Fenster Meldungen, bevor diese an die Windows-Funktionen [translatemess](/windows/win32/api/winuser/nf-winuser-translatemessage) und [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) gesendet werden. (Überschreibt `CPropertySheet::PreTranslateMessage`.)|
|[CMFCPropertySheet::RemoveCategory](#removecategory)|Entfernt einen Knoten aus dem Struktursteuerelement.|
|[Cmfcpropertysheet:: RemovePage](#removepage)|Entfernt eine Eigenschaftenseite aus dem Eigenschaftenblatt.|
|[CMFCPropertySheet::SetIconsList](#seticonslist)|Gibt die Liste der Bilder an, die in der Navigationssteuerung des Outlook-Bereichs verwendet werden.|
|[CMFCPropertySheet::SetLook](#setlook)|Gibt das Erscheinungsbild des Eigenschaftsblatts an.|

## <a name="remarks"></a>Hinweise

Die Klasse `CMFCPropertySheet` stellt Eigenschaftsblätter dar, auch als „Dialogfelder im Registerformat“ bezeichnet. Die `CMFCPropertySheet`-Klasse kann eine Eigenschaftsseite in einer Vielzahl von Möglichkeiten anzeigen.

Führen Sie die folgenden Schritte aus, um die `CMFCPropertySheet`-Klasse in Ihrer Anwendung zu verwenden:

1. Leiten Sie eine Klasse aus der `CMFCPropertySheet`-Klasse ab, und benennen Sie die Klasse, beispielsweise als „CMyPropertySheet“.

1. Erstellen Sie ein [cmfcpropertypage](../../mfc/reference/cmfcpropertypage-class.md) -Objekt für jede Eigenschaften Seite.

1. Aufrufen der [cmfcpropertysheet:: setlook](#setlook) -Methode im cmypropertysheet-Konstruktor. Ein Parameter dieser Methode gibt an, dass die Eigenschaftsseiten entweder als Registerkarten oben oder links im Eigenschaftsblatt oder als Registerkarten im Stile eines Microsoft OneNote-Eigenschaftsblatts oder als Schaltflächen auf einem Microsoft Outlook-Symbolleistensteuerelement oder als Knoten in einem Gesamtstruktursteuerelement oder als eine Liste von Elementen auf der linken Seite des Eigenschaftsblatt angezeigt werden sollen.

1. Wenn Sie ein Eigenschaften Blatt im Stil einer Microsoft Outlook-Symbolleiste erstellen, rufen Sie die [cmfcpropertysheet:: settikonslist](#seticonslist) -Methode auf, um eine Bildliste zusammen mit den Eigenschaften Seiten zuzuordnen.

1. Aufrufen der [cmfcpropertysheet:: addPage](#addpage) -Methode für jede Eigenschaften Seite.

1. Erstellen Sie ein `CMFCPropertySheet`-Steuerelement, und rufen Sie dessen `DoModal`-Methode auf.

## <a name="illustrations"></a>Abbildungen

In der folgenden Abbildung wird ein Eigenschaftsblatt gezeigt, das im Stile einer eingebetteten Microsoft Outlook-Symbolleiste vorliegt. Die Outlook-Symbolleiste wird auf der linken Seite des Eigenschaftenfensters angezeigt.

![Cmfcpropertysheet-Farb Steuerelemente](../../mfc/reference/media/cmfcpropertysheet_color.png "Cmfcpropertysheet-Farb Steuerelemente")

In der folgenden Abbildung ist ein Eigenschaften Blatt dargestellt, das ein [cmfcpropertygridctrl-Klassen](../../mfc/reference/cmfcpropertygridctrl-class.md) Objekt enthält. Bei diesem Objekt handelt es sich um ein Eigenschaftsblatt im Stile eines Eigenschaftsblatts für allgemeine Standardsteuerelemente.

![Cmfcpropertysheet-Listen-und-Eigenschaften Steuerelemente](../../mfc/reference/media/cmfcpropertysheet_list.png "Cmfcpropertysheet-Listen-und-Eigenschaften Steuerelemente")

In der folgenden Abbildung wird ein Eigenschaftsblatt gezeigt, das im Stile eines Struktursteuerelements vorliegt.

![Eigenschafts](../../mfc/reference/media/proptree.png "Eigenschafts")

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

[CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxpropertysheet. h

##  <a name="addpage"></a>Cmfcpropertysheet:: addPage

Fügt dem Eigenschaftsblatt eine Seite hinzu.

```
void AddPage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parameter

*pPage*<br/>
in Zeiger auf ein Seiten Objekt. Dieser Parameter darf nicht NULL sein.

### <a name="remarks"></a>Hinweise

Diese Methode fügt die angegebene Eigenschaften Seite als die Registerkarte am weitesten rechts im Eigenschaften Blatt hinzu. Verwenden Sie daher diese Methode, um Seiten in der Reihenfolge von links nach rechts hinzuzufügen.

Wenn sich das Eigenschaften Blatt im Stil von Microsoft Outlook befindet, zeigt das Framework links neben dem Eigenschaften Blatt eine Liste mit Navigations Schaltflächen an. Nachdem diese Methode eine Eigenschaften Seite hinzugefügt hat, wird der Liste eine entsprechende Schaltfläche hinzugefügt. Klicken Sie auf die entsprechende Schaltfläche, um eine Eigenschaften Seite anzuzeigen. Weitere Informationen zu Stilen von Eigenschaften Blättern finden Sie unter [cmfcpropertysheet:: setlook](#setlook).

##  <a name="addpagetotree"></a>Cmfcpropertysheet:: addpagetretree

Fügt dem Struktursteuerelement eine neue Eigenschaftsseite hinzu.

```
void AddPageToTree(
    CMFCPropertySheetCategoryInfo* pCategory,
    CMFCPropertyPage* pPage,
    int nIconNum=-1,
    int nSelIconNum=-1);
```

### <a name="parameters"></a>Parameter

*pCategory*<br/>
in Zeiger auf einen übergeordneten Struktur Knoten oder NULL, um die angegebene Seite dem Knoten der obersten Ebene zuzuordnen. Rufen Sie die [cmfcpropertysheet:: addtreecategory](#addtreecategory) -Methode auf, um diesen Zeiger zu erhalten.

*pPage*<br/>
in Zeiger auf ein Eigenschaften Seiten Objekt.

*nIconNum*<br/>
in NULL basierter Index eines Symbols oder-1, wenn kein Symbol verwendet wird. Wenn die Seite nicht ausgewählt ist, wird das Symbol neben der Eigenschaften Seite des Struktur Steuer Elements angezeigt. Der Standardwert ist -1.

*nSelIconNum*<br/>
in NULL basierter Index eines Symbols oder-1, wenn kein Symbol verwendet wird. Wenn die Seite ausgewählt ist, wird das Symbol neben der Eigenschaften Seite des Struktur Steuer Elements angezeigt. Der Standardwert ist -1.

### <a name="remarks"></a>Hinweise

Diese Methode fügt eine Eigenschaften Seite als Blatt eines Struktur Steuer Elements hinzu. Um eine Eigenschaften Seite hinzuzufügen, erstellen `CMFCPropertySheet` Sie ein-Objekt, rufen Sie die [cmfcpropertysheet:: setlook](#setlook) -Methode mit `CMFCPropertySheet::PropSheetLook_Tree`dem auf festgelegten *Look* -Parameter auf, und verwenden Sie dann diese Methode, um die Eigenschaften Seite hinzuzufügen.

##  <a name="addtreecategory"></a>Cmfcpropertysheet:: addtreecategory

Fügt dem Struktursteuerelement einen neuen Knoten hinzu.

```
CMFCPropertySheetCategoryInfo* AddTreeCategory(
    LPCTSTR lpszLabel,
    int nIconNum=-1,
    int nSelectedIconNum=-1,
    const CMFCPropertySheetCategoryInfo* pParentCategory=NULL);
```

### <a name="parameters"></a>Parameter

*lpszLabel*<br/>
in Der Name des Knotens.

*nIconNum*<br/>
in NULL basierter Index eines Symbols oder-1, wenn kein Symbol verwendet wird. Wenn die Seite nicht ausgewählt ist, wird das Symbol neben der Eigenschaften Seite des Struktur Steuer Elements angezeigt. Der Standardwert ist -1.

*nSelectedIconNum*<br/>
in NULL basierter Index eines Symbols oder-1, wenn kein Symbol verwendet wird. Wenn die Seite ausgewählt ist, wird das Symbol neben der Eigenschaften Seite des Struktur Steuer Elements angezeigt. Der Standardwert ist -1.

*pParentCategory*<br/>
in Zeiger auf einen übergeordneten Struktur Knoten oder NULL, um die angegebene Seite dem Knoten der obersten Ebene zuzuordnen. Legen Sie diesen Parameter mit der [cmfcpropertysheet:: addtreecategory](#addtreecategory) -Methode fest.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den neuen Knoten im Struktur Steuerelement.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um dem Struktur Steuerelement einen neuen Knoten hinzuzufügen, der auch als Kategorie bezeichnet wird. Wenn Sie einen Knoten hinzufügen möchten `CMFCPropertySheet` , erstellen Sie ein-Objekt, rufen Sie die [cmfcpropertysheet:: setlook](#setlook) - `CMFCPropertySheet::PropSheetLook_Tree`Methode mit dem auf festgelegten *Look* -Parameter auf, und fügen Sie dann den Knoten mithilfe dieser Methode hinzu.

Verwenden Sie den Rückgabewert dieser Methode in nachfolgenden Aufrufen von [cmfcpropertysheet:: addpagedetree](#addpagetotree) und [cmfcpropertysheet:: addtreecategory](#addtreecategory).

##  <a name="cmfcpropertysheet"></a>Cmfcpropertysheet:: cmfcpropertysheet

Erstellt ein `CMFCPropertySheet`-Objekt.

```
CMFCPropertySheet(
    UINT nIDCaption,
    CWnd* pParentWnd=NULL,
    UINT iSelectPage=0);

CMFCPropertySheet(
    LPCTSTR pszCaption,
    CWnd* pParentWnd=NULL,
    UINT iSelectPage=0);
```

### <a name="parameters"></a>Parameter

*pszCaption*<br/>
in Eine Zeichenfolge, die die Beschriftung des Eigenschaften Blatts enthält. Darf nicht NULL sein.

*nIDCaption*<br/>
in Eine Ressourcen-ID, die die Beschriftung des Eigenschaften Blatts enthält.

*pParentWnd*<br/>
in Ein Zeiger auf das übergeordnete Fenster des Eigenschaften Blatts oder NULL, wenn das übergeordnete Fenster das Hauptfenster der Anwendung ist. Der Standardwert ist NULL.

*iSelectPage*<br/>
in Der null basierte Index der oberen Eigenschaften Seite. Der Standardwert ist 0.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie in den Parametern für den [CPropertySheet:: CPropertySheet](../../mfc/reference/cpropertysheet-class.md#cpropertysheet) -Konstruktor.

##  <a name="enablepageheader"></a>Cmfcpropertysheet:: enablepageheader

Reserviert oben auf jeder Seite Platz, um einen benutzerdefinierten Header zu zeichnen.

```
void EnablePageHeader(int nHeaderHeight);
```

### <a name="parameters"></a>Parameter

*nHeaderHeight*<br/>
in Die Höhe des Headers in Pixel.

### <a name="remarks"></a>Hinweise

Um den Wert des *nheaderheight* -Parameters zum Zeichnen eines benutzerdefinierten Headers zu verwenden, überschreiben Sie die [cmfcpropertysheet:: ondrawpageheader](#ondrawpageheader) -Methode.

##  <a name="getheaderheight"></a>Cmfcpropertysheet:: gespiaderheight

Ruft die Höhe des aktuellen Headers ab.

```
int GetHeaderHeight() const;
```

### <a name="return-value"></a>Rückgabewert

Die Höhe des Headers in Pixel.

### <a name="remarks"></a>Hinweise

Sie sollten die [cmfcpropertysheet:: enablepageheader](#enablepageheader) -Methode aufrufen, bevor Sie diese Methode aufrufen.

##  <a name="getlook"></a>Cmfcpropertysheet:: getlook

Ruft einen Enumerationswert ab, der das Erscheinungsbild des aktuellen Eigenschaftsblatts angibt.

```
PropSheetLook GetLook() const;
```

### <a name="return-value"></a>Rückgabewert

Einer der Enumerationswerte, der die Darstellung des Eigenschaften Blatts angibt. Eine Liste möglicher Werte finden Sie in der Tabelle "Enumeration" im Abschnitt "Hinweise" unter [cmfcpropertysheet:: setlook](#setlook).

##  <a name="getnavbarwidth"></a>Cmfcpropertysheet:: getnavbarwidth

Ruft die Breite der Navigationsleiste ab.

```
int GetNavBarWidth() const;
```

### <a name="return-value"></a>Rückgabewert

Die Breite der Navigationsleiste in Pixel.

##  <a name="gettab"></a>Cmfcpropertysheet:: getTab

Ruft das interne Registerkarten-Steuerelementobjekt ab, das das aktuelle Eigenschaftsblatt-Steuerelement unterstützt.

```
CMFCTabCtrl& GetTab() const;
```

### <a name="return-value"></a>Rückgabewert

Ein internes Registerkarten-Steuerelement Objekt.

### <a name="remarks"></a>Hinweise

Sie können ein Eigenschaften Blatt so festlegen, dass es in unterschiedlichen Stilen angezeigt wird, z. b. in einem Struktur Steuerelement, einer Liste von Navigations Schaltflächen oder einem Satz von Seiten im Registerkarten Format.

Bevor Sie diese Methode aufrufen, müssen Sie die [cmfcpropertysheet:: setlook](#setlook) -Methode aufrufen, um die Darstellung des Eigenschaften Blatt-Steuer Elements festzulegen. Anschließend können Sie die [cmfcpropertysheet:: initnavigationcontrol](#initnavigationcontrol) -Methode aufrufen, um das interne Registerkarten-Steuerelement Objekt zu initialisieren. Verwenden Sie diese Methode, um das Registerkarten-Steuerelement Objekt abzurufen, und verwenden Sie dieses Objekt, um mit den Registerkarten auf dem Eigenschaften Blatt zu arbeiten.

Diese Methode bestätigt im Debugmodus, wenn das Eigenschaften Blatt-Steuerelement nicht so festgelegt ist, dass es im Stil von Microsoft OneNote angezeigt wird.

##  <a name="initnavigationcontrol"></a>Cmfcpropertysheet:: initnavigationcontrol

Initialisiert das Erscheinungsbild des aktuellen Eigenschaftsblatt-Steuerelements.

```
virtual CWnd* InitNavigationControl();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das Fenster des Eigenschaften Blatt-Steuer Elements.

### <a name="remarks"></a>Hinweise

Ein Eigenschaften Blatt-Steuerelement kann in verschiedenen Formularen angezeigt werden, z. b. in einem Satz von Seiten im Registerkarten Format, einem Struktur Steuerelement oder einer Liste von Navigations Schaltflächen. Verwenden Sie die [cmfcpropertysheet:: setlook](#setlook) -Methode, um die Darstellung des Eigenschaften Blatt-Steuer Elements anzugeben.

##  <a name="onactivatepage"></a>Cmfcpropertysheet:: onactivatepage

Wird durch das Framework aufgerufen, wenn eine Eigenschaftsseite aktiviert wird.

```
virtual void OnActivatePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parameter

*pPage*<br/>
in Zeiger auf ein Eigenschaften Seiten Objekt, das die aktivierte Eigenschaften Seite darstellt.

### <a name="remarks"></a>Hinweise

Standardmäßig wird durch diese Methode sichergestellt, dass die aktivierte Eigenschaften Seite in die Ansicht gescrollt wird. Wenn der Stil des aktuellen Eigenschaften Blatts einen Microsoft Outlook-Bereich enthält, legt diese Methode die entsprechende Outlook-Schaltfläche auf den aktivierten Zustand fest.

##  <a name="ondrawpageheader"></a>Cmfcpropertysheet:: ondrawpageheader

Wird von Framework aufgerufen, um den-Header für eine benutzerdefinierte Eigenschaften Seite zu zeichnen.

```
virtual void OnDrawPageHeader(
    CDC* pDC,
    int nPage,
    CRect rectHeader);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Zeiger auf einen Gerätekontext.

*nPage*<br/>
in Die null basierte Eigenschaften Seitenzahl.

*rectHeader*<br/>
in Ein Begrenzungs Rechteck, das angibt, wo der Header gezeichnet werden soll.

### <a name="remarks"></a>Hinweise

Standardmäßig führt diese Methode keine Aktion aus. Wenn Sie diese Methode überschreiben, rufen Sie die [cmfcpropertysheet:: enablepageheader](#enablepageheader) -Methode auf, bevor das Framework diese Methode aufruft.

##  <a name="onremovetreepage"></a>Cmfcpropertysheet:: onremovetreepage

Wird durch das Framework aufgerufen, um eine Eigenschaftsseite aus einem Struktursteuerelement zu entfernen.

```
virtual BOOL OnRemoveTreePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parameter

*pPage*<br/>
in Zeiger auf ein Eigenschaften Seiten Objekt, das die zu entfern gende Eigenschaften Seite darstellt.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn diese Methode erfolgreich ist. andernfalls false.

##  <a name="removecategory"></a>Cmfcpropertysheet:: removecategory

Entfernt einen Knoten aus dem Struktursteuerelement.

```
void RemoveCategory(CMFCPropertySheetCategoryInfo* pCategory);
```

### <a name="parameters"></a>Parameter

*pCategory*<br/>
in Zeiger auf eine Kategorie (Knoten), die entfernt werden soll.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um einen Knoten, der auch als Kategorie bezeichnet wird, aus einem Struktur Steuerelement zu entfernen. Verwenden Sie die [cmfcpropertysheet:: addtreecategory](#addtreecategory) -Methode, um einen Knoten zu einem Struktur Steuerelement hinzuzufügen.

##  <a name="removepage"></a>Cmfcpropertysheet:: RemovePage

Entfernt eine Eigenschaftenseite aus dem Eigenschaftenblatt.

```
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```

### <a name="parameters"></a>Parameter

*pPage*<br/>
in Ein Zeiger auf ein Eigenschaften Seiten Objekt, das die zu entfern gende Eigenschaften Seite darstellt. Darf nicht NULL sein.

*nPage*<br/>
in Der null basierte Index der zu entfernenden Seite.

### <a name="remarks"></a>Hinweise

Diese Methode entfernt die angegebene Eigenschaften Seite und zerstört das zugehörige Fenster. Das Eigenschaften Seiten Objekt, das der *pPage* -Parameter angibt, wird erst zerstört, wenn das [cmfcpropertysheet](../../mfc/reference/cmfcpropertysheet-class.md) -Fenster geschlossen wird.

##  <a name="seticonslist"></a>Cmfcpropertysheet:: "".

Gibt die Liste der Bilder an, die in der Navigationssteuerung des Outlook-Bereichs verwendet werden.

```
BOOL SetIconsList(
    UINT uiImageListResID,
    int cx,
    COLORREF clrTransparent=RGB(255, 0, 255));
void SetIconsList(HIMAGELIST hIcons);
```

### <a name="parameters"></a>Parameter

*uiImageListResID*<br/>
in Die Ressourcen-ID einer Bildliste.

*verschoben*<br/>
in Die Breite von Symbolen in der Bildliste in Pixel.

*clrTransparent*<br/>
in Die transparente Bildfarbe. Die Teile des Bilds, die diese Farbe aufweisen, sind transparent. Der Standardwert ist die Farbe Magenta, RGB (255, RGB).

*hIcons*<br/>
in Ein Handle für eine vorhandene Bildliste.

### <a name="return-value"></a>Rückgabewert

In der ersten Methoden Überladungs Syntax true, wenn diese Methode erfolgreich ist. andernfalls false.

### <a name="remarks"></a>Hinweise

Wenn sich das Eigenschaften Blatt im Stil von Microsoft Outlook befindet, zeigt das Framework links neben dem Eigenschaften Blatt eine Liste mit Navigations Schaltflächen an, die als Outlook-Bereich-Steuerelement bezeichnet werden. Verwenden Sie diese Methode, um die Bildliste festzulegen, die vom Outlook-Bereich-Steuerelement verwendet werden soll.

Weitere Informationen zu den Methoden, die diese Methode unterstützen, finden Sie unter [CImageList:: Create](../../mfc/reference/cimagelist-class.md#create) und [CImageList:: Add](../../mfc/reference/cimagelist-class.md#add). Weitere Informationen zum Festlegen des Stils eines Eigenschaften Blatts finden Sie unter [cmfcpropertysheet:: setlook](#setlook).

##  <a name="setlook"></a>Cmfcpropertysheet:: setlook

Gibt das Erscheinungsbild des Eigenschaftsblatts an.

```
void SetLook(
    PropSheetLook look,
    int nNavControlWidth=100);
```

### <a name="parameters"></a>Parameter

*look*<br/>
in Einer der Enumerationswerte, der die Darstellung des Eigenschaften Blatts angibt. Der Standardstil für ein Eigenschaften Blatt ist `CMFCPropertySheet::PropSheetLook_Tabs`. Weitere Informationen finden Sie in der Tabelle im Abschnitt "Hinweise" in diesem Thema.

*nNavControlWidth*<br/>
in Die Breite des Navigations Steuer Elements in Pixel. Der Standardwert ist 100.

### <a name="remarks"></a>Hinweise

Wenn Sie ein Eigenschaften Blatt in einem anderen Format als dem Standard anzeigen möchten, rufen Sie diese Methode auf, bevor Sie das Eigenschaften Blatt Fenster erstellen.

In der folgenden Tabelle sind die Enumerationswerte aufgelistet, die im *Look* -Parameter angegeben werden können.

|Wert|Beschreibung|
|-----------|-----------------|
|`CMFCPropertySheet::PropSheetLook_Tabs`|Vorgegebene Zeigt eine Registerkarte für jede Eigenschaften Seite an. Registerkarten werden am oberen Rand des Eigenschaften Blatts angezeigt und gestapelt, wenn mehr Registerkarten vorhanden sind, als in eine einzelne Zeile passen.|
|`CMFCPropertySheet::PropSheetLook_OutlookBar`|Zeigt eine Liste der Navigations Schaltflächen im Stil der Microsoft Outlook-Leiste auf der linken Seite des Eigenschaften Blatts an. Jede Schaltfläche in der Liste entspricht einer Eigenschaften Seite. Im Framework werden scrollpfeile angezeigt, wenn mehr Schaltflächen vorhanden sind, als in den sichtbaren Bereich der Liste passen.|
|`CMFCPropertySheet::PropSheetLook_Tree`|Zeigt ein Struktur Steuerelement auf der linken Seite des Eigenschaften Blatts an. Jeder übergeordnete oder untergeordnete Knoten des Struktur Steuer Elements entspricht einer Eigenschaften Seite. Im Framework werden scrollpfeile angezeigt, wenn mehr Knoten vorhanden sind, als in den sichtbaren Bereich des Struktur Steuer Elements passen.|
|`CMFCPropertySheet::PropSheetLook_OneNoteTabs`|Zeigt eine Registerkarte im Stil von Microsoft OneNote für jede Eigenschaften Seite an. Das Framework zeigt Registerkarten am oberen Rand des Eigenschaften Blatts und scrollpfeile an, wenn mehr Registerkarten vorhanden sind, als in eine einzelne Zeile passen.|
|`CMFCPropertySheet::PropSheetLook_List`|Zeigt eine Liste auf der linken Seite des Eigenschaften Blatts an. Jedes Listenelement entspricht einer Eigenschaften Seite. Im Framework werden scrollpfeile angezeigt, wenn mehr Listenelemente vorhanden sind, als in den sichtbaren Bereich der Liste passen.|

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyPage-Klasse](../../mfc/reference/cmfcpropertypage-class.md)<br/>
[CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)
