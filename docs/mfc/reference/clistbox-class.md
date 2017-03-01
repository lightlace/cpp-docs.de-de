---
title: CListBox-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CListBox
dev_langs:
- C++
helpviewer_keywords:
- CListBox class
- list boxes
ms.assetid: 7ba3c699-c286-4cd9-9066-532c41ec05d1
caps.latest.revision: 26
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
ms.openlocfilehash: f4df970f2df35d399c0c700cf504a76482ad3f6d
ms.lasthandoff: 02/24/2017

---
# <a name="clistbox-class"></a>CListBox-Klasse
Stellt die Funktionalität eines Windows-Listenfelds bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CListBox : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CListBox::CListBox](#clistbox)|Erstellt ein `CListBox`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CListBox::AddString](#addstring)|Fügt eine Zeichenfolge in ein Listenfeld an.|  
|[CListBox::CharToItem](#chartoitem)|Überschreiben, um benutzerdefinierte bieten `WM_CHAR` Ownerdrawn-Listenfelder die Zeichenfolgen nicht behandelt.|  
|[CListBox::CompareItem](#compareitem)|Aufgerufen, um die Position eines neuen Elements in einem sortierten Ownerdrawn Listenfeld zu bestimmen.|  
|[CListBox::Create](#create)|Erstellt die Windows-Listenfelds und fügt es der `CListBox` Objekt.|  
|[CListBox::DeleteItem](#deleteitem)|Wird vom Framework aufgerufen, wenn der Benutzer ein Element aus einem Ownerdrawn-Listenfeld löscht.|  
|[CListBox::DeleteString](#deletestring)|Löscht eine Zeichenfolge aus einem Listenfeld.|  
|[CListBox::Dir](#dir)|Fügt Dateinamen und/oder Laufwerke des aktuellen Verzeichnisses zu einem Listenfeld.|  
|[CListBox::DrawItem](#drawitem)|Aufgerufen, wenn sich ein Darstellungsaspekt eines Ownerdrawn-Liste im Feld ändert.|  
|[CListBox:: FindString](#findstring)|Sucht eine Zeichenfolge in einem Listenfeld.|  
|[CListBox::FindStringExact](#findstringexact)|Sucht die erste Listenfeld-Zeichenfolge, die einer angegebenen Zeichenfolge übereinstimmt.|  
|[CListBox::GetAnchorIndex](#getanchorindex)|Ruft den nullbasierten Index des aktuellen Elements in einem Listenfeld Anker ab.|  
|[CListBox::GetCaretIndex](#getcaretindex)|Bestimmt den Index des Elements, das in einem Mehrfachauswahl-Listenfeld Fokusrechtecks hat.|  
|[CListBox::GetCount](#getcount)|Gibt die Anzahl der Zeichenfolgen in einem Listenfeld zurück.|  
|[CListBox::GetCurSel](#getcursel)|Gibt den nullbasierten Index des derzeit ausgewählten Zeichenfolge in einem Listenfeld zurück.|  
|[CListBox::GetHorizontalExtent](#gethorizontalextent)|Gibt die Breite in Pixel, ein Listenfeld, das ein horizontaler Bildlauf durchgeführt werden kann.|  
|[CListBox::GetItemData](#getitemdata)|Der 32-Bit-Wert, der dem Element im Listenfeld zugeordnete zurückgegeben.|  
|[CListBox::GetItemDataPtr](#getitemdataptr)|Gibt einen Zeiger auf ein Element im Listenfeld.|  
|[CListBox::GetItemHeight](#getitemheight)|Bestimmt die Höhe der Elemente in einem Listenfeld.|  
|[CListBox::GetItemRect](#getitemrect)|Gibt das umschließende Rechteck des Elements im Listenfeld zurück, wie er derzeit angezeigt wird.|  
|[CListBox::GetListBoxInfo](#getlistboxinfo)|Ruft die Anzahl der Elemente pro Spalte ab.|  
|[CListBox::GetLocale](#getlocale)|Ruft die Gebietsschema-ID für ein Listenfeld.|  
|[CListBox::GetSel](#getsel)|Gibt den Auswahlzustand eines Elements im Listenfeld zurück.|  
|[CListBox::GetSelCount](#getselcount)|Gibt die Anzahl der Zeichenfolgen, die in einem Mehrfachauswahl-Listenfeld ausgewählte zurück.|  
|[CListBox::GetSelItems](#getselitems)|Gibt die Indizes der in einem Listenfeld ausgewählte Zeichenfolgen zurück.|  
|[CListBox::GetText](#gettext)|Kopiert ein Element im Listenfeld in einem Puffer.|  
|[CListBox::GetTextLen](#gettextlen)|Gibt die Länge in Bytes eines Elements im Listenfeld zurück.|  
|[CListBox::GetTopIndex](#gettopindex)|Gibt den Index der ersten sichtbaren Zeichenfolge in einem Listenfeld zurück.|  
|[CListBox::InitStorage](#initstorage)|Journaldateien Speicherblöcke Listenfeldelemente und Zeichenfolgen.|  
|[CListBox::InsertString](#insertstring)|Fügt eine Zeichenfolge an einer bestimmten Position in einem Listenfeld.|  
|[CListBox::ItemFromPoint](#itemfrompoint)|Gibt den Index des Elements im Listenfeld am nächsten an einem Punkt.|  
|[CListBox::MeasureItem](#measureitem)|Wird vom Framework aufgerufen, wenn ein Ownerdrawn-Listenfeld erstellt wird, um das Listenfeld Dimensionen zu bestimmen.|  
|[CListBox::ResetContent](#resetcontent)|Löscht alle Einträge aus einem Listenfeld.|  
|[CListBox::SelectString](#selectstring)|Sucht und wählt aus einer Zeichenfolge in einem Mehrfachauswahl-Listenfeld.|  
|[CListBox::SelItemRange](#selitemrange)|Aktiviert oder deaktiviert einen Bereich von Zeichenfolgen in einem Mehrfachauswahl-Listenfeld.|  
|[CListBox::SetAnchorIndex](#setanchorindex)|Legt den Anker in einem Mehrfachauswahl-Listenfeld zu einer erweiterten Auswahl fest.|  
|[CListBox::SetCaretIndex](#setcaretindex)|Legt das Fokusrechteck für das Element am angegebenen Index in einem Mehrfachauswahl-Listenfeld.|  
|[CListBox::SetColumnWidth](#setcolumnwidth)|Legt die Spaltenbreite eines mehrspaltigen Listenfelds fest.|  
|[CListBox::SetCurSel](#setcursel)|Wählt aus eine Zeichenfolge im Listenfeld.|  
|[CListBox:: SetHorizontalExtent](#sethorizontalextent)|Legt die Breite in Pixel, ein Listenfeld, das ein horizontaler Bildlauf durchgeführt werden kann.|  
|[CListBox::SetItemData](#setitemdata)|Legt den 32-Bit-Wert, der dem Element im Listenfeld zugeordnete.|  
|[CListBox::SetItemDataPtr](#setitemdataptr)|Ein Zeiger festgelegt auf das Element im Listenfeld.|  
|[CListBox::SetItemHeight](#setitemheight)|Legt die Höhe der Elemente in einem Listenfeld.|  
|[CListBox::SetLocale](#setlocale)|Legt die Gebietsschema-ID für ein Listenfeld an.|  
|[CListBox::SetSel](#setsel)|Aktiviert oder deaktiviert ein Element im Listenfeld in einem Mehrfachauswahl-Listenfeld.|  
|[CListBox::SetTabStops](#settabstops)|Legt die Tabstopp Positionen in einem Listenfeld.|  
|[CListBox::SetTopIndex](#settopindex)|Legt den nullbasierten Index des ersten sichtbaren Zeichenfolge in einem Listenfeld.|  
|[CListBox::VKeyToItem](#vkeytoitem)|Überschreiben, um benutzerdefinierte bieten `WM_KEYDOWN` für Listenfelder mit den **LBS_WANTKEYBOARDINPUT** Set formatieren.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Listenfeld zeigt eine Liste von Elementen, z. B. Dateinamen, die der Benutzer anzeigen und auswählen kann.  
  
 In einem Mehrfachauswahl-Listenfeld kann der Benutzer nur ein Element auswählen. In einem Mehrfachauswahl-Listenfeld kann eine Reihe von Elementen ausgewählt werden. Wenn der Benutzer ein Element auswählt, wird hervorgehoben, und das Listenfeld sendet eine Benachrichtigung an das übergeordnete Fenster.  
  
 Sie können ein Listenfeld, das aus einer Dialogfeldvorlage oder direkt im Code erstellen. Um direkt zu erstellen, legen die `CListBox` -Objekt, und rufen Sie dann die [erstellen](#create) Memberfunktion, die das Windows-Steuerelement erstellen und Anfügen an die `CListBox` Objekt. Um ein Listenfeld in einem Dialogfeldvorlage zu verwenden, deklarieren Sie eine Variable im Listenfeld in der Dialogfeldklasse, und verwenden Sie `DDX_Control` in Ihre Dialogfeldklasse `DoDataExchange` Funktion für das Steuerelement die Verbindung die Membervariable. (Dies wird für Sie automatisch konfiguriert, wenn Sie Ihre Dialogfeldklasse eine Steuerelementvariable hinzufügen.)  
  
 Konstruktion kann ein langwieriger Vorgang in einer abgeleiteten Klasse `CListBox`. Schreiben Sie einen Konstruktor für die abgeleitete Klasse und rufen **erstellen** von innerhalb des Konstruktors.  
  
 Wenn Sie Windows-Benachrichtigung gesendet von einem Listenfeld zum übergeordneten behandeln möchten (in der Regel eine abgeleitete Klasse [CDialog](../../mfc/reference/cdialog-class.md)), die übergeordnete Klasse für jede Nachricht eine meldungszuordnung Eintrag und Meldungshandler Memberfunktion hinzugefügt.  
  
 Jede Meldungszuordnungseintrags hat das folgende Format:  
  
 `ON_Notification( id, memberFxn )`  
  
 wobei `id` gibt die untergeordneten Fenster-ID des Listenfeld-Steuerelements, das Senden der Benachrichtigung und `memberFxn` ist der Name der übergeordneten Member-Funktion, die Sie geschrieben haben, um die Benachrichtigung zu verarbeiten.  
  
 Das übergeordnete Funktionsprototyp lautet wie folgt:  
  
 `afx_msg void memberFxn( );`  
  
 Es folgt eine Liste der möglichen Meldungszuordnungseinträge und eine Beschreibung der Fälle, in denen sie an das übergeordnete Element gesendet werden:  
  
- **ON_LBN_DBLCLK** der Benutzer doppelklickt eine Zeichenfolge in einem Listenfeld. Nur ein Listenfeld an, die die [LBS_NOTIFY](../../mfc/reference/list-box-styles.md) Stil sendet diese Benachrichtigung.  
  
- **ON_LBN_ERRSPACE** im Listenfeld kann nicht ausreichend Speicher zum Erfüllen der Anforderungs zuordnen.  
  
- **ON_LBN_KILLFOCUS** im Listenfeld den Eingabefokus verliert.  
  
- **ON_LBN_SELCANCEL** die aktuelle Auswahl im Listenfeld abgebrochen wird. Diese Nachricht wird nur gesendet, wenn ein Listenfeld der **LBS_NOTIFY** Stil.  
  
- **ON_LBN_SELCHANGE** die Auswahl im Listenfeld wurde geändert. Diese Benachrichtigung wird nicht gesendet, wenn die Auswahl ändert die [CListBox::SetCurSel](#setcursel) Member-Funktion. Diese Benachrichtigung gilt nur für ein Listenfeld, die die **LBS_NOTIFY** Stil. Die **LBN_SELCHANGE** Nachricht wird gesendet, für eine Mehrfachauswahl-Listenfeld Wenn der Benutzer eine Taste drückt, selbst wenn die Auswahl nicht geändert wird.  
  
- **ON_LBN_SETFOCUS** im Listenfeld erhält den Eingabefokus besitzt.  
  
- **ON_WM_CHARTOITEM** ein Ownerdrawn-Listenfeld, die keine Zeichenfolgen empfängt eine `WM_CHAR` Nachricht.  
  
- **ON_WM_VKEYTOITEM** ein Listenfeld mit den **LBS_WANTKEYBOARDINPUT** Stil empfängt eine `WM_KEYDOWN` Nachricht.  
  
 Bei der Erstellung einer `CListBox` Objekt in einem Dialogfeld (über eine Dialogfeldressource), die `CListBox` Objekt wird automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Bei der Erstellung einer `CListBox` Objekt innerhalb eines Fensters müssen Sie möglicherweise Zerstören der `CListBox` Objekt. Bei der Erstellung der `CListBox` Objekt auf dem Stapel automatisch zerstört wird. Bei der Erstellung der `CListBox` Objekt auf dem Heap mithilfe der **neue** -Funktion, die Sie aufrufen müssen **löschen** auf das Objekt, das es zerstört, wenn der Benutzer das übergeordnete Fenster geschlossen wird.  
  
 Wenn Sie alle in Speicher der `CListBox` Objekt, das Überschreiben der `CListBox` Destruktor, um die Zuordnung zu entfernen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CListBox`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="a-nameaddstringa--clistboxaddstring"></a><a name="addstring"></a>CListBox::AddString  
 Fügt eine Zeichenfolge in ein Listenfeld an.  
  
```  
int AddString(LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszItem`  
 Verweist auf die auf Null endende Zeichenfolge, die hinzugefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index in der Zeichenfolge im Listenfeld. Der Rückgabewert ist **LB_ERR** Wenn ein Fehler auftritt, ist der Rückgabewert **LB_ERRSPACE** ist nicht genügend Speicherplatz zum Speichern der neuen Zeichenfolge verfügbar.  
  
### <a name="remarks"></a>Hinweise  
 Wenn im Listenfeld nicht erstellt wurde, mit der [LBS_SORT](../../mfc/reference/list-box-styles.md) Stil, wird die Zeichenfolge an das Ende der Liste hinzugefügt. Andernfalls wird die Zeichenfolge in die Liste eingefügt, und die Liste sortiert. Wenn im Listenfeld mit erstellt wurde der **LBS_SORT** formatieren, aber nicht die [LBS_HASSTRINGS](../../mfc/reference/list-box-styles.md) Format, das Framework sortiert die Liste durch ein oder mehrere Aufrufe der `CompareItem` Member-Funktion.  
  
 Verwendung [InsertString](#insertstring) eine Zeichenfolge in einer bestimmten Position in das Listenfeld eingefügt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&3;](../../mfc/codesnippet/cpp/clistbox-class_1.cpp)]  
  
##  <a name="a-namechartoitema--clistboxchartoitem"></a><a name="chartoitem"></a>CListBox::CharToItem  
 Vom Framework aufgerufen, wenn das Listenfeld übergeordneten Fenster empfängt eine `WM_CHARTOITEM` Nachricht aus dem Listenfeld aus.  
  
```  
virtual int CharToItem(
    UINT nKey,  
    UINT nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nKey`  
 Der ANSI-Code, der das vom Benutzer eingegebene Zeichen werden soll.  
  
 `nIndex`  
 Die aktuelle Position der Einfügemarke im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt – 1 oder – 2 keine weitere Aktion oder eine negative Zahl an, dass ein Index eines Elements im Listenfeld aus, um die Standardaktion für die Tastatureingabe auszuführen. Die standardmäßige Implementierung gibt – 1.  
  
### <a name="remarks"></a>Hinweise  
 Die `WM_CHARTOITEM` Nachricht im Listenfeld beim Empfang einer `WM_CHAR` Nachricht, aber, nur wenn das Listenfeld alle diese Kriterien erfüllt:  
  
-   Ist ein Ownerdrawn-Listenfeld.  
  
-   Verfügt nicht über die [LBS_HASSTRINGS](../../mfc/reference/list-box-styles.md) Set formatieren.  
  
-   Hat mindestens ein Element.  
  
 Sie sollten diese Funktion nie selbst aufrufen. Überschreiben Sie diese Funktion, um eigene benutzerdefinierte Behandlung von Tastatureingaben bereitzustellen.  
  
 In der Überschreibung müssen Sie einen Wert für dem Framework angeben, welche Aktion Sie durchgeführt zurückgeben. Ein Rückgabewert von – 1 oder – 2 bedeutet, dass Sie behandelt alle Aspekte der Sie das Element auswählen und erfordert keine weitere Aktion im Listenfeld. Vor der Rückgabe – 1 oder – 2, Sie konnten die Option oder und/oder die Einfügemarke zu verschieben. Verwenden Sie zum Festlegen der Auswahl [SetCurSel](#setcursel) oder [Memberfunktion SetSel](#setsel). Verwenden Sie zum Verschieben der Einfügemarke [SetCaretIndex](#setcaretindex).  
  
 Ein Rückgabewert von 0 oder größer gibt den Index eines Elements im Listenfeld an und gibt an, dass im Listenfeld die Standardaktion für die Tastatureingabe auf das angegebene Element ausführen soll.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&4;](../../mfc/codesnippet/cpp/clistbox-class_2.cpp)]  
  
##  <a name="a-nameclistboxa--clistboxclistbox"></a><a name="clistbox"></a>CListBox::CListBox  
 Erstellt ein `CListBox`-Objekt.  
  
```  
CListBox();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen ein `CListBox` Objekt in zwei Schritten. Zunächst rufen Sie den Konstruktor **ClistBox** und rufen Sie dann **erstellen**, die die Windows-Listenfelds initialisiert und fügt es der `CListBox`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#1;](../../mfc/codesnippet/cpp/clistbox-class_3.cpp)]  
  
##  <a name="a-namecompareitema--clistboxcompareitem"></a><a name="compareitem"></a>CListBox::CompareItem  
 Aufgerufen, um die relative Position eines neuen Elements in einem sortierten Ownerdrawn Listenfeld zu bestimmen.  
  
```  
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpCompareItemStruct`  
 Ein long-Zeiger auf eine `COMPAREITEMSTRUCT` Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Die relative Position der beiden Elemente beschrieben, die der [COMPAREITEMSTRUCT](../../mfc/reference/compareitemstruct-structure.md) Struktur. Es kann eines der folgenden Werte sein:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|–1|Element 1 wird vor Element 2 sortiert.|  
|0|Artikel 1 und Artikel 2 sortieren identisch.|  
|1|Element 1 wird nach Element 2 sortiert.|  
  
 Finden Sie unter [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) eine Beschreibung der `COMPAREITEMSTRUCT` Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird dieser Member-Funktion keine Aktion ausgeführt. Bei der Erstellung einer Ownerdrawn-Listenfeld mit den **LBS_SORT** Stil, müssen Sie diese Memberfunktion auf, bei der das Framework sortieren neue Elemente im Listenfeld überschreiben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&5;](../../mfc/codesnippet/cpp/clistbox-class_4.cpp)]  
  
##  <a name="a-namecreatea--clistboxcreate"></a><a name="create"></a>CListBox::Create  
 Erstellt die Windows-Listenfelds und fügt es der `CListBox` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt den Stil des Listenfelds. Wenden Sie eine beliebige Kombination von [listenfeldstile](../../mfc/reference/list-box-styles.md) in das Feld.  
  
 `rect`  
 Gibt an, die im Listenfeld Größe und Position. Kann entweder ein `CRect` Objekt oder eine `RECT` Struktur.  
  
 `pParentWnd`  
 Gibt an, im Listenfeld des übergeordneten Fensters (in der Regel ein `CDialog` Objekt). Er darf nicht sein **NULL**.  
  
 `nID`  
 Gibt das Listenfeld-Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen ein `CListBox` Objekt in zwei Schritten. Zunächst rufen Sie den Konstruktor, und rufen Sie dann **erstellen**, die Windows-Listenfelds initialisiert und fügt es der `CListBox` Objekt.  
  
 Wenn **erstellen** ausgeführt wird, sendet Windows die [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), und [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Nachrichten an das Listenfeld-Steuerelement.  
  
 Diese Nachrichten werden standardmäßig verarbeitet die [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), und [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Memberfunktionen in der `CWnd` Basisklasse. Um die Standardbehandlung für die Nachricht zu erweitern, leiten Sie eine Klasse von `CListBox`, Hinzufügen einer Nachricht Zuordnung zu der neuen Klasse und überschreiben Sie die vorherigen Meldungshandler-Memberfunktionen. Überschreiben Sie `OnCreate`, z. B. für die erforderliche Initialisierung für eine neue Klasse.  
  
 Übernehmen Sie das folgende [Fensterstile](../../mfc/reference/window-styles.md) an ein Listenfeld-Steuerelement.  
  
- **WS_CHILD** immer  
  
- **WS_VISIBLE** in der Regel  
  
- **WS_DISABLED** selten  
  
- **WS_VSCROLL** eine vertikale Bildlaufleiste hinzufügen  
  
- **WS_HSCROLL** hinzufügen eine horizontalen Bildlaufleiste  
  
- **WS_GROUP** zum Gruppieren von Steuerelementen  
  
- **WS_TABSTOP** , können die TAB-Taste zu diesem Steuerelement  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#2;](../../mfc/codesnippet/cpp/clistbox-class_5.cpp)]  
  
##  <a name="a-namedeleteitema--clistboxdeleteitem"></a><a name="deleteitem"></a>CListBox::DeleteItem  
 Vom Framework aufgerufen, wenn der Benutzer ein Element aus einem Ownerdrawn-löscht `CListBox` -Objekt oder im Listenfeld zerstört.  
  
```  
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDeleteItemStruct`  
 Ein long-Zeiger zu einem Windows [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md) -Struktur, die Informationen über das gelöschte Element enthält.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um ein Ownerdrawn Listenfeld nach Bedarf neu gezeichnet werden.  
  
 Finden Sie unter [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) eine Beschreibung der `DELETEITEMSTRUCT` Struktur.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&6;](../../mfc/codesnippet/cpp/clistbox-class_6.cpp)]  
  
##  <a name="a-namedeletestringa--clistboxdeletestring"></a><a name="deletestring"></a>CListBox::DeleteString  
 Löscht das Element an Position `nIndex` aus dem Listenfeld aus.  
  
```  
int DeleteString(UINT nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index der Zeichenfolge, die gelöscht werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeichenfolgen in der Liste verbleiben. Der Rückgabewert ist **LB_ERR** Wenn `nIndex` Index größer als die Anzahl der Elemente in der Liste angibt.  
  
### <a name="remarks"></a>Hinweise  
 Alle Elemente, die nach `nIndex` jetzt eine Position nach unten zu verschieben. Z. B. wenn ein Listenfeld, das zwei Elemente enthält, bewirkt löschen das erste Element den verbleibenden Artikel jetzt in der ersten Position sein. `nIndex`=&0; für das Element in der ersten Position.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#7;](../../mfc/codesnippet/cpp/clistbox-class_7.cpp)]  
  
##  <a name="a-namedira--clistboxdir"></a><a name="dir"></a>CListBox::Dir  
 Eine Liste von Dateinamen und/oder Laufwerke zu einem Listenfeld hinzugefügt.  
  
```  
int Dir(
    UINT attr,  
    LPCTSTR lpszWildCard);
```  
  
### <a name="parameters"></a>Parameter  
 `attr`  
 Kann eine beliebige Kombination der `enum` Werte in beschriebenen **CFile::GetStatu**[s](../../mfc/reference/cfile-class.md#getstatus), oder eine beliebige Kombination der folgenden Werte:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|0x0000|Datei kann aus gelesen oder geschrieben werden.|  
|0 x&0001;|Datei auslesen, jedoch nicht in den geschrieben werden kann.|  
|0 x&0002;|Datei ausgeblendet, und nicht in einer Verzeichnisliste angezeigt.|  
|0 x&0004;|Datei ist eine Systemdatei.|  
|0x0010|Den Namen `lpszWildCard` gibt ein Verzeichnis an.|  
|0x0020|Datei wurde archiviert.|  
|0 x&4000;|Alle Laufwerke, die mit den angegebenen Namen übereinstimmen `lpszWildCard`.|  
|0 x&8000;|Exklusive Flag. Wenn der exklusive Flag festgelegt ist, werden nur Dateien des angegebenen Typs aufgeführt. Andernfalls werden die Dateien des angegebenen Typs zusätzlich zu "normale" Dateien aufgeführt.|  
  
 `lpszWildCard`  
 Zeigt auf eine Dateispezifikation Zeichenfolge. Die Zeichenfolge kann Platzhalter enthalten (z. B. *.\*).  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des letzten Filename zur Liste hinzugefügt werden soll. Der Rückgabewert ist **LB_ERR** Wenn ein Fehler auftritt, ist der Rückgabewert **LB_ERRSPACE** ist nicht genügend Speicherplatz zum Speichern der neuen Zeichenfolgen zur Verfügung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#8;](../../mfc/codesnippet/cpp/clistbox-class_8.cpp)]  
  
##  <a name="a-namedrawitema--clistboxdrawitem"></a><a name="drawitem"></a>CListBox::DrawItem  
 Aufgerufen, wenn sich ein Darstellungsaspekt eines Ownerdrawn-Liste im Feld ändert.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDrawItemStruct`  
 Ein long-Zeiger auf eine [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) -Struktur, die Informationen über den Typ der erforderlichen Zeichnung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die **ItemAction** und **ItemState** Mitglieder der `DRAWITEMSTRUCT` Struktur definieren, die Zeichnen-Aktion, die ausgeführt werden soll.  
  
 Standardmäßig wird dieser Member-Funktion keine Aktion ausgeführt. Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für eine Ownerdrawn- `CListBox` Objekt. Die Anwendung sollte alle Grafiken Device Interface (GDI) Objekte ausgewählt, für der Anzeigekontext im angegebenen wiederherstellen `lpDrawItemStruct` vor diesem Element Funktion beendet wird.  
  
 Finden Sie unter [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) eine Beschreibung der `DRAWITEMSTRUCT` Struktur.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#9;](../../mfc/codesnippet/cpp/clistbox-class_9.cpp)]  
  
##  <a name="a-namefindstringa--clistboxfindstring"></a><a name="findstring"></a>CListBox:: FindString  
 Sucht die erste Zeichenfolge in einem Listenfeld, das das angegebene Präfix enthält, ohne die Auswahl im Listenfeld zu ändern.  
  
```  
int FindString(
    int nStartAfter,  
    LPCTSTR lpszItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nStartAfter`  
 Enthält den nullbasierten Index des Elements vor dem ersten Element gesucht werden soll. Erreicht die Suche am Ende das Listenfeld, weiterhin von der obersten Position des Listenfelds wieder das Element mit dem angegebenen `nStartAfter`. Wenn `nStartAfter` –&1; ist, wird das ganze Listenfeld wird vom Anfang durchsucht.  
  
 `lpszItem`  
 Verweist auf die auf Null endende Zeichenfolge, die das Präfix für die Suche enthält. Die Suche gilt unabhängig, damit diese Zeichenfolge eine beliebige Kombination aus Groß- und Kleinbuchstaben enthalten kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des entsprechenden Elements oder **LB_ERR** Wenn die Suche nicht erfolgreich war.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [SelectString](#selectstring) Memberfunktion sowohl suchen, und wählen Sie eine Zeichenfolge.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#10;](../../mfc/codesnippet/cpp/clistbox-class_10.cpp)]  
  
##  <a name="a-namefindstringexacta--clistboxfindstringexact"></a><a name="findstringexact"></a>CListBox::FindStringExact  
 Sucht nach der ersten Listenfeld-Zeichenfolge, die im angegebenen Zeichenfolge entspricht `lpszFind`.  
  
```  
int FindStringExact(
    int nIndexStart,  
    LPCTSTR lpszFind) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndexStart`  
 Gibt den nullbasierten Index des Elements vor dem ersten Element gesucht werden soll. Erreicht die Suche am Ende das Listenfeld, weiterhin von der obersten Position des Listenfelds wieder das Element mit dem angegebenen `nIndexStart`. Wenn `nIndexStart` –&1; ist, wird das ganze Listenfeld wird vom Anfang durchsucht.  
  
 `lpszFind`  
 Verweist auf die zu suchende Zeichenfolge Null-terminiert. Diese Zeichenfolge kann einen vollständigen Dateinamen einschließlich der Erweiterung enthalten. Die Suche ist nicht Groß-/Kleinschreibung, damit die Zeichenfolge eine beliebige Kombination aus Groß- und Kleinbuchstaben enthalten kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des entsprechenden Elements oder **LB_ERR** Wenn die Suche nicht erfolgreich war.  
  
### <a name="remarks"></a>Hinweise  
 Wenn im Listenfeld mit einem Ownerdrawn-Stil, jedoch ohne erstellt wurde die [LBS_HASSTRINGS](../../mfc/reference/list-box-styles.md) Stil der `FindStringExact` Member-Funktion versucht, den Doppelwort Wert anhand des Werts eines `lpszFind`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#11;](../../mfc/codesnippet/cpp/clistbox-class_11.cpp)]  
  
##  <a name="a-namegetanchorindexa--clistboxgetanchorindex"></a><a name="getanchorindex"></a>CListBox::GetAnchorIndex  
 Ruft den nullbasierten Index des aktuellen Elements im Listenfeld Anker ab.  
  
```  
int GetAnchorIndex() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des aktuellen Anchor-Elements, wenn erfolgreich; andernfalls **LB_ERR**.  
  
### <a name="remarks"></a>Hinweise  
 In einem Mehrfachauswahl-Listenfeld ist das Anchor-Element der ersten bzw. letzten Element in einem Block zusammenhängender ausgewählter Elemente.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CListBox::SetAnchorIndex](#setanchorindex).  
  
##  <a name="a-namegetcaretindexa--clistboxgetcaretindex"></a><a name="getcaretindex"></a>CListBox::GetCaretIndex  
 Bestimmt den Index des Elements, das in einem Mehrfachauswahl-Listenfeld Fokusrechtecks hat.  
  
```  
int GetCaretIndex() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des Elements, das in einem Listenfeld Fokusrechtecks hat. Ist im Listenfeld eine Mehrfachauswahl-Listenfeld, ist der Rückgabewert der Index des Elements, das ausgewählt ist, sofern vorhanden.  
  
### <a name="remarks"></a>Hinweise  
 Das Element kann oder nicht mehr ausgewählt werden.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CListBox::SetCaretIndex](#setcaretindex).  
  
##  <a name="a-namegetcounta--clistboxgetcount"></a><a name="getcount"></a>CListBox::GetCount  
 Ruft die Anzahl der Elemente in einem Listenfeld ab.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Listenfeld oder **LB_ERR** Wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Die zurückgegebene Anzahl ist größer als der Wert für das letzte Element (der Index ist nullbasiert).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#12;](../../mfc/codesnippet/cpp/clistbox-class_12.cpp)]  
  
##  <a name="a-namegetcursela--clistboxgetcursel"></a><a name="getcursel"></a>CListBox::GetCurSel  
 Ruft den nullbasierten Index des derzeit ausgewählten Elements ab, sofern vorhanden, in einem Mehrfachauswahl-Listenfeld.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des aktuell ausgewählten Elements, wenn es einem Mehrfachauswahl-Listenfeld ist. Es ist `LB_ERR` Wenn derzeit kein Element ausgewählt ist.  
  
 In einem Mehrfachauswahl-Listenfeld, den Index des Elements, das den Fokus besitzt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `GetCurSel` für eine Mehrfachauswahl-Listenfeld. Verwendung [CListBox::GetSelItems](#getselitems) stattdessen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#13;](../../mfc/codesnippet/cpp/clistbox-class_13.cpp)]  
  
##  <a name="a-namegethorizontalextenta--clistboxgethorizontalextent"></a><a name="gethorizontalextent"></a>CListBox::GetHorizontalExtent  
 Ruft die Breite in Pixel, mit denen sie ein horizontaler Bildlauf durchgeführt werden kann, aus dem Listenfeld ab.  
  
```  
int GetHorizontalExtent() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die bildlauffähigen Breite des Listenfelds in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Dies gilt nur, wenn im Listenfeld eine horizontale Bildlaufleiste angezeigt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&14;](../../mfc/codesnippet/cpp/clistbox-class_14.cpp)]  
  
##  <a name="a-namegetitemdataa--clistboxgetitemdata"></a><a name="getitemdata"></a>CListBox::GetItemData  
 Ruft den dem angegebenen Listenfeld-Element zugeordnete Anwendung bereitgestellte Doppelwort ab.  
  
```  
DWORD_PTR GetItemData(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index des Elements im Listenfeld an.  
  
### <a name="return-value"></a>Rückgabewert  
 Der 32-Bit-Wert, der dem Element zugeordnete oder **LB_ERR** Wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Doppelwort wurde der `dwItemData` Parameter ein [SetItemData](#setitemdata) aufrufen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#15;](../../mfc/codesnippet/cpp/clistbox-class_15.cpp)]  
  
##  <a name="a-namegetitemdataptra--clistboxgetitemdataptr"></a><a name="getitemdataptr"></a>CListBox::GetItemDataPtr  
 Ruft die von der Anwendung bereitgestellten 32-Bit-Wert mit dem angegebenen Listenfeld-Element als Zeiger verknüpfte ( **void\***).  
  
```  
void* GetItemDataPtr(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index des Elements im Listenfeld an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ruft einen Zeiger oder -1 ab, wenn ein Fehler auftritt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox Nr.&16;](../../mfc/codesnippet/cpp/clistbox-class_16.cpp)]  
  
##  <a name="a-namegetitemheighta--clistboxgetitemheight"></a><a name="getitemheight"></a>CListBox::GetItemHeight  
 Bestimmt die Höhe der Elemente in einem Listenfeld.  
  
```  
int GetItemHeight(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index des Elements im Listenfeld an. Dieser Parameter wird verwendet, nur dann, wenn das Listenfeld die **LBS_OWNERDRAWVARIABLE** formatieren, andernfalls auf 0 festgelegt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe in Pixel, der die Elemente im Listenfeld. Weist das Listenfeld die [LBS_OWNERDRAWVARIABLE](../../mfc/reference/list-box-styles.md) Stil, der Rückgabewert ist die Höhe des angegebenen Elements vom `nIndex`. Wenn ein Fehler auftritt, ist der Rückgabewert **LB_ERR**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&17;](../../mfc/codesnippet/cpp/clistbox-class_17.cpp)]  
  
##  <a name="a-namegetitemrecta--clistboxgetitemrect"></a><a name="getitemrect"></a>CListBox::GetItemRect  
 Ruft den Dimensionen des Rechtecks, Grenzen ein Listenfeld-Element ab, wie er derzeit im Fenster im Listenfeld angezeigt wird.  
  
```  
int GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index des Elements an.  
  
 `lpRect`  
 Gibt einen long-Zeiger auf eine [RECT-Struktur](../../mfc/reference/rect-structure1.md) , empfängt die Listenfeld Clientkoordinaten des Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 **LB_ERR** , wenn ein Fehler auftritt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&18;](../../mfc/codesnippet/cpp/clistbox-class_18.cpp)]  
  
##  <a name="a-namegetlistboxinfoa--clistboxgetlistboxinfo"></a><a name="getlistboxinfo"></a>CListBox::GetListBoxInfo  
 Ruft die Anzahl der Elemente pro Spalte ab.  
  
```  
DWORD GetListBoxInfo() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Anzahl von Elementen pro Spalte der `CListBox` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionalität der [LB_GETLISTBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775208) angezeigt, wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetlocalea--clistboxgetlocale"></a><a name="getlocale"></a>CListBox::GetLocale  
 Ruft das im Listenfeld verwendete Gebietsschema ab.  
  
```  
LCID GetLocale() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert des Gebietsschemabezeichners (LCID) für die Zeichenfolgen im Listenfeld.  
  
### <a name="remarks"></a>Hinweise  
 Das Gebietsschema wird z. B. verwendet, um die Sortierreihenfolge der Zeichenfolgen in einem sortierten Listenfeld zu bestimmen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CListBox::SetLocale](#setlocale).  
  
##  <a name="a-namegetsela--clistboxgetsel"></a><a name="getsel"></a>CListBox::GetSel  
 Ruft den Auswahlzustand eines Elements ab.  
  
```  
int GetSel(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index des Elements an.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine positive Zahl, wenn das angegebene Element aktiviert ist; Andernfalls ist er 0. Der Rückgabewert ist `LB_ERR` , wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion funktioniert mit beiden einzelnen und Mehrfachauswahl-Listenfelder.  
  
 Verwenden Sie zum Abrufen des Indexes des derzeit ausgewählten Listenfeldelement [CListBox::GetCurSel](#getcursel).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox Nr.&19;](../../mfc/codesnippet/cpp/clistbox-class_19.cpp)]  
  
##  <a name="a-namegetselcounta--clistboxgetselcount"></a><a name="getselcount"></a>CListBox::GetSelCount  
 Ruft die Gesamtanzahl der ausgewählten Elemente in einem Mehrfachauswahl-Listenfeld an.  
  
```  
int GetSelCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der ausgewählten Elemente in einem Listenfeld. Im Listenfeld eine Mehrfachauswahl-Listenfeld, der Rückgabewert ist **LB_ERR**.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CListBox::GetSelItems](#getselitems).  
  
##  <a name="a-namegetselitemsa--clistboxgetselitems"></a><a name="getselitems"></a>CListBox::GetSelItems  
 Füllt einen Puffer mit einem Array von Ganzzahlen, das die Nummern der ausgewählten Elemente in einem Mehrfachauswahl-Listenfeld angibt.  
  
```  
int GetSelItems(
    int nMaxItems,  
    LPINT rgIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nMaxItems`  
 Gibt die maximale Anzahl der ausgewählten Elemente, deren Artikelnummern im Puffer abgelegt werden sollen.  
  
 `rgIndex`  
 Gibt einen Zeiger auf einen Puffer groß genug für die Anzahl der angegebenen Ganzzahlen `nMaxItems`.  
  
### <a name="return-value"></a>Rückgabewert  
 Die tatsächliche Anzahl der Elemente, die in den Puffer abgelegt werden. Im Listenfeld eine Mehrfachauswahl-Listenfeld, der Rückgabewert ist `LB_ERR`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&20;](../../mfc/codesnippet/cpp/clistbox-class_20.cpp)]  
  
##  <a name="a-namegettexta--clistboxgettext"></a><a name="gettext"></a>CListBox::GetText  
 Ruft eine Zeichenfolge aus einem Listenfeld.  
  
```  
int GetText(
    int nIndex,  
    LPTSTR lpszBuffer) const;  
  
void GetText(
    int nIndex,  
    CString& rString) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index der Zeichenfolge abgerufen werden soll.  
  
 `lpszBuffer`  
 Verweist auf den Puffer, der die Zeichenfolge empfängt. Der Puffer muss über genügend Speicherplatz für die Zeichenfolge und ein abschließendes Null-Zeichen haben. Die Größe der Zeichenfolge vorher ermittelt werden kann, durch Aufrufen der `GetTextLen` Member-Funktion.  
  
 `rString`  
 Ein Verweis auf ein `CString`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge (in Byte) der Zeichenfolge ist, außer das abschließende Nullzeichen. Wenn `nIndex` gibt keine gültigen Index, der Rückgabewert ist **LB_ERR**.  
  
### <a name="remarks"></a>Hinweise  
 Das zweite Formular dieses Members-Funktion füllt eine `CString` Objekt mit dem Zeichenfolgentext.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&21;](../../mfc/codesnippet/cpp/clistbox-class_21.cpp)]  
  
##  <a name="a-namegettextlena--clistboxgettextlen"></a><a name="gettextlen"></a>CListBox::GetTextLen  
 Ruft die Länge einer Zeichenfolge in einem Listenfeld-Element ab.  
  
```  
int GetTextLen(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index der Zeichenfolge an.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge der Zeichenfolge in Zeichen, ohne das abschließende Nullzeichen. Wenn `nIndex` gibt keine gültigen Index, der Rückgabewert ist **LB_ERR**.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CListBox::GetText](#gettext).  
  
##  <a name="a-namegettopindexa--clistboxgettopindex"></a><a name="gettopindex"></a>CListBox::GetTopIndex  
 Ruft den nullbasierten Index des ersten sichtbaren Elements in einem Listenfeld ab.  
  
```  
int GetTopIndex() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des ersten sichtbaren Elements in einem Listenfeld im Erfolgsfall **LB_ERR** andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Zu Beginn Element 0 befindet sich oben im Listenfeld, aber im Listenfeld ein Bildlauf durchgeführt wird, kann ein anderes Element oben befinden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#22;](../../mfc/codesnippet/cpp/clistbox-class_22.cpp)]  
  
##  <a name="a-nameinitstoragea--clistboxinitstorage"></a><a name="initstorage"></a>CListBox::InitStorage  
 Belegt Speicher zum Speichern von Elementen im Listenfeld.  
  
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
 Wenn erfolgreich, die maximale Anzahl von Elementen, die im Listenfeld kann gespeichert, bevor eine Neubelegung Arbeitsspeicher, andernfalls benötigt wird **LB_ERRSPACE**, d. h. nicht genügend Arbeitsspeicher verfügbar ist.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion vor dem Hinzufügen einer großen Menge von Elementen, die eine `CListBox`.  
  
 Diese Funktion können Sie die Initialisierung von Listenfelder beschleunigen, die eine große von Elementen (mehr als 100 Anzahl). Es so, dass bei nachfolgenden angegebene Arbeitsspeichermenge Journaldateien [AddString](#addstring), [InsertString](#insertstring), und [Dir](#dir) Funktionen nehmen kürzesten Zeit. Sie können die Schätzungen für die Parameter verwenden. Wenn Sie überschätzen, wird zusätzlicher Arbeitsspeicher reserviert. Wenn Sie unterschätzen, wird die normale Verteilung für Elemente verwendet, die vorab überschreiten.  
  
 Windows 95/98: der `nItems` Parameter ist auf 16-Bit-Werte beschränkt. Dies bedeutet, dass es sich bei Listenfelder mehr als 32.767 Elemente enthalten können. Obwohl die Anzahl der Elemente eingeschränkt ist, ist die Gesamtgröße der Elemente in einem Listenfeld nur durch den verfügbaren Arbeitsspeicher beschränkt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&23;](../../mfc/codesnippet/cpp/clistbox-class_23.cpp)]  
  
##  <a name="a-nameinsertstringa--clistboxinsertstring"></a><a name="insertstring"></a>CListBox::InsertString  
 Fügt eine Zeichenfolge in das Listenfeld ein.  
  
```  
int InsertString(
    int nIndex,  
    LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index der Position, die Zeichenfolge eingefügt. Wenn dieser Parameter –1 ist, wird die Zeichenfolge am Ende der Liste hinzugefügt.  
  
 `lpszItem`  
 Zeigt auf die einzufügende nullterminierte Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index der Position, an der die Zeichenfolge eingefügt wurde. Der Rückgabewert ist **LB_ERR** Wenn ein Fehler auftritt, ist der Rückgabewert **LB_ERRSPACE** ist nicht genügend Speicherplatz zum Speichern der neuen Zeichenfolge verfügbar.  
  
### <a name="remarks"></a>Hinweise  
 Im Gegensatz zu der [AddString](#addstring) Memberfunktion `InsertString` nicht dazu, dass eine Liste mit den [LBS_SORT](../../mfc/reference/list-box-styles.md) Stil sortiert werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#24;](../../mfc/codesnippet/cpp/clistbox-class_24.cpp)]  
  
##  <a name="a-nameitemfrompointa--clistboxitemfrompoint"></a><a name="itemfrompoint"></a>CListBox::ItemFromPoint  
 Bestimmt das Element im Listenfeld am nächsten an der angegebene Punkt `pt`.  
  
```  
UINT ItemFromPoint(
    CPoint pt,  
    BOOL& bOutside) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Zeigen Sie für die das nächste Element relativ zu der oberen linken Ecke des Clientbereichs des Listenfelds angegeben finden.  
  
 `bOutside`  
 Ein Verweis auf eine `BOOL` Variable, die auf `TRUE` Wenn `pt` liegt außerhalb des Clientbereichs des nächsten Listenfeldelement `FALSE` Wenn `pt` befindet sich in den Clientbereich des nächsten Listenfeldelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des nächsten Elements an der in `pt`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion können Sie im Listenfeld fest auf der Cursor zu bewegen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CListBox::SetAnchorIndex](#setanchorindex).  
  
##  <a name="a-namemeasureitema--clistboxmeasureitem"></a><a name="measureitem"></a>CListBox::MeasureItem  
 Wird vom Framework aufgerufen, wenn ein Listenfeld mit einem Ownerdrawn-Stil erstellt wird.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpMeasureItemStruct`  
 Ein long-Zeiger auf eine [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird dieser Member-Funktion keine Aktion ausgeführt. Überschreiben Sie diese Memberfunktion auf, und füllen Sie die `MEASUREITEMSTRUCT` Struktur der Dimensionen im Listenfeld Windows informiert. Wenn das Listenfeld erstellt wird, mit der [LBS_OWNERDRAWVARIABLE](../../mfc/reference/list-box-styles.md) Stil das Framework ruft diese Member-Funktion für jedes Element im Listenfeld. Andernfalls wird dieser Member nur einmal aufgerufen.  
  
 Weitere Informationen zur Verwendung der [LBS_OWNERDRAWFIXED](../../mfc/reference/list-box-styles.md) Stil in einem Ownerdrawn-Listenfeld erstellt, mit der `SubclassDlgItem` -Memberfunktion des `CWnd`, finden Sie unter [Technische Hinweis 14](../../mfc/tn014-custom-controls.md).  
  
 Finden Sie unter [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) eine Beschreibung der `MEASUREITEMSTRUCT` Struktur **.**  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#25;](../../mfc/codesnippet/cpp/clistbox-class_25.cpp)]  
  
##  <a name="a-nameresetcontenta--clistboxresetcontent"></a><a name="resetcontent"></a>CListBox::ResetContent  
 Entfernt alle Elemente aus einem Listenfeld.  
  
```  
void ResetContent();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#26;](../../mfc/codesnippet/cpp/clistbox-class_26.cpp)]  
  
##  <a name="a-nameselectstringa--clistboxselectstring"></a><a name="selectstring"></a>CListBox::SelectString  
 Suchvorgänge für ein Element im Listenfeld mit die angegebene Zeichenfolge übereinstimmt, und wenn ein übereinstimmendes Element gefunden wird, wird das Element ausgewählt.  
  
```  
int SelectString(
    int nStartAfter,  
    LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>Parameter  
 `nStartAfter`  
 Enthält den nullbasierten Index des Elements vor dem ersten Element gesucht werden soll. Erreicht die Suche am Ende das Listenfeld, weiterhin von der obersten Position des Listenfelds wieder das Element mit dem angegebenen `nStartAfter`. Wenn `nStartAfter` –&1; ist, wird das ganze Listenfeld wird vom Anfang durchsucht.  
  
 `lpszItem`  
 Verweist auf die auf Null endende Zeichenfolge, die das Präfix für die Suche enthält. Die Suche gilt unabhängig, damit diese Zeichenfolge eine beliebige Kombination aus Groß- und Kleinbuchstaben enthalten kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des ausgewählten Elements, wenn die Suche erfolgreich war. Wenn die Suche nicht erfolgreich war, ist der Rückgabewert **LB_ERR** und die aktuelle Auswahl wird nicht geändert.  
  
### <a name="remarks"></a>Hinweise  
 Im Listenfeld wird verschoben, bei Bedarf, um das ausgewählte Element in der Ansicht erscheinen.  
  
 Diese Memberfunktion kann nicht verwendet werden, in einem Listenfeld, die die [LBS_MULTIPLESEL](../../mfc/reference/list-box-styles.md) Stil.  
  
 Ein Element ausgewählt ist, nur dann, wenn die ersten Zeichen (vom Ausgangspunkt) die Zeichen in der angegebenen Zeichenfolge entsprechen `lpszItem`.  
  
 Verwenden der `FindString` Member-Funktion zu einer Zeichenfolge zu suchen, ohne das Element auszuwählen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#27;](../../mfc/codesnippet/cpp/clistbox-class_27.cpp)]  
  
##  <a name="a-nameselitemrangea--clistboxselitemrange"></a><a name="selitemrange"></a>CListBox::SelItemRange  
 Wählt mehrere aufeinander folgende Elemente in einem Mehrfachauswahl-Listenfeld aus.  
  
```  
int SelItemRange(
    BOOL bSelect,  
    int nFirstItem,  
    int nLastItem);
```  
  
### <a name="parameters"></a>Parameter  
 `bSelect`  
 Gibt an, wie die Auswahl. Wenn `bSelect` ist **TRUE**, ausgewählt und hervorgehoben, wenn die Zeichenfolge **FALSE**, wird die Hervorhebung entfernt, und die Zeichenfolge nicht mehr ausgewählt ist.  
  
 `nFirstItem`  
 Gibt den nullbasierten Index des ersten Elements festlegen.  
  
 `nLastItem`  
 Gibt den nullbasierten Index des letzten Elements festlegen.  
  
### <a name="return-value"></a>Rückgabewert  
 **LB_ERR** , wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Memberfunktion nur mit Mehrfachauswahl-Listenfelder. Wenn Sie nur ein Element in einem Mehrfachauswahl-Listenfeld auswählen müssen –, also wenn `nFirstItem` gleich `nLastItem` – rufen Sie die [Memberfunktion SetSel](#setsel) Memberfunktion stattdessen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#28;](../../mfc/codesnippet/cpp/clistbox-class_28.cpp)]  
  
##  <a name="a-namesetanchorindexa--clistboxsetanchorindex"></a><a name="setanchorindex"></a>CListBox::SetAnchorIndex  
 Legt den Anker in einem Mehrfachauswahl-Listenfeld zu einer erweiterten Auswahl fest.  
  
```  
void SetAnchorIndex(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index des Elements im Listenfeld, die den Anker.  
  
### <a name="remarks"></a>Hinweise  
 In einem Mehrfachauswahl-Listenfeld ist das Anchor-Element der ersten bzw. letzten Element in einem Block zusammenhängender ausgewählter Elemente.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#29;](../../mfc/codesnippet/cpp/clistbox-class_29.cpp)]  
  
##  <a name="a-namesetcaretindexa--clistboxsetcaretindex"></a><a name="setcaretindex"></a>CListBox::SetCaretIndex  
 Legt das Fokusrechteck für das Element am angegebenen Index in einem Mehrfachauswahl-Listenfeld.  
  
```  
int SetCaretIndex(
    int nIndex,  
    BOOL bScroll = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index des Elements, das das Fokusrechteck im Listenfeld angezeigt.  
  
 *bScroll*  
 Wenn dieser Wert 0 ist, wird das Element verschoben, bis es vollständig sichtbar ist. Wenn dieser Wert nicht 0 ist, das Element wird ein Bildlauf durchgeführt, bis es zumindest teilweise sichtbar ist.  
  
### <a name="return-value"></a>Rückgabewert  
 **LB_ERR** , wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Element nicht sichtbar ist, ist es in die Ansicht rücken.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#30;](../../mfc/codesnippet/cpp/clistbox-class_30.cpp)]  
  
##  <a name="a-namesetcolumnwidtha--clistboxsetcolumnwidth"></a><a name="setcolumnwidth"></a>CListBox::SetColumnWidth  
 Legt die Breite in Pixel aller Spalten in einem mehrspaltigen Listenfeld (erstellt mit dem [LBS_MULTICOLUMN](../../mfc/reference/list-box-styles.md) Stil).  
  
```  
void SetColumnWidth(int cxWidth);
```  
  
### <a name="parameters"></a>Parameter  
 `cxWidth`  
 Gibt die Breite in Pixel aller Spalten an.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#31;](../../mfc/codesnippet/cpp/clistbox-class_31.cpp)]  
  
##  <a name="a-namesetcursela--clistboxsetcursel"></a><a name="setcursel"></a>CListBox::SetCurSel  
 Wählt eine Zeichenfolge und Bildlauf es sichtbar, falls erforderlich.  
  
```  
int SetCurSel(int nSelect);
```  
  
### <a name="parameters"></a>Parameter  
 `nSelect`  
 Gibt den nullbasierten Index der Zeichenfolge, die ausgewählt werden. Wenn `nSelect` –&1; ist, ist keine Auswahl im Listenfeld festgelegt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 `LB_ERR`Wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die neue Zeichenfolge ausgewählt ist, entfernt das Listenfeld die Hervorhebung aus der zuvor ausgewählten Zeichenfolge.  
  
 Verwenden Sie diese Memberfunktion nur mit Mehrfachauswahl-Listenfelder.  
  
 Verwenden Sie zum Festlegen oder entfernen eine Auswahl in einem Mehrfachauswahl-Listenfeld, [CListBox::SetSel](#setsel).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#32;](../../mfc/codesnippet/cpp/clistbox-class_32.cpp)]  
  
##  <a name="a-namesethorizontalextenta--clistboxsethorizontalextent"></a><a name="sethorizontalextent"></a>CListBox:: SetHorizontalExtent  
 Legt die Breite in Pixel, ein Listenfeld, das ein horizontaler Bildlauf durchgeführt werden kann.  
  
```  
void SetHorizontalExtent(int cxExtent);
```  
  
### <a name="parameters"></a>Parameter  
 *cxExtent*  
 Gibt die Anzahl der Pixel, die mit denen im Listenfeld ein horizontaler Bildlauf durchgeführt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Größe des Listenfeldes kleiner als dieser Wert ist, wird die horizontale Bildlaufleiste Elemente im Listenfeld horizontale Bildlaufleiste. Wenn das Listenfeld genauso groß oder größer als dieser Wert ist, wird die horizontale Bildlaufleiste ausgeblendet.  
  
 So reagieren Sie auf einen Aufruf von `SetHorizontalExtent`, im Listenfeld muss mit definiert wurden die [WS_HSCROLL](../../mfc/reference/window-styles.md) Stil.  
  
 Diese Memberfunktion ist nicht für mehrspaltige Listenfelder nützlich. Für mehrspaltige Listenfelder, rufen Sie die `SetColumnWidth` -Memberfunktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&33;](../../mfc/codesnippet/cpp/clistbox-class_33.cpp)]  
  
##  <a name="a-namesetitemdataa--clistboxsetitemdata"></a><a name="setitemdata"></a>CListBox::SetItemData  
 Legt einen 32-Bit-Wert, der das angegebene Element in einem Listenfeld zugeordnet.  
  
```  
int SetItemData(
    int nIndex,  
    DWORD_PTR dwItemData);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index des Elements an.  
  
 `dwItemData`  
 Gibt den Wert des Elements zugeordnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 **LB_ERR** , wenn ein Fehler auftritt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#34;](../../mfc/codesnippet/cpp/clistbox-class_34.cpp)]  
  
##  <a name="a-namesetitemdataptra--clistboxsetitemdataptr"></a><a name="setitemdataptr"></a>CListBox::SetItemDataPtr  
 Legt den 32-Bit-Wert, der das angegebene Element in einem Listenfeld werden die angegebenen Zeiger zugeordnet ( **void\***).  
  
```  
int SetItemDataPtr(
    int nIndex,  
    void* pData);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index des Elements an.  
  
 `pData`  
 Gibt den Zeiger, um mit dem Element verknüpft werden.  
  
### <a name="return-value"></a>Rückgabewert  
 **LB_ERR** , wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 This-Zeiger bleibt gültig, für die Lebensdauer des im Listenfeld, obwohl der Position des Elements relative innerhalb des Listenfelds ändern kann, wenn Elemente hinzugefügt oder entfernt werden. Daher kann der Index des Elements in das Feld ändern, aber der Zeiger bleibt zuverlässige.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#35;](../../mfc/codesnippet/cpp/clistbox-class_35.cpp)]  
  
##  <a name="a-namesetitemheighta--clistboxsetitemheight"></a><a name="setitemheight"></a>CListBox::SetItemHeight  
 Legt die Höhe der Elemente in einem Listenfeld.  
  
```  
int SetItemHeight(
    int nIndex,  
    UINT cyItemHeight);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index des Elements im Listenfeld an. Dieser Parameter wird verwendet, nur dann, wenn das Listenfeld die **LBS_OWNERDRAWVARIABLE** formatieren, andernfalls auf 0 festgelegt werden soll.  
  
 `cyItemHeight`  
 Gibt die Höhe des Elements in Pixel an.  
  
### <a name="return-value"></a>Rückgabewert  
 **LB_ERR** , wenn der Index oder die Höhe ungültig ist.  
  
### <a name="remarks"></a>Hinweise  
 Weist das Listenfeld die [LBS_OWNERDRAWVARIABLE](../../mfc/reference/list-box-styles.md) Stil, diese Funktion legt die Höhe des angegebenen Elements vom `nIndex`. Andernfalls wird diese Funktion die Höhe aller Elemente im Listenfeld.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox Nr.&36;](../../mfc/codesnippet/cpp/clistbox-class_36.cpp)]  
  
##  <a name="a-namesetlocalea--clistboxsetlocale"></a><a name="setlocale"></a>CListBox::SetLocale  
 Legt den Gebietsschemabezeichner für das Listenfeld fest.  
  
```  
LCID SetLocale(LCID nNewLocale);
```  
  
### <a name="parameters"></a>Parameter  
 `nNewLocale`  
 Das neue Gebietsschema-ID (LCID) für das Listenfeld festzulegende Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Der vorherige Gebietsschema-ID (LCID) Wert für das Listenfeld.  
  
### <a name="remarks"></a>Hinweise  
 Wenn **SetLocale** nicht aufgerufen wird, das standardmäßige Gebietsschema vom System abgerufen wird. Dieser Standardgebietsschema kann geändert werden, mithilfe der Systemsteuerung Regions-(International-Anwendung).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#37;](../../mfc/codesnippet/cpp/clistbox-class_37.cpp)]  
  
##  <a name="a-namesetsela--clistboxsetsel"></a><a name="setsel"></a>CListBox::SetSel  
 Wählt eine Zeichenfolge in einem Mehrfachauswahl-Listenfeld aus.  
  
```  
int SetSel(
    int nIndex,  
    BOOL bSelect = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Enthält den nullbasierten Index der Zeichenfolge festgelegt werden. Wenn –&1; ist, die Auswahl hinzugefügt oder entfernt wird aus allen Zeichenfolgen, abhängig vom Wert der `bSelect`.  
  
 `bSelect`  
 Gibt an, wie die Auswahl. Wenn `bSelect` ist `TRUE`, ausgewählt und hervorgehoben, wenn die Zeichenfolge `FALSE`, die Hervorhebung wird entfernt, und die Zeichenfolge nicht mehr ausgewählt ist. Die angegebene Zeichenfolge ist aktiviert und standardmäßig markiert.  
  
### <a name="return-value"></a>Rückgabewert  
 `LB_ERR`Wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Memberfunktion nur mit Mehrfachauswahl-Listenfelder.  
  
 Verwenden Sie zum Auswählen eines Elements aus einem Mehrfachauswahl-Listenfeld [CListBox::SetCurSel](#setcursel).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#38;](../../mfc/codesnippet/cpp/clistbox-class_38.cpp)]  
  
##  <a name="a-namesettabstopsa--clistboxsettabstops"></a><a name="settabstops"></a>CListBox::SetTabStops  
 Legt die Tabstopp Positionen in einem Listenfeld.  
  
```  
void SetTabStops();  
BOOL SetTabStops(const int& cxEachStop);

 
BOOL SetTabStops(
    int nTabStops,  
    LPINT rgTabStops);
```  
  
### <a name="parameters"></a>Parameter  
 `cxEachStop`  
 Tabstopps festgelegt werden alle `cxEachStop` Dialogeinheiten. Finden Sie unter *RgTabStops* eine Beschreibung der eine Dialogeinheit.  
  
 `nTabStops`  
 Gibt die Anzahl der Tabstopps, die in der Liste enthalten sein.  
  
 `rgTabStops`  
 Verweist auf das erste Element eines Arrays von ganzen Zahlen mit der Tabstopp Positionen in Dialogeinheiten. Eine Dialogeinheit ist eine horizontale oder vertikale Abstand. Eine horizontale Dialogeinheit ein Viertel der aktuellen Dialogfeld Basis Breite Einheit entspricht, und eine vertikale Dialogeinheit ein Achtel der aktuellen Dialogfeld Basis Höhe Einheit entspricht. Die Basis Dialogeinheiten werden basierend auf der Höhe und Breite des aktuellen Systemschriftart berechnet. Die **GetDialogBaseUnits** Windows-Funktion gibt das aktuelle Dialogfeld Basiseinheit in Pixel. Die Tabstopps müssen in aufsteigender Reihenfolge sortiert werden; negative Tabstopps sind nicht zulässig.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn alle Registerkarten festgelegt wurden; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie zum Festlegen von Tabstopps auf die Standardgröße von 2 Dialogeinheiten der parameterlosen Version von dieser Memberfunktion. Um eine andere Größe als 2 Tabstopps festzulegen, rufen Sie die Version mit der `cxEachStop` Argument.  
  
 Um ein Array von Größen Tabstopps festzulegen, verwenden Sie die Version mit der `rgTabStops` und `nTabStops` Argumente. Für jeden Wert in ein Tabstopp festgelegt `rgTabStops`, bis die angegebene Anzahl `nTabStops`.  
  
 So reagieren Sie auf einen Aufruf der `SetTabStops` Member-Funktion, die im Listenfeld muss mit erstellt wurden die [LBS_USETABSTOPS](../../mfc/reference/list-box-styles.md) Stil.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox Nr.&39;](../../mfc/codesnippet/cpp/clistbox-class_39.cpp)]  
  
##  <a name="a-namesettopindexa--clistboxsettopindex"></a><a name="settopindex"></a>CListBox::SetTopIndex  
 Stellt sicher, dass ein bestimmtes Listenfeld Element sichtbar ist.  
  
```  
int SetTopIndex(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index des Elements im Listenfeld an.  
  
### <a name="return-value"></a>Rückgabewert  
 NULL Wenn erfolgreich, oder **LB_ERR** Wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Das System führt einen Bildlauf im Listenfeld bis entweder das Element vom angegebenen `nIndex` wird am Anfang der Liste im Feld oder die maximale Bildlaufbereich erreicht wurde.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#40;](../../mfc/codesnippet/cpp/clistbox-class_40.cpp)]  
  
##  <a name="a-namevkeytoitema--clistboxvkeytoitem"></a><a name="vkeytoitem"></a>CListBox::VKeyToItem  
 Vom Framework aufgerufen, wenn das Listenfeld übergeordneten Fenster empfängt eine `WM_VKEYTOITEM` Nachricht aus dem Listenfeld aus.  
  
```  
virtual int VKeyToItem(
    UINT nKey,  
    UINT nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nKey`  
 Virtueller Tastencode der Taste gedrückt, der Benutzer. Eine Liste der standardmäßigen virtuellen Tastencodes finden Sie in Winuser.h  
  
 `nIndex`  
 Die aktuelle Position der Einfügemarke im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt – 2 für keine weitere Aktion, – 1 für die Standardaktion oder eine negative Zahl an einen Index der Listenfeldelements aus, um die Standardaktion für die Tastatureingabe auszuführen.  
  
### <a name="remarks"></a>Hinweise  
 Die `WM_VKEYTOITEM` Nachricht im Listenfeld beim Empfang einer `WM_KEYDOWN` Nachricht, aber, nur wenn das Listenfeld beide der folgenden erfüllt:  
  
-   Hat die [LBS_WANTKEYBOARDINPUT](../../mfc/reference/list-box-styles.md) Set formatieren.  
  
-   Hat mindestens ein Element.  
  
 Sie sollten diese Funktion nie selbst aufrufen. Überschreiben Sie diese Funktion, um eigene benutzerdefinierte Behandlung von Tastatureingaben bereitzustellen.  
  
 Sie müssen einen Wert für dem Framework angeben, welche Aktion die Überschreibung ausgeführt zurückkehren. Ein Rückgabewert von – gibt 2 an, dass die Anwendung alle Aspekte behandelt der Sie das Element auswählen und keine weitere Aktion im Listenfeld erfordert. Vor dem Zurückgeben von – 2, könnten Sie die Option oder und/oder die Einfügemarke zu verschieben. Verwenden Sie zum Festlegen der Auswahl [SetCurSel](#setcursel) oder [Memberfunktion SetSel](#setsel). Verwenden Sie zum Verschieben der Einfügemarke [SetCaretIndex](#setcaretindex).  
  
 Ein Rückgabewert von – 1 zeigt, dass im Listenfeld die Standardaktion als Antwort auf die Tastatureingabe ausführen soll. Die standardmäßige Implementierung gibt – 1.  
  
 Ein Rückgabewert von 0 oder größer gibt den Index eines Elements im Listenfeld an und gibt an, dass im Listenfeld die Standardaktion für die Tastatureingabe auf das angegebene Element ausführen soll.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox&#41;](../../mfc/codesnippet/cpp/clistbox-class_41.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CTRLTEST](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [CButton-Klasse](../../mfc/reference/cbutton-class.md)   
 [CComboBox-Klasse](../../mfc/reference/ccombobox-class.md)   
 [CEdit-Klasse](../../mfc/reference/cedit-class.md)   
 [CScrollBar-Klasse](../../mfc/reference/cscrollbar-class.md)   
 [CStatic-Klasse](../../mfc/reference/cstatic-class.md)

