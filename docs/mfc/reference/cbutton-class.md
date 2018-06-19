---
title: CButton Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CButton
- AFXWIN/CButton
- AFXWIN/CButton::CButton
- AFXWIN/CButton::Create
- AFXWIN/CButton::DrawItem
- AFXWIN/CButton::GetBitmap
- AFXWIN/CButton::GetButtonStyle
- AFXWIN/CButton::GetCheck
- AFXWIN/CButton::GetCursor
- AFXWIN/CButton::GetIcon
- AFXWIN/CButton::GetIdealSize
- AFXWIN/CButton::GetImageList
- AFXWIN/CButton::GetNote
- AFXWIN/CButton::GetNoteLength
- AFXWIN/CButton::GetSplitGlyph
- AFXWIN/CButton::GetSplitImageList
- AFXWIN/CButton::GetSplitInfo
- AFXWIN/CButton::GetSplitSize
- AFXWIN/CButton::GetSplitStyle
- AFXWIN/CButton::GetState
- AFXWIN/CButton::GetTextMargin
- AFXWIN/CButton::SetBitmap
- AFXWIN/CButton::SetButtonStyle
- AFXWIN/CButton::SetCheck
- AFXWIN/CButton::SetCursor
- AFXWIN/CButton::SetDropDownState
- AFXWIN/CButton::SetIcon
- AFXWIN/CButton::SetImageList
- AFXWIN/CButton::SetNote
- AFXWIN/CButton::SetSplitGlyph
- AFXWIN/CButton::SetSplitImageList
- AFXWIN/CButton::SetSplitInfo
- AFXWIN/CButton::SetSplitSize
- AFXWIN/CButton::SetSplitStyle
- AFXWIN/CButton::SetState
- AFXWIN/CButton::SetTextMargin
dev_langs:
- C++
helpviewer_keywords:
- CButton [MFC], CButton
- CButton [MFC], Create
- CButton [MFC], DrawItem
- CButton [MFC], GetBitmap
- CButton [MFC], GetButtonStyle
- CButton [MFC], GetCheck
- CButton [MFC], GetCursor
- CButton [MFC], GetIcon
- CButton [MFC], GetIdealSize
- CButton [MFC], GetImageList
- CButton [MFC], GetNote
- CButton [MFC], GetNoteLength
- CButton [MFC], GetSplitGlyph
- CButton [MFC], GetSplitImageList
- CButton [MFC], GetSplitInfo
- CButton [MFC], GetSplitSize
- CButton [MFC], GetSplitStyle
- CButton [MFC], GetState
- CButton [MFC], GetTextMargin
- CButton [MFC], SetBitmap
- CButton [MFC], SetButtonStyle
- CButton [MFC], SetCheck
- CButton [MFC], SetCursor
- CButton [MFC], SetDropDownState
- CButton [MFC], SetIcon
- CButton [MFC], SetImageList
- CButton [MFC], SetNote
- CButton [MFC], SetSplitGlyph
- CButton [MFC], SetSplitImageList
- CButton [MFC], SetSplitInfo
- CButton [MFC], SetSplitSize
- CButton [MFC], SetSplitStyle
- CButton [MFC], SetState
- CButton [MFC], SetTextMargin
ms.assetid: cdc76d5b-31da-43c5-bc43-fde4cb39de5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: edcf6fd613231567cbb54b95c8be924919d93269
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357727"
---
# <a name="cbutton-class"></a>CButton-Klasse
Stellt die Funktionalität von Windows-Schaltflächensteuerelementen bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CButton : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CButton::CButton](#cbutton)|Erstellt ein `CButton`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CButton::Create](#create)|Erstellt das Schaltflächen-Steuerelement von Windows und fügt es der `CButton` Objekt.|  
|[CButton::DrawItem](#drawitem)|Überschreiben, um ein vom Besitzer gezeichnetes zeichnen `CButton` Objekt.|  
|[CButton::GetBitmap](#getbitmap)|Ruft das Handle der Bitmap für die zuvor festgelegten mit [SetBitmap](#setbitmap).|  
|[CButton::GetButtonStyle](#getbuttonstyle)|Ruft Informationen über das Steuerelement Schaltflächenformat ab.|  
|[CButton::GetCheck](#getcheck)|Ruft den Aktivierungszustand des einem Schaltflächen-Steuerelement ab.|  
|[CButton::GetCursor](#getcursor)|Ruft das Handle des Cursorbilds zuvor festgelegt wird, mit [SetCursor](#setcursor).|  
|[CButton::GetIcon](#geticon)|Ruft das Handle des zuvor mit dem Symbol [SetIcon](#seticon).|  
|[CButton::GetIdealSize](#getidealsize)|Ruft die ideale Größe das Schaltflächen-Steuerelement ab.|  
|[CButton::GetImageList](#getimagelist)|Ruft die Bildliste des Schaltflächen-Steuerelements ab.|  
|[CButton::GetNote](#getnote)|Ruft die Anmerkung-Komponente des aktuellen Befehls Link-Steuerelements ab.|  
|[CButton::GetNoteLength](#getnotelength)|Ruft die Länge des Texts Hinweis für den aktuellen Befehl Link-Steuerelement ab.|  
|[CButton::GetSplitGlyph](#getsplitglyph)|Ruft das Symbol, das das aktuelle SplitButton-Steuerelement zugeordnet.|  
|[CButton::GetSplitImageList](#getsplitimagelist)|Ruft die Bildliste für das aktuelle SplitButton-Steuerelement ab.|  
|[CButton::GetSplitInfo](#getsplitinfo)|Ruft die Informationen, die das aktuelle SplitButton-Steuerelement zu definieren.|  
|[CButton::GetSplitSize](#getsplitsize)|Ruft das umschließende Rechteck der Dropdown-Komponente des die aktuelle SplitButton-Steuerelement ab.|  
|[CButton::GetSplitStyle](#getsplitstyle)|Ruft ab, der Split-Schaltflächenstile, die das aktuelle SplitButton-Steuerelement zu definieren.|  
|[CButton::GetState](#getstate)|Ruft ab, der Aktivierungszustand, Hervorhebung Zustand und Status ein Schaltflächen-Steuerelement den Fokus.|  
|[CButton::GetTextMargin](#gettextmargin)|Ruft den Textrand des Steuerelements ab.|  
|[CButton:: SetBitmap](#setbitmap)|Gibt eine Bitmap, die auf die Schaltfläche angezeigt werden.|  
|[CButton::SetButtonStyle](#setbuttonstyle)|Der Stil einer Schaltfläche wird geändert.|  
|[CButton::SetCheck](#setcheck)|Legt den Aktivierungszustand des einem Schaltflächen-Steuerelement fest.|  
|[CButton::SetCursor](#setcursor)|Gibt ein Cursorbild auf die Schaltfläche angezeigt werden.|  
|[CButton::SetDropDownState](#setdropdownstate)|Legt den Dropdown-Zustand des aktuellen unterteilte Schaltflächen-Steuerelements.|  
|[CButton::SetIcon](#seticon)|Gibt ein Symbol auf der Schaltfläche angezeigt werden.|  
|[CButton::SetImageList](#setimagelist)|Legt die Bildliste des Schaltflächen-Steuerelements fest.|  
|[CButton::SetNote](#setnote)|Legt den Text auf dem aktuellen Befehl Link-Steuerelement fest.|  
|[CButton::SetSplitGlyph](#setsplitglyph)|Ordnet ein angegebene Symbol der aktuellen SplitButton-Steuerelement.|  
|[CButton::SetSplitImageList](#setsplitimagelist)|Ordnet eine Bildliste mit dem aktuellen SplitButton-Steuerelement.|  
|[CButton::SetSplitInfo](#setsplitinfo)|Gibt die Informationen, die das aktuelle SplitButton-Steuerelement zu definieren.|  
|[CButton::SetSplitSize](#setsplitsize)|Legt das umschließende Rechteck der Dropdown-Komponente des die aktuelle SplitButton-Steuerelement fest.|  
|[CButton::SetSplitStyle](#setsplitstyle)|Legt den Stil des aktuellen unterteilte Schaltflächen-Steuerelements fest.|  
|[CButton::SetState](#setstate)|Legt die Hervorhebungen Zustand des einem Schaltflächen-Steuerelement.|  
|[CButton::SetTextMargin](#settextmargin)|Legt den Textrand das Schaltflächen-Steuerelement fest.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Schaltflächen-Steuerelement ist eine kleine rechteckige untergeordnete Fenster, das ein- und ausschalten geklickt werden kann. Schaltflächen können allein oder in Gruppen verwendet werden und können entweder mit der Bezeichnung sein oder ohne Text angezeigt. Eine Schaltfläche ändert sich normalerweise Darstellung, wenn der Benutzer darauf klickt.  
  
 Typische Schaltflächen sind die Kontrollkästchen, Optionsfeld und Pushbutton. Ein `CButton` Objekt kann eine der folgenden, werden gemäß der [Schaltfläche Stil](../../mfc/reference/styles-used-by-mfc.md#button-styles) angegeben bei seiner Initialisierung durch die [erstellen](#create) Memberfunktion.  
  
 Darüber hinaus die [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md) abgeleitete Klasse `CButton` unterstützt die Erstellung von Schaltflächen-Steuerelemente, die mit Bitmapbildern statt mit Text beschriftet. Ein `CBitmapButton` können separate Bitmaps für eine Schaltfläche des oben, unten, mit Fokus und Zustand deaktivierten.  
  
 Sie können ein Schaltflächen-Steuerelement aus einer Dialogfeldvorlage oder direkt im Code erstellen. In beiden Fällen rufen Sie zunächst den Konstruktor `CButton` zum Erstellen der `CButton` Objekt; rufen Sie anschließend die **erstellen** Memberfunktion zum Erstellen der Windows Schaltflächensteuerelement und fügen Sie es auf die `CButton` Objekt.  
  
 Konstruktion kann ein langwieriger Vorgang in einer abgeleiteten Klasse `CButton`. Schreiben Sie einen Konstruktor für die abgeleitete Klasse, und rufen **erstellen** von innerhalb des Konstruktors.  
  
 Wenn Sie ein Button-Steuerelement an der übergeordnete per Windows-benachrichtigungsmeldungen behandeln möchten (normalerweise eine abgeleitete Klasse [CDialog](../../mfc/reference/cdialog-class.md)), die übergeordnete Klasse für jede Nachricht eine meldungszuordnung Eintrag und Nachrichtenhandler Memberfunktion hinzufügen.  
  
 Jede Meldungszuordnungseintrags weist folgende Form auf:  
  
 **ON_** Benachrichtigung **(**`id`, `memberFxn` **)**  
  
 wobei `id` gibt die untergeordneten Fenster-ID des Steuerelements, das Senden der Benachrichtigung und `memberFxn` ist der Name der übergeordneten-Memberfunktion, die Sie geschrieben haben, um die Benachrichtigung zu verarbeiten.  
  
 Das übergeordnete Funktionsprototyp lautet wie folgt:  
  
 **Afx_msg** `void` `memberFxn` **();**  
  
 Potenzielle Meldungszuordnungseinträge lauten wie folgt:  
  
|Eintrag für die Zuordnung|Mit dem beim übergeordneten gesendet...|  
|---------------|----------------------------|  
|**ON_BN_CLICKED**|Der Benutzer auf eine Schaltfläche klickt.|  
|**ON_BN_DOUBLECLICKED**|Der Benutzer auf eine Schaltfläche doppelklickt.|  
  
 Bei Erstellung einer `CButton` Objekt aus einer Ressource, die `CButton` Objekt wird automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Wenn Sie erstellen ein `CButton` Objekt innerhalb eines Fensters müssen sie zerstört werden. Bei Erstellung der `CButton` Objekt auf dem Heap mit dem **neue** -Funktion, die Sie aufrufen müssen **löschen** auf das Objekt, das sie zerstört werden, wenn der Benutzer den Windows schließt Schaltflächensteuerelement. Bei Erstellung der `CButton` -Objekt auf dem Stapel oder im übergeordneten Dialogfeldobjekt eingebettet ist, automatisch zerstört wird.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CButton`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cbutton"></a>  CButton::CButton  
 Erstellt ein `CButton`-Objekt.  
  
```  
CButton();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton#1](../../mfc/reference/codesnippet/cpp/cbutton-class_1.cpp)]  
  
##  <a name="create"></a>  CButton::Create  
 Erstellt das Schaltflächen-Steuerelement von Windows und fügt es der `CButton` Objekt.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszCaption,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszCaption`  
 Gibt den Text für das Schaltflächen-Steuerelement.  
  
 `dwStyle`  
 Gibt das Schaltflächen-Steuerelement-Stil. Wenden Sie eine beliebige Kombination von [Schaltfläche Stile](../../mfc/reference/styles-used-by-mfc.md#button-styles) auf die Schaltfläche.  
  
 `rect`  
 Gibt des Schaltflächen-Steuerelements Größe und Position. Es kann es sich um eine `CRect` Objekt oder eine `RECT` Struktur.  
  
 `pParentWnd`  
 Gibt an, das Schaltflächen-Steuerelement übergeordnetes Fenster, in der Regel eine `CDialog`. Es muss nicht **NULL**.  
  
 `nID`  
 Gibt das Schaltflächen-Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CButton` Objekt in zwei Schritten. Zuerst wird den Konstruktor aufrufen und dann **erstellen**, das erstellt des Schaltflächen-Steuerelements von Windows und fügt es der `CButton` Objekt.  
  
 Wenn die **WS_VISIBLE** Stil angegeben ist, sendet Windows dem Schaltflächen-Steuerelement alle Nachrichten, die für die Aktivierung und die Schaltfläche "anzeigen".  
  
 Übernehmen Sie die folgenden [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles) auf einem Schaltflächen-Steuerelement:  
  
- **WS_CHILD** immer  
  
- **WS_VISIBLE** in der Regel  
  
- **WS_DISABLED** selten  
  
- **WS_GROUP** zum Gruppieren von Steuerelementen  
  
- **WS_TABSTOP** auf die Schaltfläche mit den in der Tabulatorreihenfolge einschließen  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton#2](../../mfc/reference/codesnippet/cpp/cbutton-class_2.cpp)]  
  
##  <a name="drawitem"></a>  CButton::DrawItem  
 Wird vom Framework aufgerufen, wenn sich ein Darstellungsaspekt eines eine Ownerdrawn-Schaltfläche geändert hat.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDrawItemStruct`  
 Eine long-Zeiger auf eine [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) Struktur. Die Struktur enthält Informationen über das Element gezeichnet werden und den Typ der Zeichnung erforderlich.  
  
### <a name="remarks"></a>Hinweise  
 Eine Ownerdrawn-Schaltfläche verfügt über die **BS_OWNERDRAW** Satz formatieren. Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für ein vom Besitzer gezeichnetes `CButton` Objekt. Die Anwendung muss alle Device Interface (GDI) Grafikobjekten ausgewählt, für der Anzeigekontext in bereitgestellten wiederherstellen `lpDrawItemStruct` vor dem Element Funktion beendet wird.  
  
 Siehe auch die [BS_](../../mfc/reference/styles-used-by-mfc.md#button-styles) style-Werte.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton#3](../../mfc/reference/codesnippet/cpp/cbutton-class_3.cpp)]  
  
##  <a name="getbitmap"></a>  CButton::GetBitmap  
 Rufen Sie diese Memberfunktion, um das Handle für eine Bitmap, die zuvor festgelegten mit erhalten [SetBitmap](#setbitmap), d. h. mit einer Schaltfläche verknüpft sind.  
  
```  
HBITMAP GetBitmap() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für eine Bitmap. **NULL** falls zuvor keine Bitmap angegeben ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]  
  
##  <a name="getbuttonstyle"></a>  CButton::GetButtonStyle  
 Ruft Informationen über das Steuerelement Schaltflächenformat ab.  
  
```  
UINT GetButtonStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Schaltflächenstile dafür `CButton` Objekt. Diese Funktion gibt nur die [BS_](../../mfc/reference/styles-used-by-mfc.md#button-styles) Style-Werte, keine der anderen Fenster.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]  
  
##  <a name="getcheck"></a>  CButton::GetCheck  
 Ruft den Aktivierungszustand des eine Optionsfelds oder Kontrollkästchens ab.  
  
```  
int GetCheck() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert ein Schaltflächen-Steuerelement erstellt, mit der **BS_AUTOCHECKBOX**, **BS_AUTORADIOBUTTON**, **BS_AUTO3STATE**, **BS_CHECKBOX**, **BS_RADIOBUTTON**, oder **BS_3STATE** Stil ist einer der folgenden Werte:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|**BST_UNCHECKED**|Status der Schaltfläche ist deaktiviert.|  
|**BST_CHECKED**|Status der Schaltfläche aktiviert ist.|  
|**BST_INDETERMINATE**|Zustand der Schaltfläche unbestimmt ist (gilt nur, wenn die Schaltfläche "" hat die **BS_3STATE** oder **BS_AUTO3STATE** Stil).|  
  
 Wenn die Schaltfläche mit der jede andere Formatvorlage verfügt, ist der Rückgabewert **BST_UNCHECKED**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]  
  
##  <a name="getcursor"></a>  CButton::GetCursor  
 Rufen Sie diese Memberfunktion, um das Handle für einen Cursor, der zuvor festgelegten mit erhalten [SetCursor](#setcursor), d. h. mit einer Schaltfläche verknüpft sind.  
  
```  
HCURSOR GetCursor();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für ein Cursor-Image. **NULL** Wenn kein Cursor zuvor angegeben wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]  
  
##  <a name="geticon"></a>  CButton::GetIcon  
 Rufen Sie diese Memberfunktion, um das Handle für ein Symbol, und legen Sie zuvor mit get [SetIcon](#seticon), d. h. mit einer Schaltfläche verknüpft sind.  
  
```  
HICON GetIcon() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für ein Symbol. **NULL** Wenn zuvor kein Symbol angegeben wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]  
  
##  <a name="getidealsize"></a>  CButton::GetIdealSize  
 Ruft die ideale Größe für das Schaltflächen-Steuerelement ab.  
  
```  
BOOL GetIdealSize(SIZE* psize);
```  
  
### <a name="parameters"></a>Parameter  
 *psize*  
 Ein Zeiger auf die aktuelle Größe der Schaltfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen des die **BCM_GETIDEALSIZE** Nachricht, wie beschrieben in der [Schaltflächen](http://msdn.microsoft.com/library/windows/desktop/bb775943) Abschnitt des Windows SDK.  
  
##  <a name="getimagelist"></a>  CButton::GetImageList  
 Rufen Sie diese Methode, um das Schaltflächen-Steuerelement die Bildliste entnommen werden.  
  
```  
BOOL GetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```  
  
### <a name="parameters"></a>Parameter  
 `pbuttonImagelist`  
 Ein Zeiger auf die Bildliste des der `CButton` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen des die **BCM_GETIMAGELIST** Nachricht, wie beschrieben in der [Schaltflächen](http://msdn.microsoft.com/library/windows/desktop/bb775943) Abschnitt des Windows SDK.  
  
##  <a name="getnote"></a>  CButton::GetNote  
 Ruft die dem aktuellen Befehl Link-Steuerelement zugeordnete Hinweis Text ab.  
  
```  
CString GetNote() const;  
  
BOOL GetNote(
    LPTSTR lpszNote,   
    UINT* cchNote) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] `lpszNote`|Ein Zeiger auf einen Puffer, die der Aufrufer für das zuordnen und Freigeben von verwendet wird. Wenn der Rückgabewert ist `true`, enthält den Hinweis Text, der dem aktuellen Befehl Link-Steuerelement zugeordnet ist; andernfalls ist der Puffer, der Puffer ist unverändert.|  
|[in, out] `cchNote`|Ein Zeiger auf eine Variable Ganzzahl ohne Vorzeichen.<br /><br /> Wenn diese Methode aufgerufen wird, wird die Variable enthält die Größe des Puffers, die gemäß der `lpszNote` Parameter.<br /><br /> Wenn diese Methode zurückgegeben, wenn der Rückgabewert ist `true` die Variable enthält die Größe des den Hinweis, der dem aktuellen Befehl Link-Steuerelement zugeordnet. Wenn der Rückgabewert ist `false`, die Variable enthält, die Puffergröße benötigt, um den Text aufzunehmen.|  
  
### <a name="return-value"></a>Rückgabewert  
 In der ersten Überladung eine [CString](../../atl-mfc-shared/using-cstring.md) Objekt, das dem aktuellen Befehl Link-Steuerelement zugeordneten Hinweis Text enthält.  
  
 - oder -   
  
 In der zweiten Überladung `true` Wenn diese Methode erfolgreich, andernfalls ist `false`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenformat ist `BS_COMMANDLINK` oder `BS_DEFCOMMANDLINK`.  
  
 Diese Methode sendet die [BCM_GETNOTE](http://msdn.microsoft.com/library/windows/desktop/bb775965) Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="getnotelength"></a>  CButton::GetNoteLength  
 Ruft die Länge des Texts Hinweis für den aktuellen Befehl Link-Steuerelement ab.  
  
```  
UINT GetNoteLength() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge des Texts Hinweis in 16-Bit-Unicode-Zeichen für den aktuellen Befehl Link-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenformat ist `BS_COMMANDLINK` oder `BS_DEFCOMMANDLINK`.  
  
 Diese Methode sendet die [BCM_GETNOTELENGTH](http://msdn.microsoft.com/library/windows/desktop/bb775967) Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="getsplitglyph"></a>  CButton::GetSplitGlyph  
 Ruft das Symbol, das das aktuelle SplitButton-Steuerelement zugeordnet.  
  
```  
TCHAR GetSplitGlyph() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Glyphe-Zeichen, das das aktuelle SplitButton-Steuerelement zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Ein Symbol ist die physikalische Darstellung eines Zeichens in einer bestimmten Schriftart. Z. B. ein SplitButton-Steuerelement mit Glyphe, die Häkchen Unicodezeichens ergänzt werden kann (U + 2713).  
  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenformat ist `BS_SPLITBUTTON` oder `BS_DEFSPLITBUTTON`.  
  
 Diese Methode initialisiert die `mask` Mitglied einer [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) Struktur mit den `BCSIF_GLYPH` Flag, und klicken Sie dann gesendet, die Struktur in der [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Meldung, in der beschrieben wird im Windows SDK. Wenn die Nachricht Funktion zurückgibt, wird diese Methode ruft das Symbol aus der `himlGlyph` Member der Struktur.  
  
##  <a name="getsplitimagelist"></a>  CButton::GetSplitImageList  
 Ruft die [Bildliste](../../mfc/reference/cimagelist-class.md) für das aktuelle SplitButton-Steuerelement.  
  
```  
CImageList* GetSplitImageList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenformat ist `BS_SPLITBUTTON` oder `BS_DEFSPLITBUTTON`.  
  
 Diese Methode initialisiert die `mask` Mitglied einer [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) Struktur mit den `BCSIF_IMAGE` Flag, und klicken Sie dann gesendet, die Struktur in der [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Meldung, in der beschrieben wird im Windows SDK. Diese Methode ruft ab die Bildliste aus, wenn die Nachricht Funktion zurückgibt, die `himlGlyph` Member der Struktur.  
  
##  <a name="getsplitinfo"></a>  CButton::GetSplitInfo  
 Ruft ab die Parameter, die bestimmen, wie das aktuelle SplitButton-Steuerelement von Windows gezeichnet.  
  
```  
BOOL GetSplitInfo(PBUTTON_SPLITINFO pInfo) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] `pInfo`|Zeiger auf eine [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) -Struktur, die Informationen zu den aktuellen SplitButton-Steuerelement empfängt. Der Aufrufer ist verantwortlich für die Zuordnung von der Struktur.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenformat ist `BS_SPLITBUTTON` oder `BS_DEFSPLITBUTTON`.  
  
 Diese Methode sendet die [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="getsplitsize"></a>  CButton::GetSplitSize  
 Ruft das umschließende Rechteck der Dropdown-Komponente des die aktuelle SplitButton-Steuerelement ab.  
  
```  
BOOL GetSplitSize(LPSIZE pSize) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] `pSize`|Zeiger auf eine [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) -Struktur, die die Beschreibung eines Rechtecks empfängt.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenformat ist `BS_SPLITBUTTON` oder `BS_DEFSPLITBUTTON`.  
  
 Wenn das SplitButton-Steuerelement erweitert ist, können sie eine Dropdown-Komponente wie z. B. ein Listensteuerelement oder Pager-Steuerelement anzeigen. Diese Methode ruft das umschließende Rechteck, das Dropdown-Komponente enthält.  
  
 Diese Methode initialisiert die `mask` Mitglied einer [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) Struktur mit den `BCSIF_SIZE` Flag, und klicken Sie dann gesendet, die Struktur in der [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Meldung, in der beschrieben wird im Windows SDK. Bei Rückgabe der Funktion für die Nachricht wird diese Methode ruft das umschließende Rechteck von der `size` Member der Struktur.  
  
##  <a name="getsplitstyle"></a>  CButton::GetSplitStyle  
 Ruft ab, der Split-Schaltflächenstile, die das aktuelle SplitButton-Steuerelement zu definieren.  
  
```  
UINT GetSplitStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine bitweise Kombination der Split-Schaltflächenstile. Weitere Informationen finden Sie unter der `uSplitStyle` Mitglied der [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenformat ist `BS_SPLITBUTTON` oder `BS_DEFSPLITBUTTON`.  
  
 Der Split-Schaltflächenstile Geben Sie die Ausrichtung, Seitenverhältnis und grafischen Format mit dem Windows eine Teilung Schaltflächensymbol zeichnet.  
  
 Diese Methode initialisiert die `mask` Mitglied einer [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) Struktur mit den `BCSIF_STYLE` Flag, und klicken Sie dann gesendet, die Struktur in der [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Meldung, in der beschrieben wird im Windows SDK. Diese Methode ruft ab die Teilung Schaltflächenstile aus, wenn die Nachricht Funktion zurückgibt, die `uSplitStyle` Member der Struktur.  
  
##  <a name="getstate"></a>  CButton::GetState  
 Ruft den Status des einem Schaltflächen-Steuerelement ab.  
  
```  
UINT GetState() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Bitfeld, die die Kombination der Werte enthält, die den aktuellen Status des einem Schaltflächen-Steuerelement angeben. In der folgenden Tabelle sind die möglichen Werte aufgeführt.  
  
|Status der Schaltfläche|Wert|Beschreibung|  
|------------------|-----------|-----------------|  
|`BST_UNCHECKED`|0x0000|Der ursprüngliche Status.|  
|`BST_CHECKED`|0x0001|Das Schaltflächen-Steuerelement aktiviert ist.|  
|`BST_INDETERMINATE`|0x0002|Der Status ist unbestimmt (nur möglich, wenn das Schaltflächen-Steuerelement mit drei Status hat).|  
|`BST_PUSHED`|0x0004|Das Schaltflächen-Steuerelement geklickt wird.|  
|`BST_FOCUS`|0x0008|Das Schaltflächen-Steuerelement besitzt den Fokus.|  
  
### <a name="remarks"></a>Hinweise  
 Ein Schaltflächen-Steuerelement mit dem `BS_3STATE` oder `BS_AUTO3STATE` Schaltflächenformat erstellt ein Kontrollkästchen mit dem dritten Zustand mit der Bezeichnung unbestimmten Zustand. Unbestimmte Zustand gibt an, dass das Kontrollkästchen weder aktiviert noch deaktiviert ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]  
  
##  <a name="gettextmargin"></a>  CButton::GetTextMargin  
 Rufen Sie diese Methode, um den Textrand erhalten die `CButton` Objekt.  
  
```  
BOOL GetTextMargin(RECT* pmargin);
```  
  
### <a name="parameters"></a>Parameter  
 `pmargin`  
 Ein Zeiger auf den Textrand der `CButton` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Textrand zurück.  
  
### <a name="remarks"></a>Hinweise  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen des die **BCM_GETTEXTMARGIN** Nachricht, wie beschrieben in der [Schaltflächen](http://msdn.microsoft.com/library/windows/desktop/bb775943) Abschnitt des Windows SDK.  
  
##  <a name="setbitmap"></a>  CButton:: SetBitmap  
 Rufen Sie diese Memberfunktion, um die Schaltfläche eine neue Bitmapdatei zuzuordnen.  
  
```  
HBITMAP SetBitmap(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>Parameter  
 `hBitmap`  
 Das Handle einer Bitmap.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle einer Bitmap, die zuvor auf die Schaltfläche "" zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Die Bitmap wird automatisch auf die Schaltfläche standardmäßig zentriert platziert werden. Wenn die Bitmap für die Schaltfläche zu groß ist, wird es beidseitig abgeschnitten. Sie können andere Ausrichtungsoptionen, u. a. folgende:  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 Im Gegensatz zu [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), die vier Bitmaps pro Schaltfläche verwendet `SetBitmap` wird nur eine Bitmap pro der Schaltfläche verwendet. Wenn die Schaltfläche aufgerufen werden, scheinbar Bitmap ab, nach unten und rechts zu verschieben.  
  
 Sie sind verantwortlich für die Bitmap freigeben, wenn Sie damit fertig sind.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]  
  
##  <a name="setbuttonstyle"></a>  CButton::SetButtonStyle  
 Der Stil einer Schaltfläche wird geändert.  
  
```  
void SetButtonStyle(
    UINT nStyle,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nStyle`  
 Gibt an, die [Schaltfläche Stil](../../mfc/reference/styles-used-by-mfc.md#button-styles).  
  
 `bRedraw`  
 Gibt an, ob die Schaltfläche neu gezeichnet wird. Ein Wert ungleich NULL zeichnet die Schaltfläche. Wert 0 ist nicht die Schaltfläche neu zeichnet. Die Schaltfläche mit der in der Standardeinstellung neu gezeichnet wird.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `GetButtonStyle` Memberfunktion versucht, das Schaltflächenformat abzurufen. Das niederwertige Wort des Formats Schaltfläche ist die Schaltfläche-spezifische-Format.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]  
  
##  <a name="setcheck"></a>  CButton::SetCheck  
 Legt fest oder setzt den Aktivierungszustand einer Optionsfeld oder Kontrollkästchen.  
  
```  
void SetCheck(int nCheck);
```  
  
### <a name="parameters"></a>Parameter  
 `nCheck`  
 Gibt den Aktivierungszustand an. Dieser Parameter kann eine der folgenden sein:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|**BST_UNCHECKED**|Zustand der Schaltfläche auf deaktiviert festgelegt.|  
|**BST_CHECKED**|Legen Sie den Zustand der Schaltfläche überprüft.|  
|**BST_INDETERMINATE**|Legen Sie den Zustand der Schaltfläche auf unbestimmt. Dieser Wert kann verwendet werden, nur dann, wenn die Schaltfläche "" hat die **BS_3STATE** oder **BS_AUTO3STATE** Stil.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wirkt sich nicht auf eine Schaltfläche aus.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]  
  
##  <a name="setcursor"></a>  CButton::SetCursor  
 Rufen Sie diese Memberfunktion, um die Schaltfläche "" einen neuen Cursor zuzuordnen.  
  
```  
HCURSOR SetCursor(HCURSOR hCursor);
```  
  
### <a name="parameters"></a>Parameter  
 `hCursor`  
 Das Handle eines Cursors.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle eines Cursors, der zuvor auf die Schaltfläche "" zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Der Cursor wird automatisch auf die Schaltfläche standardmäßig zentriert platziert werden. Wenn der Cursor für die Schaltfläche zu groß ist, wird es beidseitig abgeschnitten. Sie können andere Ausrichtungsoptionen, u. a. folgende:  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 Im Gegensatz zu [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), die vier Bitmaps pro Schaltfläche verwendet `SetCursor` verwendet nur einen Cursor pro die Schaltfläche "". Wenn die Schaltfläche aufgerufen werden, wird der Cursor nach unten und rechts verschoben angezeigt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]  
  
##  <a name="setdropdownstate"></a>  CButton::SetDropDownState  
 Legt den Dropdown-Zustand des aktuellen unterteilte Schaltflächen-Steuerelements.  
  
```  
BOOL SetDropDownState(BOOL fDropDown);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `fDropDown`|`true` festzulegende `BST_DROPDOWNPUSHED` Zustand befindet, andernfalls `false`.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Ein SplitButton-Steuerelement verfügt über einen Stil des `BS_SPLITBUTTON` oder `BS_DEFSPLITBUTTON` und besteht aus einer Schaltfläche und ein Dropdown-Pfeil rechts davon. Weitere Informationen finden Sie unter [Schaltflächenstile](http://msdn.microsoft.com/library/windows/desktop/bb775951). In der Regel wird die Dropdownliste Status festgelegt, klickt der Benutzer den Dropdown Pfeil. Verwenden Sie diese Methode, um die Dropdown-Zustand des Steuerelements programmgesteuert festzulegen. Der Dropdownpfeil gezeichnet wird schattiert, um den Status anzugeben.  
  
 Diese Methode sendet die [BCM_SETDROPDOWNSTATE](http://msdn.microsoft.com/library/windows/desktop/bb775973) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_splitButton`, d. h. verwendet, um das SplitButton-Steuerelement programmgesteuert zugreifen. Diese Variable wird im folgenden Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel legt fest, den Status des das SplitButton-Steuerelement, um anzugeben, dass das Dropdown-Pfeil wird per Push übertragen.  
  
 [!code-cpp[NVC_MFC_CButton_s1#6](../../mfc/reference/codesnippet/cpp/cbutton-class_11.cpp)]  
  
##  <a name="setelevationrequired"></a>  CButton::SetElevationRequired  
 Legt den Zustand des aktuellen Button-Steuerelements, `elevation required`, der für das Steuerelement zum Anzeigen eines Symbols mit höherer Sicherheit erforderlich ist.  
  
```  
BOOL SetElevationRequired(BOOL fElevationRequired);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `fElevationRequired`|`true` festzulegende `elevation required` Zustand befindet, andernfalls `false`.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Linksteuerelement Schaltfläche oder einen Befehl mit erhöhten Rechten Sicherheitsberechtigungen zum Ausführen einer Aktion erforderlich ist, legen Sie das Steuerelement zum `elevation required` Zustand. Anschließend zeigt Windows das Symbol "sicherheitsschild: Benutzerkontensteuerung (UAC)" auf dem Steuerelement. Weitere Informationen finden Sie unter "User Account Control" [MSDN](http://go.microsoft.com/fwlink/p/?linkid=18507).  
  
 Diese Methode sendet die [BCM_SETSHIELD](http://msdn.microsoft.com/library/windows/desktop/bb775979) Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="seticon"></a>  CButton::SetIcon  
 Rufen Sie diese Memberfunktion, um die Schaltfläche ein Symbol "Neues" zuzuordnen.  
  
```  
HICON SetIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>Parameter  
 `hIcon`  
 Das Handle eines Symbols.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle eines Symbols, auf die Schaltfläche mit den zuvor zugeordnet waren.  
  
### <a name="remarks"></a>Hinweise  
 Das Symbol wird automatisch auf die Schaltfläche standardmäßig zentriert platziert werden. Wenn das Symbol für die Schaltfläche zu groß ist, wird es beidseitig abgeschnitten. Sie können andere Ausrichtungsoptionen, u. a. folgende:  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 Im Gegensatz zu [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), die vier Bitmaps pro Schaltfläche verwendet `SetIcon` wird nur ein Symbol pro der Schaltfläche verwendet. Wenn die Schaltfläche aufgerufen werden, wird das Symbol nach unten und nach rechts verschoben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]  
  
##  <a name="setimagelist"></a>  CButton::SetImageList  
 Rufen Sie diese Methode, um die Bildliste des legen die `CButton` Objekt.  
  
```  
BOOL SetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```  
  
### <a name="parameters"></a>Parameter  
 `pbuttonImagelist`  
 Ein Zeiger auf die neue Bildliste.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg **"false"** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen des die **BCM_SETIMAGELIST** Nachricht, wie beschrieben in der [Schaltflächen](http://msdn.microsoft.com/library/windows/desktop/bb775943) Abschnitt des Windows SDK.  
  
##  <a name="setnote"></a>  CButton::SetNote  
 Legt den Text der Anmerkung für den aktuellen Befehl Link-Steuerelement.  
  
```  
BOOL SetNote(LPCTSTR lpszNote);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `lpszNote`|Ein Zeiger auf eine Unicode-Zeichenfolge, die als Hinweis Text für das Link-Steuerelement festgelegt wird.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenformat ist `BS_COMMANDLINK` oder `BS_DEFCOMMANDLINK`.  
  
 Diese Methode sendet die [BCM_SETNOTE](http://msdn.microsoft.com/library/windows/desktop/bb775977) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_cmdLink`, d. h. verwendet, um das Link-Steuerelement programmgesteuert zugreifen. Diese Variable wird im folgenden Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel legt den Hinweis Text für die Link-Steuerelement fest.  
  
 [!code-cpp[NVC_MFC_CButton_s1#7](../../mfc/reference/codesnippet/cpp/cbutton-class_12.cpp)]  
  
##  <a name="setsplitglyph"></a>  CButton::SetSplitGlyph  
 Ordnet ein angegebene Symbol der aktuellen SplitButton-Steuerelement.  
  
```  
BOOL SetSplitGlyph(TCHAR chGlyph);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `chGlyph`|Ein Zeichen, der angibt, das Symbol, das als die unterteilte Schaltfläche Dropdown-Pfeil verwendet.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, die das Schaltflächenformat `BS_SPLITBUTTON` oder `BS_DEFSPLITBUTTON`.  
  
 Ein Symbol ist die physikalische Darstellung eines Zeichens in einer bestimmten Schriftart. Die `chGlyph` Parameter wird nicht verwendet werden, als das Symbol, jedoch wird stattdessen verwendet werden, um aus einem Satz von vordefinierten Symbolen ein Symbol auswählen. Dropdown-Pfeil Standardglyphe wird angegeben, indem ein Zeichen "6" und das Unicode-Zeichen Schwarz nach unten ZEIGENDEN DREIECK (U + 25BC) ähnelt.  
  
 Diese Methode initialisiert die `mask` Mitglied ein [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) Struktur mit der `BCSIF_GLYPH` Flag und die `himlGlyph` Element mit der `chGlyph` übergeben wird, und sendet, die in der -Struktur[ BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="setsplitimagelist"></a>  CButton::SetSplitImageList  
 Ordnet eine [Bildliste](../../mfc/reference/cimagelist-class.md) mit der aktuellen SplitButton-Steuerelement.  
  
```  
BOOL SetSplitImageList(CImageList* pSplitImageList);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `pSplitImageList`|Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) Objekt, das das aktuelle SplitButton-Steuerelement zugewiesen.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenformat ist `BS_SPLITBUTTON` oder `BS_DEFSPLITBUTTON`.  
  
 Diese Methode initialisiert die `mask` Mitglied ein [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) Struktur mit der `BCSIF_IMAGE` Flag und die `himlGlyph` Element mit der `pSplitImageList` übergeben wird, und sendet, die in der -Struktur[ BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="setsplitinfo"></a>  CButton::SetSplitInfo  
 Gibt Parameter an, die bestimmen, wie das aktuelle SplitButton-Steuerelement von Windows gezeichnet.  
  
```  
BOOL SetSplitInfo(PBUTTON_SPLITINFO pInfo);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `pInfo`|Zeiger auf eine [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) Struktur, die das aktuelle SplitButton-Steuerelement definiert.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenformat ist `BS_SPLITBUTTON` oder `BS_DEFSPLITBUTTON`.  
  
 Diese Methode sendet die [BCM_SETSPLITINFO verwenden](http://msdn.microsoft.com/library/windows/desktop/bb775981) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_splitButton`, d. h. verwendet, um das SplitButton-Steuerelement programmgesteuert zugreifen.  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird ändert das Symbol, das für die unterteilte Schaltfläche Dropdown-Pfeil verwendet wird. Im Beispiel ersetzt eine oben zeigenden Dreieck-Symbol für das standardmäßige nach unten zeigenden Dreieck-Symbol. Das Symbol, das angezeigt wird, hängt das Zeichen an die von Ihnen in der `himlGlyph` Mitglied der `BUTTON_SPLITINFO` Struktur. Das nach unten zeigenden Dreieck-Symbol wird angegeben, indem ein Zeichen "6"und das oben zeigenden Dreieck-Symbol wird angegeben, indem ein Zeichen "5". Vergleich finden Sie in der Hilfsmethode [CButton::SetSplitGlyph](#setsplitglyph).  
  
 [!code-cpp[NVC_MFC_CButton_s1#4](../../mfc/reference/codesnippet/cpp/cbutton-class_13.cpp)]  
  
##  <a name="setsplitsize"></a>  CButton::SetSplitSize  
 Legt das umschließende Rechteck der Dropdown-Komponente des die aktuelle SplitButton-Steuerelement fest.  
  
```  
BOOL SetSplitSize(LPSIZE pSize);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `pSize`|Zeiger auf eine [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur, die ein umschließendes Rechteck beschreibt.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenformat ist `BS_SPLITBUTTON` oder `BS_DEFSPLITBUTTON`.  
  
 Wenn das SplitButton-Steuerelement erweitert ist, können sie eine Dropdown-Komponente wie z. B. ein Listensteuerelement oder Pager-Steuerelement anzeigen. Diese Methode gibt die Größe des umschließenden Rechtecks, das Dropdown-Komponente enthält.  
  
 Diese Methode initialisiert die `mask` Mitglied ein [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) Struktur mit der `BCSIF_SIZE` Flag und die `size` Element mit der `pSize` übergeben wird, und sendet, die in der -Struktur[ BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_splitButton`, d. h. verwendet, um das SplitButton-Steuerelement programmgesteuert zugreifen. Diese Variable wird im folgenden Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die Größe des Dropdown-Pfeil der Teilung verdoppelt.  
  
 [!code-cpp[NVC_MFC_CButton_s1#5](../../mfc/reference/codesnippet/cpp/cbutton-class_14.cpp)]  
  
##  <a name="setsplitstyle"></a>  CButton::SetSplitStyle  
 Legt den Stil des aktuellen unterteilte Schaltflächen-Steuerelements fest.  
  
```  
BOOL SetSplitStyle(UINT uSplitStyle);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `uSplitStyle`|Eine bitweise Kombination der Split-Schaltflächenstile. Weitere Informationen finden Sie unter der `uSplitStyle` Mitglied der [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) Struktur.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenformat ist `BS_SPLITBUTTON` oder `BS_DEFSPLITBUTTON`.  
  
 Der Split-Schaltflächenstile Geben Sie die Ausrichtung, Seitenverhältnis und grafischen Format mit dem Windows eine Teilung Schaltflächensymbol zeichnet. Weitere Informationen finden Sie unter der `uSplitStyle` Mitglied der [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) Struktur.  
  
 Diese Methode initialisiert die `mask` Mitglied ein [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) Struktur mit der `BCSIF_STYLE` Flag und die `uSplitStyle` Element mit der `uSplitStyle` übergeben wird, und sendet, die in der -Struktur[ BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_splitButton`, d. h. verwendet, um das SplitButton-Steuerelement programmgesteuert zugreifen.  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel legt den Stil des Dropdown-Pfeil der Teilung fest. Die `BCSS_ALIGNLEFT` Stil zeigt den Pfeil links neben der Schaltfläche und die `BCSS_STRETCH` Stil behält den Dropdown-Pfeil Proportionen aus, wenn Sie die Größe der Schaltfläche.  
  
 [!code-cpp[NVC_MFC_CButton_s1#3](../../mfc/reference/codesnippet/cpp/cbutton-class_15.cpp)]  
  
##  <a name="setstate"></a>  CButton::SetState  
 Legt fest, ob ein Schaltflächen-Steuerelement hervorgehoben ist.  
  
```  
void SetState(BOOL bHighlight);
```  
  
### <a name="parameters"></a>Parameter  
 *bHighlight*  
 Gibt an, ob die Schaltfläche hervorgehoben werden. Ein Wert ungleich Null werden hervorgehoben, die Schaltfläche ""; ein Wert von 0 entfernt alle Hervorhebung.  
  
### <a name="remarks"></a>Hinweise  
 Hervorhebung wirkt sich auf der Außenseite des einem Schaltflächen-Steuerelement aus. Er wirkt sich nicht auf den Aktivierungszustand des ein Kontrollkästchen oder ein Optionsfeld aus.  
  
 Automatisch wird ein Schaltflächen-Steuerelement hervorgehoben, wenn der Benutzer klickt auf und die linke Maustaste gedrückt enthält. Die Hervorhebung wird entfernt, wenn der Benutzer die Maustaste loslässt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]  
  
##  <a name="settextmargin"></a>  CButton::SetTextMargin  
 Rufen Sie diese Methode zum Festlegen der Textrand der `CButton` Objekt.  
  
```  
BOOL SetTextMargin(RECT* pmargin);
```  
  
### <a name="parameters"></a>Parameter  
 `pmargin`  
 Ein Zeiger auf den neuen Textrand.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" bei Erfolg, bei einem Fehler FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen des die **BCM_SETTEXTMARGIN** Nachricht, wie beschrieben in der [Schaltflächen](http://msdn.microsoft.com/library/windows/desktop/bb775943) Abschnitt des Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [CComboBox-Klasse](../../mfc/reference/ccombobox-class.md)   
 [CEdit-Klasse](../../mfc/reference/cedit-class.md)   
 [CListBox-Klasse](../../mfc/reference/clistbox-class.md)   
 [CScrollBar-Klasse](../../mfc/reference/cscrollbar-class.md)   
 [CStatic-Klasse](../../mfc/reference/cstatic-class.md)   
 [CBitmapButton-Klasse](../../mfc/reference/cbitmapbutton-class.md)   
 [CDialog-Klasse](../../mfc/reference/cdialog-class.md)
