---
title: CButton Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CButton
dev_langs:
- C++
helpviewer_keywords:
- CButton class
- checkbox buttons
- pushbuttons
- button control [MFC]
- check boxes, button controls
- button objects (CButton)
- radio buttons, CButton class
ms.assetid: cdc76d5b-31da-43c5-bc43-fde4cb39de5b
caps.latest.revision: 19
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
ms.openlocfilehash: 751d4aee2c734acd455734ca694eb88bb149fc09
ms.lasthandoff: 02/24/2017

---
# <a name="cbutton-class"></a>CButton-Klasse
Stellt die Funktionalität von Windows-Schaltflächensteuerelementen bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CButton : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CButton::CButton](#cbutton)|Erstellt ein `CButton`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CButton::Create](#create)|Das Windows-Schaltflächen-Steuerelement erstellt, und fügt es der `CButton` Objekt.|  
|[CButton::DrawItem](#drawitem)|Außerkraftsetzung zum Zeichnen eines Ownerdrawn- `CButton` Objekt.|  
|[CButton::GetBitmap](#getbitmap)|Ruft das Handle der Bitmap für die zuvor festgelegten mit [SetBitmap](#setbitmap).|  
|[CButton::GetButtonStyle](#getbuttonstyle)|Ruft Informationen zu den Schaltflächenstil-Steuerelement.|  
|[CButton::GetCheck](#getcheck)|Ruft den Aktivierungsstatus des Button-Steuerelements ab.|  
|[CButton::GetCursor](#getcursor)|Ruft das Handle des Cursorbilds zuvor mit festgelegten [SetCursor](#setcursor).|  
|[CButton::GetIcon](#geticon)|Ruft das Handle des zuvor mit dem Symbol [SetIcon](#seticon).|  
|[CButton::GetIdealSize](#getidealsize)|Ruft die ideale Größe des Button-Steuerelements ab.|  
|[CButton::GetImageList](#getimagelist)|Ruft die Bildliste des Button-Steuerelements ab.|  
|[CButton::GetNote](#getnote)|Ruft die Anmerkung-Komponente des aktuellen Link-Steuerelements ab.|  
|[CButton::GetNoteLength](#getnotelength)|Ruft die Länge des Texts Hinweis für den aktuellen Befehl Link-Steuerelement ab.|  
|[CButton::GetSplitGlyph](#getsplitglyph)|Ruft das Symbol, das das aktuelle SplitButton-Steuerelement zugeordnet.|  
|[CButton::GetSplitImageList](#getsplitimagelist)|Ruft die Bildliste für das aktuelle SplitButton-Steuerelement ab.|  
|[CButton::GetSplitInfo](#getsplitinfo)|Ruft Informationen, die das aktuelle SplitButton-Steuerelement definiert.|  
|[CButton::GetSplitSize](#getsplitsize)|Ruft das umschließende Rechteck der Dropdown-Komponente von der aktuellen SplitButton-Steuerelement ab.|  
|[CButton::GetSplitStyle](#getsplitstyle)|Ruft die Split-Button-Stile, die das aktuelle SplitButton-Steuerelement zu definieren.|  
|[CButton::GetState](#getstate)|Ruft ab, des Aktivierungszustands Hervorhebung Zustand und Status ein Schaltflächen-Steuerelement den Fokus.|  
|[CButton::GetTextMargin](#gettextmargin)|Ruft den Textrand des Button-Steuerelements ab.|  
|[CButton:: SetBitmap](#setbitmap)|Gibt eine Bitmap für die Schaltfläche angezeigt werden soll.|  
|[CButton::SetButtonStyle](#setbuttonstyle)|Ändert den Stil einer Schaltfläche.|  
|[CButton::SetCheck](#setcheck)|Legt den Aktivierungszustand des Button-Steuerelements fest.|  
|[CButton::SetCursor](#setcursor)|Gibt ein Cursorbild auf die Schaltfläche angezeigt werden.|  
|[CButton::SetDropDownState](#setdropdownstate)|Legt die Dropdown-Status der aktuellen SplitButton-Steuerelement fest.|  
|[CButton::SetIcon](#seticon)|Gibt ein Symbol auf der Schaltfläche angezeigt werden.|  
|[CButton::SetImageList](#setimagelist)|Legt die Bildliste des Button-Steuerelements fest.|  
|[CButton::SetNote](#setnote)|Auf dem aktuellen Befehl Link-Steuerelement festgelegt.|  
|[CButton::SetSplitGlyph](#setsplitglyph)|Ordnet einen angegebenen Symbol das aktuelle SplitButton-Steuerelement.|  
|[CButton::SetSplitImageList](#setsplitimagelist)|Das aktuelle SplitButton-Steuerelement eine Bildliste zugeordnet.|  
|[CButton::SetSplitInfo](#setsplitinfo)|Gibt Informationen an, die das aktuelle SplitButton-Steuerelement definiert.|  
|[CButton::SetSplitSize](#setsplitsize)|Legt das umschließende Rechteck der Dropdown-Komponente von der aktuellen SplitButton-Steuerelement fest.|  
|[CButton::SetSplitStyle](#setsplitstyle)|Legt den Stil für das aktuelle SplitButton-Steuerelement.|  
|[CButton::SetState](#setstate)|Legt den hervorheben Zustand eines Steuerelements fest.|  
|[CButton::SetTextMargin](#settextmargin)|Wird der Textrand des Button-Steuerelements.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Schaltflächen-Steuerelement ist ein kleines, rechteckiges untergeordneten-Fenster, das ein- und ausschalten geklickt werden kann. Schaltflächen können einzeln oder in Gruppen verwendet werden und können entweder benannt oder ohne Text angezeigt. Eine Schaltfläche ändert Darstellung in der Regel, wenn der Benutzer darauf klickt.  
  
 Normale Schaltflächen sind die Kontrollkästchen, Optionsfeld und Pushbutton. Ein `CButton` Objekt kann einen solchen werden gemäß der [Schaltfläche Stil](../../mfc/reference/button-styles.md) angegeben, die bei der Initialisierung von der [erstellen](#create) Member-Funktion.  
  
 Darüber hinaus die [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md) abgeleitete Klasse `CButton` unterstützt die Erstellung von Schaltflächen-Steuerelemente, die mit Bitmapbildern statt mit Text bezeichnet. Ein `CBitmapButton` können separate Bitmaps für eine Schaltfläche des oben, unten, konzentriert und Zustand deaktivierten.  
  
 Sie können ein Button-Steuerelement aus einer Dialogfeldvorlage oder direkt im Code erstellen. In beiden Fällen rufen Sie zuerst den Konstruktor `CButton` zum Erstellen der `CButton` Objekt, rufen Sie dann die **erstellen** zum Erstellen der Windows-Memberfunktion Schaltflächensteuerelement und fügen Sie es auf die `CButton` Objekt.  
  
 Konstruktion kann ein langwieriger Vorgang in einer abgeleiteten Klasse `CButton`. Schreiben Sie einen Konstruktor für die abgeleitete Klasse und rufen **erstellen** von innerhalb des Konstruktors.  
  
 Wenn Sie ein Button-Steuerelement an sein übergeordnetes Element per Windows-Benachrichtigung behandeln möchten (in der Regel eine abgeleitete Klasse [CDialog](../../mfc/reference/cdialog-class.md)), die übergeordnete Klasse für jede Nachricht eine meldungszuordnung Eintrag und Meldungshandler Memberfunktion hinzugefügt.  
  
 Jede Meldungszuordnungseintrags hat das folgende Format:  
  
 **ON_**Notification **(**`id`, `memberFxn`**)**  
  
 wobei `id` gibt die untergeordneten Fenster-ID des Steuerelements, das die Benachrichtigung gesendet und `memberFxn` ist der Name der übergeordneten Member-Funktion, die Sie geschrieben haben, um die Benachrichtigung zu verarbeiten.  
  
 Das übergeordnete Funktionsprototyp lautet wie folgt:  
  
 **afx_msg** `void` `memberFxn` **( );**  
  
 Potenzielle Meldungszuordnungseinträge lauten wie folgt:  
  
|Eintrag für die Zuordnung|Wenn übergeordnete gesendet...|  
|---------------|----------------------------|  
|**ON_BN_CLICKED**|Der Benutzer klickt auf eine Schaltfläche.|  
|**ON_BN_DOUBLECLICKED**|Der Benutzer auf eine Schaltfläche doppelklickt.|  
  
 Bei der Erstellung einer `CButton` Objekt aus einer Ressource, die `CButton` Objekt wird automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Wenn Sie erstellen ein `CButton` -Objekt innerhalb eines Fensters müssen Sie möglicherweise zerstört. Bei der Erstellung der `CButton` Objekt auf dem Heap mithilfe der **neue** -Funktion, die Sie aufrufen müssen **löschen** auf das Objekt, das es zerstört, wenn der Benutzer Windows schließt Schaltflächensteuerelement. Bei der Erstellung der `CButton` Objekt auf dem Stapel oder im übergeordneten Dialogfeldobjekt eingebettet ist, wird automatisch zerstört.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CButton`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="a-namecbuttona--cbuttoncbutton"></a><a name="cbutton"></a>CButton::CButton  
 Erstellt ein `CButton`-Objekt.  
  
```  
CButton();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton&#1;](../../mfc/reference/codesnippet/cpp/cbutton-class_1.cpp)]  
  
##  <a name="a-namecreatea--cbuttoncreate"></a><a name="create"></a>CButton::Create  
 Das Windows-Schaltflächen-Steuerelement erstellt, und fügt es der `CButton` Objekt.  
  
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
 Gibt das Schaltflächen-Steuerelement-Stil. Wenden Sie eine beliebige Kombination von [Schaltfläche](../../mfc/reference/button-styles.md) auf die Schaltfläche.  
  
 `rect`  
 Gibt des Schaltflächen-Steuerelements Größe und Position. Es kann entweder eine `CRect` Objekt oder eine `RECT` Struktur.  
  
 `pParentWnd`  
 Gibt an, das Schaltflächen-Steuerelement des übergeordneten Fensters, in der Regel eine `CDialog`. Er darf nicht sein **NULL**.  
  
 `nID`  
 Gibt das Schaltflächen-Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen ein `CButton` Objekt in zwei Schritten. Zunächst rufen Sie den Konstruktor, und rufen Sie dann **erstellen**, die das Windows-Schaltflächen-Steuerelement erstellt, und fügt es der `CButton` Objekt.  
  
 Wenn die **WS_VISIBLE** Stil angegeben, Windows dem Schaltflächen-Steuerelement sendet alle Nachrichten, die für die Aktivierung und die Schaltfläche "anzeigen".  
  
 Übernehmen Sie das folgende [Fensterstile](../../mfc/reference/window-styles.md) auf ein Schaltflächen-Steuerelement:  
  
- **WS_CHILD** immer  
  
- **WS_VISIBLE** in der Regel  
  
- **WS_DISABLED** selten  
  
- **WS_GROUP** zum Gruppieren von Steuerelementen  
  
- **WS_TABSTOP** die Schaltfläche in der Tabulatorreihenfolge eingeschlossen werden soll.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton&#2;](../../mfc/reference/codesnippet/cpp/cbutton-class_2.cpp)]  
  
##  <a name="a-namedrawitema--cbuttondrawitem"></a><a name="drawitem"></a>CButton::DrawItem  
 Vom Framework aufgerufen, wenn sich ein Darstellungsaspekt einer Ownerdrawn-Schaltfläche geändert hat.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDrawItemStruct`  
 Ein long-Zeiger auf eine [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) Struktur. Die Struktur enthält Informationen über das Element gezeichnet werden und den Typ der Zeichnung, die erforderlich sind.  
  
### <a name="remarks"></a>Hinweise  
 Eine Ownerdrawn Schaltfläche verfügt über die **BS_OWNERDRAW** Set formatieren. Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für eine Ownerdrawn- `CButton` Objekt. Die Anwendung sollte alle Grafiken Device Interface (GDI) Objekte ausgewählt, für der Anzeigekontext im angegebenen wiederherstellen `lpDrawItemStruct` vor dem Element Funktion beendet wird.  
  
 Siehe auch die [BS_](../../mfc/reference/button-styles.md) Stilwerte.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton&3;](../../mfc/reference/codesnippet/cpp/cbutton-class_3.cpp)]  
  
##  <a name="a-namegetbitmapa--cbuttongetbitmap"></a><a name="getbitmap"></a>CButton::GetBitmap  
 Rufen Sie diese Memberfunktion, um das Handle einer Bitmap mit zuvor festgelegten abrufen [SetBitmap](#setbitmap), d. h. eine Schaltfläche zugeordnet.  
  
```  
HBITMAP GetBitmap() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für eine Bitmap. **NULL** falls zuvor keine Bitmap angegeben ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton&4;](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]  
  
##  <a name="a-namegetbuttonstylea--cbuttongetbuttonstyle"></a><a name="getbuttonstyle"></a>CButton::GetButtonStyle  
 Ruft Informationen zu den Schaltflächenstil-Steuerelement.  
  
```  
UINT GetButtonStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Schaltflächenstile für diesen `CButton` Objekt. Diese Funktion gibt nur die [BS_](../../mfc/reference/button-styles.md) Style-Werte, keine der anderen Fenster.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton&5;](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]  
  
##  <a name="a-namegetchecka--cbuttongetcheck"></a><a name="getcheck"></a>CButton::GetCheck  
 Ruft den Aktivierungszustand des ein Optionsfeld oder Kontrollkästchen.  
  
```  
int GetCheck() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert ein Schaltflächen-Steuerelement erstellt, mit der **BS_AUTOCHECKBOX**, **BS_AUTORADIOBUTTON**, **BS_AUTO3STATE**, **BS_CHECKBOX**, **BS_RADIOBUTTON**, oder **BS_3STATE** Stil ist einer der folgenden Werte:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|**BST_UNCHECKED**|Status der Schaltfläche ist deaktiviert.|  
|**BST_CHECKED**|Status wird überprüft.|  
|**BST_INDETERMINATE**|Status unbestimmt ist (gilt nur, wenn die Schaltfläche den **BS_3STATE** oder **BS_AUTO3STATE** Stil).|  
  
 Wenn die Schaltfläche andere verfügt, wird der Rückgabewert ist **BST_UNCHECKED**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton&6;](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]  
  
##  <a name="a-namegetcursora--cbuttongetcursor"></a><a name="getcursor"></a>CButton::GetCursor  
 Rufen Sie diese Memberfunktion, um das Handle eines Cursors mit zuvor festgelegten abrufen [SetCursor](#setcursor), d. h. eine Schaltfläche zugeordnet.  
  
```  
HCURSOR GetCursor();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für ein Cursorbild. **NULL** Wenn zuvor kein Cursor angegeben wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton&#7;](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]  
  
##  <a name="a-namegeticona--cbuttongeticon"></a><a name="geticon"></a>CButton::GetIcon  
 Rufen Sie diese Memberfunktion, um das Handle für ein Symbol, das zuvor mit festgelegten erhalten [SetIcon](#seticon), d. h. eine Schaltfläche zugeordnet.  
  
```  
HICON GetIcon() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für ein Symbol. **NULL** Wenn zuvor kein Symbol angegeben wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton&#8;](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]  
  
##  <a name="a-namegetidealsizea--cbuttongetidealsize"></a><a name="getidealsize"></a>CButton::GetIdealSize  
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
 Diese Memberfunktion emuliert die Funktionen der der **BCM_GETIDEALSIZE** angezeigt, wie in beschrieben die [Schaltflächen](http://msdn.microsoft.com/library/windows/desktop/bb775943) Teil der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetimagelista--cbuttongetimagelist"></a><a name="getimagelist"></a>CButton::GetImageList  
 Rufen Sie diese Methode zum Abrufen der Liste der Images aus dem Schaltflächen-Steuerelement.  
  
```  
BOOL GetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```  
  
### <a name="parameters"></a>Parameter  
 `pbuttonImagelist`  
 Ein Zeiger auf die Bildliste des der `CButton` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen der der **BCM_GETIMAGELIST** angezeigt, wie in beschrieben die [Schaltflächen](http://msdn.microsoft.com/library/windows/desktop/bb775943) Teil der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetnotea--cbuttongetnote"></a><a name="getnote"></a>CButton::GetNote  
 Ruft den Text als Notiz ein Steuerelement der aktuellen Verbindung zugeordnet.  
  
```  
CString GetNote() const;  
  
BOOL GetNote(
    LPTSTR lpszNote,   
    UINT* cchNote) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] `lpszNote`|Ein Zeiger auf einen Puffer, die der Aufrufer für das zuordnen und Freigeben von zuständig ist. Wenn der Rückgabewert ist `true`, enthält der Text als Notiz ein, die dem aktuellen Befehl Link-Steuerelement zugeordnet ist, andernfalls ist der Puffer, der Puffer ist unverändert.|  
|[in, out] `cchNote`|Ein Zeiger auf eine Ganzzahl-Variable.<br /><br /> Wenn diese Methode aufgerufen wird, wird die Variable enthält die Größe des angegebenen Puffers die `lpszNote` Parameter.<br /><br /> Wenn diese Methode zurückgegeben, wenn der Rückgabewert ist `true` die Variable enthält die Größe der Notiz Steuerelement der aktuellen Verbindung zugeordnet. Wenn der Rückgabewert ist `false`, die Variable enthält den Hinweis enthalten erforderliche Puffergröße.|  
  
### <a name="return-value"></a>Rückgabewert  
 In der ersten Überladung ist ein [CString](../../atl-mfc-shared/using-cstring.md) -Objekt, das die dem aktuellen Befehl Link-Steuerelement zugeordnete Text als Notiz ein enthält.  
  
 - oder -   
  
 In der zweiten Überladung ist `true` Wenn diese Methode erfolgreich; andernfalls ist `false`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenstil ist `BS_COMMANDLINK` oder `BS_DEFCOMMANDLINK`.  
  
 Diese Methode sendet die [BCM_GETNOTE](http://msdn.microsoft.com/library/windows/desktop/bb775965) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetnotelengtha--cbuttongetnotelength"></a><a name="getnotelength"></a>CButton::GetNoteLength  
 Ruft die Länge des Texts Hinweis für den aktuellen Befehl Link-Steuerelement ab.  
  
```  
UINT GetNoteLength() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge des Texts Hinweis in 16-Bit-Unicode-Zeichen für den aktuellen Befehl Link-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenstil ist `BS_COMMANDLINK` oder `BS_DEFCOMMANDLINK`.  
  
 Diese Methode sendet die [BCM_GETNOTELENGTH](http://msdn.microsoft.com/library/windows/desktop/bb775967) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetsplitglypha--cbuttongetsplitglyph"></a><a name="getsplitglyph"></a>CButton::GetSplitGlyph  
 Ruft das Symbol, das das aktuelle SplitButton-Steuerelement zugeordnet.  
  
```  
TCHAR GetSplitGlyph() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Symbol-Zeichen, das das aktuelle SplitButton-Steuerelement zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Ein Symbol ist die physische Darstellung eines Zeichens in einer bestimmten Schriftart. Beispielsweise kann ein Trennschaltflächen-Steuerelement ergänzt werden, durch das Symbol des Häkchen Unicode-Zeichens (U +&2713;).  
  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenstil ist `BS_SPLITBUTTON` oder `BS_DEFSPLITBUTTON`.  
  
 Diese Methode initialisiert die `mask` Mitglied einer [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) Struktur mit der `BCSIF_GLYPH` Flag und dann sendet, die Struktur in der [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Bei Rückgabe der Funktion Nachricht ruft diese Methode das Symbol aus der `himlGlyph` Member der Struktur.  
  
##  <a name="a-namegetsplitimagelista--cbuttongetsplitimagelist"></a><a name="getsplitimagelist"></a>CButton::GetSplitImageList  
 Ruft die [Bildliste](../../mfc/reference/cimagelist-class.md) für das aktuelle SplitButton-Steuerelement.  
  
```  
CImageList* GetSplitImageList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenstil ist `BS_SPLITBUTTON` oder `BS_DEFSPLITBUTTON`.  
  
 Diese Methode initialisiert die `mask` Mitglied einer [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) Struktur mit der `BCSIF_IMAGE` Flag und dann sendet, die Struktur in der [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Gibt die Nachricht-Funktion ruft diese Methode die Bildliste aus der `himlGlyph` Member der Struktur.  
  
##  <a name="a-namegetsplitinfoa--cbuttongetsplitinfo"></a><a name="getsplitinfo"></a>CButton::GetSplitInfo  
 Ruft Parameter, die bestimmen, wie das aktuelle SplitButton-Steuerelement von Windows gezeichnet.  
  
```  
BOOL GetSplitInfo(PBUTTON_SPLITINFO pInfo) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] `pInfo`|Zeiger auf eine [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) -Struktur, die Informationen über das aktuelle SplitButton-Steuerelement empfängt. Der Aufrufer ist verantwortlich für die Zuordnung von der Struktur.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenstil ist `BS_SPLITBUTTON` oder `BS_DEFSPLITBUTTON`.  
  
 Diese Methode sendet die [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetsplitsizea--cbuttongetsplitsize"></a><a name="getsplitsize"></a>CButton::GetSplitSize  
 Ruft das umschließende Rechteck der Dropdown-Komponente von der aktuellen SplitButton-Steuerelement ab.  
  
```  
BOOL GetSplitSize(LPSIZE pSize) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] `pSize`|Zeiger auf eine [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) -Struktur, die die Beschreibung eines Rechtecks empfängt.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenstil ist `BS_SPLITBUTTON` oder `BS_DEFSPLITBUTTON`.  
  
 Wenn das SplitButton-Steuerelement erweitert ist, können sie eine Dropdown-Komponente wie z. B. ein Listensteuerelement oder Pager-Steuerelement anzeigen. Diese Methode ruft das umschließende Rechteck, das Dropdown-Komponente enthält.  
  
 Diese Methode initialisiert die `mask` Mitglied einer [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) Struktur mit der `BCSIF_SIZE` Flag und dann sendet, die Struktur in der [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Gibt die Nachricht-Funktion ruft diese Methode das umschließende Rechteck von der `size` Member der Struktur.  
  
##  <a name="a-namegetsplitstylea--cbuttongetsplitstyle"></a><a name="getsplitstyle"></a>CButton::GetSplitStyle  
 Ruft die Split-Button-Stile, die das aktuelle SplitButton-Steuerelement zu definieren.  
  
```  
UINT GetSplitStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine bitweise Kombination der Split-Schaltflächenstile. Weitere Informationen finden Sie unter der `uSplitStyle` Mitglied der [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenstil ist `BS_SPLITBUTTON` oder `BS_DEFSPLITBUTTON`.  
  
 Die Split-Schaltflächenstile geben Ausrichtung, Seitenverhältnis und Grafikformat mit dem Windows eine Split-Schaltflächensymbol gezeichnet.  
  
 Diese Methode initialisiert die `mask` Mitglied einer [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) Struktur mit der `BCSIF_STYLE` Flag und dann sendet, die Struktur in der [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Gibt die Nachricht-Funktion wird diese Methode ruft die Split-Schaltflächenstile aus der `uSplitStyle` Member der Struktur.  
  
##  <a name="a-namegetstatea--cbuttongetstate"></a><a name="getstate"></a>CButton::GetState  
 Ruft den Zustand eines Steuerelements.  
  
```  
UINT GetState() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Bitfeld, die die Kombination der Werte enthält, die den aktuellen Status eines Steuerelements angeben. In der folgenden Tabelle sind die möglichen Werte aufgeführt.  
  
|Status|Wert|Beschreibung|  
|------------------|-----------|-----------------|  
|`BST_UNCHECKED`|0x0000|Der ursprüngliche Status.|  
|`BST_CHECKED`|0 x&0001;|Das Schaltflächen-Steuerelement aktiviert ist.|  
|`BST_INDETERMINATE`|0 x&0002;|Der Status ist unbestimmt (nur möglich, wenn das Schaltflächen-Steuerelement drei Zustände aufweisen).|  
|`BST_PUSHED`|0 x&0004;|Das Schaltflächen-Steuerelement geklickt wird.|  
|`BST_FOCUS`|0 x&0008;|Das Schaltflächen-Steuerelement besitzt den Fokus.|  
  
### <a name="remarks"></a>Hinweise  
 Ein Schaltflächen-Steuerelement mit dem `BS_3STATE` oder `BS_AUTO3STATE` Schaltflächenstil erstellt ein Kontrollkästchen mit dem dritten Zustand mit dem Namen unbestimmten Zustand. Unbestimmte Zustand gibt an, dass das Kontrollkästchen weder aktiviert noch deaktiviert ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton&#9;](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]  
  
##  <a name="a-namegettextmargina--cbuttongettextmargin"></a><a name="gettextmargin"></a>CButton::GetTextMargin  
 Rufen Sie diese Methode zum Abrufen der Rand des von der `CButton` Objekt.  
  
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
 Diese Memberfunktion emuliert die Funktionen der der **BCM_GETTEXTMARGIN** angezeigt, wie in beschrieben die [Schaltflächen](http://msdn.microsoft.com/library/windows/desktop/bb775943) Teil der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetbitmapa--cbuttonsetbitmap"></a><a name="setbitmap"></a>CButton:: SetBitmap  
 Rufen Sie diese Memberfunktion auf die Schaltfläche eine neue Bitmap zuordnen.  
  
```  
HBITMAP SetBitmap(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>Parameter  
 `hBitmap`  
 Das Handle einer Bitmap.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle einer Bitmap, die zuvor mit der Schaltfläche zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Die Bitmap wird auf der Schaltfläche zentriert wird standardmäßig automatisch eingefügt. Wenn die Bitmap für die Schaltfläche zu groß ist, wird es auf einer Seite abgeschnitten. Sie können andere Ausrichtungsoptionen, einschließlich der folgenden:  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 Im Gegensatz zu [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), die vier Bitmaps pro Schaltfläche verwendet `SetBitmap` wird nur eine Bitmap pro der Schaltfläche verwendet. Wenn die Schaltfläche gedrückt wird, wird die Bitmap nach unten und rechts verschoben angezeigt.  
  
 Sie sind verantwortlich für die Bitmap freigeben, wenn Sie damit fertig sind.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton&4;](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]  
  
##  <a name="a-namesetbuttonstylea--cbuttonsetbuttonstyle"></a><a name="setbuttonstyle"></a>CButton::SetButtonStyle  
 Ändert den Stil einer Schaltfläche.  
  
```  
void SetButtonStyle(
    UINT nStyle,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nStyle`  
 Gibt die [Schaltfläche Stil](../../mfc/reference/button-styles.md).  
  
 `bRedraw`  
 Gibt an, ob die Schaltfläche neu gezeichnet wird. Ein Wert ungleich NULL zeichnet die Schaltfläche neu. Wert 0 ist nicht die Schaltfläche neu zeichnen. Die Schaltfläche wird standardmäßig neu gezeichnet.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `GetButtonStyle` Member-Funktion, um den Schaltflächenstil abzurufen. Das niederwertige Wort von der vollständigen Schaltflächenstil ist die Schaltfläche-spezifisches Format.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton&5;](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]  
  
##  <a name="a-namesetchecka--cbuttonsetcheck"></a><a name="setcheck"></a>CButton::SetCheck  
 Legt fest oder setzt den Aktivierungszustand des ein Optionsfeld oder Kontrollkästchen.  
  
```  
void SetCheck(int nCheck);
```  
  
### <a name="parameters"></a>Parameter  
 `nCheck`  
 Gibt den Status überprüfen. Dieser Parameter kann einen der folgenden sein:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|**BST_UNCHECKED**|Legen Sie den Zustand der Schaltfläche auf deaktiviert.|  
|**BST_CHECKED**|Legen Sie den Zustand der Schaltfläche aktiviert.|  
|**BST_INDETERMINATE**|Legen Sie den Zustand der Schaltfläche einem unbestimmten Zustand. Dieser Wert kann verwendet werden, nur, wenn die Schaltfläche den **BS_3STATE** oder **BS_AUTO3STATE** Stil.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion hat keine Auswirkung auf eine Schaltfläche.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton&6;](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]  
  
##  <a name="a-namesetcursora--cbuttonsetcursor"></a><a name="setcursor"></a>CButton::SetCursor  
 Rufen Sie diese Memberfunktion, um einen neuen Cursor mit der Schaltfläche verknüpfen.  
  
```  
HCURSOR SetCursor(HCURSOR hCursor);
```  
  
### <a name="parameters"></a>Parameter  
 `hCursor`  
 Das Handle des Cursors.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle eines Cursors, der zuvor mit der Schaltfläche zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Der Cursor wird auf der Schaltfläche zentriert wird standardmäßig automatisch eingefügt. Wenn der Cursor für die Schaltfläche zu groß ist, wird es auf einer Seite abgeschnitten. Sie können andere Ausrichtungsoptionen, einschließlich der folgenden:  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 Im Gegensatz zu [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), die vier Bitmaps pro Schaltfläche verwendet `SetCursor` pro die Schaltfläche nur ein Cursor verwendet. Wenn die Schaltfläche gedrückt wird, wird der Cursor nach unten und rechts verschoben angezeigt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton&#7;](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]  
  
##  <a name="a-namesetdropdownstatea--cbuttonsetdropdownstate"></a><a name="setdropdownstate"></a>CButton::SetDropDownState  
 Legt die Dropdown-Status der aktuellen SplitButton-Steuerelement fest.  
  
```  
BOOL SetDropDownState(BOOL fDropDown);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `fDropDown`|`true`festzulegende `BST_DROPDOWNPUSHED` Zustand befindet, andernfalls `false`.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Ein Trennschaltflächen-Steuerelement hat eine `BS_SPLITBUTTON` oder `BS_DEFSPLITBUTTON` und besteht aus einer Schaltfläche und ein Dropdown-Pfeil rechts davon. Weitere Informationen finden Sie unter [Schaltflächenstile](http://msdn.microsoft.com/library/windows/desktop/bb775951). In der Regel wird die Dropdown-Liste Status festgelegt, klickt der Benutzer auf den Dropdown Pfeil. Verwenden Sie diese Methode zum programmgesteuerten Festlegen des Zustands der Dropdown-Liste des Steuerelements. Die Dropdown-Pfeil gezeichnet wird schattiert dargestellt, um den Status anzuzeigen.  
  
 Diese Methode sendet die [BCM_SETDROPDOWNSTATE](http://msdn.microsoft.com/library/windows/desktop/bb775973) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_splitButton`, d. h. verwendet, um programmgesteuert auf das SplitButton-Steuerelement zugreifen. Im folgenden Beispiel wird diese Variable verwendet.  
  
 [!code-cpp[NVC_MFC_CButton_s&#1;1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel legt fest, den Zustand der das SplitButton-Steuerelement an, dass der Dropdownpfeil übertragen wird.  
  
 [!code-cpp[NVC_MFC_CButton_s1&6;](../../mfc/reference/codesnippet/cpp/cbutton-class_11.cpp)]  
  
##  <a name="a-namesetelevationrequireda--cbuttonsetelevationrequired"></a><a name="setelevationrequired"></a>CButton::SetElevationRequired  
 Legt den Zustand des aktuellen Button-Steuerelements, `elevation required`, der für das Steuerelement zum Anzeigen eines Symbols erhöhter Sicherheit erforderlich ist.  
  
```  
BOOL SetElevationRequired(BOOL fElevationRequired);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `fElevationRequired`|`true`festzulegende `elevation required` Zustand befindet, andernfalls `false`.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Schaltfläche oder Link-Steuerelement erhöhten Sicherheitsberechtigungen zum Ausführen einer Aktion erforderlich ist, legen Sie das Steuerelement zum `elevation required` Zustand. Anschließend zeigt Windows die Benutzerkontensteuerung (UAC) Shield-Symbol für das Steuerelement. Weitere Informationen finden Sie unter "User Account Control" [MSDN](http://go.microsoft.com/fwlink/linkid=18507).  
  
 Diese Methode sendet die [BCM_SETSHIELD](http://msdn.microsoft.com/library/windows/desktop/bb775979) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameseticona--cbuttonseticon"></a><a name="seticon"></a>CButton::SetIcon  
 Rufen Sie diese Memberfunktion, um ein neues Symbol der Schaltfläche zuordnen.  
  
```  
HICON SetIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>Parameter  
 `hIcon`  
 Das Handle eines Symbols.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle eines zuvor mit der Schaltfläche verknüpften Symbols.  
  
### <a name="remarks"></a>Hinweise  
 Das Symbol wird auf der Schaltfläche zentriert wird standardmäßig automatisch eingefügt. Wenn das Symbol für die Schaltfläche zu groß ist, wird es auf einer Seite abgeschnitten. Sie können andere Ausrichtungsoptionen, einschließlich der folgenden:  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 Im Gegensatz zu [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), die vier Bitmaps pro Schaltfläche verwendet `SetIcon` nur ein Symbol pro der Schaltfläche verwendet. Wenn die Schaltfläche gedrückt wird, wird das Symbol nach unten und nach rechts verschoben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton&#8;](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]  
  
##  <a name="a-namesetimagelista--cbuttonsetimagelist"></a><a name="setimagelist"></a>CButton::SetImageList  
 Rufen Sie diese Methode, um die Bildliste des legen die `CButton` Objekt.  
  
```  
BOOL SetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```  
  
### <a name="parameters"></a>Parameter  
 `pbuttonImagelist`  
 Ein Zeiger auf die neue Bildliste.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen der der **BCM_SETIMAGELIST** angezeigt, wie in beschrieben die [Schaltflächen](http://msdn.microsoft.com/library/windows/desktop/bb775943) Teil der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetnotea--cbuttonsetnote"></a><a name="setnote"></a>CButton::SetNote  
 Wird der Hinweis für den aktuellen Befehl Link-Steuerelement.  
  
```  
BOOL SetNote(LPCTSTR lpszNote);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `lpszNote`|Ein Zeiger auf eine Unicode-Zeichenfolge, die als Hinweis Text für das Link-Steuerelement festgelegt wird.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenstil ist `BS_COMMANDLINK` oder `BS_DEFCOMMANDLINK`.  
  
 Diese Methode sendet die [BCM_SETNOTE](http://msdn.microsoft.com/library/windows/desktop/bb775977) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_cmdLink`, d. h. verwendet, um programmgesteuert auf das Link-Steuerelement zugreifen. Im folgenden Beispiel wird diese Variable verwendet.  
  
 [!code-cpp[NVC_MFC_CButton_s&#1;1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel legt den Hinweis Text für das Link-Steuerelement fest.  
  
 [!code-cpp[NVC_MFC_CButton_s&#1;7](../../mfc/reference/codesnippet/cpp/cbutton-class_12.cpp)]  
  
##  <a name="a-namesetsplitglypha--cbuttonsetsplitglyph"></a><a name="setsplitglyph"></a>CButton::SetSplitGlyph  
 Ordnet einen angegebenen Symbol das aktuelle SplitButton-Steuerelement.  
  
```  
BOOL SetSplitGlyph(TCHAR chGlyph);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `chGlyph`|Ein Zeichen, das das Symbol für die Verwendung als Dropdown-Pfeil der Split angibt.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, die den Schaltflächenstil `BS_SPLITBUTTON` oder `BS_DEFSPLITBUTTON`.  
  
 Ein Symbol ist die physische Darstellung eines Zeichens in einer bestimmten Schriftart. Die `chGlyph`Parameter wird nicht als das Symbol verwendet, jedoch wird stattdessen verwendet werden, um ein Symbol aus einem Satz von vordefinierten Symbolen auswählen. Das Standardsymbol für das Dropdown-Pfeil wird durch das Zeichen '6' angegeben und das Unicode-Zeichen Schwarz nach unten ZEIGENDEN DREIECK (U +&25;BC) ähnelt.  
  
 Diese Methode initialisiert die `mask` Mitglied eine [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) Struktur mit der `BCSIF_GLYPH` Flag und `himlGlyph` Member mit der `chGlyph` übergeben wird, und sendet, die Struktur in der [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetsplitimagelista--cbuttonsetsplitimagelist"></a><a name="setsplitimagelist"></a>CButton::SetSplitImageList  
 Ordnet eine [Bildliste](../../mfc/reference/cimagelist-class.md) mit der aktuellen SplitButton-Steuerelement.  
  
```  
BOOL SetSplitImageList(CImageList* pSplitImageList);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `pSplitImageList`|Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) Objekt, das das aktuelle SplitButton-Steuerelement zugewiesen.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenstil ist `BS_SPLITBUTTON` oder `BS_DEFSPLITBUTTON`.  
  
 Diese Methode initialisiert die `mask` Mitglied eine [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) Struktur mit der `BCSIF_IMAGE` Flag und `himlGlyph` Member mit der `pSplitImageList` übergeben wird, und sendet, die Struktur in der [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetsplitinfoa--cbuttonsetsplitinfo"></a><a name="setsplitinfo"></a>CButton::SetSplitInfo  
 Gibt Parameter an, die bestimmen, wie das aktuelle SplitButton-Steuerelement von Windows gezeichnet.  
  
```  
BOOL SetSplitInfo(PBUTTON_SPLITINFO pInfo);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `pInfo`|Zeiger auf eine [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) -Struktur, die das aktuelle SplitButton-Steuerelement definiert.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenstil ist `BS_SPLITBUTTON` oder `BS_DEFSPLITBUTTON`.  
  
 Diese Methode sendet die [BCM_SETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775981) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_splitButton`, d. h. verwendet, um programmgesteuert auf das SplitButton-Steuerelement zugreifen.  
  
 [!code-cpp[NVC_MFC_CButton_s&#1;1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird ändert sich das Symbol, das für die Split Dropdown-Pfeil verwendet wird. Das Beispiel ersetzt ein oben zeigenden Dreieck ein Symbol für den nach unten zeigenden Dreieck Standardsymbol. Das Symbol, das angezeigt wird, hängt das Zeichen, das Sie, in angeben der `himlGlyph` Mitglied der `BUTTON_SPLITINFO` Struktur. Das nach unten zeigenden Dreieck-Symbol wird angegeben, indem ein Zeichen '&6; 'und das oben zeigenden Dreieck-Symbol wird angegeben, indem ein Zeichen '&5;'. Vergleich finden Sie in der Hilfsmethode [CButton::SetSplitGlyph](#setsplitglyph).  
  
 [!code-cpp[NVC_MFC_CButton_s1&4;](../../mfc/reference/codesnippet/cpp/cbutton-class_13.cpp)]  
  
##  <a name="a-namesetsplitsizea--cbuttonsetsplitsize"></a><a name="setsplitsize"></a>CButton::SetSplitSize  
 Legt das umschließende Rechteck der Dropdown-Komponente von der aktuellen SplitButton-Steuerelement fest.  
  
```  
BOOL SetSplitSize(LPSIZE pSize);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `pSize`|Zeiger auf eine [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur, die ein umschließendes Rechteck beschreibt.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenstil ist `BS_SPLITBUTTON` oder `BS_DEFSPLITBUTTON`.  
  
 Wenn das SplitButton-Steuerelement erweitert ist, können sie eine Dropdown-Komponente wie z. B. ein Listensteuerelement oder Pager-Steuerelement anzeigen. Diese Methode gibt die Größe des umschließenden Rechtecks, das Dropdown-Komponente enthält.  
  
 Diese Methode initialisiert die `mask` Mitglied eine [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) Struktur mit der `BCSIF_SIZE` Flag und `size` Member mit der `pSize` übergeben wird, und sendet, die Struktur in der [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_splitButton`, d. h. verwendet, um programmgesteuert auf das SplitButton-Steuerelement zugreifen. Im folgenden Beispiel wird diese Variable verwendet.  
  
 [!code-cpp[NVC_MFC_CButton_s&#1;1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die Größe des Dropdown-Pfeil der geteilten verdoppelt.  
  
 [!code-cpp[NVC_MFC_CButton_s1&5;](../../mfc/reference/codesnippet/cpp/cbutton-class_14.cpp)]  
  
##  <a name="a-namesetsplitstylea--cbuttonsetsplitstyle"></a><a name="setsplitstyle"></a>CButton::SetSplitStyle  
 Legt den Stil für das aktuelle SplitButton-Steuerelement.  
  
```  
BOOL SetSplitStyle(UINT uSplitStyle);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `uSplitStyle`|Eine bitweise Kombination der Split-Schaltflächenstile. Weitere Informationen finden Sie unter der `uSplitStyle` Mitglied der [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) Struktur.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur für Steuerelemente, deren Schaltflächenstil ist `BS_SPLITBUTTON` oder `BS_DEFSPLITBUTTON`.  
  
 Die Split-Schaltflächenstile geben Ausrichtung, Seitenverhältnis und Grafikformat mit dem Windows eine Split-Schaltflächensymbol gezeichnet. Weitere Informationen finden Sie unter der `uSplitStyle` Mitglied der [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) Struktur.  
  
 Diese Methode initialisiert die `mask` Mitglied eine [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) Struktur mit der `BCSIF_STYLE` Flag und `uSplitStyle` Member mit der `uSplitStyle` übergeben wird, und sendet, die Struktur in der [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_splitButton`, d. h. verwendet, um programmgesteuert auf das SplitButton-Steuerelement zugreifen.  
  
 [!code-cpp[NVC_MFC_CButton_s&#1;1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird das Format des Dropdown-Pfeil der Split. Die `BCSS_ALIGNLEFT` Stil zeigt den Pfeil auf der linken Seite der Schaltfläche, und die `BCSS_STRETCH` Stil behält den Dropdown-Pfeil Proportionen beim Ändern der Größe der Schaltfläche.  
  
 [!code-cpp[NVC_MFC_CButton_s1&3;](../../mfc/reference/codesnippet/cpp/cbutton-class_15.cpp)]  
  
##  <a name="a-namesetstatea--cbuttonsetstate"></a><a name="setstate"></a>CButton::SetState  
 Legt fest, ob ein Schaltflächen-Steuerelement hervorgehoben ist.  
  
```  
void SetState(BOOL bHighlight);
```  
  
### <a name="parameters"></a>Parameter  
 *bHighlight*  
 Gibt an, ob die Schaltfläche hervorgehoben werden. Ein Wert ungleich NULL hebt die Schaltfläche; ein Wert von 0 entfernt Hervorhebung.  
  
### <a name="remarks"></a>Hinweise  
 Hervorhebung und wirkt sich auf der Außenseite des einem Schaltflächen-Steuerelement. Es wirkt sich nicht auf den Aktivierungszustand des ein Kontrollkästchen oder ein Optionsfeld aus.  
  
 Ein Button-Steuerelement wird automatisch markiert, wenn der Benutzer klickt und die linke Maustaste gedrückt hält. Die Hervorhebung wird entfernt, wenn der Benutzer die Maustaste loslässt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CButton&#9;](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]  
  
##  <a name="a-namesettextmargina--cbuttonsettextmargin"></a><a name="settextmargin"></a>CButton::SetTextMargin  
 Rufen Sie diese Methode zum Festlegen der Rand des von der `CButton` Objekt.  
  
```  
BOOL SetTextMargin(RECT* pmargin);
```  
  
### <a name="parameters"></a>Parameter  
 `pmargin`  
 Ein Zeiger auf den Rand des neuen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, bei Erfolg, bei einem Fehler FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen der der **BCM_SETTEXTMARGIN** angezeigt, wie in beschrieben die [Schaltflächen](http://msdn.microsoft.com/library/windows/desktop/bb775943) Teil der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
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

