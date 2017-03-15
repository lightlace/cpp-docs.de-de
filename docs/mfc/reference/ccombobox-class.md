---
title: CComboBox-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComboBox
dev_langs:
- C++
helpviewer_keywords:
- combo boxes, CComboBox objects
- CComboBox class
ms.assetid: 4e73b5df-0d2e-4658-9706-38133fb10513
caps.latest.revision: 25
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
ms.openlocfilehash: 5328c245e0d662c4701042b37c16870d6b1e33c7
ms.lasthandoff: 02/24/2017

---
# <a name="ccombobox-class"></a>CComboBox-Klasse
Stellt die Funktionalität eines Windows-Kombinationsfelds bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CComboBox : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComboBox::CComboBox](#ccombobox)|Erstellt ein `CComboBox`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComboBox:: AddString](#addstring)|Fügt eine Zeichenfolge am Ende der Liste im Listenfeld eines Kombinationsfelds oder Position in der sortierten von Listenfeldern mit dem **CBS_SORT** Stil.|  
|[CComboBox::Clear](#clear)|Löscht (deaktiviert) die aktuelle Auswahl und ggf. in das Bearbeitungssteuerelement.|  
|[CComboBox::CompareItem](#compareitem)|Aufgerufen, um die relative Position eines neuen Listenelements in einem sortierten Ownerdrawn-Kombinationsfeld zu bestimmen.|  
|[CComboBox::Copy](#copy)|Kopiert die aktuelle Auswahl und gegebenenfalls in die Zwischenablage in **CF_TEXT** Format.|  
|[CComboBox::Create](#create)|Das Kombinationsfeld erstellt, und fügt es der `CComboBox` Objekt.|  
|[CComboBox::Cut](#cut)|(Teilstücke) Löscht die aktuelle Auswahl, sofern zutreffend, bearbeiten steuern und den gelöschten Text in die Zwischenablage in kopiert **CF_TEXT** Format.|  
|[CComboBox::DeleteItem](#deleteitem)|Vom Framework aufgerufen, wenn ein Listenelement in einem Ownerdrawn-Kombinationsfeld gelöscht wird.|  
|[CComboBox::DeleteString](#deletestring)|Löscht eine Zeichenfolge aus dem Listenfeld eines Kombinationsfelds an.|  
|[CComboBox::Dir](#dir)|Eine Liste von Dateinamen hinzugefügt in das Listenfeld eines Kombinationsfelds.|  
|[CComboBox::DrawItem](#drawitem)|Aufgerufen, wenn sich ein Darstellungsaspekt einer Ownerdrawn-Kombinationsfeld ändert.|  
|[CComboBox:: FindString](#findstring)|Sucht die erste Zeichenfolge, die das angegebene Präfix im Listenfeld eines Kombinationsfelds enthält.|  
|[CComboBox::FindStringExact](#findstringexact)|Sucht die erste Listenfeld Zeichenfolge (in ein Kombinationsfeld) mit der angegebene Zeichenfolge übereinstimmt.|  
|[CComboBox::GetComboBoxInfo](#getcomboboxinfo)|Ruft Informationen über die `CComboBox` Objekt.|  
|[CComboBox::GetCount](#getcount)|Ruft die Anzahl der Elemente im Listenfeld eines Kombinationsfelds ab.|  
|[CComboBox::GetCueBanner](#getcuebanner)|Ruft den Hinweistext, der angezeigt wird, für ein Kombinationsfeld-Steuerelement ab.|  
|[CComboBox::GetCurSel](#getcursel)|Ruft den Index des derzeit ausgewählten Elements ab, ggf. in das Listenfeld eines Kombinationsfelds.|  
|[CComboBox::GetDroppedControlRect](#getdroppedcontrolrect)|Ruft die Bildschirmkoordinaten des sichtbar (Dropdown) Listenfeld der ein Dropdown-Kombinationsfeld ab.|  
|[CComboBox::GetDroppedState](#getdroppedstate)|Bestimmt, ob das Listenfeld ein Dropdown-Kombinationsfeld angezeigt wird (unten verworfen).|  
|[CComboBox::GetDroppedWidth](#getdroppedwidth)|Ruft die minimal zulässige Breite für das Dropdown-Listenfeld Teil eines Kombinationsfelds ab.|  
|[CComboBox::GetEditSel](#geteditsel)|Ruft die Zeichenpositionen Start- und Enddatum der aktuellen Auswahl in das Steuerelement zum Bearbeiten eines Kombinationsfelds ab.|  
|[CComboBox::GetExtendedUI](#getextendedui)|Bestimmt, ob ein Kombinationsfeld Standard--Benutzeroberfläche oder die erweiterte Benutzeroberfläche hat.|  
|[CComboBox::GetHorizontalExtent](#gethorizontalextent)|Gibt die Breite in Pixel, der im Listenfeld Teil des Kombinationsfelds ein horizontaler Bildlauf durchgeführt werden kann.|  
|[CComboBox::GetItemData](#getitemdata)|Ruft die von der Anwendung bereitgestellten 32-Bit-Wert dem angegebenen Kombinationsfeld-Element zugeordnet.|  
|[CComboBox::GetItemDataPtr](#getitemdataptr)|Ruft ab, der von der Anwendung bereitgestellten 32-Bit-Zeiger, der das angegebene Kombinationsfeld-Element zugeordnet ist.|  
|[CComboBox::GetItemHeight](#getitemheight)|Ruft die Höhe der Listenelemente in einem Kombinationsfeld ab.|  
|[CComboBox::GetLBText](#getlbtext)|Ruft eine Zeichenfolge aus dem Listenfeld eines Kombinationsfelds ab.|  
|[CComboBox::GetLBTextLen](#getlbtextlen)|Ruft die Länge einer Zeichenfolge im Listenfeld eines Kombinationsfelds ab.|  
|[CComboBox::GetLocale](#getlocale)|Ruft die Gebietsschema-ID für ein Kombinationsfeld.|  
|[CComboBox::GetMinVisible](#getminvisible)|Ruft die minimale Anzahl der sichtbaren Elemente in der Dropdown-Liste der aktuellen Kombinationsfeld ab.|  
|[CComboBox::GetTopIndex](#gettopindex)|Gibt den Index des ersten sichtbaren Elements im Listenfeld Teil des Kombinationsfelds zurück.|  
|[CComboBox::InitStorage](#initstorage)|Journaldateien Speicherblöcke für Elemente und Zeichenfolgen in das Listenfeld Teil des Kombinationsfelds.|  
|[CComboBox::InsertString](#insertstring)|Fügt eine Zeichenfolge in das Listenfeld eines Kombinationsfelds ein.|  
|[CComboBox::LimitText](#limittext)|Begrenzt die Länge des Texts, die der Benutzer das Steuerelement zum Bearbeiten eines Kombinationsfelds eingeben kann.|  
|[CComboBox::MeasureItem](#measureitem)|Vom Framework aufgerufen Kombinationsfeld Feld Dimensionen zu ermitteln, wann ein Ownerdrawn-Kombinationsfeld erstellt wird.|  
|[CComboBox::Paste](#paste)|Die Daten aus der Zwischenablage in das Bearbeitungssteuerelement an der Cursorposition eingefügt. Daten werden eingefügt, nur dann, wenn Daten in die Zwischenablage enthält, **CF_TEXT** Format.|  
|[CComboBox::ResetContent](#resetcontent)|Entfernt, die alle Elemente aus der Liste im Feld und edit-Steuerelement eines Kombinationsfelds.|  
|[CComboBox::SelectString](#selectstring)|Sucht nach einer Zeichenfolge im Listenfeld eines Kombinationsfelds und, wenn die Zeichenfolge gefunden wird, wählt die Zeichenfolge im Listenfeld und kopiert die Zeichenfolge in das Bearbeitungssteuerelement.|  
|[CComboBox::SetCueBanner](#setcuebanner)|Legt den Hinweistext, der für ein Kombinationsfeld-Steuerelement angezeigt wird.|  
|[CComboBox::SetCurSel](#setcursel)|Wählt eine Zeichenfolge im Listenfeld eines Kombinationsfelds an.|  
|[CComboBox::SetDroppedWidth](#setdroppedwidth)|Legt die minimal zulässige Breite für das Dropdown-Listenfeld Teil eines Kombinationsfelds fest.|  
|[CComboBox::SetEditSel](#seteditsel)|Wählt Zeichen in das Steuerelement zum Bearbeiten eines Kombinationsfelds.|  
|[CComboBox::SetExtendedUI](#setextendedui)|Wählt die Standard-Benutzeroberfläche oder die erweiterte Benutzeroberfläche für ein Kombinationsfeld, ist die **CBS_DROPDOWN** oder **CBS_DROPDOWNLIST** Stil.|  
|[CComboBox::SetHorizontalExtent](#sethorizontalextent)|Legt die Breite in Pixel, der im Listenfeld Teil des Kombinationsfelds ein horizontaler Bildlauf durchgeführt werden kann.|  
|[CComboBox::SetItemData](#setitemdata)|Legt den 32-Bit-Wert, der das angegebene Element in einem Kombinationsfeld zugeordnet.|  
|[CComboBox::SetItemDataPtr](#setitemdataptr)|Legt den 32-Bit-Zeiger, der das angegebene Element in einem Kombinationsfeld zugeordnet.|  
|[CComboBox::SetItemHeight](#setitemheight)|Legt die Höhe der Listenelemente in einem Kombinationsfeld oder die Höhe des Bereichs bearbeiten-Steuerelement (oder statischer Text) eines Kombinationsfelds fest.|  
|[CComboBox::SetLocale](#setlocale)|Legt den Gebietsschemabezeichner für das Kombinationsfeld fest.|  
|[CComboBox::SetMinVisibleItems](#setminvisibleitems)|Legt die minimale Anzahl der sichtbaren Elemente in der Dropdown-Liste des aktuellen Kombinationsfelds fest.|  
|[CComboBox::SetTopIndex](#settopindex)|Weist den Listenfeld Teil im Kombinationsfeld, das Element mit dem angegebenen Index oben angezeigt.|  
|[CComboBox::ShowDropDown](#showdropdown)|Blendet das Listenfeld ein Kombinationsfeld, ist die **CBS_DROPDOWN** oder **CBS_DROPDOWNLIST** Stil.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Kombinationsfeld besteht aus einem Listenfeld mit einem statischen Steuerelement oder einem Bearbeitungssteuerelement kombiniert. Listenfeld Teil des Steuerelements kann jederzeit angezeigt werden oder kann nur Dropdown-Liste bei der Auswahl der Dropdown-Pfeil neben dem Steuerelement.  
  
 Das aktuell ausgewählte Element im Listenfeld (sofern vorhanden) wird in der statischen oder edit-Steuerelement. Darüber hinaus im Kombinationsfeld die Dropdown-Liste-Formatvorlage ist, der Benutzer kann das erste Zeichen eines der Elemente in der Liste eingeben, und klicken Sie im Listenfeld wenn sichtbar ist, wird markieren das nächste Element mit diesem ersten Zeichen.  
  
 Die folgende Tabelle vergleicht die drei Kombinationsfeld [Stile](../../mfc/reference/combo-box-styles.md).  
  
|Stil|Wenn im Listenfeld angezeigt wird|Statische oder Edit-Steuerelement|  
|-----------|-------------------------------|-----------------------------|  
|Einfach|Immer|Bearbeiten|  
|Drop-down|Wenn Sie gelöscht|Bearbeiten|  
|Dropdownliste|Wenn Sie gelöscht|Statisch|  
  
 Sie erstellen ein `CComboBox` Objekt aus entweder einer Dialogfeldvorlage oder direkt im Code. In beiden Fällen rufen Sie zuerst den Konstruktor `CComboBox` zum Erstellen der `CComboBox` Objekt, rufen Sie dann die [erstellen](#create) Memberfunktion, um das Steuerelement zu erstellen, und fügen Sie es auf die `CComboBox` Objekt.  
  
 Wenn Sie ein Kombinationsfeld zum übergeordneten per Windows-Benachrichtigung behandeln möchten (in der Regel eine abgeleitete Klasse `CDialog`), die übergeordnete Klasse für jede Nachricht eine meldungszuordnung Eintrag und Meldungshandler Memberfunktion hinzugefügt.  
  
 Jede Meldungszuordnungseintrags hat das folgende Format:  
  
 **ON_**Notification **(**`id`**,**`memberFxn`**)**  
  
 wobei `id` gibt die ID der untergeordneten Fenster des Kombinationsfeld-Steuerelements Senden der Benachrichtigung und `memberFxn` ist der Name der übergeordneten Member-Funktion, die Sie geschrieben haben, um die Benachrichtigung zu verarbeiten.  
  
 Das übergeordnete Funktionsprototyp lautet wie folgt:  
  
 **afx_msg** `void` `memberFxn` **( );**  
  
 Die Reihenfolge, in der bestimmte Benachrichtigungen gesendet werden sollen, kann nicht vorhergesagt werden. Insbesondere eine **CBN_SELCHANGE** Benachrichtigung kann auftreten, entweder vor oder nach einem **CBN_CLOSEUP** Benachrichtigung.  
  
 Potenzielle Meldungszuordnungseinträge lauten wie folgt:  
  
- **ON_CBN_CLOSEUP** (Windows 3.1 und höher.) Im Listenfeld eines Kombinationsfelds wurde geschlossen. Diese Nachricht wird nicht gesendet, für ein Kombinationsfeld, ist die [CBS_SIMPLE](../../mfc/reference/combo-box-styles.md) Stil.  
  
- **ON_CBN_DBLCLK** der Benutzer doppelklickt eine Zeichenfolge im Listenfeld eines Kombinationsfelds. Diese Nachricht wird nur gesendet, für ein Kombinationsfeld mit der **CBS_SIMPLE** Stil. Für ein Kombinationsfeld mit der [CBS_DROPDOWN](../../mfc/reference/combo-box-styles.md) oder [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) formatieren, Doppelklick kann nicht auftreten, ein Klick im Listenfeld Blendet.  
  
- **ON_CBN_DROPDOWN** im Listenfeld eines Kombinationsfelds wird nach unten (sichtbar gemacht werden). Diese Benachrichtigung kann nur für ein Kombinationsfeld mit auftreten der **CBS_DROPDOWN** oder **CBS_DROPDOWNLIST** Stil.  
  
- **ON_CBN_EDITCHANGE** der Benutzer eine Aktion, die möglicherweise, den Text im Bearbeitungssteuerelement Teil eines Kombinationsfelds geändert übernommen hat. Im Gegensatz zu den **CBN_EDITUPDATE** Nachricht diese Nachricht wird gesendet, nachdem Windows den Bildschirm aktualisiert. Es wird nicht gesendet, wenn das Kombinationsfeld verfügt die **CBS_DROPDOWNLIST** Stil.  
  
- **ON_CBN_EDITUPDATE** der Edit-Steuerelement Teil eines Kombinationsfelds geänderten Text angezeigt wird. Diese Benachrichtigung wird gesendet, nachdem das Steuerelement den Text formatiert hat, aber bevor der Text angezeigt. Es wird nicht gesendet, wenn das Kombinationsfeld verfügt die **CBS_DROPDOWNLIST** Stil.  
  
- **ON_CBN_ERRSPACE** das Kombinationsfeld kann nicht genügend Speicher um eine bestimmte Anforderung zu erfüllen.  
  
- **ON_CBN_SELENDCANCEL** (Windows 3.1 und höher.) Gibt an, dass die Auswahl des Benutzers abgebrochen werden soll. Der Benutzer klickt auf ein Element, und klickt dann auf ein anderes Fenster oder Steuerelement im Listenfeld eines Kombinationsfelds ausgeblendet. Diese Nachricht wird gesendet, bevor die **CBN_CLOSEUP** Benachrichtigung, um anzugeben, dass die Auswahl des Benutzers ignoriert werden sollen. Die **CBN_SELENDCANCEL** oder **CBN_SELENDOK** Nachricht wird gesendet, auch wenn die **CBN_CLOSEUP** -Nachricht wird nicht gesendet (wie im Fall eines Kombinationsfelds mit der **CBS_SIMPLE** Stil).  
  
- **ON_CBN_SELENDOK** der Benutzer wählt ein Element aus und klicken Sie dann die EINGABETASTE drückt oder klickt auf die unten-Taste, um das Listenfeld eines Kombinationsfelds auszublenden. Diese Nachricht wird gesendet, bevor die **CBN_CLOSEUP** Nachricht, um anzugeben, dass die Auswahl des Benutzers als gültig betrachtet werden sollten. Die **CBN_SELENDCANCEL** oder **CBN_SELENDOK** Nachricht wird gesendet, auch wenn die **CBN_CLOSEUP** -Nachricht wird nicht gesendet (wie im Fall eines Kombinationsfelds mit der **CBS_SIMPLE** Stil).  
  
- **ON_CBN_KILLFOCUS** im Kombinationsfeld den Eingabefokus verliert.  
  
- **ON_CBN_SELCHANGE** die Auswahl im Listenfeld eines Kombinationsfelds geändert werden, weil der Benutzer im Listenfeld klicken oder die Auswahl mithilfe der Pfeiltasten ändern wird. Bei der Verarbeitung dieser Nachricht der Text in das Steuerelement zum Bearbeiten des Kombinationsfelds kann nur abgerufen werden über `GetLBText` oder eine andere ähnliche Funktion. `GetWindowText`kann verwendet werden.  
  
- **ON_CBN_SETFOCUS** im Kombinationsfeld den Eingabefokus erhält.  
  
 Bei der Erstellung einer `CComboBox` Objekt in einem Dialogfeld (über eine Dialogfeldressource), die `CComboBox` Objekt wird automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Wenn Sie Einbetten einer `CComboBox` Objekt in ein anderes Fenster-Objekt müssen Sie nicht zerstört. Bei der Erstellung der `CComboBox` Objekt auf dem Stapel automatisch zerstört wird. Bei der Erstellung der `CComboBox` Objekt auf dem Heap mithilfe der **neue** -Funktion, die Sie aufrufen müssen **löschen** auf das Objekt, das es zerstört, wenn die Windows-Kombinationsfelds zerstört wird.  
  
 **Hinweis** Wenn verarbeiten soll `WM_KEYDOWN` und `WM_CHAR` Nachrichten müssen Unterklasse des Kombinationsfelds bearbeiten und Liste der Steuerelemente, leiten Sie eine Klasse von `CEdit` und `CListBox`, und fügen Sie Handler für diese Nachrichten in die abgeleiteten Klassen. Weitere Informationen finden Sie unter [Http://support.microsoft.com/default.aspxscid=kb;en-us; Q174667](http://support.microsoft.com/default.aspxscid=kb;en-us;q174667) und [CWnd:: SubclassWindow](../../mfc/reference/cwnd-class.md#subclasswindow).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CComboBox`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="a-nameaddstringa--ccomboboxaddstring"></a><a name="addstring"></a>CComboBox:: AddString  
 Fügt eine Zeichenfolge in das Listenfeld eines Kombinationsfelds an.  
  
```  
int AddString(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszString`  
 Verweist auf die auf Null endende Zeichenfolge, die hinzugefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert größer als oder gleich 0 ist, ist der nullbasierte Index in der Zeichenfolge im Listenfeld. Der Rückgabewert ist **CB_ERR** Wenn ein Fehler auftritt, ist der Rückgabewert **CB_ERRSPACE** ist nicht genügend Speicherplatz zum Speichern der neuen Zeichenfolge verfügbar.  
  
### <a name="remarks"></a>Hinweise  
 Wenn im Listenfeld nicht erstellt wurde, mit der [CBS_SORT](../../mfc/reference/combo-box-styles.md) Stil, wird die Zeichenfolge an das Ende der Liste hinzugefügt. Andernfalls wird die Zeichenfolge in die Liste eingefügt, und die Liste sortiert.  
  
> [!NOTE]
>  Diese Funktion wird vom Windows **ComboBoxEx** -Steuerelement nicht unterstützt. Weitere Informationen zu diesem Steuerelement finden Sie unter [ComboBoxEx Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb775738) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Verwenden Sie zum Einfügen einer Zeichenfolge in einer bestimmten Position in der Liste der [InsertString](#insertstring) Member-Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&3;](../../mfc/reference/codesnippet/cpp/ccombobox-class_1.cpp)]  
  
##  <a name="a-nameccomboboxa--ccomboboxccombobox"></a><a name="ccombobox"></a>CComboBox::CComboBox  
 Erstellt ein `CComboBox`-Objekt.  
  
```  
CComboBox();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#1;](../../mfc/reference/codesnippet/cpp/ccombobox-class_2.cpp)]  
  
##  <a name="a-namecleara--ccomboboxclear"></a><a name="clear"></a>CComboBox::Clear  
 Löscht (deaktiviert) die aktuelle Auswahl, sofern vorhanden, in das Steuerelement zum Bearbeiten des Kombinationsfelds.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Hinweise  
 Um die aktuelle Auswahl löschen, und fügen Sie den gelöschten Inhalt in die Zwischenablage, verwenden Sie die [Ausschneiden](#cut) Member-Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&4;](../../mfc/reference/codesnippet/cpp/ccombobox-class_3.cpp)]  
  
##  <a name="a-namecompareitema--ccomboboxcompareitem"></a><a name="compareitem"></a>CComboBox::CompareItem  
 Aufgerufen, um die relative Position eines neuen Elements im Listenfeld Teil einer sortierten Ownerdrawn-Kombinationsfeld zu bestimmen.  
  
```  
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpCompareItemStruct`  
 Ein long-Zeiger auf eine [COMPAREITEMSTRUCT](../../mfc/reference/compareitemstruct-structure.md) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Die relative Position der beiden Elemente gemäß der `COMPAREITEMSTRUCT` Struktur. Die folgenden Werte sind möglich:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|– 1|Element 1 wird vor Element 2 sortiert.|  
|0|Artikel 1 und Artikel 2 sortieren identisch.|  
|1|Element 1 wird nach Element 2 sortiert.|  
  
 Finden Sie unter [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) eine Beschreibung der `COMPAREITEMSTRUCT`.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird dieser Member-Funktion keine Aktion ausgeführt. Wenn Sie ein Ownerdrawn-Kombinationsfeld mit Erstellen der **LBS_SORT** Stil, müssen Sie diese Memberfunktion auf, bei der das Framework sortieren neue Elemente im Listenfeld überschreiben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&5;](../../mfc/reference/codesnippet/cpp/ccombobox-class_4.cpp)]  
  
##  <a name="a-namecopya--ccomboboxcopy"></a><a name="copy"></a>CComboBox::Copy  
 Kopiert die aktuelle Auswahl und ggf. in das Steuerelement zum Bearbeiten des Kombinationsfelds in der Zwischenablage in **CF_TEXT** Format.  
  
```  
void Copy();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&6;](../../mfc/reference/codesnippet/cpp/ccombobox-class_5.cpp)]  
  
##  <a name="a-namecreatea--ccomboboxcreate"></a><a name="create"></a>CComboBox::Create  
 Das Kombinationsfeld erstellt, und fügt es der `CComboBox` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt das Format des Kombinationsfelds. Wenden Sie eine beliebige Kombination von [kombinationsfeldstile](../../mfc/reference/combo-box-styles.md) in das Feld.  
  
 `rect`  
 Verweist auf die Position und Größe des Kombinationsfelds. Kann ein [RECT-Struktur](../../mfc/reference/rect-structure1.md) oder ein `CRect` Objekt.  
  
 `pParentWnd`  
 Gibt das Kombinationsfeld des übergeordneten Fensters (in der Regel eine `CDialog`). Er darf nicht sein **NULL**.  
  
 `nID`  
 Gibt das Kombinationsfeld-Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen ein `CComboBox` Objekt in zwei Schritten. Zunächst rufen Sie den Konstruktor, und rufen Sie dann **erstellen**, die die Windows-Kombinationsfeld erstellt, und fügt es der `CComboBox` Objekt.  
  
 Wenn **erstellen** ausgeführt wird, sendet Windows die [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), und [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Nachrichten an das Kombinationsfeld.  
  
 Diese Nachrichten werden standardmäßig verarbeitet die [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), und [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Memberfunktionen in der `CWnd` Basisklasse. Um die Standardbehandlung für die Nachricht zu erweitern, leiten Sie eine Klasse von `CComboBox`, eine Nachricht Zuordnung an die neue Klasse hinzufügen und die vorherigen Meldungshandler Memberfunktionen überschreiben. Überschreiben Sie `OnCreate`, z. B. für die erforderliche Initialisierung für eine neue Klasse.  
  
 Übernehmen Sie das folgende [Fensterstile](../../mfc/reference/window-styles.md) an ein Kombinationsfeld-Steuerelement. :  
  
- **WS_CHILD** immer  
  
- **WS_VISIBLE** in der Regel  
  
- **WS_DISABLED** selten  
  
- **WS_VSCROLL** vertikaler Bildlauf für das Listenfeld im Kombinationsfeld hinzufügen  
  
- **WS_HSCROLL** horizontalen Bildlauf für das Listenfeld im Kombinationsfeld hinzufügen  
  
- **WS_GROUP** zum Gruppieren von Steuerelementen  
  
- **WS_TABSTOP** hinzufügen im Kombinationsfeld in die Tab-Reihenfolge  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#2;](../../mfc/reference/codesnippet/cpp/ccombobox-class_6.cpp)]  
  
##  <a name="a-namecuta--ccomboboxcut"></a><a name="cut"></a>CComboBox::Cut  
 Löscht (Teilstücke) die aktuelle Auswahl, wenn vorhanden, in dem Kombinationsfeld Bearbeiten steuern und kopiert den gelöschten Text in die Zwischenablage in **CF_TEXT** Format.  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>Hinweise  
 Um die aktuelle Auswahl löschen, ohne den gelöschten Text in die Zwischenablage, rufen die [löschen](#clear) Member-Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#7;](../../mfc/reference/codesnippet/cpp/ccombobox-class_7.cpp)]  
  
##  <a name="a-namedeleteitema--ccomboboxdeleteitem"></a><a name="deleteitem"></a>CComboBox::DeleteItem  
 Vom Framework aufgerufen, wenn der Benutzer ein Element aus einem Ownerdrawn-löscht `CComboBox` -Objekt oder das Kombinationsfeld zerstört.  
  
```  
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDeleteItemStruct`  
 Ein long-Zeiger zu einem Windows [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md) -Struktur, die Informationen über das gelöschte Element enthält. Finden Sie unter [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) eine Beschreibung dieser Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um das Kombinationsfeld nach Bedarf neu zu zeichnen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#8;](../../mfc/reference/codesnippet/cpp/ccombobox-class_8.cpp)]  
  
##  <a name="a-namedeletestringa--ccomboboxdeletestring"></a><a name="deletestring"></a>CComboBox::DeleteString  
 Löscht das Element an Position `nIndex` aus dem Kombinationsfeld.  
  
```  
int DeleteString(UINT nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den Index in der Zeichenfolge, die gelöscht werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Rückgabewert größer als oder gleich 0 ist, ist es die Anzahl der Zeichenfolgen in der Liste verbleiben. Der Rückgabewert ist **CB_ERR** Wenn `nIndex` Index größer als die Anzahl der Elemente in der Liste angibt.  
  
### <a name="remarks"></a>Hinweise  
 Alle Elemente, die nach `nIndex` jetzt eine Position nach unten zu verschieben. Z. B. wenn ein Kombinationsfeld zwei Elemente enthält, bewirkt löschen das erste Element den verbleibenden Artikel jetzt in der ersten Position sein. `nIndex`=&0; für das Element in der ersten Position.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#9;](../../mfc/reference/codesnippet/cpp/ccombobox-class_9.cpp)]  
  
##  <a name="a-namedira--ccomboboxdir"></a><a name="dir"></a>CComboBox::Dir  
 Eine Liste von Dateien oder Laufwerke hinzugefügt in die Liste im Kombinationsfeld.  
  
```  
int Dir(
    UINT attr,  
    LPCTSTR lpszWildCard);
```  
  
### <a name="parameters"></a>Parameter  
 `attr`  
 Kann eine beliebige Kombination der `enum` Werte in beschriebenen [CFile:: GetStatus](../../mfc/reference/cfile-class.md#getstatus) oder eine beliebige Kombination der folgenden Werte:  
  
- **DDL_READWRITE** Datei aus gelesen oder geschrieben werden kann.  
  
- **DDL_READONLY** Datei auslesen, jedoch nicht geschrieben werden kann.  
  
- **DDL_HIDDEN** Datei ausgeblendet, und nicht in einer Verzeichnisliste angezeigt.  
  
- **DDL_SYSTEM** Datei eine Systemdatei ist.  
  
- **DDL_DIRECTORY** angegebene `lpszWildCard` gibt ein Verzeichnis an.  
  
- **DDL_ARCHIVE** Datei wurde archiviert.  
  
- **DDL_DRIVES** zählen sämtliche Laufwerke, die mit den angegebenen Namen übereinstimmen `lpszWildCard`.  
  
- **DDL_EXCLUSIVE** exklusive Flag. Wenn der exklusive Flag festgelegt ist, werden nur Dateien des angegebenen Typs aufgeführt. Andernfalls werden die Dateien des angegebenen Typs zusätzlich zu "normale" Dateien aufgeführt.  
  
 `lpszWildCard`  
 Zeigt auf eine Dateispezifikation Zeichenfolge. Die Zeichenfolge kann Platzhalter enthalten (z. B. *.\*).  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Rückgabewert größer als oder gleich 0 ist, ist es den nullbasierten Index des letzten Filename zur Liste hinzugefügt. Der Rückgabewert ist **CB_ERR** Wenn ein Fehler auftritt, ist der Rückgabewert **CB_ERRSPACE** ist nicht genügend Speicherplatz zum Speichern der neuen Zeichenfolgen zur Verfügung.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird vom Windows **ComboBoxEx** -Steuerelement nicht unterstützt. Weitere Informationen zu diesem Steuerelement finden Sie unter [ComboBoxEx Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb775738) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#10;](../../mfc/reference/codesnippet/cpp/ccombobox-class_10.cpp)]  
  
##  <a name="a-namedrawitema--ccomboboxdrawitem"></a><a name="drawitem"></a>CComboBox::DrawItem  
 Aufgerufen, wenn sich ein Darstellungsaspekt eines Ownerdrawn-Kombinationsfeld Feld ändert.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDrawItemStruct`  
 Ein Zeiger auf eine [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) -Struktur, die Informationen über den Typ der erforderlichen Zeichnung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die **ItemAction** Mitglied der `DRAWITEMSTRUCT` Struktur definiert die Zeichnen-Aktion, die ausgeführt werden soll. Finden Sie unter [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) eine Beschreibung dieser Struktur.  
  
 Standardmäßig wird dieser Member-Funktion keine Aktion ausgeführt. Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für eine Ownerdrawn- `CComboBox` Objekt. Bevor Sie diese Memberfunktion beendet wird, sollte die Anwendung alle Grafiken Device Interface (GDI) Objekte ausgewählt, für der Anzeigekontext im angegebenen wiederherstellen `lpDrawItemStruct`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#11;](../../mfc/reference/codesnippet/cpp/ccombobox-class_11.cpp)]  
  
##  <a name="a-namefindstringa--ccomboboxfindstring"></a><a name="findstring"></a>CComboBox:: FindString  
 Findet, aber nicht auswählen, die erste Zeichenfolge, die das angegebene Präfix im Listenfeld eines Kombinationsfelds enthält.  
  
```  
int FindString(
    int nStartAfter,  
    LPCTSTR lpszString) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nStartAfter`  
 Enthält den nullbasierten Index des Elements vor dem ersten Element gesucht werden soll. Erreicht die Suche am Ende das Listenfeld, weiterhin von der obersten Position des Listenfelds wieder das Element mit dem angegebenen `nStartAfter`. Wenn –&1; ist, wird das ganze Listenfeld vom Anfang durchsucht.  
  
 `lpszString`  
 Verweist auf die auf Null endende Zeichenfolge, die das Präfix für die Suche enthält. Die Suche gilt unabhängig, damit diese Zeichenfolge eine beliebige Kombination aus Groß- und Kleinbuchstaben enthalten kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Rückgabewert größer als oder gleich 0 ist, ist es den nullbasierten Index des übereinstimmenden Elements. Es ist **CB_ERR** Wenn die Suche nicht erfolgreich war.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird vom Windows **ComboBoxEx** -Steuerelement nicht unterstützt. Weitere Informationen zu diesem Steuerelement finden Sie unter [ComboBoxEx Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb775738) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#12;](../../mfc/reference/codesnippet/cpp/ccombobox-class_12.cpp)]  
  
##  <a name="a-namefindstringexacta--ccomboboxfindstringexact"></a><a name="findstringexact"></a>CComboBox::FindStringExact  
 Rufen Sie die `FindStringExact` Memberfunktion, die die erste Listenfeld-Zeichenfolge (in ein Kombinationsfeld) zu suchen, der im angegebenen Zeichenfolge übereinstimmt `lpszFind`.  
  
```  
int FindStringExact(
    int nIndexStart,  
    LPCTSTR lpszFind) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndexStart`  
 Gibt den nullbasierten Index des Elements vor dem ersten Element gesucht werden soll. Erreicht die Suche am Ende das Listenfeld, weiterhin von der obersten Position des Listenfelds wieder das Element mit dem angegebenen `nIndexStart`. Wenn `nIndexStart` –&1; ist, wird das ganze Listenfeld wird vom Anfang durchsucht.  
  
 `lpszFind`  
 Verweist auf die zu suchende Zeichenfolge Null-terminiert. Diese Zeichenfolge kann einen vollständigen Dateinamen einschließlich der Erweiterung enthalten. Die Suche ist nicht Groß-/Kleinschreibung, damit diese Zeichenfolge eine beliebige Kombination aus Groß- und Kleinbuchstaben enthalten kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des entsprechenden Elements oder **CB_ERR** Wenn die Suche nicht erfolgreich war.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Kombinationsfeld mit einem Ownerdrawn-Stil, jedoch ohne erstellt wurde die [CBS_HASSTRINGS](../../mfc/reference/combo-box-styles.md) Stil `FindStringExact` versucht, den Doppelwort Wert anhand des Werts eines `lpszFind`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#13;](../../mfc/reference/codesnippet/cpp/ccombobox-class_13.cpp)]  
  
##  <a name="a-namegetcomboboxinfoa--ccomboboxgetcomboboxinfo"></a><a name="getcomboboxinfo"></a>CComboBox::GetComboBoxInfo  
 Ruft Informationen für die `CComboBox` Objekt.  
  
```  
BOOL GetComboBoxInfo(PCOMBOBOXINFO pcbi) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *pcbi*  
 Ein Zeiger auf die [COMBOBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775798) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionalität der [CB_GETCOMBOBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775839) angezeigt, wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetcounta--ccomboboxgetcount"></a><a name="getcount"></a>CComboBox::GetCount  
 Rufen Sie diese Memberfunktion, um die Anzahl der Elemente im Listenfeld Teil eines Kombinationsfelds abzurufen.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente. Die zurückgegebene Anzahl ist größer als der Wert für das letzte Element (der Index ist nullbasiert). Es ist **CB_ERR** Wenn ein Fehler auftritt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&14;](../../mfc/reference/codesnippet/cpp/ccombobox-class_14.cpp)]  
  
##  <a name="a-namegetcuebannera--ccomboboxgetcuebanner"></a><a name="getcuebanner"></a>CComboBox::GetCueBanner  
 Ruft den Hinweistext, der angezeigt wird, für ein Kombinationsfeld-Steuerelement ab.  
  
```  
CString GetCueBanner() const;  
  
BOOL GetCueBanner(
    LPTSTR lpszText,   
    int cchText) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] `lpszText`|Ein Zeiger auf einen Puffer, der den hinweisbannertext empfängt.|  
|[in] `cchText`|Größe des Puffers, die den `lpszText` -Parameter zeigt.|  
  
### <a name="return-value"></a>Rückgabewert  
 In der ersten Überladung eine [CString](../../atl-mfc-shared/using-cstring.md) -Objekt, das den hinweisbannertext enthält, falls vorhanden; andernfalls ein `CString` Objekt mit Länge&0;.  
  
 - oder -   
  
 In der zweiten Überladung ist `true` Wenn diese Methode erfolgreich; andernfalls ist `false`.  
  
### <a name="remarks"></a>Hinweise  
 Hinweistext ist eine Aufforderung, die in das Eingabefeld ein Kombinationsfeld-Steuerelement angezeigt wird. Der Hinweistext wird angezeigt, bis der Benutzer die Eingabe vornimmt.  
  
 Diese Methode sendet die [CB_GETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb775843) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetcursela--ccomboboxgetcursel"></a><a name="getcursel"></a>CComboBox::GetCurSel  
 Rufen Sie diese Memberfunktion, um zu bestimmen, welches Element im Kombinationsfeld ausgewählt wird.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des derzeit ausgewählten Elements im Listenfeld eines Kombinationsfelds oder **CB_ERR** kein Element ausgewählt ist.  
  
### <a name="remarks"></a>Hinweise  
 `GetCurSel`Gibt einen Index in der Liste zurück.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#15;](../../mfc/reference/codesnippet/cpp/ccombobox-class_15.cpp)]  
  
##  <a name="a-namegetdroppedcontrolrecta--ccomboboxgetdroppedcontrolrect"></a><a name="getdroppedcontrolrect"></a>CComboBox::GetDroppedControlRect  
 Rufen Sie die `GetDroppedControlRect` Memberfunktion, die die Bildschirmkoordinaten des Feldes sichtbar (gelöscht) Dropdownliste ein Dropdown-Kombinationsfeld abzurufen.  
  
```  
void GetDroppedControlRect(LPRECT lprect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *lprect*  
 Verweist auf die [RECT-Struktur](../../mfc/reference/rect-structure1.md) , die die Koordinaten empfangen wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox Nr.&16;](../../mfc/reference/codesnippet/cpp/ccombobox-class_16.cpp)]  
  
##  <a name="a-namegetdroppedstatea--ccomboboxgetdroppedstate"></a><a name="getdroppedstate"></a>CComboBox::GetDroppedState  
 Rufen Sie die `GetDroppedState` Member-Funktion, um festzustellen, ob das Listenfeld ein Dropdown-Kombinationsfeld angezeigt wird (unten verworfen).  
  
```  
BOOL GetDroppedState() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Listenfeld angezeigt wird; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&17;](../../mfc/reference/codesnippet/cpp/ccombobox-class_17.cpp)]  
  
##  <a name="a-namegetdroppedwidtha--ccomboboxgetdroppedwidth"></a><a name="getdroppedwidth"></a>CComboBox::GetDroppedWidth  
 Rufen Sie diese Funktion, um die minimale zulässige Breite in Pixel im Listenfeld eines Kombinationsfelds abzurufen.  
  
```  
int GetDroppedWidth() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg die minimale zulässige Breite in Pixel; andernfalls **CB_ERR**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion gilt nur für Kombinationsfelder mit der [CBS_DROPDOWN](../../mfc/reference/combo-box-styles.md) oder [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) Stil.  
  
 Standardmäßig ist die minimale zulässige Breite des Dropdown-Listenfelds 0. Die minimale zulässige Breite kann festgelegt werden, durch Aufrufen von [SetDroppedWidth](#setdroppedwidth). Listenfeld Teil des Kombinationsfelds angezeigt wird, wird die Breite größer als die zulässige Mindestbreite oder das Kombinationsfeld Feldbreite.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [SetDroppedWidth](#setdroppedwidth).  
  
##  <a name="a-namegeteditsela--ccomboboxgeteditsel"></a><a name="geteditsel"></a>CComboBox::GetEditSel  
 Ruft die Zeichenpositionen Start- und Enddatum der aktuellen Auswahl in das Steuerelement zum Bearbeiten eines Kombinationsfelds ab.  
  
```  
DWORD GetEditSel() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine 32-Bit-Wert, der die Anfangsposition in das niederwertige Wort und die Position des ersten Zeichens nicht ausgewählten nach dem Ende der Auswahl in das höherwertige Wort enthält. Wenn diese Funktion, in einem Kombinationsfeld ohne ein Bearbeitungssteuerelement verwendet wird, **CB_ERR** wird zurückgegeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&18;](../../mfc/reference/codesnippet/cpp/ccombobox-class_18.cpp)]  
  
##  <a name="a-namegetextendeduia--ccomboboxgetextendedui"></a><a name="getextendedui"></a>CComboBox::GetExtendedUI  
 Rufen Sie die `GetExtendedUI` Member-Funktion, um festzustellen, ob ein Kombinationsfeld Standard--Benutzeroberfläche oder die erweiterte Benutzeroberfläche hat.  
  
```  
BOOL GetExtendedUI() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Kombinationsfeld die erweiterte Benutzeroberfläche wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die erweiterte Benutzeroberfläche kann auf folgende Weise identifiziert werden:  
  
-   Durch Klicken auf die statisches Steuerelement wird im Listenfeld nur für Kombinationsfelder mit der [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) Stil.  
  
-   Drücken die nach-unten-Taste zeigt im Listenfeld (F4 ist deaktiviert).  
  
 Bildlauf im statischen Steuerelement ist deaktiviert, wenn die Elementliste nicht sichtbar (Pfeil) Schlüssel deaktiviert werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox Nr.&19;](../../mfc/reference/codesnippet/cpp/ccombobox-class_19.cpp)]  
  
##  <a name="a-namegethorizontalextenta--ccomboboxgethorizontalextent"></a><a name="gethorizontalextent"></a>CComboBox::GetHorizontalExtent  
 Ruft die Breite in Pixel, die mit denen Listenfeld Teil des Kombinationsfelds ein horizontaler Bildlauf durchgeführt werden kann, aus dem Kombinationsfeld ab.  
  
```  
UINT GetHorizontalExtent() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die bildlauffähigen Breite Teil des im Listenfeld des im Kombinationsfeld in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Dies gilt nur, wenn der Listenfeld Teil des Kombinationsfelds eine horizontale Bildlaufleiste angezeigt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&20;](../../mfc/reference/codesnippet/cpp/ccombobox-class_20.cpp)]  
  
##  <a name="a-namegetitemdataa--ccomboboxgetitemdata"></a><a name="getitemdata"></a>CComboBox::GetItemData  
 Ruft die von der Anwendung bereitgestellten 32-Bit-Wert dem angegebenen Kombinationsfeld-Element zugeordnet.  
  
```  
DWORD_PTR GetItemData(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Enthält den nullbasierten Index eines Elements im Listenfeld des Kombinationsfelds.  
  
### <a name="return-value"></a>Rückgabewert  
 Der 32-Bit-Wert, der dem Element zugeordnete oder **CB_ERR** Wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Die 32-Bit-Wert kann festgelegt werden, mit der `dwItemData` Parameter ein [SetItemData](#setitemdata) Member-Funktionsaufruf. Verwenden der `GetItemDataPtr` Member-Funktion, wenn die 32-Bit-Wert abgerufen werden soll, ein Zeiger ist ( **void\***).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&21;](../../mfc/reference/codesnippet/cpp/ccombobox-class_21.cpp)]  
  
##  <a name="a-namegetitemdataptra--ccomboboxgetitemdataptr"></a><a name="getitemdataptr"></a>CComboBox::GetItemDataPtr  
 Ruft die von der Anwendung bereitgestellten 32-Bit-Wert mit dem angegebenen Kombinationsfeld-Element als Zeiger verknüpfte ( **void\***).  
  
```  
void* GetItemDataPtr(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Enthält den nullbasierten Index eines Elements im Listenfeld des Kombinationsfelds.  
  
### <a name="return-value"></a>Rückgabewert  
 Ruft einen Zeiger oder -1 ab, wenn ein Fehler auftritt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#22;](../../mfc/reference/codesnippet/cpp/ccombobox-class_22.cpp)]  
  
##  <a name="a-namegetitemheighta--ccomboboxgetitemheight"></a><a name="getitemheight"></a>CComboBox::GetItemHeight  
 Rufen Sie die `GetItemHeight` Memberfunktion, die die Höhe der Listenelemente in einem Kombinationsfeld abzurufen.  
  
```  
int GetItemHeight(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt die Komponente des Kombinationsfelds, dessen Höhe ist abgerufen werden sollen. Wenn der `nIndex` Parameter ist&1;, die Höhe des bearbeiten-Steuerelement (oder statischer Text) Teils des Kombinationsfelds abgerufen wird. Wenn das Kombinationsfeld hat die [CBS_OWNERDRAWVARIABLE](../../mfc/reference/combo-box-styles.md) Stil `nIndex` gibt den nullbasierten Index des Listenelements, deren Höhe ist abgerufen werden sollen. Andernfalls `nIndex` muss auf 0 festgelegt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe des angegebenen Elements in einem Kombinationsfeld in Pixel. Der Rückgabewert beim Auftreten eines Fehlers ist **CB_ERR** .  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&23;](../../mfc/reference/codesnippet/cpp/ccombobox-class_23.cpp)]  
  
##  <a name="a-namegetlbtexta--ccomboboxgetlbtext"></a><a name="getlbtext"></a>CComboBox::GetLBText  
 Ruft eine Zeichenfolge aus dem Listenfeld eines Kombinationsfelds ab.  
  
```  
int GetLBText(
    int nIndex,  
    LPTSTR lpszText) const;  
  
void GetLBText(
    int nIndex,  
    CString& rString) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Enthält den nullbasierten Index der Zeichenfolge im Listenfeld kopiert werden soll.  
  
 `lpszText`  
 Zeigt auf einen Puffer, der zum Empfangen der Zeichenfolgennachricht ist. Der Puffer muss über genügend Speicherplatz für die Zeichenfolge und ein abschließendes Null-Zeichen haben.  
  
 `rString`  
 Ein Verweis auf eine `CString`.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge (in Byte) der Zeichenfolge ist, außer das abschließende Nullzeichen. Wenn `nIndex` gibt keine gültigen Index, der Rückgabewert ist **CB_ERR**.  
  
### <a name="remarks"></a>Hinweise  
 Das zweite Formular dieses Members-Funktion füllt eine `CString` -Objekt mit der Text des Elements.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#24;](../../mfc/reference/codesnippet/cpp/ccombobox-class_24.cpp)]  
  
##  <a name="a-namegetlbtextlena--ccomboboxgetlbtextlen"></a><a name="getlbtextlen"></a>CComboBox::GetLBTextLen  
 Ruft die Länge einer Zeichenfolge im Listenfeld eines Kombinationsfelds ab.  
  
```  
int GetLBTextLen(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Enthält den nullbasierten Index der Zeichenfolge im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge der Zeichenfolge in Byte ohne das abschließende Nullzeichen. Wenn `nIndex` gibt keine gültigen Index, der Rückgabewert ist **CB_ERR**.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CComboBox::GetLBText](#getlbtext).  
  
##  <a name="a-namegetlocalea--ccomboboxgetlocale"></a><a name="getlocale"></a>CComboBox::GetLocale  
 Ruft das von der im Kombinationsfeld verwendete Gebietsschema ab.  
  
```  
LCID GetLocale() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert des Gebietsschemabezeichners (LCID) für die Zeichenfolgen im Kombinationsfeld.  
  
### <a name="remarks"></a>Hinweise  
 Das Gebietsschema wird z. B. verwendet, um die Sortierreihenfolge der Zeichenfolgen in einem sortierten Kombinationsfeld zu bestimmen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CComboBox::SetLocale](#setlocale).  
  
##  <a name="a-namegetminvisiblea--ccomboboxgetminvisible"></a><a name="getminvisible"></a>CComboBox::GetMinVisible  
 Ruft die minimale Anzahl der sichtbaren Elemente in der Dropdown-Liste der aktuellen Kombinationsfeld-Steuerelement ab.  
  
```  
int GetMinVisible() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die minimale Anzahl der sichtbaren Elemente in der aktuellen Dropdown-Liste.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [CB_GETMINVISIBLE](http://msdn.microsoft.com/library/windows/desktop/bb775915) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegettopindexa--ccomboboxgettopindex"></a><a name="gettopindex"></a>CComboBox::GetTopIndex  
 Ruft den nullbasierten Index des ersten sichtbaren Elements im Listenfeld Teil im Kombinationsfeld ab.  
  
```  
int GetTopIndex() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des ersten sichtbaren Elements im Listenfeld Teil im Kombinationsfeld, wenn erfolgreich, **CB_ERR** andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Zu Beginn Element 0 befindet sich oben im Listenfeld, aber im Listenfeld ein Bildlauf durchgeführt wird, kann ein anderes Element oben befinden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#25;](../../mfc/reference/codesnippet/cpp/ccombobox-class_25.cpp)]  
  
##  <a name="a-nameinitstoragea--ccomboboxinitstorage"></a><a name="initstorage"></a>CComboBox::InitStorage  
 Belegt Speicher zum Speichern von Listenfeldelemente im Listenfeld Teil des Kombinationsfelds.  
  
```  
int InitStorage(
    int nItems,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>Parameter  
 `nItems`  
 Gibt die Anzahl von Elementen hinzugefügt.  
  
 `nBytes`  
 Gibt die Menge des Arbeitsspeichers in Bytes, die für Element Zeichenfolgen zugeordnet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, die maximale Anzahl von Elementen, der im Listenfeld Teil des Kombinationsfelds kann gespeichert, bevor eine Neubelegung Arbeitsspeicher, andernfalls benötigt wird **CB_ERRSPACE**, d. h. nicht genügend Arbeitsspeicher verfügbar ist.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion vor dem Hinzufügen von eine große Anzahl von Elementen mit dem Listenfeld-Teil der `CComboBox`.  
  
 Windows 95/98: der `wParam` Parameter ist auf 16-Bit-Werte beschränkt. Dies bedeutet, dass es sich bei Listenfelder mehr als 32.767 Elemente enthalten können. Obwohl die Anzahl der Elemente eingeschränkt ist, ist die Gesamtgröße der Elemente in einem Listenfeld nur durch den verfügbaren Arbeitsspeicher beschränkt.  
  
 Diese Funktion können Sie die Initialisierung von Listenfelder beschleunigen, die eine große von Elementen (mehr als 100 Anzahl). Es so, dass bei nachfolgenden angegebene Arbeitsspeichermenge Journaldateien [AddString](#addstring), [InsertString](#insertstring), und [Dir](#dir) Funktionen nehmen kürzesten Zeit. Sie können die Schätzungen für die Parameter verwenden. Wenn Sie überschätzen, wird zusätzlicher Arbeitsspeicher reserviert. Wenn Sie unterschätzen, wird die normale Verteilung für Elemente verwendet, die vorab überschreiten.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#26;](../../mfc/reference/codesnippet/cpp/ccombobox-class_26.cpp)]  
  
##  <a name="a-nameinsertstringa--ccomboboxinsertstring"></a><a name="insertstring"></a>CComboBox::InsertString  
 Fügt eine Zeichenfolge in das Listenfeld eines Kombinationsfelds ein.  
  
```  
int InsertString(
    int nIndex,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Enthält den nullbasierten Index der Position im Listenfeld, die die Zeichenfolge aufnehmen soll. Wenn dieser Parameter –1 ist, wird die Zeichenfolge am Ende der Liste hinzugefügt.  
  
 `lpszString`  
 Zeigt auf die einzufügende nullterminierte Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index der Position, an der die Zeichenfolge eingefügt wurde. Der Rückgabewert beim Auftreten eines Fehlers ist **CB_ERR** . Der Rückgabewert ist **CB_ERRSPACE** , wenn zum Speichern der neuen Zeichenfolge nicht genügend Platz vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Im Gegensatz zu der [AddString](#addstring) Member-Funktion, die `InsertString` Member-Funktion nicht dazu, dass eine Liste mit den [CBS_SORT](../../mfc/reference/combo-box-styles.md) Stil sortiert werden.  
  
> [!NOTE]
>  Diese Funktion wird vom Windows **ComboBoxEx** -Steuerelement nicht unterstützt. Weitere Informationen zu diesem Steuerelement finden Sie unter [ComboBoxEx Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb775738) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#27;](../../mfc/reference/codesnippet/cpp/ccombobox-class_27.cpp)]  
  
##  <a name="a-namelimittexta--ccomboboxlimittext"></a><a name="limittext"></a>CComboBox::LimitText  
 Beschränkt die Länge in Bytes, der den Text, den der Benutzer in das Steuerelement zum Bearbeiten eines Kombinationsfelds eingeben kann.  
  
```  
BOOL LimitText(int nMaxChars);
```  
  
### <a name="parameters"></a>Parameter  
 `nMaxChars`  
 Gibt die Länge (in Byte) des Textes, den der Benutzer eingeben kann. Wenn dieser Parameter 0 ist, wird die Textlänge bis 65.535 Byte festgelegt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, falls erfolgreich. Wenn für ein Kombinationsfeld, mit dem Namen [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) oder für ein Kombinationsfeld, ohne dass ein Bearbeitungssteuerelement, ist der Rückgabewert **CB_ERR**.  
  
### <a name="remarks"></a>Hinweise  
 Verfügt das Kombinationsfeld nicht das Format [CBS_AUTOHSCROLL](../../mfc/reference/combo-box-styles.md), festlegen, die größer als die Größe des Bearbeitungssteuerelements sein Text hat keine Auswirkung.  
  
 `LimitText`nur begrenzt den Text, den der Benutzer eingeben kann. Es wirkt sich nicht auf einen beliebigen Text bereits in der Edit-Steuerelement, wenn die Nachricht wird gesendet, und beeinträchtigt die Länge des Texts in das Bearbeitungssteuerelement kopiert, wenn eine Zeichenfolge im Listenfeld ausgewählt ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#28;](../../mfc/reference/codesnippet/cpp/ccombobox-class_28.cpp)]  
  
##  <a name="a-namemeasureitema--ccomboboxmeasureitem"></a><a name="measureitem"></a>CComboBox::MeasureItem  
 Wird vom Framework aufgerufen, wenn das Kombinationsfeld mit einem Ownerdrawn-Stil erstellt wird.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpMeasureItemStruct`  
 Ein long-Zeiger auf eine [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird dieser Member-Funktion keine Aktion ausgeführt. Überschreiben Sie diese Memberfunktion auf, und füllen Sie die `MEASUREITEMSTRUCT` Struktur informiert Windows der Dimensionen in der Liste im Feld im Kombinationsfeld. Wenn das Kombinationsfeld erstellt wird, mit der [CBS_OWNERDRAWVARIABLE](../../mfc/reference/combo-box-styles.md) Stil das Framework ruft diese Member-Funktion für jedes Element im Listenfeld. Andernfalls wird dieser Member nur einmal aufgerufen.  
  
 Mithilfe der **CBS_OWNERDRAWFIXED** Stil in einem Ownerdrawn-Kombinationsfeld erstellt, mit der [SubclassDlgItem](../../mfc/reference/cwnd-class.md#subclassdlgitem) Memberfunktion `CWnd` weitere Programmierung Aspekte umfasst. Finden Sie unter [Technische Hinweis 14](../../mfc/tn014-custom-controls.md).  
  
 Finden Sie unter [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) eine Beschreibung der `MEASUREITEMSTRUCT` Struktur.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#29;](../../mfc/reference/codesnippet/cpp/ccombobox-class_29.cpp)]  
  
##  <a name="a-namepastea--ccomboboxpaste"></a><a name="paste"></a>CComboBox::Paste  
 Die Daten aus der Zwischenablage in das Bearbeitungssteuerelement des Kombinationsfelds an der Cursorposition eingefügt.  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>Hinweise  
 Daten werden eingefügt, nur dann, wenn Daten in die Zwischenablage enthält, **CF_TEXT** Format.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#30;](../../mfc/reference/codesnippet/cpp/ccombobox-class_30.cpp)]  
  
##  <a name="a-nameresetcontenta--ccomboboxresetcontent"></a><a name="resetcontent"></a>CComboBox::ResetContent  
 Entfernt, die alle Elemente aus der Liste im Feld und edit-Steuerelement eines Kombinationsfelds.  
  
```  
void ResetContent();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#31;](../../mfc/reference/codesnippet/cpp/ccombobox-class_31.cpp)]  
  
##  <a name="a-nameselectstringa--ccomboboxselectstring"></a><a name="selectstring"></a>CComboBox::SelectString  
 Sucht nach einer Zeichenfolge im Listenfeld eines Kombinationsfelds, und wenn die Zeichenfolge gefunden wird, wählt die Zeichenfolge im Listenfeld aus und kopiert ihn in das Bearbeitungssteuerelement.  
  
```  
int SelectString(
    int nStartAfter,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Parameter  
 `nStartAfter`  
 Enthält den nullbasierten Index des Elements vor dem ersten Element gesucht werden soll. Erreicht die Suche am Ende das Listenfeld, weiterhin von der obersten Position des Listenfelds wieder das Element mit dem angegebenen `nStartAfter`. Wenn –&1; ist, wird das ganze Listenfeld vom Anfang durchsucht.  
  
 `lpszString`  
 Verweist auf die auf Null endende Zeichenfolge, die das Präfix für die Suche enthält. Die Suche gilt unabhängig, damit diese Zeichenfolge eine beliebige Kombination aus Groß- und Kleinbuchstaben enthalten kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des ausgewählten Elements, wenn die Zeichenfolge gefunden wurde. Wenn die Suche nicht erfolgreich war, ist der Rückgabewert **CB_ERR** und die aktuelle Auswahl wird nicht geändert.  
  
### <a name="remarks"></a>Hinweise  
 Eine Zeichenfolge ausgewählt ist, nur dann, wenn die ersten Zeichen (vom Ausgangspunkt) der Zeichen in der Präfixzeichenfolge entsprechen.  
  
 Beachten Sie, dass die `SelectString` und `FindString` Memberfunktionen beide sucht eine Zeichenfolge, aber die `SelectString` Memberfunktion wählt auch die Zeichenfolge.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#32;](../../mfc/reference/codesnippet/cpp/ccombobox-class_32.cpp)]  
  
##  <a name="a-namesetcuebannera--ccomboboxsetcuebanner"></a><a name="setcuebanner"></a>CComboBox::SetCueBanner  
 Legt den Hinweistext, der für ein Kombinationsfeld-Steuerelement angezeigt wird.  
  
```  
BOOL SetCueBanner(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] *LpszText*|Ein Zeiger auf eine auf Null endende Puffer, der den Hinweistext enthält.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Hinweistext ist eine Aufforderung, die in das Eingabefeld ein Kombinationsfeld-Steuerelement angezeigt wird. Der Hinweistext wird angezeigt, bis der Benutzer die Eingabe vornimmt.  
  
 Diese Methode sendet die [CB_SETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb775897) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_combobox`, d. h. verwendet, um programmgesteuert auf das Kombinationsfeld-Steuerelement zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CComboBox_s&#1;1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird das hinweisbanner für das Kombinationsfeld-Steuerelement.  
  
 [!code-cpp[NVC_MFC_CComboBox_s&#1;2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]  
  
##  <a name="a-namesetcursela--ccomboboxsetcursel"></a><a name="setcursel"></a>CComboBox::SetCurSel  
 Wählt eine Zeichenfolge im Listenfeld eines Kombinationsfelds an.  
  
```  
int SetCurSel(int nSelect);
```  
  
### <a name="parameters"></a>Parameter  
 `nSelect`  
 Gibt den nullbasierten Index der Zeichenfolge auswählen. Wenn –&1; ist, aktuelle Auswahl im Listenfeld entfernt, und das Edit-Steuerelement deaktiviert ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des Elements ausgewählt, wenn die Nachricht erfolgreich ist. Der Rückgabewert ist **CB_ERR** Wenn `nSelect` ist größer als die Anzahl der Elemente in der Liste oder wenn `nSelect` –&1; ist, die die Auswahl löscht festgelegt ist.  
  
### <a name="remarks"></a>Hinweise  
 Bei Bedarf führt einen Bildlauf im Listenfeld die Zeichenfolge an (wenn im Listenfeld angezeigt wird). Der Text in das Steuerelement zum Bearbeiten des Kombinationsfelds wird entsprechend die neue Auswahl geändert. Die vorherige Auswahl im Listenfeld wird entfernt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&33;](../../mfc/reference/codesnippet/cpp/ccombobox-class_35.cpp)]  
  
##  <a name="a-namesetdroppedwidtha--ccomboboxsetdroppedwidth"></a><a name="setdroppedwidth"></a>CComboBox::SetDroppedWidth  
 Rufen Sie diese Funktion, um die minimale zulässige Breite in Pixel im Listenfeld eines Kombinationsfelds festgelegt.  
  
```  
int SetDroppedWidth(UINT nWidth);
```  
  
### <a name="parameters"></a>Parameter  
 `nWidth`  
 Die zulässige Mindestbreite Teil des im Listenfeld des im Kombinationsfeld in Pixel.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, die neue Breite auf der Liste, andernfalls Feld **CB_ERR**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion gilt nur für Kombinationsfelder mit der [CBS_DROPDOWN](../../mfc/reference/combo-box-styles.md) oder [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) Stil.  
  
 Standardmäßig ist die minimale zulässige Breite des Dropdown-Listenfelds 0. Listenfeld Teil des Kombinationsfelds angezeigt wird, wird die Breite größer als die zulässige Mindestbreite oder das Kombinationsfeld Feldbreite.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#34;](../../mfc/reference/codesnippet/cpp/ccombobox-class_36.cpp)]  
  
##  <a name="a-nameseteditsela--ccomboboxseteditsel"></a><a name="seteditsel"></a>CComboBox::SetEditSel  
 Wählt Zeichen in das Steuerelement zum Bearbeiten eines Kombinationsfelds.  
  
```  
BOOL SetEditSel(
    int nStartChar,  
    int nEndChar);
```  
  
### <a name="parameters"></a>Parameter  
 `nStartChar`  
 Gibt die Position an. Wenn Sie die Anfangsposition auf-1 festgelegt ist, wird die bestehende Auswahl entfernt.  
  
 `nEndChar`  
 Gibt die Endposition. Die Endposition ist –&1; ist, dann alle Text von der Startposition bis zum letzten Zeichen in das Steuerelement zum Bearbeiten ausgewählt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Member-Funktion erfolgreich ist; andernfalls 0. Es ist **CB_ERR** Wenn `CComboBox` hat die [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) formatieren oder verfügt nicht über ein Listenfeld.  
  
### <a name="remarks"></a>Hinweise  
 Die Positionen sind nullbasiert. Um das erste Zeichen des Bearbeitungssteuerelements auszuwählen, geben Sie die Startposition 0. Die Endposition ist für das Zeichen unmittelbar nach dem letzten Zeichen auswählen. Markieren Sie die ersten vier Zeichen des Bearbeitungssteuerelements würden Sie z. B. Startposition 0 und eine Endposition 4 verwenden.  
  
> [!NOTE]
>  Diese Funktion wird vom Windows **ComboBoxEx** -Steuerelement nicht unterstützt. Weitere Informationen zu diesem Steuerelement finden Sie unter [ComboBoxEx Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb775738) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CComboBox::GetEditSel](#geteditsel).  
  
##  <a name="a-namesetextendeduia--ccomboboxsetextendedui"></a><a name="setextendedui"></a>CComboBox::SetExtendedUI  
 Rufen Sie die `SetExtendedUI` Memberfunktion, wählen Sie die Standard-Benutzeroberfläche oder die erweiterte Benutzeroberfläche für ein Kombinationsfeld, ist die [CBS_DROPDOWN](../../mfc/reference/combo-box-styles.md) oder [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) Stil.  
  
```  
int SetExtendedUI(BOOL bExtended = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *bDie*  
 Gibt an, ob das Kombinationsfeld die erweiterte Benutzeroberfläche oder die Standardbenutzeroberfläche verwenden möchten. Der Wert **TRUE** wählt die erweiterte Benutzeroberfläche, der Wert **FALSE** wählt die Standardbenutzeroberfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 **CB_OKAY** Wenn der Vorgang erfolgreich ist oder **CB_ERR** Wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Die erweiterte Benutzeroberfläche kann auf folgende Weise identifiziert werden:  
  
-   Durch Klicken auf die statisches Steuerelement wird im Listenfeld nur für Kombinationsfelder mit der **CBS_DROPDOWNLIST** Stil.  
  
-   Drücken die nach-unten-Taste zeigt im Listenfeld (F4 ist deaktiviert).  
  
 Bildlauf im statischen Steuerelement ist deaktiviert, wenn die Liste nicht angezeigt wird (die Pfeiltasten sind deaktiviert).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CComboBox::GetExtendedUI](#getextendedui).  
  
##  <a name="a-namesethorizontalextenta--ccomboboxsethorizontalextent"></a><a name="sethorizontalextent"></a>CComboBox::SetHorizontalExtent  
 Legt die Breite in Pixel mit denen Listenfeld Teil des Kombinationsfelds ein horizontaler Bildlauf durchgeführt werden kann.  
  
```  
void SetHorizontalExtent(UINT nExtent);
```  
  
### <a name="parameters"></a>Parameter  
 *nExtent*  
 Gibt die Anzahl der Pixel, die mit denen Listenfeld Teil des Kombinationsfelds ein horizontaler Bildlauf durchgeführt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Breite des Listenfelds kleiner als dieser Wert ist, wird die horizontale Bildlaufleiste Elemente im Listenfeld horizontale Bildlaufleiste. Wenn die Breite des Listenfelds gleich oder größer als dieser Wert ist, wird die horizontale Bildlaufleiste ausgeblendet oder, wenn das Kombinationsfeld die [CBS_DISABLENOSCROLL](../../mfc/reference/combo-box-styles.md) Stil deaktiviert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#35;](../../mfc/reference/codesnippet/cpp/ccombobox-class_37.cpp)]  
  
##  <a name="a-namesetitemdataa--ccomboboxsetitemdata"></a><a name="setitemdata"></a>CComboBox::SetItemData  
 Legt den 32-Bit-Wert, der das angegebene Element in einem Kombinationsfeld zugeordnet.  
  
```  
int SetItemData(
    int nIndex,  
    DWORD_PTR dwItemData);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Enthält einen nullbasierten Index für das Element fest.  
  
 `dwItemData`  
 Enthält den neuen Wert des Elements zugeordnet.  
  
### <a name="return-value"></a>Rückgabewert  
 **CB_ERR** , wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `SetItemDataPtr` Member-Funktion, wenn die 32-Bit-Element ist ein Zeiger sein.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox Nr.&36;](../../mfc/reference/codesnippet/cpp/ccombobox-class_38.cpp)]  
  
##  <a name="a-namesetitemdataptra--ccomboboxsetitemdataptr"></a><a name="setitemdataptr"></a>CComboBox::SetItemDataPtr  
 Legt den 32-Bit-Wert, der das angegebene Element in einem Kombinationsfeld die angegebenen Zeiger zugeordnet ( **void\***).  
  
```  
int SetItemDataPtr(
    int nIndex,  
    void* pData);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Enthält einen nullbasierten Index des Elements an.  
  
 `pData`  
 Enthält den Zeiger auf dem Element zugeordnet.  
  
### <a name="return-value"></a>Rückgabewert  
 **CB_ERR** , wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 This-Zeiger bleibt gültig, für die Lebensdauer des im Kombinationsfeld, obwohl der Position des Elements relative innerhalb des Kombinationsfelds ändern kann, wenn Elemente hinzugefügt oder entfernt werden. Daher kann der Index des Elements in das Feld ändern, aber der Zeiger bleibt zuverlässige.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#37;](../../mfc/reference/codesnippet/cpp/ccombobox-class_39.cpp)]  
  
##  <a name="a-namesetitemheighta--ccomboboxsetitemheight"></a><a name="setitemheight"></a>CComboBox::SetItemHeight  
 Rufen Sie die `SetItemHeight` Memberfunktion, die die Höhe der Listenelemente in einem Kombinationsfeld oder die Höhe des Bereichs bearbeiten-Steuerelement (oder statischer Text) eines Kombinationsfelds festgelegt.  
  
```  
int SetItemHeight(
    int nIndex,  
    UINT cyItemHeight);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt an, ob die Höhe der Listenelemente oder die Höhe des bearbeiten-Steuerelement (oder statischer Text) Teils des Kombinationsfelds festgelegt ist.  
  
 Verfügt das Kombinationsfeld die [CBS_OWNERDRAWVARIABLE](../../mfc/reference/combo-box-styles.md) Stil `nIndex` gibt den nullbasierten Index des Listenelements, deren Höhe ist, andernfalls werden `nIndex` 0 und die Höhe der alle Liste Elemente festgelegt werden muss.  
  
 Wenn `nIndex` ist-1, die Höhe des Bearbeitungssteuerelements- oder statischer Text Teil des Kombinationsfelds wird festgelegt werden.  
  
 `cyItemHeight`  
 Die Höhe in Pixel angibt, der im Kombinationsfeld Komponente identifizierten `nIndex`.  
  
### <a name="return-value"></a>Rückgabewert  
 **CB_ERR** , wenn der Index oder die Höhe ungültig, andernfalls 0 ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Höhe des bearbeiten-Steuerelement (oder statischer Text) Teils des Kombinationsfelds wird unabhängig von der Höhe der Listenelemente festgelegt werden. Eine Anwendung muss sicherzustellen, dass die Höhe des Bereichs bearbeiten-Steuerelement (oder statischer Text) nicht kleiner als die Höhe eines bestimmten Listenfeld-Elements.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#38;](../../mfc/reference/codesnippet/cpp/ccombobox-class_40.cpp)]  
  
##  <a name="a-namesetlocalea--ccomboboxsetlocale"></a><a name="setlocale"></a>CComboBox::SetLocale  
 Legt den Gebietsschemabezeichner für dieses Kombinationsfeld fest.  
  
```  
LCID SetLocale(LCID nNewLocale);
```  
  
### <a name="parameters"></a>Parameter  
 `nNewLocale`  
 Der neue Gebietsschema-ID (LCID) Wert für das Kombinationsfeld festgelegt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der vorherige Gebietsschema-ID (LCID) Wert für dieses Kombinationsfeld.  
  
### <a name="remarks"></a>Hinweise  
 Wenn **SetLocale** nicht aufgerufen wird, das standardmäßige Gebietsschema vom System abgerufen wird. Dieser Standardgebietsschema kann geändert werden, mithilfe der Systemsteuerung Regions-(International-Anwendung).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox Nr.&39;](../../mfc/reference/codesnippet/cpp/ccombobox-class_41.cpp)]  
  
##  <a name="a-namesetminvisibleitemsa--ccomboboxsetminvisibleitems"></a><a name="setminvisibleitems"></a>CComboBox::SetMinVisibleItems  
 Legt die minimale Anzahl der sichtbaren Elemente in der Dropdown-Liste des aktuellen Kombinationsfeld-Steuerelement fest.  
  
```  
BOOL SetMinVisibleItems(int iMinVisible);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iMinVisible`|Gibt die minimale Anzahl der sichtbaren Elemente.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [CB_SETMINVISIBLE](http://msdn.microsoft.com/library/windows/desktop/bb775915) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_combobox`, d. h. verwendet, um programmgesteuert auf das Kombinationsfeld-Steuerelement zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CComboBox_s&#1;1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel fügt 20 Elemente in der Dropdownliste ein Kombinationsfeld-Steuerelement. Dann gibt an, dass mindestens 10 Elemente angezeigt werden, wenn ein Benutzer auf den Dropdown Pfeil drückt.  
  
 [!code-cpp[NVC_MFC_CComboBox_s&#1;2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]  
  
##  <a name="a-namesettopindexa--ccomboboxsettopindex"></a><a name="settopindex"></a>CComboBox::SetTopIndex  
 Stellt sicher, dass ein bestimmtes Element im Listenfeld Teil des Kombinationsfelds angezeigt wird.  
  
```  
int SetTopIndex(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index des Elements im Listenfeld an.  
  
### <a name="return-value"></a>Rückgabewert  
 NULL Wenn erfolgreich, oder **CB_ERR** Wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Das System führt einen Bildlauf im Listenfeld bis entweder das Element vom angegebenen `nIndex` wird am Anfang der Liste im Feld oder die maximale Bildlaufbereich erreicht wurde.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox&#40;](../../mfc/reference/codesnippet/cpp/ccombobox-class_42.cpp)]  
  
##  <a name="a-nameshowdropdowna--ccomboboxshowdropdown"></a><a name="showdropdown"></a>CComboBox::ShowDropDown  
 Blendet das Listenfeld ein Kombinationsfeld, ist die [CBS_DROPDOWN](../../mfc/reference/combo-box-styles.md) oder [CBS_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) Stil.  
  
```  
void ShowDropDown(BOOL bShowIt = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *bShowIt*  
 Gibt an, ob im Dropdown-Listenfeld angezeigt oder ausgeblendet werden. Der Wert **TRUE** im Listenfeld zeigt. Der Wert **FALSE** Blendet Sie aus dem Listenfeld.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird ein Kombinationsfeld dieses Formats im Listenfeld angezeigt.  
  
 Diese Memberfunktion hat keine Auswirkung auf das Kombinationsfeld erstellt, mit der [CBS_SIMPLE](../../mfc/reference/combo-box-styles.md) Stil.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CComboBox::GetDroppedState](#getdroppedstate).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Muster CTRLBARS](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [CButton-Klasse](../../mfc/reference/cbutton-class.md)   
 [CEdit-Klasse](../../mfc/reference/cedit-class.md)   
 [CListBox-Klasse](../../mfc/reference/clistbox-class.md)   
 [CScrollBar-Klasse](../../mfc/reference/cscrollbar-class.md)   
 [CStatic-Klasse](../../mfc/reference/cstatic-class.md)   
 [CDialog-Klasse](../../mfc/reference/cdialog-class.md)

