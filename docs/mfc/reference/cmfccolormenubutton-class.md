---
title: Klasse CMFCColorMenuButton | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CMFCColorMenuButton class
ms.assetid: 42685704-e994-4f7b-9553-62283c27b754
caps.latest.revision: 29
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
ms.openlocfilehash: a9b1e7a3dbfe4d98b3d51850723eb22ec1f9da06
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolormenubutton-class"></a>CMFCColorMenuButton-Klasse
Die `CMFCColorMenuButton` -Klasse unterstützt einen Menübefehl oder eine Symbolleisten-Schaltfläche, die ein Farben-Auswahldialogfeld startet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCColorMenuButton : public CMFCToolBarMenuButton  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorMenuButton::CMFCColorMenuButton](#cmfccolormenubutton)|Erstellt ein `CMFCColorMenuButton`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton)|Aktiviert und deaktiviert eine 'Automatische' Schaltfläche, die über die normale Schaltflächen positioniert ist. ("Automatisch" Standardsystem ist mit der Bezeichnung **automatische**.)|  
|[CMFCColorMenuButton::EnableDocumentColors](#enabledocumentcolors)|Ermöglicht die Anzeige von dokumentspezifische Farben anstelle von Systemfarben.|  
|[CMFCColorMenuButton::EnableOtherButton](#enableotherbutton)|Aktiviert und deaktiviert eine "other"-Schaltfläche, die unter die normale Schaltflächen positioniert ist. (Das Standardbetriebssystem "other" Schaltfläche hat die Bezeichnung **Weitere Farben... **.)|  
|[CMFCColorMenuButton::EnableTearOff](#enabletearoff)|Aktiviert die Möglichkeit, aus einem Bereich Farbe zu entfernen.|  
|[CMFCColorMenuButton::GetAutomaticColor](#getautomaticcolor)|Ruft die aktuelle Farbe ab.|  
|[CMFCColorMenuButton::GetColor](#getcolor)|Ruft die aktuelle Schaltfläche Farbe ab.|  
|[CMFCColorMenuButton::GetColorByCmdID](#getcolorbycmdid)|Ruft die Farbe, die einen angegebenen Befehls-ID entspricht.|  
|[CMFCColorMenuButton::OnChangeParentWnd](#onchangeparentwnd)|Vom Framework aufgerufen, wenn das übergeordnete Fenster geändert wird.|  
|[CMFCColorMenuButton::OpenColorDialog](#opencolordialog)|Öffnet ein Dialogfeld zur Farbauswahl.|  
|[CMFCColorMenuButton::SetColor](#setcolor)|Legt die Farbe der Schaltfläche für die aktuelle Farbe fest.|  
|[CMFCColorMenuButton::SetColorByCmdID](#setcolorbycmdid)|Legt die Farbe der Menüschaltfläche angegebene Farbe fest.|  
|[CMFCColorMenuButton::SetColorName](#setcolorname)|Legt einen neuen Namen für die angegebene Farbe fest.|  
|[CMFCColorMenuButton::SetColumnsNumber](#setcolumnsnumber)|Legt die Anzahl der Spalten, die angezeigt werden ein `CMFCColorBar` Objekt.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorMenuButton::CopyFrom](#copyfrom)|Eine andere Symbolleisten-Schaltfläche kopiert in der aktuellen Schaltfläche.|  
|[CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu)|Erstellt ein Farben-Auswahldialogfeld.|  
|[CMFCColorMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|Gibt an, ob leere Menüs unterstützt werden.|  
|[CMFCColorMenuButton::OnDraw](#ondraw)|Aufgerufen, um ein Bild auf einer Schaltfläche anzuzeigen.|  
|[CMFCColorMenuButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Aufgerufen, bevor ein `CMFCColorMenuButton` Objekt wird in der Liste der Symbolleiste Anpassungsdialogfelds angezeigt.|  
  
## <a name="remarks"></a>Hinweise  
 Ersetzt den ursprüngliche Menübefehl oder Symbolleisten-Schaltfläche mit einer `CMFCColorMenuButton` Objekt, die `CMFCColorMenuButton` Objekt, und legen Sie geeignete [CMFCColorBar-Klasse](../../mfc/reference/cmfccolorbar-class.md) Formatvorlagen und rufen Sie dann die `ReplaceButton` Methode der [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md) Klasse. Wenn Sie eine Symbolleiste angepasst haben, rufen Sie die [CMFCToolBarsCustomizeDialog::ReplaceButton](../../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) Methode.  
  
 Farben-Auswahldialogfeld wird erstellt, während der Verarbeitung der [CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu) -Ereignishandler. Der Ereignishandler benachrichtigt den übergeordneten Frame mit einem `WM_COMMAND` Nachricht. Das `CMFCColorMenuButton` Objekt sendet die Steuerelement-ID, die die ursprüngliche Menü Menübefehl oder eine Symbolleisten-Schaltfläche zugewiesen ist.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie zum Erstellen und konfigurieren eine Farbe-Schaltfläche mithilfe verschiedener Methoden in der `CMFCColorMenuButton` Klasse. Im Beispiel eine `CPalette` Objekt zuerst erstellt und dann verwendet, um ein Objekt von der `CMFCColorMenuButton` Klasse. Das `CMFCColorMenuButton` Objekt wird dann durch Aktivieren der automatischen und andere Schaltflächen und festlegen, die Farbe und die Anzahl der Spalten konfiguriert. Dieser Code ist Teil der [WordPad-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad&5;](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_1.h)]  
[!code-cpp[NVC_MFC_WordPad&6;](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)  
  
 [CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcolormenubutton.h  
  
##  <a name="cmfccolormenubutton"></a>CMFCColorMenuButton::CMFCColorMenuButton  
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
 Ein Zeiger auf die Schaltfläche Farben-Palette.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Der erste Konstruktor ist der Standardkonstruktor. Das Objekt, aktuelle Farbe und automatische Farbe werden auf Schwarz (RGB (0, 0, 0)) initialisiert.  
  
 Der zweite Konstruktor initialisiert die Schaltfläche, um die Farbe, die der angegebenen Befehls-ID entspricht.  
  
##  <a name="copyfrom"></a>CMFCColorMenuButton::CopyFrom  
 Kopiert eine [CMFCToolBarMenuButton Klasse](../../mfc/reference/cmfctoolbarmenubutton-class.md)-abgeleitetes Objekt in einen anderen.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `src`  
 Schaltfläche "Quelle" kopieren.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode zum Kopieren von Objekten, die von abgeleitet sind die `CMFCColorMenuButton` Objekt.  
  
##  <a name="createpopupmenu"></a>CMFCColorMenuButton::CreatePopupMenu  
 Erstellt ein Farben-Auswahldialogfeld.  
  
```  
virtual CMFCPopupMenu* CreatePopupMenu();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Objekt, das ein Farben-Auswahldialogfeld darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn der Benutzer eine Farbe-Schaltfläche drückt.  
  
##  <a name="enableautomaticbutton"></a>CMFCColorMenuButton::EnableAutomaticButton  
 Aktiviert und deaktiviert eine 'Automatische' Schaltfläche, die über die normale Schaltflächen positioniert ist. ("Automatisch" Standardsystem ist mit der Bezeichnung **automatische**.)  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszLabel`  
 Gibt den Text der Schaltfläche, der angezeigt wird, wenn die automatische wird.  
  
 [in] `colorAutomatic`  
 Gibt eine neue automatische Farbe an.  
  
 [in] `bEnable`  
 Gibt an, ob die Schaltfläche automatisch eingestellt ist.  
  
### <a name="remarks"></a>Hinweise  
 "Automatische" wendet die aktuelle Standardfarbe.  
  
##  <a name="enabledocumentcolors"></a>CMFCColorMenuButton::EnableDocumentColors  
 Ermöglicht die Anzeige von dokumentspezifische Farben anstelle von Systemfarben.  
  
```  
void EnableDocumentColors(
    LPCTSTR lpszLabel,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszLabel`  
 Gibt den Text der Schaltfläche.  
  
 [in] `bEnable`  
 `TRUE`Anzeige von Farben für die spezifischen oder `FALSE` Systemfarben angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um die Farben des aktuellen Dokuments oder der Farben der Systempalette anzuzeigen, wenn der Benutzer eine Farbe-Schaltfläche klickt.  
  
##  <a name="enableotherbutton"></a>CMFCColorMenuButton::EnableOtherButton  
 Aktiviert und deaktiviert eine "other"-Schaltfläche, die unter die normale Schaltflächen positioniert ist. (Das Standardbetriebssystem "other" Schaltfläche hat die Bezeichnung **Weitere Farben... **.)  
  
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
 Geben Sie `TRUE` zum Anzeigen der `CMFCColorDialog` klicken Sie im Dialogfeld oder `FALSE` im standard-Dialogfeld angezeigt.  
  
 [in] `bEnable`  
 Geben Sie `TRUE` zum Anzeigen der Schaltfläche "other"; andernfalls `FALSE`. Die Standardeinstellung ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enabletearoff"></a>CMFCColorMenuButton::EnableTearOff  
 Aktiviert die Möglichkeit, aus einem Bereich Farbe zu entfernen.  
  
```  
void EnableTearOff(
    UINT uiID,  
    int nVertDockColumns=-1,  
    int nHorzDockRows=-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiID`  
 Gibt die ID für den Bereich der abtrennbare.  
  
 [in] `nVertDockColumns`  
 Gibt die Anzahl der Spalten im vertikal angedockten Fenster in abtrennbare Zustand an.  
  
 [in] `nHorzDockRows`  
 Gibt die Anzahl der Zeilen für den Bereich horizontal angedockten Farbe in abtrennbare Zustand.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Funktion "abtrennbare" für den Bereich der Farbe zu aktivieren, die einblendet, wenn die `CMFCColorMenuButton` gedrückt wird.  
  
##  <a name="getautomaticcolor"></a>CMFCColorMenuButton::GetAutomaticColor  
 Ruft die aktuelle Farbe ab.  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein RGB-Farbwert, der die aktuelle Farbe darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Farbe zu erhalten, die festgelegt wird, indem [CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton).  
  
##  <a name="getcolor"></a>CMFCColorMenuButton::GetColor  
 Ruft die aktuelle Schaltfläche Farbe ab.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Farbe der Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcolorbycmdid"></a>CMFCColorMenuButton::GetColorByCmdID  
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
 Verwenden Sie diese Methode, wenn Sie mehrere Schaltflächen in einer Anwendung haben. Wenn der Benutzer eine Farbe klickt, sendet die Schaltfläche die Befehls-ID in eine `WM_COMMAND` Nachricht zu seinem übergeordneten Element. Die `GetColorByCmdID` Methode verwendet die Befehls-ID, um die entsprechende Farbe abzurufen.  
  
##  <a name="isemptymenuallowed"></a>CMFCColorMenuButton::IsEmptyMenuAllowed  
 Gibt an, ob leere Menüs unterstützt werden.  
  
```  
virtual BOOL IsEmptyMenuAllowed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn leere Menüs sind zulässig. andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig werden leere Menüs unterstützt. Überschreiben Sie diese Methode zum Ändern dieses Verhaltens in einer abgeleiteten Klasse.  
  
##  <a name="onchangeparentwnd"></a>CMFCColorMenuButton::OnChangeParentWnd  
 Vom Framework aufgerufen, wenn das übergeordnete Fenster geändert wird.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParent`  
 Ein Zeiger auf den neuen übergeordneten Fenster.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondraw"></a>CMFCColorMenuButton::OnDraw  
 Aufgerufen, um ein Bild auf einer Schaltfläche anzuzeigen.  
  
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
 `TRUE`um anzugeben, dass die Symbolleiste befindet sich in einem horizontalen angedockten Zustand; andernfalls `FALSE`. Die Standardeinstellung ist `TRUE`.  
  
 [in] `bCustomizeMode`  
 `TRUE`um anzugeben, dass die Anwendung im Anpassungsmodus; andernfalls `FALSE`. Die Standardeinstellung ist `FALSE`.  
  
 [in] `bHighlight`  
 `TRUE`um anzugeben, dass die Schaltfläche hervorgehoben ist; andernfalls `FALSE`. Die Standardeinstellung ist `FALSE`.  
  
 [in] `bDrawBorder`  
 `TRUE`um anzugeben, dass der Rahmen der Schaltfläche angezeigt wird; andernfalls `FALSE`. Die Standardeinstellung ist `TRUE`.  
  
 [in] `bGrayDisabledButtons`  
 `TRUE`um anzugeben, dass das deaktiviert werden Schaltflächen (abgeblendet); abgeblendet. andernfalls `FALSE`. Die Standardeinstellung ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondrawoncustomizelist"></a>CMFCColorMenuButton::OnDrawOnCustomizeList  
 Aufgerufen, bevor ein `CMFCColorMenuButton` Objekt wird in der Liste der Symbolleiste Anpassungsdialogfelds angezeigt.  
  
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
 `TRUE`Gibt an, dass die Schaltfläche ausgewählt wird. andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite der Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen wenn ein `CMFCColorMenuButton` Objekt wird im Listenfeld angezeigt, während des Anpassungsvorgangs Symbolleiste.  
  
##  <a name="opencolordialog"></a>CMFCColorMenuButton::OpenColorDialog  
 Öffnet ein Dialogfeld zur Farbauswahl.  
  
```  
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,  
    COLORREF& colorRes);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `colorDefault`  
 Die Standardfarbe, die im Dialogfeld "Farbe" ausgewählt ist.  
  
 [out] `colorRes`  
 Gibt die Farbe, die der Benutzer im Dialogfeld Farbe auswählt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer eine neue Farbe auswählt; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Schaltfläche geklickt wird, rufen Sie diese Methode, um ein Dialogfeld zu öffnen. Wenn der Rückgabewert ungleich NULL ist, befindet sich die Farbe, die der Benutzer wählt in der `colorRes` Parameter. Verwenden der [CMFCColorMenuButton::EnableOtherButton](#enableotherbutton) Methode, um das Dialogfeld Standardfarbe wechseln und die [CMFCColorDialog Klasse](../../mfc/reference/cmfccolordialog-class.md) (Dialogfeld).  
  
##  <a name="setcolor"></a>CMFCColorMenuButton::SetColor  
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
 `TRUE`Anwenden der `clr` Parameter Farbe an, die alle zugeordneten oder Symbolleistenschaltfläche; anderenfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Farbe der Schaltfläche für die aktuelle Farbe ändern. Wenn die `bNotify` Parameter ungleich NULL ist, wird die Farbe der entsprechenden Schaltfläche auf alle zugehörigen Popup-Menü oder Symbolleiste auf die durch angegebene Farbe geändert die `clr` Parameter.  
  
##  <a name="setcolorbycmdid"></a>CMFCColorMenuButton::SetColorByCmdID  
 Legt die Farbe der Menüschaltfläche angegebene Farbe fest.  
  
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
  
##  <a name="setcolorname"></a>CMFCColorMenuButton::SetColorName  
 Legt einen neuen Namen für die angegebene Farbe fest.  
  
```  
static void SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
 Die RGB-Wert der Farbe, deren Name geändert wird.  
  
 [in] `strName`  
 Der neue Name der Farbe.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setcolumnsnumber"></a>CMFCColorMenuButton::SetColumnsNumber  
 Legt die Anzahl der Spalten, die ein Farben-Auswahlsteuerelement angezeigt ( [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) Objekt).  
  
```  
void SetColumnsNumber(int nColumns);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nColumns`  
 Die Anzahl der Spalten angezeigt werden sollen.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCColorBar-Klasse](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarsCustomizeDialog-Klasse](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)   
 [CMFCColorButton-Klasse](../../mfc/reference/cmfccolorbutton-class.md)

