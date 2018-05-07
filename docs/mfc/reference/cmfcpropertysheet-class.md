---
title: CMFCPropertySheet-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b61adc98f6b6e84f5e2ef10f88ae41720e2fbf9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
|`CMFCPropertySheet::GetThisClass`|Durch das Framework verwendet wird, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol)|Initialisiert das Erscheinungsbild des aktuellen Eigenschaftsblatt-Steuerelements.|  
|[CMFCPropertySheet::OnActivatePage](#onactivatepage)|Wird durch das Framework aufgerufen, wenn eine Eigenschaftsseite aktiviert wird.|  
|[CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader)|Wird durch das Framework aufgerufen, um einen benutzerdefinierten Eigenschaftsseitenheader zu zeichnen.|  
|`CMFCPropertySheet::OnInitDialog`|Behandelt die [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) Nachricht. (Überschreibt [CPropertySheet:: OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|  
|[CMFCPropertySheet::OnRemoveTreePage](#onremovetreepage)|Wird durch das Framework aufgerufen, um eine Eigenschaftsseite aus einem Struktursteuerelement zu entfernen.|  
|`CMFCPropertySheet::PreTranslateMessage`|Übersetzt fenstermeldungen, bevor sie an verteilt wurden die [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktionen. (Überschreibt `CPropertySheet::PreTranslateMessage`.)|  
|[CMFCPropertySheet::RemoveCategory](#removecategory)|Entfernt einen Knoten aus dem Struktursteuerelement.|  
|[CMFCPropertySheet::RemovePage](#removepage)|Entfernt eine Eigenschaftenseite aus dem Eigenschaftenblatt.|  
|[CMFCPropertySheet::SetIconsList](#seticonslist)|Gibt die Liste der Bilder an, die in der Navigationssteuerung des Outlook-Bereichs verwendet werden.|  
|[CMFCPropertySheet:: Setlook](#setlook)|Gibt das Erscheinungsbild des Eigenschaftsblatts an.|  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse `CMFCPropertySheet` stellt Eigenschaftsblätter dar, auch als „Dialogfelder im Registerformat“ bezeichnet. Die `CMFCPropertySheet`-Klasse kann eine Eigenschaftsseite in einer Vielzahl von Möglichkeiten anzeigen.  
  
 Führen Sie die folgenden Schritte aus, um die `CMFCPropertySheet`-Klasse in Ihrer Anwendung zu verwenden:  
  
1.  Leiten Sie eine Klasse aus der `CMFCPropertySheet`-Klasse ab, und benennen Sie die Klasse, beispielsweise als „CMyPropertySheet“.  
  
2.  Erstellen einer [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md) Objekt für jede Eigenschaftsseite auf.  
  
3.  Rufen Sie die [CMFCPropertySheet:: Setlook](#setlook) Methode im CMyPropertySheet-Konstruktor. Ein Parameter dieser Methode gibt an, dass die Eigenschaftsseiten entweder als Registerkarten oben oder links im Eigenschaftsblatt oder als Registerkarten im Stile eines Microsoft OneNote-Eigenschaftsblatts oder als Schaltflächen auf einem Microsoft Outlook-Symbolleistensteuerelement oder als Knoten in einem Struktursteuerelement oder als eine Liste von Elementen auf der linken Seite des Eigenschaftsblatt angezeigt werden sollen.  
  
4.  Wenn Sie ein Eigenschaftsblatt im Stile einer Microsoft Outlook-Symbolleiste erstellen, rufen Sie die [CMFCPropertySheet::SetIconsList](#seticonslist) Methode, um eine Bildliste zusammen mit den Eigenschaftenseiten zuzuordnen.  
  
5.  Rufen Sie die [CMFCPropertySheet:: addPage](#addpage) Methode für jede Eigenschaftsseite auf.  
  
6.  Erstellen Sie ein `CMFCPropertySheet`-Steuerelement, und rufen Sie dessen `DoModal`-Methode auf.  
  
## <a name="illustrations"></a>Abbildungen  
 In der folgenden Abbildung wird ein Eigenschaftsblatt gezeigt, das im Stile einer eingebetteten Microsoft Outlook-Symbolleiste vorliegt. Die Outlook-Symbolleiste wird auf der linken Seite des Eigenschaftenfensters angezeigt.  
  
 ![CMFCPropertySheet-Farbsteuerelemente](../../mfc/reference/media/cmfcpropertysheet_color.png "Cmfcpropertysheet_color")  
  
 Die folgende Abbildung zeigt ein Eigenschaftenblatt, der enthält einem [CMFCPropertyGridCtrl Klasse](../../mfc/reference/cmfcpropertygridctrl-class.md) Objekt. Bei diesem Objekt handelt es sich um ein Eigenschaftsblatt im Stile eines Eigenschaftsblatts für allgemeine Standardsteuerelemente.  
  
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
 [in] `pPage`  
 Ein Zeiger auf ein Page-Objekt. Dieser Parameter darf nicht sein `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode fügt die angegebene Eigenschaftenseite als Registerkarte ganz rechts im Eigenschaftenblatt. Aus diesem Grund verwenden Sie diese Methode zum Hinzufügen von Seiten in der Reihenfolge von links nach rechts.  
  
 Wenn das Eigenschaftenblatt im Stil von Microsoft Outlook ist, zeigt das Framework eine Liste der Navigationsschaltflächen auf der linken Seite des Eigenschaftsblatt an. Nachdem Sie diese Methode auf eine Eigenschaftenseite hinzufügt, werden der Liste eine entsprechende Schaltfläche hinzugefügt. Klicken Sie auf die entsprechende Schaltfläche, um eine Eigenschaftsseite anzuzeigen. Weitere Informationen zu Stilen von Eigenschaftenblättern finden Sie unter [CMFCPropertySheet:: Setlook](#setlook).  
  
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
 [in] `pCategory`  
 Zeiger auf einen übergeordneten Strukturknoten oder `NULL` Knoten der obersten Ebene die angegebene Seite zugeordnet werden soll. Rufen Sie die [CMFCPropertySheet::AddTreeCategory](#addtreecategory) Methode zum Abrufen der this-Zeiger.  
  
 [in] `pPage`  
 Ein Zeiger auf eine Eigenschaft Page-Objekt.  
  
 [in] `nIconNum`  
 Nullbasierte Index des eines Symbols oder-1 zurück, wenn kein Symbol verwendet wird. Das Symbol wird neben der Eigenschaftenseite des Strukturansicht-Steuerelement angezeigt, wenn die Seite nicht ausgewählt ist. Der Standardwert ist -1.  
  
 [in] `nSelIconNum`  
 Nullbasierte Index des eines Symbols oder-1 zurück, wenn kein Symbol verwendet wird. Das Symbol wird neben der Eigenschaftenseite des Strukturansicht-Steuerelement angezeigt, wenn die Seite aktiviert ist. Der Standardwert ist -1.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode fügt einer Eigenschaftenseite als Endknoten eines Struktursteuerelements hinzu. Um eine Eigenschaftsseite hinzuzufügen, erstellen eine `CMFCPropertySheet` -Objekt, rufen Sie die [CMFCPropertySheet:: Setlook](#setlook) Methode mit der `look` Parameter festgelegt wird, um `CMFCPropertySheet::PropSheetLook_Tree`, und verwenden Sie diese Methode, um die Eigenschaftsseite "hinzuzufügen.  
  
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
 [in] `lpszLabel`  
 Der Name des Knotens.  
  
 [in] `nIconNum`  
 Nullbasierte Index des eines Symbols oder-1 zurück, wenn kein Symbol verwendet wird. Das Symbol wird neben der Eigenschaftenseite des Strukturansicht-Steuerelement angezeigt, wenn die Seite nicht ausgewählt ist. Der Standardwert ist -1.  
  
 [in] `nSelectedIconNum`  
 Nullbasierte Index des eines Symbols oder-1 zurück, wenn kein Symbol verwendet wird. Das Symbol wird neben der Eigenschaftenseite des Strukturansicht-Steuerelement angezeigt, wenn die Seite aktiviert ist. Der Standardwert ist -1.  
  
 [in] `pParentCategory`  
 Zeiger auf einen übergeordneten Strukturknoten oder `NULL` Knoten der obersten Ebene die angegebene Seite zugeordnet werden soll. Legen Sie diesen Parameter mit dem [CMFCPropertySheet::AddTreeCategory](#addtreecategory) Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den neuen Knoten in der Strukturansicht.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, einen neuen Knoten, der auch als Kategorie bezeichnet wird, die Strukturansicht-Steuerelement hinzufügen. Um einen Knoten hinzuzufügen, erstellen eine `CMFCPropertySheet` -Objekt, rufen Sie die [CMFCPropertySheet:: Setlook](#setlook) Methode mit der `look` Parametersatz auf `CMFCPropertySheet::PropSheetLook_Tree`, und verwenden Sie diese Methode zum Hinzufügen des Knotens.  
  
 Verwenden Sie bei nachfolgenden Aufrufen den Rückgabewert dieser Methode [CMFCPropertySheet::AddPageToTree](#addpagetotree) und [CMFCPropertySheet::AddTreeCategory](#addtreecategory).  
  
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
 [in] `pszCaption`  
 Eine Zeichenfolge, die Beschriftung des Eigenschaftsblatts enthält. Nicht mit `NULL`.  
  
 [in] `nIDCaption`  
 Eine Ressourcen-ID, die Beschriftung des Eigenschaftsblatts enthält.  
  
 [in] `pParentWnd`  
 Zeiger auf das übergeordnete Fenster im Eigenschaftsblatt oder `NULL` ist das übergeordnete Fenster das Hauptfenster der Anwendung. Der Standardwert ist `NULL`.  
  
 [in] `iSelectPage`  
 Der nullbasierte Index der oberen Seite. Der Standardwert ist 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie die Parameter für die [CPropertySheet::CPropertySheet](../../mfc/reference/cpropertysheet-class.md#cpropertysheet) Konstruktor.  
  
##  <a name="enablepageheader"></a>  CMFCPropertySheet::EnablePageHeader  
 Reserviert oben auf jeder Seite Platz, um einen benutzerdefinierten Header zu zeichnen.  
  
```  
void EnablePageHeader(int nHeaderHeight);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nHeaderHeight`  
 Die Höhe des Headers, in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie den Wert von der `nHeaderHeight` Parameter um einen benutzerdefinierten Header zu zeichnen außer Kraft setzen die [CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader) Methode.  
  
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
 Einer der Enumerationswerte, der die Darstellung des Eigenschaftsblatts angibt. Eine Liste der möglichen Werte, finden Sie in der Enumerationstabelle im Abschnitt "Hinweise" der [CMFCPropertySheet:: Setlook](#setlook).  
  
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
 Eine interne Registerkarten-Steuerelementobjekt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können ein Eigenschaftenblatt festlegen, damit es in verschiedenen Formaten, z. B. ein Strukturansicht-Steuerelement, eine Liste der Navigationsschaltflächen oder einen Satz von Seiten im Registerformat angezeigt.  
  
 Bevor Sie diese Methode aufrufen, rufen die [CMFCPropertySheet:: Setlook](#setlook) Methode, um die Darstellung der Eigenschaftsblatt-Steuerelement festlegen. Rufen Sie anschließend die [CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol) Methode, um das interne Registerkarten-Steuerelement-Objekt zu initialisieren. Verwenden Sie diese Methode zum Abrufen von Registerkarten-Steuerelementobjekt, und verwenden Sie dieses Objekt zum Arbeiten mit den Registerkarten auf der Eigenschaftsseite auf.  
  
 Diese Methode bestätigt im Debugmodus, wenn die Eigenschaftsblatt-Steuerelement nicht festgelegt ist, im Microsoft OneNote-Format angezeigt werden.  
  
##  <a name="initnavigationcontrol"></a>  CMFCPropertySheet::InitNavigationControl  
 Initialisiert das Erscheinungsbild des aktuellen Eigenschaftsblatt-Steuerelements.  
  
```  
virtual CWnd* InitNavigationControl();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Fenster des dem Eigenschaftsblatt-Steuerelements.  
  
### <a name="remarks"></a>Hinweise  
 Ein Eigenschaftsblatt-Steuerelement kann in mehrere unterschiedliche Formulare, z. B. einen Satz von Seiten im Registerformat, ein Strukturansicht-Steuerelement oder eine Liste der Navigationsschaltflächen angezeigt werden. Verwenden der [CMFCPropertySheet:: Setlook](#setlook) Methode, um die Darstellung der dem Eigenschaftsblatt-Steuerelements festzulegen.  
  
##  <a name="onactivatepage"></a>  CMFCPropertySheet::OnActivatePage  
 Wird durch das Framework aufgerufen, wenn eine Eigenschaftsseite aktiviert wird.  
  
```  
virtual void OnActivatePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pPage`  
 Ein Zeiger auf eine Eigenschaft Page-Objekt, das die enabled-Eigenschaftenseite darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird sichergestellt, dass diese Methode, dass die enabled-Eigenschaftenseite einen Bildlauf angezeigt wird. Wenn das Format des aktuellen Eigenschaftsblatts einer Microsoft Outlook-Bereichs enthält, legt diese Methode die entsprechende Schaltfläche "Outlook" aktiviert werden.  
  
##  <a name="ondrawpageheader"></a>  CMFCPropertySheet::OnDrawPageHeader  
 Wird aufgerufen, durch das Framework den Header für eine benutzerdefinierte Eigenschaftenseite gezeichnet werden soll.  
  
```  
virtual void OnDrawPageHeader(
    CDC* pDC,  
    int nPage,  
    CRect rectHeader);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext.  
  
 [in] `nPage`  
 Die nullbasierte Eigenschaft Seitenzahl.  
  
 [in] `rectHeader`  
 Ein umschließendes Rechteck, das angibt, wo Sie die Header zu zeichnen.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird diese Methode keine Aktion ausgeführt. Wenn Sie diese Methode überschreiben, rufen Sie die [CMFCPropertySheet::EnablePageHeader](#enablepageheader) -Methode auf, bevor das Framework diese Methode ruft.  
  
##  <a name="onremovetreepage"></a>  CMFCPropertySheet::OnRemoveTreePage  
 Wird durch das Framework aufgerufen, um eine Eigenschaftsseite aus einem Struktursteuerelement zu entfernen.  
  
```  
virtual BOOL OnRemoveTreePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pPage`  
 Ein Zeiger auf eine Eigenschaft Page-Objekt, das So entfernen Sie die Eigenschaftenseite darstellt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
##  <a name="removecategory"></a>  CMFCPropertySheet::RemoveCategory  
 Entfernt einen Knoten aus dem Struktursteuerelement.  
  
```  
void RemoveCategory(CMFCPropertySheetCategoryInfo* pCategory);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pCategory`  
 Ein Zeiger auf eine Kategorie (Knoten) entfernt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode zum Entfernen von Knoten, die auch als Kategorie aus einem Struktursteuerelement bezeichnet wird. Verwenden der [CMFCPropertySheet::AddTreeCategory](#addtreecategory) Methode zum Hinzufügen eines Knotens zu einem Strukturansicht-Steuerelement.  
  
##  <a name="removepage"></a>  CMFCPropertySheet::RemovePage  
 Entfernt eine Eigenschaftenseite aus dem Eigenschaftenblatt.  
  
```  
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pPage`  
 Ein Zeiger auf die Eigenschaft Page-Objekt, das So entfernen Sie die Eigenschaftenseite darstellt. Nicht mit `NULL`.  
  
 [in] `nPage`  
 Nullbasierte Index des zu entfernenden Seite.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode entfernt die angegebene Eigenschaftenseite und dessen zugeordnete Fenster zerstört. Die Eigenschaftenseite Objekt, mit der `pPage` Parameter gibt erst zerstört, nachdem die [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) Fenster geschlossen wird.  
  
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
 [in] `uiImageListResID`  
 Die Ressourcen-ID von einer Bildliste.  
  
 [in] `cx`  
 Die Breite in Pixel der Symbole in der Bildliste.  
  
 [in] `clrTransparent`  
 Die Farbe transparentes Bild. Die Teile des Bilds, die diese Farbe werden transparent sein. Der Standardwert ist das Farbe Magenta, RGB(255,0,255).  
  
 [in] `hIcons`  
 Ein Handle für eine vorhandene Bildliste.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei der ersten Methode überladen Syntax `TRUE` Wenn diese Methode erfolgreich, andernfalls ist `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Eigenschaftenblatt im Stil von Microsoft Outlook ist, zeigt das Framework eine Liste der Navigationsschaltflächen das Bereichssteuerelement Outlook auf der linken Seite des Eigenschaftsblatt aufgerufen. Verwenden Sie diese Methode, um die Bildliste von Outlook-Bereichssteuerelements zu verwendende festzulegen.  
  
 Weitere Informationen zu den Methoden, die diese Methode zu unterstützen, finden Sie unter [CImageList:: Create](../../mfc/reference/cimagelist-class.md#create) und [CImageList::Add](../../mfc/reference/cimagelist-class.md#add). Weitere Informationen zum Festlegen von des Stils eines Eigenschaftenblatts finden Sie unter [CMFCPropertySheet:: Setlook](#setlook).  
  
##  <a name="setlook"></a>  CMFCPropertySheet:: Setlook  
 Gibt das Erscheinungsbild des Eigenschaftsblatts an.  
  
```  
void SetLook(
    PropSheetLook look,  
    int nNavControlWidth=100);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `look`  
 Einer der Enumerationswerte, der die Darstellung des Eigenschaftsblatts angibt. Ist das Standardformat für ein Eigenschaftenblatt `CMFCPropertySheet::PropSheetLook_Tabs`. Weitere Informationen finden Sie in der Tabelle im Abschnitt "Hinweise" dieses Themas.  
  
 [in] `nNavControlWidth`  
 Die Breite des Steuerelements Navigationsleiste in Pixel. Der Standardwert ist 100.  
  
### <a name="remarks"></a>Hinweise  
 Um ein Eigenschaftenblatt in einem Format der Standardnummer anzuzeigen, rufen Sie diese Methode vor dem Erstellen des Fensters für Eigenschaftenblatt.  
  
 Die folgende Tabelle enthält die Enumerationswerte, der in angegeben werden, können die `look` Parameter.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`CMFCPropertySheet::PropSheetLook_Tabs`|(Standard) Zeigt eine Registerkarte für jede Eigenschaftsseite auf. Registerkarten am oberen Rand der Eigenschaftenseite angezeigt werden und werden gestapelt, wenn es weitere Registerkarten sind als in einer einzelnen Zeile passen.|  
|`CMFCPropertySheet::PropSheetLook_OutlookBar`|Zeigt eine Liste der Navigationsschaltflächen im Stil von Microsoft Outlook-Leiste auf der linken Seite des Eigenschaftsblatt an. Jede Schaltfläche in der Liste entspricht einer Eigenschaftenseite. Das Framework zeigt Bildlaufpfeile an, wenn weitere Schaltflächen als in der Liste den sichtbaren Bereich passt.|  
|`CMFCPropertySheet::PropSheetLook_Tree`|Zeigt eine Strukturansicht-Steuerelements auf der linken Seite des Eigenschaftsblatt an. Jeder über- oder untergeordneten Knoten des Strukturansicht-Steuerelements entspricht einer Eigenschaftenseite. Vom Framework angezeigt Bildlaufpfeile auf, wenn weitere Knoten als in den sichtbaren Bereich des Strukturansicht-Steuerelements passen vorhanden sind.|  
|`CMFCPropertySheet::PropSheetLook_OneNoteTabs`|Zeigt eine Registerkarte im Stile eines Microsoft OneNote für jede Eigenschaftsseite auf. Das Framework Registerkarten am oberen Rand der Eigenschaftenseite angezeigt. dabei Bildlaufpfeile treten mehrere Registerkarten als werden in einer einzelnen Zeile passen.|  
|`CMFCPropertySheet::PropSheetLook_List`|Zeigt eine Liste auf der linken Seite des Eigenschaftsblatt an. Jedes Listenelement entspricht einer Eigenschaftenseite. Das Framework zeigt Bildlaufpfeile aus, wenn es weitere Listenelemente gibt als in der Liste den sichtbaren Bereich passt.|  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyPage-Klasse](../../mfc/reference/cmfcpropertypage-class.md)   
 [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)
