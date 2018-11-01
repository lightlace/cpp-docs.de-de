---
title: CMFCPropertySheet-Klasse
ms.date: 11/04/2016
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
ms.openlocfilehash: 8e643474d577c606e80f5f34c6166a59753610f2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531611"
---
# <a name="cmfcpropertysheet-class"></a>CMFCPropertySheet-Klasse

Die Klasse `CMFCPropertySheet` unterstützt ein Eigenschaftenblatt, in dem jede Eigenschaftenseite durch eine Seitenregisterkarte, eine Symbolleisten-Schaltfläche, einen Strukturansichtsknoten oder ein Listenelement angegeben wird.

## <a name="syntax"></a>Syntax

```
class CMFCPropertySheet : public CPropertySheet
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCPropertySheet::CMFCPropertySheet](#cmfcpropertysheet)|Erstellt ein `CMFCPropertySheet`-Objekt.|
|`CMFCPropertySheet::~CMFCPropertySheet`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCPropertySheet:: addPage](#addpage)|Fügt dem Eigenschaftsblatt eine Seite hinzu.|
|[CMFCPropertySheet::AddPageToTree](#addpagetotree)|Fügt dem Struktursteuerelement eine neue Eigenschaftsseite hinzu.|
|[CMFCPropertySheet::AddTreeCategory](#addtreecategory)|Fügt dem Struktursteuerelement einen neuen Knoten hinzu.|
|[CMFCPropertySheet::EnablePageHeader](#enablepageheader)|Reserviert oben auf jeder Seite Platz, um einen benutzerdefinierten Header zu zeichnen.|
|[CMFCPropertySheet::GetHeaderHeight](#getheaderheight)|Ruft die Höhe des aktuellen Headers ab.|
|[CMFCPropertySheet::GetLook](#getlook)|Ruft einen Enumerationswert ab, der das Erscheinungsbild des aktuellen Eigenschaftsblatts angibt.|
|[CMFCPropertySheet::GetNavBarWidth](#getnavbarwidth)|Ruft die Breite der Navigationsleiste in Pixel ab.|
|[CMFCPropertySheet::GetTab](#gettab)|Ruft das interne Registerkarten-Steuerelementobjekt ab, das das aktuelle Eigenschaftsblatt-Steuerelement unterstützt.|
|`CMFCPropertySheet::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|
|[CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol)|Initialisiert das Erscheinungsbild des aktuellen Eigenschaftsblatt-Steuerelements.|
|[CMFCPropertySheet::OnActivatePage](#onactivatepage)|Wird durch das Framework aufgerufen, wenn eine Eigenschaftsseite aktiviert wird.|
|[CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader)|Wird durch das Framework aufgerufen, um einen benutzerdefinierten Eigenschaftsseitenheader zu zeichnen.|
|`CMFCPropertySheet::OnInitDialog`|Verarbeitet die [WM_INITDIALOG](/windows/desktop/dlgbox/wm-initdialog) Nachricht. (Überschreibt [CPropertySheet:: OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|
|[CMFCPropertySheet::OnRemoveTreePage](#onremovetreepage)|Wird durch das Framework aufgerufen, um eine Eigenschaftsseite aus einem Struktursteuerelement zu entfernen.|
|`CMFCPropertySheet::PreTranslateMessage`|Übersetzt fenstermeldungen, bevor sie um weitergeleitet werden die [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) und [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows-Funktionen. (Überschreibt `CPropertySheet::PreTranslateMessage`.)|
|[CMFCPropertySheet::RemoveCategory](#removecategory)|Entfernt einen Knoten aus dem Struktursteuerelement.|
|[CMFCPropertySheet::RemovePage](#removepage)|Entfernt eine Eigenschaftenseite aus dem Eigenschaftenblatt.|
|[CMFCPropertySheet::SetIconsList](#seticonslist)|Gibt die Liste der Bilder an, die in der Navigationssteuerung des Outlook-Bereichs verwendet werden.|
|[CMFCPropertySheet:: Setlook](#setlook)|Gibt das Erscheinungsbild des Eigenschaftsblatts an.|

## <a name="remarks"></a>Hinweise

Die Klasse `CMFCPropertySheet` stellt Eigenschaftsblätter dar, auch als „Dialogfelder im Registerformat“ bezeichnet. Die `CMFCPropertySheet`-Klasse kann eine Eigenschaftsseite in einer Vielzahl von Möglichkeiten anzeigen.

Führen Sie die folgenden Schritte aus, um die `CMFCPropertySheet`-Klasse in Ihrer Anwendung zu verwenden:

1. Leiten Sie eine Klasse aus der `CMFCPropertySheet`-Klasse ab, und benennen Sie die Klasse, beispielsweise als „CMyPropertySheet“.

1. Erstellen einer [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md) Objekt für jede Eigenschaftsseite auf.

1. Rufen Sie die [CMFCPropertySheet:: Setlook](#setlook) Methode im CMyPropertySheet-Konstruktor. Ein Parameter dieser Methode gibt an, dass die Eigenschaftsseiten entweder als Registerkarten oben oder links im Eigenschaftsblatt oder als Registerkarten im Stile eines Microsoft OneNote-Eigenschaftsblatts oder als Schaltflächen auf einem Microsoft Outlook-Symbolleistensteuerelement oder als Knoten in einem Struktursteuerelement oder als eine Liste von Elementen auf der linken Seite des Eigenschaftsblatt angezeigt werden sollen.

1. Wenn Sie ein Eigenschaftenblatt im Stile einer Microsoft Outlook-Symbolleiste erstellen, rufen die [CMFCPropertySheet::SetIconsList](#seticonslist) Methode, um eine Bildliste zusammen mit den Eigenschaftsseiten zu verknüpfen.

1. Rufen Sie die [CMFCPropertySheet:: addPage](#addpage) -Methode für jede Eigenschaftsseite auf.

1. Erstellen Sie ein `CMFCPropertySheet`-Steuerelement, und rufen Sie dessen `DoModal`-Methode auf.

## <a name="illustrations"></a>Abbildungen

In der folgenden Abbildung wird ein Eigenschaftsblatt gezeigt, das im Stile einer eingebetteten Microsoft Outlook-Symbolleiste vorliegt. Die Outlook-Symbolleiste wird auf der linken Seite des Eigenschaftenfensters angezeigt.

![CMFCPropertySheet-Farbsteuerelemente](../../mfc/reference/media/cmfcpropertysheet_color.png "Cmfcpropertysheet_color")

Die folgende Abbildung zeigt ein Eigenschaftenblatt an, die enthält eine [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md) Objekt. Bei diesem Objekt handelt es sich um ein Eigenschaftsblatt im Stile eines Eigenschaftsblatts für allgemeine Standardsteuerelemente.

![CMFCPropertySheet-Listen- und Farbsteuerelemente](../../mfc/reference/media/cmfcpropertysheet_list.png "Cmfcpropertysheet_list")

In der folgenden Abbildung wird ein Eigenschaftsblatt gezeigt, das im Stile eines Struktursteuerelements vorliegt.

![Eigenschaftenstruktur](../../mfc/reference/media/proptree.png "Proptree")

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

[CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxpropertysheet.h

##  <a name="addpage"></a>  CMFCPropertySheet:: addPage

Fügt dem Eigenschaftsblatt eine Seite hinzu.

```
void AddPage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parameter

*P_seite*<br/>
[in] Zeiger auf ein Page-Objekt. Dieser Parameter darf nicht NULL sein.

### <a name="remarks"></a>Hinweise

Diese Methode fügt die angegebene Eigenschaftenseite als die Registerkarte ganz rechts im Eigenschaftenfenster Eigenschaft an. Aus diesem Grund verwenden Sie diese Methode, um Seiten in links-nach-rechts-Reihenfolge hinzuzufügen.

Wenn das Eigenschaftenblatt im Stil von Microsoft Outlook ist, zeigt das Framework eine Liste der Navigationsschaltflächen auf der linken Seite des Eigenschaftenblatts an. Nachdem diese Methode auf einer Eigenschaftenseite hinzugefügt werden, werden der Liste eine entsprechende Schaltfläche hinzugefügt. Um eine Eigenschaftenseite anzuzeigen, klicken Sie auf die entsprechende Schaltfläche. Weitere Informationen zu Stilen der Eigenschaftenblätter, finden Sie unter [CMFCPropertySheet:: Setlook](#setlook).

##  <a name="addpagetotree"></a>  CMFCPropertySheet::AddPageToTree

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
[in] Zeiger auf einen übergeordneten Strukturknoten oder NULL, Knoten der obersten Ebene die angegebene Seite zugeordnet werden soll. Rufen Sie die [CMFCPropertySheet::AddTreeCategory](#addtreecategory) Methode zum Abrufen der this-Zeiger.

*P_seite*<br/>
[in] Zeiger auf ein Eigenschaft-Page-Objekt.

*nIconNum*<br/>
[in] Nullbasierte Index, der ein Symbol oder -1, wenn kein Symbol verwendet wird. Das Symbol wird neben der Eigenschaftenseite des Strukturansicht-Steuerelement angezeigt, wenn die Seite nicht aktiviert ist. Der Standardwert ist -1.

*nSelIconNum*<br/>
[in] Nullbasierte Index, der ein Symbol oder -1, wenn kein Symbol verwendet wird. Das Symbol wird neben der Eigenschaftenseite des Strukturansicht-Steuerelement angezeigt, wenn die Seite aktiviert ist. Der Standardwert ist -1.

### <a name="remarks"></a>Hinweise

Diese Methode fügt eine Eigenschaftenseite als ein Blatt ein Strukturansicht-Steuerelement hinzu. Erstellen Sie zum Hinzufügen einer Eigenschaftenseite ein `CMFCPropertySheet` Objekt, rufen Sie die [CMFCPropertySheet:: Setlook](#setlook) -Methode mit der *suchen* Parametersatz zu `CMFCPropertySheet::PropSheetLook_Tree`, und klicken Sie dann diese Methode verwenden, um die Eigenschaftenseite hinzufügen .

##  <a name="addtreecategory"></a>  CMFCPropertySheet::AddTreeCategory

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
[in] Der Name des Knotens.

*nIconNum*<br/>
[in] Nullbasierte Index, der ein Symbol oder -1, wenn kein Symbol verwendet wird. Das Symbol wird neben der Eigenschaftenseite des Strukturansicht-Steuerelement angezeigt, wenn die Seite nicht aktiviert ist. Der Standardwert ist -1.

*nSelectedIconNum*<br/>
[in] Nullbasierte Index, der ein Symbol oder -1, wenn kein Symbol verwendet wird. Das Symbol wird neben der Eigenschaftenseite des Strukturansicht-Steuerelement angezeigt, wenn die Seite aktiviert ist. Der Standardwert ist -1.

*pParentCategory*<br/>
[in] Zeiger auf einen übergeordneten Strukturknoten oder NULL, Knoten der obersten Ebene die angegebene Seite zugeordnet werden soll. Legen Sie diesen Parameter mit dem [CMFCPropertySheet::AddTreeCategory](#addtreecategory) Methode.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den neuen Knoten in der Strukturansicht.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode einen neuen Knoten, die auch als Kategorie bezeichnet wird, das Strukturansicht-Steuerelement hinzufügen. Um einen Knoten hinzuzufügen, erstellen eine `CMFCPropertySheet` Objekt, rufen Sie die [CMFCPropertySheet:: Setlook](#setlook) -Methode mit der *suchen* Parametersatz zu `CMFCPropertySheet::PropSheetLook_Tree`, und klicken Sie dann diese Methode verwenden, um den Knoten hinzuzufügen.

Den Rückgabewert dieser Methode verwenden, bei nachfolgenden Aufrufen von [CMFCPropertySheet::AddPageToTree](#addpagetotree) und [CMFCPropertySheet::AddTreeCategory](#addtreecategory).

##  <a name="cmfcpropertysheet"></a>  CMFCPropertySheet::CMFCPropertySheet

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
[in] Eine Zeichenfolge, die Beschriftung des Eigenschaftsblatts enthält. Darf nicht NULL sein.

*nIDCaption*<br/>
[in] Ein Ressourcen-ID, die Beschriftung des Eigenschaftsblatts enthält.

*pParentWnd*<br/>
[in] Zeiger auf das übergeordnete Fenster des Eigenschaftenblatt oder NULL, wenn das übergeordnete Fenster, das Hauptfenster der Anwendung ist. Der Standardwert ist NULL.

*iSelectPage*<br/>
[in] Der nullbasierte Index der Seite Top-Eigenschaft. Der Standardwert ist 0.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie die Parameter für die [CPropertySheet::CPropertySheet](../../mfc/reference/cpropertysheet-class.md#cpropertysheet) Konstruktor.

##  <a name="enablepageheader"></a>  CMFCPropertySheet::EnablePageHeader

Reserviert oben auf jeder Seite Platz, um einen benutzerdefinierten Header zu zeichnen.

```
void EnablePageHeader(int nHeaderHeight);
```

### <a name="parameters"></a>Parameter

*nHeaderHeight*<br/>
[in] Die Höhe des Headers, in Pixel.

### <a name="remarks"></a>Hinweise

Verwenden Sie den Wert des der *nHeaderHeight* überschreiben Sie Parameter, um einen benutzerdefinierten Header, zeichnen die [CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader) Methode.

##  <a name="getheaderheight"></a>  CMFCPropertySheet::GetHeaderHeight

Ruft die Höhe des aktuellen Headers ab.

```
int GetHeaderHeight() const;
```

### <a name="return-value"></a>Rückgabewert

Die Höhe des Headers, in Pixel.

### <a name="remarks"></a>Hinweise

Rufen Sie die [CMFCPropertySheet::EnablePageHeader](#enablepageheader) -Methode auf, bevor Sie diese Methode aufrufen.

##  <a name="getlook"></a>  CMFCPropertySheet::GetLook

Ruft einen Enumerationswert ab, der das Erscheinungsbild des aktuellen Eigenschaftsblatts angibt.

```
PropSheetLook GetLook() const;
```

### <a name="return-value"></a>Rückgabewert

Einer der Enumerationswerte, der die Darstellung des Eigenschaftsblatts angibt. Eine Liste der möglichen Werte, finden Sie in der Enumerationstabelle im Abschnitt "Hinweise" des [CMFCPropertySheet:: Setlook](#setlook).

##  <a name="getnavbarwidth"></a>  CMFCPropertySheet::GetNavBarWidth

Ruft die Breite der Navigationsleiste ab.

```
int GetNavBarWidth() const;
```

### <a name="return-value"></a>Rückgabewert

Die Breite der Navigationsleiste in Pixel.

##  <a name="gettab"></a>  CMFCPropertySheet::GetTab

Ruft das interne Registerkarten-Steuerelementobjekt ab, das das aktuelle Eigenschaftsblatt-Steuerelement unterstützt.

```
CMFCTabCtrl& GetTab() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Objekt des interne Registerkarten-Steuerelement.

### <a name="remarks"></a>Hinweise

Sie können ein Eigenschaftenblatt festlegen, sodass es in verschiedenen Formaten, z. B. ein Strukturansicht-Steuerelement, eine Liste der Navigationsschaltflächen oder einen Satz von Seiten im Registerformat angezeigt wird.

Bevor Sie diese Methode aufrufen, rufen die [CMFCPropertySheet:: Setlook](#setlook) Methode, um die Darstellung der Eigenschaftsblatt-Steuerelements festlegen. Rufen Sie dann die [CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol) Methode, um das interne Registerkarten-Steuerelement-Objekt zu initialisieren. Verwenden Sie diese Methode zum Abrufen von Registerkarten-Steuerelementobjekt, und klicken Sie dann dieses Objekt verwenden, arbeiten Sie mit den Registerkarten auf der Eigenschaftsseite auf.

Diese Methode bestätigt im Debugmodus ausgeführt, wenn die Eigenschaftsblatt-Steuerelement nicht festgelegt ist, im Stil von Microsoft OneNote angezeigt werden.

##  <a name="initnavigationcontrol"></a>  CMFCPropertySheet::InitNavigationControl

Initialisiert das Erscheinungsbild des aktuellen Eigenschaftsblatt-Steuerelements.

```
virtual CWnd* InitNavigationControl();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das Fenster des dem Eigenschaftsblatt-Steuerelements.

### <a name="remarks"></a>Hinweise

Ein Eigenschaftsblatt-Steuerelement kann in mehrere unterschiedliche Formulare, z. B. eine Reihe von Seiten im Registerformat, ein Strukturansicht-Steuerelement oder eine Liste der Navigationsschaltflächen erscheinen. Verwenden der [CMFCPropertySheet:: Setlook](#setlook) Methode, um die Darstellung der Eigenschaftsblatt-Steuerelements angeben.

##  <a name="onactivatepage"></a>  CMFCPropertySheet::OnActivatePage

Wird durch das Framework aufgerufen, wenn eine Eigenschaftsseite aktiviert wird.

```
virtual void OnActivatePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parameter

*P_seite*<br/>
[in] Zeiger auf ein Eigenschaft-Page-Objekt, das die enabled-Eigenschaft darstellt.

### <a name="remarks"></a>Hinweise

Standardmäßig gewährleistet diese Methode an, dass die Seite für die enabled-Eigenschaft in die Ansicht gescrollt wird. Wenn das Format des aktuellen Eigenschaftsblatts einen Bereich von Microsoft Outlook enthält, legt diese Methode die entsprechende Schaltfläche "Outlook" aktiviert werden.

##  <a name="ondrawpageheader"></a>  CMFCPropertySheet::OnDrawPageHeader

Wird aufgerufen, durch das Framework die Header für eine benutzerdefinierte Eigenschaft-Seite zu zeichnen.

```
virtual void OnDrawPageHeader(
    CDC* pDC,
    int nPage,
    CRect rectHeader);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Zeiger auf einen Gerätekontext.

*. nSeite*<br/>
[in] Die nullbasierte Eigenschaft Seitenzahl.

*rectHeader*<br/>
[in] Ein umgebendes Rechteck, das angibt, wo Sie die Header zu zeichnen.

### <a name="remarks"></a>Hinweise

Standardmäßig führt diese Methode keine Aktion. Wenn Sie diese Methode überschreiben, rufen Sie die [CMFCPropertySheet::EnablePageHeader](#enablepageheader) -Methode auf, bevor das Framework diese Methode ruft.

##  <a name="onremovetreepage"></a>  CMFCPropertySheet::OnRemoveTreePage

Wird durch das Framework aufgerufen, um eine Eigenschaftsseite aus einem Struktursteuerelement zu entfernen.

```
virtual BOOL OnRemoveTreePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>Parameter

*P_seite*<br/>
[in] Zeiger auf ein Eigenschaft-Page-Objekt, das die zu entfernende Eigenschaftenseite darstellt.

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

##  <a name="removecategory"></a>  CMFCPropertySheet::RemoveCategory

Entfernt einen Knoten aus dem Struktursteuerelement.

```
void RemoveCategory(CMFCPropertySheetCategoryInfo* pCategory);
```

### <a name="parameters"></a>Parameter

*pCategory*<br/>
[in] Zeiger auf eine Kategorie (Knoten) entfernt.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode zum Entfernen eines Knotens, der auch als eine Kategorie aus ein Strukturansicht-Steuerelement bezeichnet wird. Verwenden der [CMFCPropertySheet::AddTreeCategory](#addtreecategory) Methode zum Hinzufügen eines Knotens zu einem Strukturansicht-Steuerelement.

##  <a name="removepage"></a>  CMFCPropertySheet::RemovePage

Entfernt eine Eigenschaftenseite aus dem Eigenschaftenblatt.

```
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```

### <a name="parameters"></a>Parameter

*P_seite*<br/>
[in] Zeiger auf die Eigenschaft-Page-Objekt, das die zu entfernende Eigenschaftenseite darstellt. Darf nicht NULL sein.

*. nSeite*<br/>
[in] Nullbasierte Index des zu entfernenden Seite.

### <a name="remarks"></a>Hinweise

Diese Methode entfernt die Seite für die angegebene Eigenschaft und ein zugehörigen Fenster zerstört. Die Eigenschaftsseite "-Objekt, das *P_seite* Parameter gibt an, wird nicht zerstört werden, bis der [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) Schließen des Fensters.

##  <a name="seticonslist"></a>  CMFCPropertySheet::SetIconsList

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
[in] Die Ressourcen-ID von einer Bildliste.

*CX*<br/>
[in] Die Breite der Symbole in der Bildliste in Pixel.

*clrTransparent*<br/>
[in] Die Farbe, transparentes Bild. Die Teile des Bilds an, die diese Farbe werden transparent sein. Der Standardwert ist das Farbe Magenta, RGB(255,0,255).

*hIcons*<br/>
[in] Ein Handle für eine vorhandene Image-Liste.

### <a name="return-value"></a>Rückgabewert

Überladen Sie bei der ersten Methode Syntax "true", wenn diese Methode erfolgreich ist; andernfalls "false".

### <a name="remarks"></a>Hinweise

Wenn das Eigenschaftenblatt im Stil von Microsoft Outlook ist, zeigt das Framework eine Liste mit den Navigationsschaltflächen, das Outlook-Steuerelement, auf der linken Seite des Eigenschaftenblatts aufgerufen. Verwenden Sie diese Methode zum Festlegen der Liste der Bilder, die von der Outlook-Steuerelement verwendet werden.

Weitere Informationen zu den Methoden, die diese Methode zu unterstützen, finden Sie unter [CImageList:: Create](../../mfc/reference/cimagelist-class.md#create) und [CImageList::Add](../../mfc/reference/cimagelist-class.md#add). Weitere Informationen dazu, wie Sie das Format für ein Eigenschaftenblatt festzulegen, finden Sie unter [CMFCPropertySheet:: Setlook](#setlook).

##  <a name="setlook"></a>  CMFCPropertySheet:: Setlook

Gibt das Erscheinungsbild des Eigenschaftsblatts an.

```
void SetLook(
    PropSheetLook look,
    int nNavControlWidth=100);
```

### <a name="parameters"></a>Parameter

*Suchen Sie*<br/>
[in] Einer der Enumerationswerte, der die Darstellung des Eigenschaftsblatts angibt. Ist das Standardformat für ein Eigenschaftenblatt `CMFCPropertySheet::PropSheetLook_Tabs`. Weitere Informationen finden Sie in der Tabelle im Abschnitt "Hinweise" dieses Themas.

*nNavControlWidth*<br/>
[in] Die Breite des Steuerelements Navigation in Pixel. Der Standardwert ist 100.

### <a name="remarks"></a>Hinweise

Um ein Eigenschaftenblatt in einem Stil als den Standardwert anzuzeigen, rufen Sie diese Methode auf, bevor Sie das Eigenschaftenfenster für die Tabelle erstellen.

Die folgende Tabelle enthält die Enumerationswerte, der in angegeben werden, können die *suchen* Parameter.

|Wert|Beschreibung|
|-----------|-----------------|
|`CMFCPropertySheet::PropSheetLook_Tabs`|(Standard) Zeigt eine Registerkarte für jede Eigenschaftsseite auf. Registerkarten am oberen Rand der Eigenschaftenblatt angezeigt werden und sind gestapelt werden weitere Registerkarten als in einer einzelnen Zeile passen.|
|`CMFCPropertySheet::PropSheetLook_OutlookBar`|Zeigt eine Liste mit den Navigationsschaltflächen, im Stil von Microsoft Outlook-Leiste auf der linken Seite des Eigenschaftenblatts an. Jede Schaltfläche in der Liste entspricht einer Eigenschaftenseite. Wenn sind weitere Schaltflächen als in den sichtbaren Bereich der Liste passt, zeigt das Framework Bildlaufpfeile auf.|
|`CMFCPropertySheet::PropSheetLook_Tree`|Zeigt eine Strukturansicht auf der linken Seite des Eigenschaftenblatts an. Jedes übergeordneten oder untergeordneten Knoten des Strukturansicht-Steuerelements entspricht auf einer Eigenschaftenseite. Wenn es mehr Knoten sind als in den sichtbaren Bereich des Strukturansicht-Steuerelements passen, zeigt das Framework Bildlaufpfeile auf.|
|`CMFCPropertySheet::PropSheetLook_OneNoteTabs`|Zeigt eine Registerkarte im Stil von Microsoft OneNote für jede Eigenschaftsseite auf. Das Framework Registerkarten oben auf der Eigenschaftenseite angezeigt und Bildlaufpfeile auf, wenn es weitere Registerkarten als werden werden in einer einzelnen Zeile passen.|
|`CMFCPropertySheet::PropSheetLook_List`|Zeigt eine Liste auf der linken Seite des Eigenschaftenblatts an. Jedes Listenelement entspricht einer Eigenschaftenseite. Wenn weitere Listenelemente enthält als in den sichtbaren Bereich der Liste passt, zeigt das Framework Bildlaufpfeilen.|

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyPage-Klasse](../../mfc/reference/cmfcpropertypage-class.md)<br/>
[CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)
