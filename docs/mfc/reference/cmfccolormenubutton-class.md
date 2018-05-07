---
title: CMFCColorMenuButton Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableAutomaticButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableDocumentColors
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableOtherButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableTearOff
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetAutomaticColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnChangeParentWnd
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OpenColorDialog
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorName
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColumnsNumber
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CopyFrom
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CreatePopupMenu
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::IsEmptyMenuAllowed
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDraw
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDrawOnCustomizeList
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorMenuButton [MFC], CMFCColorMenuButton
- CMFCColorMenuButton [MFC], EnableAutomaticButton
- CMFCColorMenuButton [MFC], EnableDocumentColors
- CMFCColorMenuButton [MFC], EnableOtherButton
- CMFCColorMenuButton [MFC], EnableTearOff
- CMFCColorMenuButton [MFC], GetAutomaticColor
- CMFCColorMenuButton [MFC], GetColor
- CMFCColorMenuButton [MFC], GetColorByCmdID
- CMFCColorMenuButton [MFC], OnChangeParentWnd
- CMFCColorMenuButton [MFC], OpenColorDialog
- CMFCColorMenuButton [MFC], SetColor
- CMFCColorMenuButton [MFC], SetColorByCmdID
- CMFCColorMenuButton [MFC], SetColorName
- CMFCColorMenuButton [MFC], SetColumnsNumber
- CMFCColorMenuButton [MFC], CopyFrom
- CMFCColorMenuButton [MFC], CreatePopupMenu
- CMFCColorMenuButton [MFC], IsEmptyMenuAllowed
- CMFCColorMenuButton [MFC], OnDraw
- CMFCColorMenuButton [MFC], OnDrawOnCustomizeList
ms.assetid: 42685704-e994-4f7b-9553-62283c27b754
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1c19386aeac0d85565ae7834a881d710d9226ef9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cmfccolormenubutton-class"></a>CMFCColorMenuButton-Klasse
Die `CMFCColorMenuButton` Klasse unterstützt einen Menübefehl oder eine Symbolleisten-Schaltfläche, die ein Farben-Auswahldialogfeld startet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCColorMenuButton : public CMFCToolBarMenuButton  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorMenuButton::CMFCColorMenuButton](#cmfccolormenubutton)|Erstellt ein `CMFCColorMenuButton`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton)|Aktiviert und deaktiviert eine "Automatische"-Schaltfläche, die über die normale Schaltflächen positioniert ist. (Die Schaltfläche "automatisch Standardbetriebssystem" ist mit der Bezeichnung **automatische**.)|  
|[CMFCColorMenuButton::EnableDocumentColors](#enabledocumentcolors)|Ermöglicht die Anzeige von dokumentspezifische Farben statt Systemfarben an.|  
|[CMFCColorMenuButton::EnableOtherButton](#enableotherbutton)|Aktiviert und deaktiviert eine "other" Schaltfläche, die unter den regulären Farbe Schaltflächen positioniert ist. (Das Standardbetriebssystem "other" Schaltfläche ist mit der Bezeichnung **Weitere Farben**.)|  
|[CMFCColorMenuButton::EnableTearOff](#enabletearoff)|Bietet die Möglichkeit zum Deaktivieren einer Farbe Bereich entfernen.|  
|[CMFCColorMenuButton::GetAutomaticColor](#getautomaticcolor)|Ruft die aktuelle Farbe ab.|  
|[CMFCColorMenuButton::GetColor](#getcolor)|Ruft die aktuelle Schaltfläche Farbe ab.|  
|[CMFCColorMenuButton::GetColorByCmdID](#getcolorbycmdid)|Ruft die Farbe, die einen angegebenen Befehls-ID entspricht.|  
|[CMFCColorMenuButton::OnChangeParentWnd](#onchangeparentwnd)|Vom Framework aufgerufen, wenn das übergeordnete Fenster geändert wird.|  
|[CMFCColorMenuButton::OpenColorDialog](#opencolordialog)|Wird ein Farbauswahl-Dialogfeld geöffnet.|  
|[CMFCColorMenuButton::SetColor](#setcolor)|Legt die Farbe der Schaltfläche für die aktuelle Farbe fest.|  
|[CMFCColorMenuButton::SetColorByCmdID](#setcolorbycmdid)|Legt die Farbe der Schaltfläche für die angegebene Farbe-Menü an.|  
|[CMFCColorMenuButton::SetColorName](#setcolorname)|Legt einen neuen Namen für die angegebene Farbe fest.|  
|[CMFCColorMenuButton::SetColumnsNumber](#setcolumnsnumber)|Legt die Anzahl von angezeigten Spalten eine `CMFCColorBar` Objekt.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorMenuButton::CopyFrom](#copyfrom)|Kopiert ein anderes Symbolleisten-Schaltfläche auf die Schaltfläche mit den aktuellen an.|  
|[CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu)|Erstellt ein Farben-Auswahldialogfeld.|  
|[CMFCColorMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|Gibt an, ob leere Menüs unterstützt werden.|  
|[CMFCColorMenuButton::OnDraw](#ondraw)|Wird aufgerufen, durch das Framework um ein Bild auf einer Schaltfläche anzuzeigen.|  
|[CMFCColorMenuButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Aufgerufen, bevor ein `CMFCColorMenuButton` Objekt wird in der Liste der eines Anpassungsdialogfelds Symbolleiste angezeigt.|  
  
## <a name="remarks"></a>Hinweise  
 Ersetzt die ursprüngliche Menübefehl oder Symbolleisten-Schaltfläche mit einer `CMFCColorMenuButton` Objekt, das Erstellen der `CMFCColorMenuButton` Objektsatz, geeignete [CMFCColorBar-Klasse](../../mfc/reference/cmfccolorbar-class.md) Formatvorlagen und rufen Sie dann die `ReplaceButton` Methode von der [CMFCToolBar Klasse](../../mfc/reference/cmfctoolbar-class.md) Klasse. Wenn Sie eine Symbolleiste anpassen, rufen Sie die [CMFCToolBarsCustomizeDialog::ReplaceButton](../../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) Methode.  
  
 Farben-Auswahldialogfeld wird erstellt, bei der Verarbeitung der [CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu) -Ereignishandler. Der Ereignishandler benachrichtigt den übergeordneten Frame mit einem `WM_COMMAND` Nachricht. Die `CMFCColorMenuButton` Objekt sendet die Steuerelement-ID, die die ursprünglichen Menübefehl oder Symbolleisten-Schaltfläche zugewiesen ist.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen und Konfigurieren einer Menüschaltfläche Farbe mithilfe verschiedener Methoden in der `CMFCColorMenuButton` Klasse. Im Beispiel eine `CPalette` Objekt zuerst erstellt und dann verwendet, um ein Objekt des erstellen die `CMFCColorMenuButton` Klasse. Die `CMFCColorMenuButton` Objekt wird dann durch Aktivieren der automatischen und andere Schaltflächen und Festlegen der Farbe und die Anzahl der Spalten konfiguriert. Dieses Codebeispiel ist Teil der [WordPad-Beispiels](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#5](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_1.h)]  
[!code-cpp[NVC_MFC_WordPad#6](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)  
  
 [CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcolormenubutton.h  
  
##  <a name="cmfccolormenubutton"></a>  CMFCColorMenuButton::CMFCColorMenuButton  
 Erstellt ein `CMFCColorMenuButton`-Objekt.  
  
```  
CMFCColorMenuButton();

 
CMFCColorMenuButton(
    UINT uiCmdID,  
    LPCTSTR lpszText,  
    CPalette* pPalette=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdID`  
 Eine Schaltfläche Befehls-ID.  
  
 [in] `lpszText`  
 Der Text der Schaltfläche.  
  
 [in] `pPalette`  
 Ein Zeiger auf die Schaltfläche-Farbpalette.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Der erste Konstruktor ist der Standardkonstruktor. Das Objekt aktuelle Farbe und automatische Färbung werden auf Schwarz (RGB (0, 0, 0)) initialisiert.  
  
 Der zweite Konstruktor initialisiert die Schaltfläche, um die Farbe, die der angegebenen Befehls-ID entspricht.  
  
##  <a name="copyfrom"></a>  CMFCColorMenuButton::CopyFrom  
 Kopiert eine [CMFCToolBarMenuButton Klasse](../../mfc/reference/cmfctoolbarmenubutton-class.md)-abgeleitetes Objekt in eine andere.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `src`  
 Quelle, um zu kopieren.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode zum Kopieren von Objekten, die abgeleitet sind die `CMFCColorMenuButton` Objekt.  
  
##  <a name="createpopupmenu"></a>  CMFCColorMenuButton::CreatePopupMenu  
 Erstellt ein Farben-Auswahldialogfeld.  
  
```  
virtual CMFCPopupMenu* CreatePopupMenu();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Objekt, das ein Farben-Auswahldialogfeld darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn der Benutzer eine Menüschaltfläche Farbe drückt.  
  
##  <a name="enableautomaticbutton"></a>  CMFCColorMenuButton::EnableAutomaticButton  
 Aktiviert und deaktiviert eine "Automatische"-Schaltfläche, die über die normale Schaltflächen positioniert ist. (Die Schaltfläche "automatisch Standardbetriebssystem" ist mit der Bezeichnung **automatische**.)  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszLabel`  
 Gibt den Text der Schaltfläche angezeigt wird, wenn die Schaltfläche "" Automatische steht.  
  
 [in] `colorAutomatic`  
 Gibt eine neue automatische Farbe an.  
  
 [in] `bEnable`  
 Gibt an, ob die Schaltfläche automatisch erfolgt.  
  
### <a name="remarks"></a>Hinweise  
 Die Schaltfläche "Automatische" wendet die aktuelle Standardfarbe.  
  
##  <a name="enabledocumentcolors"></a>  CMFCColorMenuButton::EnableDocumentColors  
 Ermöglicht die Anzeige von dokumentspezifische Farben statt Systemfarben an.  
  
```  
void EnableDocumentColors(
    LPCTSTR lpszLabel,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszLabel`  
 Gibt den Text der Schaltfläche.  
  
 [in] `bEnable`  
 `TRUE` Um dokumentspezifische Farben anzuzeigen oder `FALSE` Systemfarben angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um die Farben des aktuellen Dokuments oder das Systempalettenfarben anzuzeigen, klickt der Benutzer eine Menüschaltfläche Farbe.  
  
##  <a name="enableotherbutton"></a>  CMFCColorMenuButton::EnableOtherButton  
 Aktiviert und deaktiviert eine "other" Schaltfläche, die unter den regulären Farbe Schaltflächen positioniert ist. (Das Standardbetriebssystem "other" Schaltfläche ist mit der Bezeichnung **Weitere Farben**.)  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg=TRUE,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszLabel`  
 Gibt den Text der Schaltfläche.  
  
 [in] `bAltColorDlg`  
 Geben Sie `TRUE` anzuzeigende der `CMFCColorDialog` (Dialogfeld), oder `FALSE` um das Dialogfeld Farbe Standardbetriebssystem anzuzeigen.  
  
 [in] `bEnable`  
 Geben Sie `TRUE` auf die Schaltfläche "other"; anzuzeigen, andernfalls `FALSE`. Die Standardeinstellung ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enabletearoff"></a>  CMFCColorMenuButton::EnableTearOff  
 Bietet die Möglichkeit zum Deaktivieren einer Farbe Bereich entfernen.  
  
```  
void EnableTearOff(
    UINT uiID,  
    int nVertDockColumns=-1,  
    int nHorzDockRows=-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiID`  
 Gibt die ID für den Bereich abtrennbare.  
  
 [in] `nVertDockColumns`  
 Gibt die Anzahl der Spalten im Bereich vertikal angedockten Farbe im abtrennbare Status an.  
  
 [in] `nHorzDockRows`  
 Gibt die Anzahl der Zeilen für den Bereich horizontal angedockt Farbe im abtrennbare Status an.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um das Feature "abtrennbare" für den Bereich der Farbe zu aktivieren, die sich wann holt die `CMFCColorMenuButton` gedrückt wird.  
  
##  <a name="getautomaticcolor"></a>  CMFCColorMenuButton::GetAutomaticColor  
 Ruft die aktuelle Farbe ab.  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein RGB-Farbwert, der die aktuelle Farbe darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die automatische Färbung zu erhalten, die festgelegt wird, indem Sie [CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton).  
  
##  <a name="getcolor"></a>  CMFCColorMenuButton::GetColor  
 Ruft die aktuelle Schaltfläche Farbe ab.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Farbe der Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcolorbycmdid"></a>  CMFCColorMenuButton::GetColorByCmdID  
 Ruft die Farbe, die einen angegebenen Befehls-ID entspricht.  
  
```  
static COLORREF GetColorByCmdID(UINT uiCmdID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdID`  
 Eine Befehls-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Farbe, die der angegebenen Befehls-ID entspricht.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, wenn Sie mehrere Farbe Schaltflächen in einer Anwendung verfügen. Klickt der Benutzer eine farbenschaltfläche, sendet die Schaltfläche "" die Befehls-ID in einem `WM_COMMAND` Nachricht an seinem übergeordneten Element. Die `GetColorByCmdID` Methode verwendet die Befehls-ID, um die entsprechende Farbe abzurufen.  
  
##  <a name="isemptymenuallowed"></a>  CMFCColorMenuButton::IsEmptyMenuAllowed  
 Gibt an, ob leere Menüs unterstützt werden.  
  
```  
virtual BOOL IsEmptyMenuAllowed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn leere Menüs zulässig sind; andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig werden leere Menüs unterstützt. Überschreiben Sie diese Methode, um dieses Verhalten in einer abgeleiteten Klasse zu ändern.  
  
##  <a name="onchangeparentwnd"></a>  CMFCColorMenuButton::OnChangeParentWnd  
 Vom Framework aufgerufen, wenn das übergeordnete Fenster geändert wird.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParent`  
 Ein Zeiger auf das neue übergeordnete Fenster.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondraw"></a>  CMFCColorMenuButton::OnDraw  
 Wird aufgerufen, durch das Framework um ein Bild auf einer Schaltfläche anzuzeigen.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    CMFCToolBarImages* pImages,  
    BOOL bHorz=TRUE,  
    BOOL bCustomizeMode=FALSE,  
    BOOL bHighlight=FALSE,  
    BOOL bDrawBorder=TRUE,  
    BOOL bGrayDisabledButtons=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Ein Rechteck, das den Bereich zu zeichnenden umschließt.  
  
 [in] `pImages`  
 Verweist auf eine Liste von symbolleistenbildern.  
  
 [in] `bHorz`  
 `TRUE` um anzugeben, dass die Symbolleiste in einem horizontalen angedockten Zustand ist; andernfalls `FALSE`. Die Standardeinstellung ist `TRUE`.  
  
 [in] `bCustomizeMode`  
 `TRUE` um anzugeben, dass die Anwendung im Anpassungsmodus; andernfalls `FALSE`. Die Standardeinstellung ist `FALSE`.  
  
 [in] `bHighlight`  
 `TRUE` um anzugeben, dass die Schaltfläche "" markiert ist; andernfalls `FALSE`. Die Standardeinstellung ist `FALSE`.  
  
 [in] `bDrawBorder`  
 `TRUE` um anzugeben, dass der Rahmen der Schaltfläche angezeigt wird; andernfalls `FALSE`. Die Standardeinstellung ist `TRUE`.  
  
 [in] `bGrayDisabledButtons`  
 `TRUE` um anzugeben, dass, die deaktiviert werden Schaltflächen (abgeblendet); abgeblendet. andernfalls `FALSE`. Die Standardeinstellung ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondrawoncustomizelist"></a>  CMFCColorMenuButton::OnDrawOnCustomizeList  
 Aufgerufen, bevor ein `CMFCColorMenuButton` Objekt wird in der Liste der eines Anpassungsdialogfelds Symbolleiste angezeigt.  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Ein Rechteck, das die Schaltfläche gezeichnet werden umschließt.  
  
 [in] `bSelected`  
 `TRUE` Gibt an, dass die Schaltfläche mit der ausgewählten Status aufweist. andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite der Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen bei einem `CMFCColorMenuButton` Objekt wird bei der Anpassung der Symbolleiste im Listenfeld angezeigt.  
  
##  <a name="opencolordialog"></a>  CMFCColorMenuButton::OpenColorDialog  
 Wird ein Farbauswahl-Dialogfeld geöffnet.  
  
```  
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,  
    COLORREF& colorRes);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `colorDefault`  
 Die Standardfarbe, die im Dialogfeld "Farbe" ausgewählt ist.  
  
 [out] `colorRes`  
 Gibt die Farbe, die der Benutzer über das Farbendialogfeld auswählt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer eine neue Farbe auswählt; andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Schaltfläche geklickt wird, rufen Sie diese Methode, um ein Dialogfeld zu öffnen. Wenn der Rückgabewert ungleich NULL ist, wird die Farbe, die der Benutzer wählt gespeichert, der `colorRes` Parameter. Verwenden der [CMFCColorMenuButton::EnableOtherButton](#enableotherbutton) Methode zum Wechseln zwischen den standardmäßigen Farbe (Dialogfeld) und die [CMFCColorDialog Klasse](../../mfc/reference/cmfccolordialog-class.md) (Dialogfeld).  
  
##  <a name="setcolor"></a>  CMFCColorMenuButton::SetColor  
 Legt die Farbe der Schaltfläche für die aktuelle Farbe fest.  
  
```  
virtual void SetColor(
    COLORREF clr,  
    BOOL bNotify=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `clr`  
 Ein Wert für den RGB-Farbe.  
  
 [in] `bNotify`  
 `TRUE` Anwenden der `clr` Parameter Farbe an, die alle zugeordneten Menüschaltfläche oder Symbolleisten-Schaltfläche; anderenfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Farbe der Schaltfläche für die aktuelle Farbe zu ändern. Wenn die `bNotify` Parameter ungleich NULL ist, wird die Farbe der entsprechenden Schaltflächen auf alle zugehörigen Popup-Menü oder auf der Symbolleiste auf die angegebene durch Farbe geändert die `clr` Parameter.  
  
##  <a name="setcolorbycmdid"></a>  CMFCColorMenuButton::SetColorByCmdID  
 Legt die Farbe der Schaltfläche für die angegebene Farbe-Menü an.  
  
```  
static void SetColorByCmdID(
    UINT uiCmdID,  
    COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdID`  
 Die Ressourcen-ID einer Menüschaltfläche Farbe.  
  
 [in] `color`  
 Ein Wert für den RGB-Farbe.  
  
##  <a name="setcolorname"></a>  CMFCColorMenuButton::SetColorName  
 Legt einen neuen Namen für die angegebene Farbe fest.  
  
```  
static void SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
 Den RGB-Wert, der die Farbe, deren Name geändert.  
  
 [in] `strName`  
 Der neue Name der Farbe.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setcolumnsnumber"></a>  CMFCColorMenuButton::SetColumnsNumber  
 Legt die Anzahl der Spalten für die Anzeige in ein Farben-Auswahlsteuerelement ( [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) Objekt).  
  
```  
void SetColumnsNumber(int nColumns);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nColumns`  
 Die Anzahl der anzuzeigenden Spalten.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCColorBar-Klasse](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarsCustomizeDialog-Klasse](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)   
 [CMFCColorButton-Klasse](../../mfc/reference/cmfccolorbutton-class.md)
