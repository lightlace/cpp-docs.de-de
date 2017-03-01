---
title: CMFCPropertySheet-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertySheet
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertySheet::PreTranslateMessage method
- CMFCPropertySheet::OnInitDialog method
- CMFCPropertySheet class
ms.assetid: 01d93573-9698-440f-a6a4-5bebbee879dc
caps.latest.revision: 35
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
ms.openlocfilehash: a157a0afa4542bc023ba4d7149e78a71bbd56e74
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpropertysheet-class"></a>CMFCPropertySheet-Klasse
Die Klasse `CMFCPropertySheet` unterstützt ein Eigenschaftenblatt, in dem jede Eigenschaftenseite durch eine Seitenregisterkarte, eine Symbolleisten-Schaltfläche, einen Strukturansichtsknoten oder ein Listenelement angegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCPropertySheet : public CPropertySheet  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCPropertySheet::CMFCPropertySheet](#cmfcpropertysheet)|Erstellt ein `CMFCPropertySheet`-Objekt.|  
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
|`CMFCPropertySheet::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
|[CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol)|Initialisiert das Erscheinungsbild des aktuellen Eigenschaftsblatt-Steuerelements.|  
|[CMFCPropertySheet::OnActivatePage](#onactivatepage)|Wird durch das Framework aufgerufen, wenn eine Eigenschaftsseite aktiviert wird.|  
|[CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader)|Wird durch das Framework aufgerufen, um einen benutzerdefinierten Eigenschaftsseitenheader zu zeichnen.|  
|`CMFCPropertySheet::OnInitDialog`|Behandelt das [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) Nachricht. (Überschreibt [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|  
|[CMFCPropertySheet::OnRemoveTreePage](#onremovetreepage)|Wird durch das Framework aufgerufen, um eine Eigenschaftsseite aus einem Struktursteuerelement zu entfernen.|  
|`CMFCPropertySheet::PreTranslateMessage`|Windows-Nachrichten übersetzt, bevor sie an verteilt sind die [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktionen. (Überschreibt `CPropertySheet::PreTranslateMessage`.)|  
|[CMFCPropertySheet::RemoveCategory](#removecategory)|Entfernt einen Knoten aus dem Struktursteuerelement.|  
|[CMFCPropertySheet::RemovePage](#removepage)|Entfernt eine Eigenschaftenseite aus dem Eigenschaftenblatt.|  
|[CMFCPropertySheet::SetIconsList](#seticonslist)|Gibt die Liste der Bilder an, die in der Navigationssteuerung des Outlook-Bereichs verwendet werden.|  
|[CMFCPropertySheet::SetLook](#setlook)|Gibt das Erscheinungsbild des Eigenschaftsblatts an.|  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse `CMFCPropertySheet` stellt Eigenschaftsblätter dar, auch als „Dialogfelder im Registerformat“ bezeichnet. Die `CMFCPropertySheet`-Klasse kann eine Eigenschaftsseite in einer Vielzahl von Möglichkeiten anzeigen.  
  
 Führen Sie die folgenden Schritte aus, um die `CMFCPropertySheet`-Klasse in Ihrer Anwendung zu verwenden:  
  
1.  Leiten Sie eine Klasse aus der `CMFCPropertySheet`-Klasse ab, und benennen Sie die Klasse, beispielsweise als „CMyPropertySheet“.  
  
2.  Erstellen einer [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md) -Objekt für die einzelnen Eigenschaftenseiten.  
  
3.  Rufen Sie die [CMFCPropertySheet::SetLook](#setlook) -Methode in der CMyPropertySheet-Konstruktor. Ein Parameter dieser Methode gibt an, dass die Eigenschaftsseiten entweder als Registerkarten oben oder links im Eigenschaftsblatt oder als Registerkarten im Stile eines Microsoft OneNote-Eigenschaftsblatts oder als Schaltflächen auf einem Microsoft Outlook-Symbolleistensteuerelement oder als Knoten in einem Struktursteuerelement oder als eine Liste von Elementen auf der linken Seite des Eigenschaftsblatt angezeigt werden sollen.  
  
4.  Wenn Sie ein Eigenschaftenblatt im Stil der Microsoft Outlook-Symbolleiste erstellen, rufen die [CMFCPropertySheet::SetIconsList](#seticonslist) Methode eine Bildliste zusammen mit den Eigenschaftenseiten zuordnen.  
  
5.  Rufen Sie die [CMFCPropertySheet::AddPage](#addpage) Methode für die einzelnen Eigenschaftenseiten.  
  
6.  Erstellen Sie ein `CMFCPropertySheet`-Steuerelement, und rufen Sie dessen `DoModal`-Methode auf.  
  
## <a name="illustrations"></a>Abbildungen  
 In der folgenden Abbildung wird ein Eigenschaftsblatt gezeigt, das im Stile einer eingebetteten Microsoft Outlook-Symbolleiste vorliegt. Die Outlook-Symbolleiste wird auf der linken Seite des Eigenschaftenfensters angezeigt.  
  
 ![CMFCPropertySheet-Farbsteuerelemente](../../mfc/reference/media/cmfcpropertysheet_color.png "Cmfcpropertysheet_color")  
  
 Die folgende Abbildung zeigt ein Eigenschaftenblatt, die enthält eine [CMFCPropertyGridCtrl Klasse](../../mfc/reference/cmfcpropertygridctrl-class.md) Objekt. Bei diesem Objekt handelt es sich um ein Eigenschaftsblatt im Stile eines Eigenschaftsblatts für allgemeine Standardsteuerelemente.  
  
 ![CMFCPropertySheet-Listen- und Farbsteuerelemente](../../mfc/reference/media/cmfcpropertysheet_list.png "Cmfcpropertysheet_list")  
  
 In der folgenden Abbildung wird ein Eigenschaftsblatt gezeigt, das im Stile eines Struktursteuerelements vorliegt.  
  
 ![Eigenschaftenstruktur](../../mfc/reference/media/proptree.png "Proptree")  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxpropertysheet.h  
  
##  <a name="a-nameaddpagea--cmfcpropertysheetaddpage"></a><a name="addpage"></a>CMFCPropertySheet::AddPage  
 Fügt dem Eigenschaftsblatt eine Seite hinzu.  
  
```  
void AddPage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pPage`  
 Ein Zeiger auf ein Page-Objekt. Dieser Parameter darf nicht `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode fügt die angegebene Eigenschaftenseite als Registerkarte ganz rechts im Eigenschaftenblatt. Daher verwenden Sie diese Methode zum Hinzufügen von Seiten in der Reihenfolge von links nach rechts.  
  
 Wenn das Eigenschaftenfenster im Stil von Microsoft Outlook ist, zeigt das Framework eine Liste der Navigationsschaltflächen auf der linken Seite der Eigenschaftenseite. Nachdem diese Methode eine Eigenschaftenseite hinzugefügt hat, werden der Liste eine Schaltfläche hinzugefügt. Klicken Sie auf die entsprechende Schaltfläche, um eine Eigenschaftenseite anzuzeigen. Weitere Informationen zu Stilen Eigenschaftenblätter finden Sie unter [CMFCPropertySheet::SetLook](#setlook).  
  
##  <a name="a-nameaddpagetotreea--cmfcpropertysheetaddpagetotree"></a><a name="addpagetotree"></a>CMFCPropertySheet::AddPageToTree  
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
 Zeiger auf einen übergeordneten Strukturknoten oder `NULL` Knoten der obersten Ebene die angegebene Seite zugeordnet. Rufen Sie die [CMFCPropertySheet::AddTreeCategory](#addtreecategory) Methode, um diesen Zeiger abzurufen.  
  
 [in] `pPage`  
 Ein Zeiger auf eine Eigenschaft Page-Objekt.  
  
 [in] `nIconNum`  
 Nullbasierte Index des eines Symbols oder -1, wenn kein Symbol verwendet wird. Das Symbol wird neben der Strukturansicht-Steuerelement-Eigenschaftenseite angezeigt, wenn die Seite nicht aktiviert ist. Der Standardwert ist -1.  
  
 [in] `nSelIconNum`  
 Nullbasierte Index des eines Symbols oder -1, wenn kein Symbol verwendet wird. Das Symbol wird neben der Strukturansicht-Steuerelement-Eigenschaftenseite angezeigt, wenn die Seite aktiviert ist. Der Standardwert ist -1.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode fügt eine Eigenschaftenseite als Blatt ein Strukturansicht-Steuerelement. Um eine Eigenschaft hinzuzufügen, erstellen eine `CMFCPropertySheet` Objekt, rufen Sie die [CMFCPropertySheet::SetLook](#setlook) -Methode mit der `look` Parametersatz zu `CMFCPropertySheet::PropSheetLook_Tree`, und klicken Sie dann diese Methode verwenden, um die Eigenschaftenseite hinzufügen.  
  
##  <a name="a-nameaddtreecategorya--cmfcpropertysheetaddtreecategory"></a><a name="addtreecategory"></a>CMFCPropertySheet::AddTreeCategory  
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
 Nullbasierte Index des eines Symbols oder -1, wenn kein Symbol verwendet wird. Das Symbol wird neben der Strukturansicht-Steuerelement-Eigenschaftenseite angezeigt, wenn die Seite nicht aktiviert ist. Der Standardwert ist -1.  
  
 [in] `nSelectedIconNum`  
 Nullbasierte Index des eines Symbols oder -1, wenn kein Symbol verwendet wird. Das Symbol wird neben der Strukturansicht-Steuerelement-Eigenschaftenseite angezeigt, wenn die Seite aktiviert ist. Der Standardwert ist -1.  
  
 [in] `pParentCategory`  
 Zeiger auf einen übergeordneten Strukturknoten oder `NULL` Knoten der obersten Ebene die angegebene Seite zugeordnet. Legen Sie diesen Parameter mit dem [CMFCPropertySheet::AddTreeCategory](#addtreecategory) Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den neuen Knoten in der Strukturansicht.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um einen neuen Knoten, der auch als Kategorie bezeichnet wird, zum Strukturansicht-Steuerelement hinzufügen. Um einen Knoten hinzuzufügen, erstellen Sie eine `CMFCPropertySheet` Objekt, rufen Sie die [CMFCPropertySheet::SetLook](#setlook) -Methode mit der `look` Parametersatz zu `CMFCPropertySheet::PropSheetLook_Tree`, und verwenden Sie diese Methode den Knoten hinzufügen.  
  
 Verwenden Sie den Rückgabewert dieser Methode bei nachfolgenden Aufrufen von [CMFCPropertySheet::AddPageToTree](#addpagetotree) und [CMFCPropertySheet::AddTreeCategory](#addtreecategory).  
  
##  <a name="a-namecmfcpropertysheeta--cmfcpropertysheetcmfcpropertysheet"></a><a name="cmfcpropertysheet"></a>CMFCPropertySheet::CMFCPropertySheet  
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
 Eine Zeichenfolge, die die Eigenschaftenblatt Beschriftung enthält. Nicht `NULL`.  
  
 [in] `nIDCaption`  
 Eine Ressourcen-ID, die die Eigenschaftenblatt Beschriftung enthält.  
  
 [in] `pParentWnd`  
 Zeiger auf das übergeordnete Fenster im Eigenschaftsfenster oder `NULL` , wenn das übergeordnete Fenster im Hauptfenster der Anwendung ist. Der Standardwert ist `NULL`.  
  
 [in] `iSelectPage`  
 Der nullbasierte Index der oberen Seite. Der Standardwert ist 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie die Parameter für die [CPropertySheet::CPropertySheet](../../mfc/reference/cpropertysheet-class.md#cpropertysheet) Konstruktor.  
  
##  <a name="a-nameenablepageheadera--cmfcpropertysheetenablepageheader"></a><a name="enablepageheader"></a>CMFCPropertySheet::EnablePageHeader  
 Reserviert oben auf jeder Seite Platz, um einen benutzerdefinierten Header zu zeichnen.  
  
```  
void EnablePageHeader(int nHeaderHeight);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nHeaderHeight`  
 Die Höhe des Headers, in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert von der `nHeaderHeight` überschreiben, Parameter, um einen benutzerdefinierten Header, zeichnen die [CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader) Methode.  
  
##  <a name="a-namegetheaderheighta--cmfcpropertysheetgetheaderheight"></a><a name="getheaderheight"></a>CMFCPropertySheet::GetHeaderHeight  
 Ruft die Höhe des aktuellen Headers ab.  
  
```  
int GetHeaderHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe des Headers, in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die [CMFCPropertySheet::EnablePageHeader](#enablepageheader) -Methode auf, bevor Sie diese Methode aufrufen.  
  
##  <a name="a-namegetlooka--cmfcpropertysheetgetlook"></a><a name="getlook"></a>CMFCPropertySheet::GetLook  
 Ruft einen Enumerationswert ab, der das Erscheinungsbild des aktuellen Eigenschaftsblatts angibt.  
  
```  
PropSheetLook GetLook() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der Enumerationswerte, der die Darstellung der Eigenschaftenseite. Eine Liste der möglichen Werte finden Sie unter der Enumerationstabelle im Abschnitt "Hinweise" des [CMFCPropertySheet::SetLook](#setlook).  
  
##  <a name="a-namegetnavbarwidtha--cmfcpropertysheetgetnavbarwidth"></a><a name="getnavbarwidth"></a>CMFCPropertySheet::GetNavBarWidth  
 Ruft die Breite der Navigationsleiste ab.  
  
```  
int GetNavBarWidth() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite der Navigationsleiste in Pixel.  
  
##  <a name="a-namegettaba--cmfcpropertysheetgettab"></a><a name="gettab"></a>CMFCPropertySheet::GetTab  
 Ruft das interne Registerkarten-Steuerelementobjekt ab, das das aktuelle Eigenschaftsblatt-Steuerelement unterstützt.  
  
```  
CMFCTabCtrl& GetTab() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Registerkarte intern Control-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können ein Eigenschaftenblatt festgelegt, sodass in unterschiedlichen Formaten, z. B. ein Strukturansicht-Steuerelement eine Liste der Navigationsschaltflächen oder eine Gruppe von Seiten im Registerformat angezeigt.  
  
 Bevor Sie diese Methode aufrufen, rufen Sie die [CMFCPropertySheet::SetLook](#setlook) Methode, um die Darstellung des Steuerelements Eigenschaftenblatt festlegen. Rufen Sie dann die [CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol) Methode, um die Registerkarte intern Control-Objekt zu initialisieren. Verwenden Sie diese Methode, auf die Registerkarte Control-Objekt abrufen und dann dieses Objekt verwenden, arbeiten Sie mit den Registerkarten auf dem Eigenschaftenblatt.  
  
 Diese Methode bestätigt im Debugmodus, wenn Stylesheet-Steuerelement die Eigenschaft nicht festgelegt ist, im Stil von Microsoft OneNote angezeigt werden.  
  
##  <a name="a-nameinitnavigationcontrola--cmfcpropertysheetinitnavigationcontrol"></a><a name="initnavigationcontrol"></a>CMFCPropertySheet::InitNavigationControl  
 Initialisiert das Erscheinungsbild des aktuellen Eigenschaftsblatt-Steuerelements.  
  
```  
virtual CWnd* InitNavigationControl();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Fenster des Steuerelements Eigenschaftenblatt.  
  
### <a name="remarks"></a>Hinweise  
 Ein Stylesheet-Steuerelement kann in verschiedenen Formularen, wie z. B. einen Satz von Seiten im Registerformat, ein Strukturansicht-Steuerelement oder eine Liste der Navigationsschaltflächen angezeigt werden. Verwenden der [CMFCPropertySheet::SetLook](#setlook) Methode, um die Darstellung des Steuerelements Eigenschaftenblatt anzugeben.  
  
##  <a name="a-nameonactivatepagea--cmfcpropertysheetonactivatepage"></a><a name="onactivatepage"></a>CMFCPropertySheet::OnActivatePage  
 Wird durch das Framework aufgerufen, wenn eine Eigenschaftsseite aktiviert wird.  
  
```  
virtual void OnActivatePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pPage`  
 Ein Zeiger auf eine Eigenschaft Page-Objekt, das die enabled-Eigenschaft darstellt.  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung gewährleistet diese Methode an, dass die Seite enabled-Eigenschaft ein Bildlauf durchgeführt wird. Enthält die Art des aktuellen Eigenschaftenblatt einen Bereich von Microsoft Outlook, legt diese Methode die entsprechende Outlook-Schaltfläche aktiviert werden.  
  
##  <a name="a-nameondrawpageheadera--cmfcpropertysheetondrawpageheader"></a><a name="ondrawpageheader"></a>CMFCPropertySheet::OnDrawPageHeader  
 Vom Framework aufgerufen wird den Header für eine benutzerdefinierte Eigenschaftenseite zu zeichnen.  
  
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
 Ein umgebendes Rechteck, das angibt, wo Sie das Zeichnen des Headers.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig bewirkt diese Methode nichts. Wenn Sie diese Methode überschreiben, rufen Sie die [CMFCPropertySheet::EnablePageHeader](#enablepageheader) -Methode auf, bevor das Framework diese Methode ruft.  
  
##  <a name="a-nameonremovetreepagea--cmfcpropertysheetonremovetreepage"></a><a name="onremovetreepage"></a>CMFCPropertySheet::OnRemoveTreePage  
 Wird durch das Framework aufgerufen, um eine Eigenschaftsseite aus einem Struktursteuerelement zu entfernen.  
  
```  
virtual BOOL OnRemoveTreePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pPage`  
 Ein Zeiger auf eine Eigenschaft Page-Objekt, das die Eigenschaftenseite entfernen darstellt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
##  <a name="a-nameremovecategorya--cmfcpropertysheetremovecategory"></a><a name="removecategory"></a>CMFCPropertySheet::RemoveCategory  
 Entfernt einen Knoten aus dem Struktursteuerelement.  
  
```  
void RemoveCategory(CMFCPropertySheetCategoryInfo* pCategory);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pCategory`  
 Ein Zeiger auf eine Kategorie (Knoten) entfernt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode zum Entfernen von Knoten, die auch als Kategorie aus einem Strukturansicht-Steuerelement bezeichnet wird. Verwenden der [CMFCPropertySheet::AddTreeCategory](#addtreecategory) -Methode zum Hinzufügen eines Knotens zu einem Strukturansicht-Steuerelement.  
  
##  <a name="a-nameremovepagea--cmfcpropertysheetremovepage"></a><a name="removepage"></a>CMFCPropertySheet::RemovePage  
 Entfernt eine Eigenschaftenseite aus dem Eigenschaftenblatt.  
  
```  
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pPage`  
 Ein Zeiger auf die Eigenschaft Page-Objekt, das die Eigenschaftenseite entfernen darstellt. Nicht `NULL`.  
  
 [in] `nPage`  
 Nullbasierte Index des zu entfernenden Seite.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode entfernt die angegebene Eigenschaftenseite und dessen zugeordnete Fenster zerstört. Die Eigenschaftenseite Objekt, das `pPage` Parameter gibt, wird nicht zerstört, bis der [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) Fenster wird geschlossen.  
  
##  <a name="a-nameseticonslista--cmfcpropertysheetseticonslist"></a><a name="seticonslist"></a>CMFCPropertySheet::SetIconsList  
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
 Die Ressourcen-ID einer Bildliste.  
  
 [in] `cx`  
 Die Breite der Symbole in der Bildliste in Pixel.  
  
 [in] `clrTransparent`  
 Die Farbe, transparentes Bild. Die Teile des Bilds, die diese Farbe werden transparent sein. Der Standardwert ist das Farbe Magenta, RGB(255,0,255).  
  
 [in] `hIcons`  
 Ein Handle für eine vorhandene Image-Liste.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei der ersten Methode überladen Syntax `TRUE` Wenn diese Methode erfolgreich; andernfalls ist `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Eigenschaftenfenster im Stil von Microsoft Outlook ist, zeigt das Framework eine Liste der Schaltflächen, die Outlook-Steuerelements auf der linken Seite der Eigenschaftenseite aufgerufen. Verwenden Sie diese Methode, um die Liste der Images, die von der Outlook-Steuerelement verwendet werden festzulegen.  
  
 Weitere Informationen zu den Methoden, die diese Methode unterstützen, finden Sie unter [CImageList:: Create](../../mfc/reference/cimagelist-class.md#create) und [CImageList::Add](../../mfc/reference/cimagelist-class.md#add). Weitere Informationen zum Festlegen des Stils eines Eigenschaftenblatts finden Sie unter [CMFCPropertySheet::SetLook](#setlook).  
  
##  <a name="a-namesetlooka--cmfcpropertysheetsetlook"></a><a name="setlook"></a>CMFCPropertySheet::SetLook  
 Gibt das Erscheinungsbild des Eigenschaftsblatts an.  
  
```  
void SetLook(
    PropSheetLook look,  
    int nNavControlWidth=100);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `look`  
 Einer der Enumerationswerte, der die Darstellung der Eigenschaftenseite. Ist das Standardformat für ein Eigenschaftenblatt `CMFCPropertySheet::PropSheetLook_Tabs`. Weitere Informationen finden Sie in der Tabelle im Abschnitt "Hinweise" dieses Themas.  
  
 [in] `nNavControlWidth`  
 Die Breite des Steuerelements Navigation in Pixel. Der Standardwert ist 100.  
  
### <a name="remarks"></a>Hinweise  
 Um ein Eigenschaftenblatt in einem Stil als den Standardwert anzuzeigen, rufen Sie diese Methode vor dem Erstellen des Fensters für die Eigenschaft.  
  
 Die folgende Tabelle enthält die Enumerationswerte, der in angegeben werden, können der `look` Parameter.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`CMFCPropertySheet::PropSheetLook_Tabs`|(Standard) Zeigt eine Registerkarte für die einzelnen Eigenschaftenseiten. Registerkarten im oberen Bereich der Eigenschaftenseite angezeigt werden und sind gestapelt werden weitere Registerkarten als in eine einzelne Zeile passen.|  
|`CMFCPropertySheet::PropSheetLook_OutlookBar`|Zeigt eine Liste der Navigationsschaltflächen im Stil der Microsoft Outlook-Leiste auf der linken Seite der Eigenschaftenseite. Jede Schaltfläche in der Liste entspricht einer Eigenschaftenseite. Das Framework zeigt Bildlaufpfeile befinden sich weitere Schaltflächen als in den sichtbaren Bereich der Liste passen.|  
|`CMFCPropertySheet::PropSheetLook_Tree`|Zeigt eine Strukturansicht auf der linken Seite der Eigenschaftenseite. Jeder über- oder untergeordneten Knoten des Strukturansicht-Steuerelements entspricht auf einer Eigenschaftenseite. Das Framework zeigt Pfeile, wenn mehrere Knoten als in den sichtbaren Bereich des Strukturansicht-Steuerelements passen vorhanden sind.|  
|`CMFCPropertySheet::PropSheetLook_OneNoteTabs`|Zeigt eine Registerkarte im Stil von Microsoft OneNote für die einzelnen Eigenschaftenseiten. Das Framework Registerkarten am oberen Rand der Seite Eigenschaften angezeigt und Bildlaufpfeile befinden sich mehrere Registerkarten als werden in einer einzelnen Zeile passen.|  
|`CMFCPropertySheet::PropSheetLook_List`|Zeigt eine Liste auf der linken Seite der Eigenschaftenseite. Jedes Listenelement entspricht einer Eigenschaftenseite. Das Framework zeigt Pfeile, wenn weitere Listenelemente enthält als in den sichtbaren Bereich der Liste passen.|  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyPage-Klasse](../../mfc/reference/cmfcpropertypage-class.md)   
 [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)

