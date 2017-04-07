---
title: CListBox-Klasse | Microsoft Docs
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
- AFXWIN/CListBox
- AFXWIN/CListBox::CListBox
- AFXWIN/CListBox::AddString
- AFXWIN/CListBox::CharToItem
- AFXWIN/CListBox::CompareItem
- AFXWIN/CListBox::Create
- AFXWIN/CListBox::DeleteItem
- AFXWIN/CListBox::DeleteString
- AFXWIN/CListBox::Dir
- AFXWIN/CListBox::DrawItem
- AFXWIN/CListBox::FindString
- AFXWIN/CListBox::FindStringExact
- AFXWIN/CListBox::GetAnchorIndex
- AFXWIN/CListBox::GetCaretIndex
- AFXWIN/CListBox::GetCount
- AFXWIN/CListBox::GetCurSel
- AFXWIN/CListBox::GetHorizontalExtent
- AFXWIN/CListBox::GetItemData
- AFXWIN/CListBox::GetItemDataPtr
- AFXWIN/CListBox::GetItemHeight
- AFXWIN/CListBox::GetItemRect
- AFXWIN/CListBox::GetListBoxInfo
- AFXWIN/CListBox::GetLocale
- AFXWIN/CListBox::GetSel
- AFXWIN/CListBox::GetSelCount
- AFXWIN/CListBox::GetSelItems
- AFXWIN/CListBox::GetText
- AFXWIN/CListBox::GetTextLen
- AFXWIN/CListBox::GetTopIndex
- AFXWIN/CListBox::InitStorage
- AFXWIN/CListBox::InsertString
- AFXWIN/CListBox::ItemFromPoint
- AFXWIN/CListBox::MeasureItem
- AFXWIN/CListBox::ResetContent
- AFXWIN/CListBox::SelectString
- AFXWIN/CListBox::SelItemRange
- AFXWIN/CListBox::SetAnchorIndex
- AFXWIN/CListBox::SetCaretIndex
- AFXWIN/CListBox::SetColumnWidth
- AFXWIN/CListBox::SetCurSel
- AFXWIN/CListBox::SetHorizontalExtent
- AFXWIN/CListBox::SetItemData
- AFXWIN/CListBox::SetItemDataPtr
- AFXWIN/CListBox::SetItemHeight
- AFXWIN/CListBox::SetLocale
- AFXWIN/CListBox::SetSel
- AFXWIN/CListBox::SetTabStops
- AFXWIN/CListBox::SetTopIndex
- AFXWIN/CListBox::VKeyToItem
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 4b1b1963af7740820b1285c3df8724f9ea4332b1
ms.lasthandoff: 04/01/2017

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
|[CListBox::AddString](#addstring)|Fügt eine Zeichenfolge an ein Listenfeld an.|  
|[CListBox::CharToItem](#chartoitem)|Überschreiben, um den benutzerdefinierten `WM_CHAR` Klassenbehandlung für Ownerdrawn-Listenfelder Zeichenfolgen aufweisen.|  
|[CListBox::CompareItem](#compareitem)|Vom Framework aufgerufen, der die Position eines neuen Elements in einem sortierten Besitzer gezeichnetes Listenfeld zu ermitteln.|  
|[CListBox::Create](#create)|Erstellt die Windows-Listenfelds und fügt es der `CListBox` Objekt.|  
|[CListBox::DeleteItem](#deleteitem)|Vom Framework aufgerufen, wenn der Benutzer ein Element aus einem Besitzer gezeichnetes Listenfeld gelöscht wird.|  
|[CListBox::DeleteString](#deletestring)|Löscht eine Zeichenfolge aus einem Listenfeld.|  
|[CListBox::Dir](#dir)|Fügt Dateinamen und/oder Laufwerke des aktuellen Verzeichnisses an ein Listenfeld an.|  
|[CListBox::DrawItem](#drawitem)|Wird aufgerufen, durch das Framework, wenn sich ein Darstellungsaspekt eines Ownerdrawn-Liste im Feld ändert.|  
|[CListBox:: FindString](#findstring)|Sucht nach einer Zeichenfolge in einem Listenfeld.|  
|[CListBox::FindStringExact](#findstringexact)|Sucht nach der ersten Listenfeld-Zeichenfolge, die einer angegebenen Zeichenfolge übereinstimmt.|  
|[CListBox::GetAnchorIndex](#getanchorindex)|Ruft den nullbasierten Index des aktuellen Elements in einem Listenfeld Anker ab.|  
|[CListBox::GetCaretIndex](#getcaretindex)|Bestimmt den Index des Elements, das in einem Listenfeld Mehrfachauswahl Fokusrechtecks verfügt.|  
|[CListBox::GetCount](#getcount)|Gibt die Anzahl der Zeichenfolgen in einem Listenfeld zurück.|  
|[CListBox::GetCurSel](#getcursel)|Gibt den nullbasierten Index des derzeit ausgewählten Zeichenfolge in einem Listenfeld zurück.|  
|[CListBox::GetHorizontalExtent](#gethorizontalextent)|Gibt die Breite in Pixel, ein Listenfeld horizontal gescrollt werden kann.|  
|[CListBox::GetItemData](#getitemdata)|Der 32-Bit-Wert, der dem Element im Listenfeld zugeordnete zurückgegeben.|  
|[CListBox::GetItemDataPtr](#getitemdataptr)|Gibt einen Zeiger auf ein Element im Listenfeld.|  
|[CListBox::GetItemHeight](#getitemheight)|Bestimmt die Höhe der Elemente in einem Listenfeld.|  
|[CListBox::GetItemRect](#getitemrect)|Gibt das umschließende Rechteck des Elements im Listenfeld an, wie er derzeit angezeigt wird.|  
|[CListBox::GetListBoxInfo](#getlistboxinfo)|Ruft die Anzahl von Elementen pro Spalte ab.|  
|[CListBox::GetLocale](#getlocale)|Ruft den Gebietsschemabezeichner für ein Listenfeld ab.|  
|[CListBox::GetSel](#getsel)|Gibt den Auswahlzustand eines Elements im Listenfeld zurück.|  
|[CListBox::GetSelCount](#getselcount)|Gibt die Anzahl von Zeichenfolgen, die derzeit in einem Mehrfachauswahl-Listenfeld ausgewählt.|  
|[CListBox::GetSelItems](#getselitems)|Gibt die Indizes der in einem Listenfeld ausgewählte Zeichenfolgen zurück.|  
|[CListBox::GetText](#gettext)|Kopiert ein Element im Listenfeld in einen Puffer.|  
|[CListBox::GetTextLen](#gettextlen)|Gibt die Länge in Bytes eines Elements im Listenfeld zurück.|  
|[CListBox::GetTopIndex](#gettopindex)|Gibt den Index der ersten sichtbaren Zeichenfolge in einem Listenfeld zurück.|  
|[CListBox::InitStorage](#initstorage)|Reserviert Speicherblöcke Listenfeldelemente und Zeichenfolgen.|  
|[CListBox::InsertString](#insertstring)|Fügt eine Zeichenfolge an einer bestimmten Position in einem Listenfeld an.|  
|[CListBox::ItemFromPoint](#itemfrompoint)|Gibt den Index des Elements im Listenfeld am nächsten einen Punkt zurück.|  
|[CListBox::MeasureItem](#measureitem)|Vom Framework aufgerufen, wenn ein Besitzer gezeichnetes Listenfeld erstellt wird, um im Listenfeld Dimensionen zu bestimmen.|  
|[CListBox::ResetContent](#resetcontent)|Löscht alle Einträge aus einem Listenfeld.|  
|[CListBox::SelectString](#selectstring)|Sucht und wählt eine Zeichenfolge in einem Einzelauswahl-Listenfeld aus.|  
|[CListBox::SelItemRange](#selitemrange)|Aktiviert bzw. deaktiviert einen Bereich von Zeichenfolgen in einem Mehrfachauswahl-Listenfeld.|  
|[CListBox::SetAnchorIndex](#setanchorindex)|Legt fest, die Verankerung in einem Mehrfachauswahl-Listenfeld, um eine erweiterte Auswahl zu beginnen.|  
|[CListBox::SetCaretIndex](#setcaretindex)|Legt Fokusrechtecks auf das Element am angegebenen Index in einem Listenfeld Mehrfachauswahl fest.|  
|[CListBox::SetColumnWidth](#setcolumnwidth)|Legt die Spaltenbreite eines mehrspaltigen Listenfelds an.|  
|[CListBox::SetCurSel](#setcursel)|Wählt eine Zeichenfolge im Listenfeld aus.|  
|[CListBox:: SetHorizontalExtent](#sethorizontalextent)|Legt die Breite in Pixel, ein Listenfeld horizontal gescrollt werden kann.|  
|[CListBox::SetItemData](#setitemdata)|Legt den 32-Bit-Wert, der dem Element im Listenfeld zugeordnete.|  
|[CListBox::SetItemDataPtr](#setitemdataptr)|Legt einen Zeiger auf das Element im Listenfeld fest.|  
|[CListBox::SetItemHeight](#setitemheight)|Legt die Höhe der Elemente in einem Listenfeld fest.|  
|[CListBox::SetLocale](#setlocale)|Legt den Gebietsschemabezeichner für ein Listenfeld an.|  
|[CListBox::SetSel](#setsel)|Aktiviert bzw. deaktiviert das hebt die Auswahl eines Elements im Listenfeld in einem Mehrfachauswahl-Listenfeld.|  
|[CListBox::SetTabStops](#settabstops)|Legt die Tabstopp Positionen in einem Listenfeld an.|  
|[CListBox::SetTopIndex](#settopindex)|Legt den nullbasierten Index des ersten sichtbaren Zeichenfolge in einem Listenfeld fest.|  
|[CListBox::VKeyToItem](#vkeytoitem)|Überschreiben, um den benutzerdefinierten `WM_KEYDOWN` Klassenbehandlung für Listenfelder mit der **LBS_WANTKEYBOARDINPUT** Satz formatieren.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Listenfeld zeigt eine Liste von Elementen, z. B. Dateinamen, die der Benutzer anzeigen und auswählen kann.  
  
 In einem Listenfeld mit Einfachauswahl kann der Benutzer nur ein Element auswählen. In einem Listenfeld mit Mehrfachauswahl kann ein Bereich von Elementen ausgewählt werden. Wenn der Benutzer ein Element auswählt, wird hervorgehoben, und das Listenfeld sendet eine Meldung an das übergeordnete Fenster.  
  
 Sie können ein Listenfeld, das aus einer Dialogfeldvorlage oder direkt im Code erstellen. Um direkt zu erstellen, erstellen die `CListBox` -Objekt, und rufen Sie dann die [erstellen](#create) Memberfunktion versucht, erstellen das Listenfeld-Steuerelement von Windows, und fügen Sie es auf die `CListBox` Objekt. Um ein Listenfeld, in einer Dialogfeldvorlage zu verwenden, deklarieren Sie eine Variable im Listenfeld in Ihre Dialogfeldklasse, verwenden Sie `DDX_Control` in Ihre Dialogfeldklasse `DoDataExchange` Funktion, um die Membervariable auf das Steuerelement eine Verbindung herstellen. (Dies ist für Sie automatisch konfiguriert, wenn Sie Ihre Dialogfeldklasse Steuerungsvariable hinzufügen.)  
  
 Konstruktion kann ein langwieriger Vorgang in einer abgeleiteten Klasse `CListBox`. Schreiben Sie einen Konstruktor für die abgeleitete Klasse, und rufen **erstellen** von innerhalb des Konstruktors.  
  
 Wenn Sie ein Listenfeld an seinem übergeordneten Element per Windows-benachrichtigungsmeldungen behandeln möchten (normalerweise eine abgeleitete Klasse [CDialog](../../mfc/reference/cdialog-class.md)), die übergeordnete Klasse für jede Nachricht eine meldungszuordnung Eintrag und Nachrichtenhandler Memberfunktion hinzufügen.  
  
 Jede Meldungszuordnungseintrags weist folgende Form auf:  
  
 `ON_Notification( id, memberFxn )`  
  
 wobei `id` gibt die untergeordneten Fenster-ID des Listenfeld-Steuerelements, das Senden der Benachrichtigung und `memberFxn` ist der Name der übergeordneten-Memberfunktion, die Sie geschrieben haben, um die Benachrichtigung zu verarbeiten.  
  
 Das übergeordnete Funktionsprototyp lautet wie folgt:  
  
 `afx_msg void memberFxn( );`  
  
 Es folgt eine Liste der möglichen Meldungszuordnungseinträge und eine Beschreibung der Fälle, in denen sie zum übergeordneten Element gesendet werden:  
  
- **ON_LBN_DBLCLK** der Benutzer auf eine Zeichenfolge in einem Listenfeld doppelklickt. Nur ein Listenfeld, das verfügt die [LBS_NOTIFY](../../mfc/reference/list-box-styles.md) Stil sendet diese Benachrichtigung.  
  
- **ON_LBN_ERRSPACE** im Listenfeld nicht genügend Speicherplatz zum Erfüllen der Anforderungs zuweisen.  
  
- **ON_LBN_KILLFOCUS** im Listenfeld den Eingabefokus verliert.  
  
- **ON_LBN_SELCANCEL** die aktuelle Auswahl der im Listenfeld wird abgebrochen. Diese Meldung wird nur gesendet, wenn ein Listenfeld der **LBS_NOTIFY** Stil.  
  
- **ON_LBN_SELCHANGE** die Auswahl im Listenfeld wurde geändert. Diese Benachrichtigung wird nicht gesendet werden, wenn die Auswahl, durch geändert wird die [CListBox::SetCurSel](#setcursel) Memberfunktion. Diese Benachrichtigung gilt nur für ein Listenfeld, das verfügt die **LBS_NOTIFY** Stil. Die **LBN_SELCHANGE** Nachricht wird gesendet, für eine Mehrfachauswahl-Listenfeld, wenn der Benutzer eine Taste drückt, selbst wenn die Auswahl nicht ändert.  
  
- **ON_LBN_SETFOCUS** im Listenfeld den Eingabefokus empfängt.  
  
- **ON_WM_CHARTOITEM** empfängt ein Besitzer gezeichnetes Listenfeld, die keine Zeichenfolgen ist ein `WM_CHAR` Nachricht.  
  
- **ON_WM_VKEYTOITEM** ein Listenfeld mit den **LBS_WANTKEYBOARDINPUT** Stil empfängt eine `WM_KEYDOWN` Nachricht.  
  
 Bei Erstellung einer `CListBox` Objekt in einem Dialogfeld (über eine Dialogfeldressource), die `CListBox` Objekt wird automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Bei Erstellung einer `CListBox` Objekt innerhalb eines Fensters müssen Sie möglicherweise Zerstören der `CListBox` Objekt. Bei Erstellung der `CListBox` Objekt im Stapel befindet, automatisch zerstört wird. Bei Erstellung der `CListBox` Objekt auf dem Heap mit dem **neue** -Funktion, die Sie aufrufen müssen **löschen** auf das Objekt, das sie zerstört werden, wenn der Benutzer das übergeordnete Fenster geschlossen wird.  
  
 Wenn Sie alle in Speicher der `CListBox` Objekt außer Kraft, indem die `CListBox` Destruktor, der die Zuordnung zu verwerfen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CListBox`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="addstring"></a>CListBox::AddString  
 Fügt eine Zeichenfolge an ein Listenfeld an.  
  
```  
int AddString(LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszItem`  
 Verweist auf die Null-terminierte Zeichenfolge, die hinzugefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index in der Zeichenfolge im Listenfeld. Der Rückgabewert ist **LB_ERR** Wenn ein Fehler auftritt; der Rückgabewert ist **LB_ERRSPACE** ist nicht genügend Speicherplatz zum Speichern der neuen Zeichenfolge zur Verfügung.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Listenfeld nicht erstellt wurde, mit der [LBS_SORT](../../mfc/reference/list-box-styles.md) Stil, wird die Zeichenfolge am Ende der Liste hinzugefügt. Andernfalls die Zeichenfolge wird in der Liste eingefügt, und die Liste sortiert wird. Wenn das Listenfeld mit erstellt wurde der **LBS_SORT** formatieren, aber nicht die [LBS_HASSTRINGS](../../mfc/reference/list-box-styles.md) Format, das Framework sortiert die Liste durch einen oder mehrere Aufrufe der `CompareItem` Memberfunktion.  
  
 Verwendung [InsertString](#insertstring) um eine Zeichenfolge in einer bestimmten Position in das Listenfeld einzufügen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox Nr. 3](../../mfc/codesnippet/cpp/clistbox-class_1.cpp)]  
  
##  <a name="chartoitem"></a>CListBox::CharToItem  
 Vom Framework aufgerufen, wenn das Listenfeld übergeordneten Fenster empfängt eine `WM_CHARTOITEM` Nachricht aus dem Listenfeld aus.  
  
```  
virtual int CharToItem(
    UINT nKey,  
    UINT nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nKey`  
 Der ANSI-Code, der das Zeichen, die der Benutzer eingegeben werden soll.  
  
 `nIndex`  
 Die aktuelle Position der Einfügemarke im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt - 1 "oder"-2 für die keine weitere Aktion oder eine nicht negative Zahl an, dass ein Index eines Elements im Listenfeld für die die Standardaktion für die Tastatureingabe ausgeführt. Die Standardimplementierung gibt - 1.  
  
### <a name="remarks"></a>Hinweise  
 Die `WM_CHARTOITEM` Nachricht vom Listenfeld beim Empfang einer `WM_CHAR` Nachricht aber nur wenn das Listenfeld alle diese Kriterien erfüllt:  
  
-   Ist ein Besitzer gezeichnetes Listenfeld an.  
  
-   Verfügt nicht über die [LBS_HASSTRINGS](../../mfc/reference/list-box-styles.md) Satz formatieren.  
  
-   Verfügt über mindestens ein Element aus.  
  
 Sie sollten diese Funktion niemals selbst aufrufen. Überschreiben Sie diese Funktion um eine eigene benutzerdefinierte Behandlung tastaturmeldungen bereitzustellen.  
  
 In der Außerkraftsetzung müssen Sie einen Wert für dem Framework angeben, welche Aktion Sie ausführen, zurückgeben. Ein Rückgabewert von - 1 "oder"-2, gibt Sie an, dass alle Aspekte der Auswahl des Elements behandelt und erfordert keine weitere Aktion vom Listenfeld. Vor der Rückgabe - 1 "oder"-2, Sie konnte legen Sie die Auswahl oder Verschieben der Einfügemarke oder beides. Verwenden Sie zum Festlegen der Auswahl [SetCurSel](#setcursel) oder [Memberfunktion SetSel](#setsel). Verwenden Sie zum Verschieben der Einfügemarke [SetCaretIndex](#setcaretindex).  
  
 Ein Rückgabewert von 0 oder größer gibt den Index eines Elements im Listenfeld an und gibt an, dass im Listenfeld die Standardaktion für die Tastatureingabe auf das angegebene Element durchführen soll.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #4](../../mfc/codesnippet/cpp/clistbox-class_2.cpp)]  
  
##  <a name="clistbox"></a>CListBox::CListBox  
 Erstellt ein `CListBox`-Objekt.  
  
```  
CListBox();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CListBox` Objekt in zwei Schritten. Rufen Sie zunächst den Konstruktor **ClistBox** und rufen dann **erstellen**, die die Windows-Listenfelds initialisiert und fügt es der `CListBox`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox Nr. 1](../../mfc/codesnippet/cpp/clistbox-class_3.cpp)]  
  
##  <a name="compareitem"></a>CListBox::CompareItem  
 Wird aufgerufen, durch das Framework, um die relative Position eines neuen Elements in einem sortierten Besitzer gezeichnetes Listenfeld zu ermitteln.  
  
```  
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpCompareItemStruct`  
 Eine long-Zeiger auf eine `COMPAREITEMSTRUCT` Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die relative Position der beiden Elemente beschrieben, die der [COMPAREITEMSTRUCT](../../mfc/reference/compareitemstruct-structure.md) Struktur. Es kann eine der folgenden Werte sein:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|-1|Element 1 wird vor Element 2 sortiert.|  
|0|Artikel 1 und Artikel 2 sortieren identisch.|  
|1|Element 1 sortiert nach dem Element 2.|  
  
 Finden Sie unter [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) eine Beschreibung der `COMPAREITEMSTRUCT` Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird diese Memberfunktion keine Aktion ausgeführt. Bei der Erstellung einer Besitzer gezeichnetes Listenfeld mit den **LBS_SORT** Stil, müssen Sie diese Memberfunktion, um das Framework Unterstützung bei der Sortierung neue Elemente hinzugefügt werden, in das Listenfeld überschreiben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox Nr. 5](../../mfc/codesnippet/cpp/clistbox-class_4.cpp)]  
  
##  <a name="create"></a>CListBox::Create  
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
 Gibt den Stil des Listenfelds an. Wenden Sie eine beliebige Kombination von [listenfeldstile](../../mfc/reference/list-box-styles.md) in das Feld.  
  
 `rect`  
 Gibt an, die im Listenfeld Größe und Position. Kann es sich um eine `CRect` Objekt oder eine `RECT` Struktur.  
  
 `pParentWnd`  
 Gibt an, das Listenfeld übergeordnete Fenster (normalerweise eine `CDialog` Objekt). Es muss nicht **NULL**.  
  
 `nID`  
 Gibt an, das Listenfeld-Steuerelement-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CListBox` Objekt in zwei Schritten. Zunächst den Konstruktor aufrufen und dann **erstellen**, die die Windows-Listenfelds initialisiert und fügt es der `CListBox` Objekt.  
  
 Wenn **erstellen** ausgeführt wird, sendet Windows die [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), und [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Nachrichten an das Listenfeld-Steuerelement.  
  
 Diese Nachrichten werden standardmäßig verarbeitet der [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), und [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Memberfunktionen in der `CWnd` Basisklasse. Um die Standard-Meldungsbehandlung zu erweitern, leiten Sie eine Klasse von `CListBox`eine meldungszuordnung an die neue Klasse hinzufügen und die vorherigen Meldungshandler Memberfunktionen überschreiben. Überschreiben Sie `OnCreate`, z. B. für die erforderliche Initialisierung für eine neue Klasse.  
  
 Übernehmen Sie die folgenden [Fensterstile](../../mfc/reference/window-styles.md) an ein Listenfeld-Steuerelement.  
  
- **WS_CHILD** immer  
  
- **WS_VISIBLE** in der Regel  
  
- **WS_DISABLED** selten  
  
- **WS_VSCROLL** eine vertikale Bildlaufleiste hinzufügen  
  
- **WS_HSCROLL** eine horizontale Bildlaufleiste hinzufügen  
  
- **WS_GROUP** zum Gruppieren von Steuerelementen  
  
- **WS_TABSTOP** zu ermöglichen, TAB-Taste auf dieses Steuerelement  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #2](../../mfc/codesnippet/cpp/clistbox-class_5.cpp)]  
  
##  <a name="deleteitem"></a>CListBox::DeleteItem  
 Vom Framework aufgerufen, wenn der Benutzer ein Element aus einem Besitzer gezeichneten löscht `CListBox` -Objekt oder im Listenfeld zerstört.  
  
```  
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDeleteItemStruct`  
 Eine long-Zeiger auf ein Windows [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md) -Struktur, die Informationen über das gelöschte Element enthält.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um einen Besitzer gezeichnetes Listenfeld nach Bedarf neu gezeichnet werden.  
  
 Finden Sie unter [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) eine Beschreibung der `DELETEITEMSTRUCT` Struktur.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox 6](../../mfc/codesnippet/cpp/clistbox-class_6.cpp)]  
  
##  <a name="deletestring"></a>CListBox::DeleteString  
 Löscht das Element an Position `nIndex` aus dem Listenfeld aus.  
  
```  
int DeleteString(UINT nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index des zu löschenden Zeichenfolge an.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der in der Liste Verbleibende Zeichenfolgen. Der Rückgabewert ist **LB_ERR** Wenn `nIndex` Index größer als die Anzahl der Elemente in der Liste angibt.  
  
### <a name="remarks"></a>Hinweise  
 Alle Elemente, die nach `nIndex` nun eine Position nach unten verschieben. Z. B. wenn ein Listenfeld, das zwei Elemente enthält, verursacht löschen das erste Element der verbleibenden Element aus, um in der ersten Position aussehen. `nIndex`= 0 für das Element in der ersten Position.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #7](../../mfc/codesnippet/cpp/clistbox-class_7.cpp)]  
  
##  <a name="dir"></a>CListBox::Dir  
 Fügt eine Liste der Dateinamen, Laufwerke oder beides an ein Listenfeld an.  
  
```  
int Dir(
    UINT attr,  
    LPCTSTR lpszWildCard);
```  
  
### <a name="parameters"></a>Parameter  
 `attr`  
 Kann eine beliebige Kombination der `enum` Werte, die in beschriebenen **CFile::GetStatu**[s](../../mfc/reference/cfile-class.md#getstatus), oder eine beliebige Kombination der folgenden Werte:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|0x0000|Datei kann aus gelesen oder geschrieben werden.|  
|0 x 0001|Datei auslesen, jedoch nicht geschrieben werden kann.|  
|0 x 0002|Datei ausgeblendet, und nicht in einer Verzeichnisliste angezeigt.|  
|0 x 0004|Datei ist eine Systemdatei.|  
|0x0010|Indem der angegebene Name `lpszWildCard` gibt das Verzeichnis an.|  
|0x0020|Datei wurde archiviert.|  
|0 x 4000|Schließen Sie alle Laufwerke, die die vom angegebenen Namen entsprechen `lpszWildCard`.|  
|0 x 8000|Exklusive Flag. Wenn die exklusive Flag festgelegt ist, werden nur Dateien des angegebenen Typs aufgeführt. Dateien des angegebenen Typs werden hingegen neben "Standard"-Dateien aufgeführt.|  
  
 `lpszWildCard`  
 Zeigt auf eine Dateispezifikation Zeichenfolge. Die Zeichenfolge kann Platzhalter enthalten (z. B. *.\*).  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des letzten Dateinamen zur Liste hinzugefügt. Der Rückgabewert ist **LB_ERR** Wenn ein Fehler auftritt; der Rückgabewert ist **LB_ERRSPACE** ist nicht genügend Speicherplatz zur Verfügung, um die neuen Zeichenfolgen zu speichern.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #8](../../mfc/codesnippet/cpp/clistbox-class_8.cpp)]  
  
##  <a name="drawitem"></a>CListBox::DrawItem  
 Wird aufgerufen, durch das Framework, wenn sich ein Darstellungsaspekt eines Ownerdrawn-Liste im Feld ändert.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDrawItemStruct`  
 Eine long-Zeiger auf eine [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) -Struktur, die Informationen über den Typ der Zeichnung erforderlich.  
  
### <a name="remarks"></a>Hinweise  
 Die **ItemAction** und **ItemState** Mitglied der `DRAWITEMSTRUCT` Struktur definieren, die Zeichnen-Aktion, die ausgeführt werden soll.  
  
 Standardmäßig wird diese Memberfunktion keine Aktion ausgeführt. Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für ein Ownerdrawn- `CListBox` Objekt. Die Anwendung muss alle Device Interface (GDI) Grafikobjekten ausgewählt, für der Anzeigekontext in bereitgestellten wiederherstellen `lpDrawItemStruct` vor diesem Element Funktion beendet wird.  
  
 Finden Sie unter [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) eine Beschreibung der `DRAWITEMSTRUCT` Struktur.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox 9](../../mfc/codesnippet/cpp/clistbox-class_9.cpp)]  
  
##  <a name="findstring"></a>CListBox:: FindString  
 Sucht die erste Zeichenfolge in einem Listenfeld, das das angegebene Präfix enthält, ohne die Auswahl im Listenfeld zu ändern.  
  
```  
int FindString(
    int nStartAfter,  
    LPCTSTR lpszItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nStartAfter`  
 Enthält den nullbasierten Index des Elements vor dem ersten zu durchsuchenden Element. Wenn die Suche am Ende das Listenfeld erreicht wird, weiterhin von der obersten Position des Listenfelds zurück durch angegebene Element `nStartAfter`. Wenn `nStartAfter` ist-1 und das gesamte Listenfeld wird vom Anfang durchsucht.  
  
 `lpszItem`  
 Verweist auf die auf Null endende Zeichenfolge, die das Präfix für die Suche enthält. Die Suche gilt unabhängig, damit diese Zeichenfolge eine beliebige Kombination von Groß- und Kleinbuchstaben enthalten kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des entsprechenden Elements oder **LB_ERR** , wenn die Suche nicht erfolgreich war.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [SelectString](#selectstring) Memberfunktion versucht, sowohl suchen, und wählen Sie eine Zeichenfolge.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #10](../../mfc/codesnippet/cpp/clistbox-class_10.cpp)]  
  
##  <a name="findstringexact"></a>CListBox::FindStringExact  
 Sucht nach der ersten Listenfeld-Zeichenfolge, die die angegebene Zeichenfolge entspricht `lpszFind`.  
  
```  
int FindStringExact(
    int nIndexStart,  
    LPCTSTR lpszFind) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndexStart`  
 Gibt den nullbasierten Index des Elements vor dem ersten zu durchsuchenden Element. Wenn die Suche am Ende das Listenfeld erreicht wird, weiterhin von der obersten Position des Listenfelds zurück durch angegebene Element `nIndexStart`. Wenn `nIndexStart` ist-1 und das gesamte Listenfeld wird vom Anfang durchsucht.  
  
 `lpszFind`  
 Verweist auf die Null-terminierte Zeichenfolge gesucht. Diese Zeichenfolge kann einen vollständigen Dateinamen, einschließlich der Erweiterung enthalten. Die Suche ist nicht Groß-/Kleinschreibung beachtet werden, damit die Zeichenfolge eine beliebige Kombination von Groß- und Kleinbuchstaben enthalten kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des entsprechenden Elements oder **LB_ERR** , wenn die Suche nicht erfolgreich war.  
  
### <a name="remarks"></a>Hinweise  
 Wenn im Listenfeld in einem Ownerdrawn-Format, aber ohne erstellt wurde die [LBS_HASSTRINGS](../../mfc/reference/list-box-styles.md) Stil, die `FindStringExact` Memberfunktion versucht, mit dem Wert Doppelwort gegen den Wert von übereinstimmen `lpszFind`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox Nr. 11](../../mfc/codesnippet/cpp/clistbox-class_11.cpp)]  
  
##  <a name="getanchorindex"></a>CListBox::GetAnchorIndex  
 Ruft den nullbasierten Index des aktuellen Elements im Listenfeld Anker ab.  
  
```  
int GetAnchorIndex() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des aktuellen Anchor-Elements, wenn erfolgreich; andernfalls **LB_ERR**.  
  
### <a name="remarks"></a>Hinweise  
 In einem Listenfeld mit Mehrfachauswahl ist das Anchor-Element der ersten bzw. letzten Element in einem Block zusammenhängender ausgewählter Elemente.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CListBox::SetAnchorIndex](#setanchorindex).  
  
##  <a name="getcaretindex"></a>CListBox::GetCaretIndex  
 Bestimmt den Index des Elements, das in einem Listenfeld Mehrfachauswahl Fokusrechtecks verfügt.  
  
```  
int GetCaretIndex() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des Elements, das in einem Listenfeld Fokusrechtecks hat. Wenn das Listenfeld ein Listenfeld mit einfacher Auswahl ist, ist der Rückgabewert der Index des Elements, das ausgewählt ist, sofern vorhanden.  
  
### <a name="remarks"></a>Hinweise  
 Das Element kann oder nicht ausgewählt werden.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CListBox::SetCaretIndex](#setcaretindex).  
  
##  <a name="getcount"></a>CListBox::GetCount  
 Ruft die Anzahl der Elemente in einem Listenfeld ab.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Listenfeld oder **LB_ERR** Wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Die zurückgegebene Anzahl ist größer als der Indexwert des letzten Elements (der Index ist nullbasiert).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #12](../../mfc/codesnippet/cpp/clistbox-class_12.cpp)]  
  
##  <a name="getcursel"></a>CListBox::GetCurSel  
 Ruft den nullbasierten Index des derzeit ausgewählten Elements ab, ggf. in einem Listenfeld mit einfacher Auswahl.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des derzeit ausgewählten Elements wird jedoch ein Listenfeld mit einfacher Auswahl. Es ist `LB_ERR` Wenn derzeit kein Element ausgewählt ist.  
  
 In einem Mehrfachauswahl-Listenfeld, den Index des Elements, das den Fokus besitzt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie nicht `GetCurSel` für eine Mehrfachauswahl-Listenfeld. Verwendung [CListBox::GetSelItems](#getselitems) stattdessen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #13](../../mfc/codesnippet/cpp/clistbox-class_13.cpp)]  
  
##  <a name="gethorizontalextent"></a>CListBox::GetHorizontalExtent  
 Ruft die Breite in Pixel, die mit denen sie horizontal gescrollt werden kann, aus dem Listenfeld ab.  
  
```  
int GetHorizontalExtent() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die bildlauffähigen Breite des Listenfelds in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist nur anwendbar, wenn Sie im Listenfeld eine horizontale Bildlaufleiste angezeigt wurde.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox Nr. 14](../../mfc/codesnippet/cpp/clistbox-class_14.cpp)]  
  
##  <a name="getitemdata"></a>CListBox::GetItemData  
 Ruft den von der Anwendung bereitgestellten Doppelwort-Wert, der dem angegebenen Listenfeld-Element zugeordnet.  
  
```  
DWORD_PTR GetItemData(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index des Elements im Listenfeld an.  
  
### <a name="return-value"></a>Rückgabewert  
 Der 32-Bit-Wert, der dem Element zugeordnet oder **LB_ERR** Wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Der Doppelwort-Wert war die `dwItemData` Parameter eine [SetItemData](#setitemdata) aufrufen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #15](../../mfc/codesnippet/cpp/clistbox-class_15.cpp)]  
  
##  <a name="getitemdataptr"></a>CListBox::GetItemDataPtr  
 Ruft ab, der von der Anwendung bereitgestellten 32-Bit-Wert zugeordnet ist, mit dem angegebenen Listenfeld-Element als ein Zeiger ( **"void"\***).  
  
```  
void* GetItemDataPtr(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index des Elements im Listenfeld an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ruft ab einen Zeiger oder -1, wenn ein Fehler auftritt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox Nr. 16](../../mfc/codesnippet/cpp/clistbox-class_16.cpp)]  
  
##  <a name="getitemheight"></a>CListBox::GetItemHeight  
 Bestimmt die Höhe der Elemente in einem Listenfeld.  
  
```  
int GetItemHeight(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index des Elements im Listenfeld an. Dieser Parameter wird verwendet, nur dann, wenn Sie im Listenfeld die **LBS_OWNERDRAWVARIABLE** formatieren; andernfalls muss auf 0 festgelegt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe in Pixel, der die Elemente im Listenfeld. Wenn das Listenfeld die [LBS_OWNERDRAWVARIABLE](../../mfc/reference/list-box-styles.md) Formatvorlage, der Rückgabewert ist die Höhe des Elements gemäß `nIndex`. Wenn ein Fehler auftritt, ist der Rückgabewert **LB_ERR**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #17](../../mfc/codesnippet/cpp/clistbox-class_17.cpp)]  
  
##  <a name="getitemrect"></a>CListBox::GetItemRect  
 Ruft die Abmessungen des Rechtecks, Grenzen ein Listenfeld-Element ab, wie er derzeit im Fenster im Listenfeld angezeigt wird.  
  
```  
int GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index des Elements an.  
  
 `lpRect`  
 Gibt einen long-Zeiger auf eine [RECT-Struktur](../../mfc/reference/rect-structure1.md) , empfängt das Listenfeld Clientkoordinaten des Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 **LB_ERR** , wenn ein Fehler auftritt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox Nr. 18](../../mfc/codesnippet/cpp/clistbox-class_18.cpp)]  
  
##  <a name="getlistboxinfo"></a>CListBox::GetListBoxInfo  
 Ruft die Anzahl von Elementen pro Spalte ab.  
  
```  
DWORD GetListBoxInfo() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Anzahl von Elementen pro Spalte, die von der `CListBox` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen des die [LB_GETLISTBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775208) Nachricht, wie beschrieben in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getlocale"></a>CListBox::GetLocale  
 Ruft das von dem Listenfeld verwendete Gebietsschema ab.  
  
```  
LCID GetLocale() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert des Gebietsschemabezeichners (LCID) für die Zeichenfolgen im Listenfeld.  
  
### <a name="remarks"></a>Hinweise  
 Das Gebietsschema wird beispielsweise verwendet, um die Sortierreihenfolge der Zeichenfolgen in einem sortierten Listenfeld zu ermitteln.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CListBox::SetLocale](#setlocale).  
  
##  <a name="getsel"></a>CListBox::GetSel  
 Ruft den Auswahlzustand eines Elements ab.  
  
```  
int GetSel(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index des Elements an.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine positive Zahl, wenn das angegebene Element ausgewählt ist; Andernfalls ist er 0. Der Rückgabewert ist `LB_ERR` , wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion funktioniert mit beiden einzigen und Mehrfachauswahl-Listenfelder.  
  
 Verwenden Sie zum Abrufen des Indexes des derzeit ausgewählten Listenfeldelement [CListBox::GetCurSel](#getcursel).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox Nr. 19](../../mfc/codesnippet/cpp/clistbox-class_19.cpp)]  
  
##  <a name="getselcount"></a>CListBox::GetSelCount  
 Ruft die Gesamtanzahl der ausgewählten Elemente in einem Listenfeld Mehrfachauswahl ab.  
  
```  
int GetSelCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der ausgewählten Elemente in einem Listenfeld. Wenn das Listenfeld ein Listenfeld mit einfacher Auswahl ist, wird der Rückgabewert ist **LB_ERR**.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CListBox::GetSelItems](#getselitems).  
  
##  <a name="getselitems"></a>CListBox::GetSelItems  
 Füllt einen Puffer mit einem Array von ganzen Zahlen, der die Artikelnummern ausgewählter Elemente in einem Listenfeld Mehrfachauswahl angibt.  
  
```  
int GetSelItems(
    int nMaxItems,  
    LPINT rgIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nMaxItems`  
 Gibt die maximale Anzahl der ausgewählten Elemente, deren Artikelnummern sind im Puffer abgelegt werden soll.  
  
 `rgIndex`  
 Gibt einen Zeiger auf einen Puffer groß genug für die Anzahl von ganzen Zahlen gemäß `nMaxItems`.  
  
### <a name="return-value"></a>Rückgabewert  
 Die tatsächliche Anzahl von Elementen, die im Puffer abgelegt werden. Wenn das Listenfeld ein Listenfeld mit einfacher Auswahl ist, wird der Rückgabewert ist `LB_ERR`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox Nr. 20](../../mfc/codesnippet/cpp/clistbox-class_20.cpp)]  
  
##  <a name="gettext"></a>CListBox::GetText  
 Ruft eine Zeichenfolge aus einem Listenfeld ab.  
  
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
 Gibt den nullbasierten Index der Zeichenfolge abgerufen werden sollen.  
  
 `lpszBuffer`  
 Verweist auf den Puffer, der die Zeichenfolge empfängt. Der Puffer muss genügend Speicherplatz für die Zeichenfolge und ein abschließendes Nullzeichen aufweisen. Die Größe der Zeichenfolge voraus bestimmt werden kann, durch Aufrufen der `GetTextLen` Memberfunktion.  
  
 `rString`  
 Ein Verweis auf ein `CString`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge (in Byte) der Zeichenfolge ist, außer das abschließende Nullzeichen. Wenn `nIndex` gibt keinen gültigen Index, der Rückgabewert ist **LB_ERR**.  
  
### <a name="remarks"></a>Hinweise  
 Die zweite Form dieses Members-Funktion füllt eine `CString` Objekt mit dem Zeichenfolgentext.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #21](../../mfc/codesnippet/cpp/clistbox-class_21.cpp)]  
  
##  <a name="gettextlen"></a>CListBox::GetTextLen  
 Ruft die Länge einer Zeichenfolge in ein Element im Listenfeld ab.  
  
```  
int GetTextLen(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index der Zeichenfolge an.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge der Zeichenfolge in Zeichen, ohne das abschließende Nullzeichen. Wenn `nIndex` gibt keinen gültigen Index, der Rückgabewert ist **LB_ERR**.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CListBox::GetText](#gettext).  
  
##  <a name="gettopindex"></a>CListBox::GetTopIndex  
 Ruft den nullbasierten Index des ersten sichtbaren Elements in einem Listenfeld ab.  
  
```  
int GetTopIndex() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des ersten sichtbaren Elements in einem Listenfeld im Erfolgsfall **LB_ERR** andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Zu Beginn Element 0 befindet sich oben im Listenfeld, aber wenn das Listenfeld Bildlauf durchgeführt wird, möglicherweise ein anderes Element oben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #22](../../mfc/codesnippet/cpp/clistbox-class_22.cpp)]  
  
##  <a name="initstorage"></a>CListBox::InitStorage  
 Belegt Speicher für das Speichern von Listenfeld Elemente.  
  
```  
int InitStorage(
    int nItems,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>Parameter  
 `nItems`  
 Gibt die Anzahl von Elementen hinzufügen.  
  
 `nBytes`  
 Gibt die Größe des Speichers in Bytes, die für Element Zeichenfolgen zugeordnet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, die maximale Anzahl von Elementen, die im Listenfeld kann gespeichert werden, bevor eine neuzuordnung von Arbeitsspeicher, andernfalls erforderlich ist **LB_ERRSPACE**, d. h. nicht genügend Arbeitsspeicher verfügbar ist.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird vor dem Hinzufügen von eine große Anzahl von Elementen, die eine `CListBox`.  
  
 Diese Funktion hilft der Initialisierung des Listenfelder beschleunigen, die eine große Anzahl von Elementen (mehr als 100) aufweisen. Es reserviert so, dass bei nachfolgenden angegebene Arbeitsspeichermenge [AddString](#addstring), [InsertString](#insertstring), und [Dir](#dir) akzeptieren Funktionen kurz wie möglich. Sie können die Schätzungen für die Parameter verwenden. Wenn Sie überschätzen, wird zusätzlicher Arbeitsspeicher reserviert. Wenn Sie unterschätzen, wird die normale Verteilung für Elemente verwendet, die den eingeteilt überschreiten.  
  
 Windows 95/98: der `nItems` Parameter ist auf 16-Bit-Werte beschränkt. Dies bedeutet, dass Listenfelder mehr als 32.767 Elemente enthalten können. Obwohl die Anzahl der Elemente eingeschränkt ist, ist die Gesamtgröße der Elemente in einem Listenfeld, das nur durch den verfügbaren Speicher beschränkt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #23](../../mfc/codesnippet/cpp/clistbox-class_23.cpp)]  
  
##  <a name="insertstring"></a>CListBox::InsertString  
 Fügt eine Zeichenfolge in das Listenfeld ein.  
  
```  
int InsertString(
    int nIndex,  
    LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index der Position die Zeichenfolge eingefügt. Wenn dieser Parameter-1 ist, wird die Zeichenfolge am Ende der Liste hinzugefügt.  
  
 `lpszItem`  
 Zeigt auf die einzufügende nullterminierte Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index der Position, an der die Zeichenfolge eingefügt wurde. Der Rückgabewert ist **LB_ERR** Wenn ein Fehler auftritt; der Rückgabewert ist **LB_ERRSPACE** ist nicht genügend Speicherplatz zum Speichern der neuen Zeichenfolge zur Verfügung.  
  
### <a name="remarks"></a>Hinweise  
 Im Gegensatz zu der [AddString](#addstring) Memberfunktion, `InsertString` nicht dazu, dass eine Liste mit den [LBS_SORT](../../mfc/reference/list-box-styles.md) Stil sortiert werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #24](../../mfc/codesnippet/cpp/clistbox-class_24.cpp)]  
  
##  <a name="itemfrompoint"></a>CListBox::ItemFromPoint  
 Bestimmt das Element im Listenfeld am nächsten liegt der Punkt im angegebenen `pt`.  
  
```  
UINT ItemFromPoint(
    CPoint pt,  
    BOOL& bOutside) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Zeigen Sie für die das nächste Element, relativ zur linken oberen Ecke des Clientbereichs des Listenfelds angegeben gesucht.  
  
 `bOutside`  
 Ein Verweis auf eine `BOOL` Variable, die festgelegt wird `TRUE` Wenn `pt` ist außerhalb des Client das nächste Listenfeldelement `FALSE` Wenn `pt` befindet sich innerhalb der Clientbereich der nächste Listenfeldelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des nächsten Elements zu dem Punkt im angegebenen `pt`.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Funktion verwenden, um zu bestimmen, welches Element im Listenfeld den Mauszeiger bewegt wird, über.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CListBox::SetAnchorIndex](#setanchorindex).  
  
##  <a name="measureitem"></a>CListBox::MeasureItem  
 Vom Framework aufgerufen, wenn ein Listenfeld mit einem Ownerdrawn-Stil erstellt wird.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpMeasureItemStruct`  
 Eine long-Zeiger auf eine [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird diese Memberfunktion keine Aktion ausgeführt. Überschreiben Sie diese Memberfunktion auf, und geben Sie die `MEASUREITEMSTRUCT` Struktur Windows der Dimensionen im Listenfeld zu informieren. Wenn Sie im Listenfeld mit erstellt wird die [LBS_OWNERDRAWVARIABLE](../../mfc/reference/list-box-styles.md) Format, das Framework ruft diese Memberfunktion für jedes Element im Listenfeld. Andernfalls wird bei diesem Member nur einmal aufgerufen.  
  
 Weitere Informationen zum Verwenden der [LBS_OWNERDRAWFIXED](../../mfc/reference/list-box-styles.md) Format in ein Besitzer gezeichnetes Listenfeld mit erstellt die `SubclassDlgItem` Memberfunktion von `CWnd`, finden Sie unter den Ausführungen im [technischen Hinweis 14](../../mfc/tn014-custom-controls.md).  
  
 Finden Sie unter [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) eine Beschreibung der `MEASUREITEMSTRUCT` Struktur **.**  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #25](../../mfc/codesnippet/cpp/clistbox-class_25.cpp)]  
  
##  <a name="resetcontent"></a>CListBox::ResetContent  
 Entfernt alle Elemente aus einem Listenfeld.  
  
```  
void ResetContent();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #26](../../mfc/codesnippet/cpp/clistbox-class_26.cpp)]  
  
##  <a name="selectstring"></a>CListBox::SelectString  
 Suchvorgänge für ein Element im Listenfeld, die mit die angegebene Zeichenfolge übereinstimmt, und wenn ein übereinstimmendes Element gefunden wird, wird das Element ausgewählt.  
  
```  
int SelectString(
    int nStartAfter,  
    LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>Parameter  
 `nStartAfter`  
 Enthält den nullbasierten Index des Elements vor dem ersten zu durchsuchenden Element. Wenn die Suche am Ende das Listenfeld erreicht wird, weiterhin von der obersten Position des Listenfelds zurück durch angegebene Element `nStartAfter`. Wenn `nStartAfter` ist-1 und das gesamte Listenfeld wird vom Anfang durchsucht.  
  
 `lpszItem`  
 Verweist auf die auf Null endende Zeichenfolge, die das Präfix für die Suche enthält. Die Suche gilt unabhängig, damit diese Zeichenfolge eine beliebige Kombination von Groß- und Kleinbuchstaben enthalten kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des ausgewählten Elements, wenn die Suche erfolgreich war. Wenn die Suche nicht erfolgreich war, ist der Rückgabewert **LB_ERR** und die aktuelle Auswahl nicht geändert wird.  
  
### <a name="remarks"></a>Hinweise  
 Im Listenfeld wird, falls erforderlich, um das ausgewählte Element sichtbar zu machen ein Bildlauf durchgeführt.  
  
 Diese Memberfunktion kann nicht verwendet werden, mit einem Listenfeld, das verfügt die [LBS_MULTIPLESEL](../../mfc/reference/list-box-styles.md) Stil.  
  
 Ein Element ausgewählt ist, nur dann, wenn die ersten Zeichen (aus den Ausgangspunkt) mit den Zeichen in der angegebenen Zeichenfolge übereinstimmen `lpszItem`.  
  
 Verwenden der `FindString` Memberfunktion versucht, einer Zeichenfolge zu suchen, ohne das Element auszuwählen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #27](../../mfc/codesnippet/cpp/clistbox-class_27.cpp)]  
  
##  <a name="selitemrange"></a>CListBox::SelItemRange  
 Wählt mehrere aufeinander folgende Elemente in einer Mehrfachauswahl-Listenfeld aus.  
  
```  
int SelItemRange(
    BOOL bSelect,  
    int nFirstItem,  
    int nLastItem);
```  
  
### <a name="parameters"></a>Parameter  
 `bSelect`  
 Gibt an, wie die Auswahl. Wenn `bSelect` ist **"true"**, ausgewählt und hervorgehoben, wenn die Zeichenfolge **"false"**, wird die Hervorhebung entfernt, und die Zeichenfolge nicht mehr ausgewählt ist.  
  
 `nFirstItem`  
 Gibt den nullbasierten Index des ersten Elements festlegen.  
  
 `nLastItem`  
 Gibt den nullbasierten Index des letzten Elements festlegen.  
  
### <a name="return-value"></a>Rückgabewert  
 **LB_ERR** , wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Memberfunktion auf, nur mit Mehrfachauswahl-Listenfelder. Wenn Sie nur ein Element in einem Mehrfachauswahl-Listenfeld auswählen müssen – d. h. wenn `nFirstItem` ist gleich `nLastItem` – Aufrufen der [Memberfunktion SetSel](#setsel) Memberfunktion stattdessen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #28](../../mfc/codesnippet/cpp/clistbox-class_28.cpp)]  
  
##  <a name="setanchorindex"></a>CListBox::SetAnchorIndex  
 Legt fest, die Verankerung in einem Mehrfachauswahl-Listenfeld, um eine erweiterte Auswahl zu beginnen.  
  
```  
void SetAnchorIndex(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index des Elements im Listenfeld, die dem Anker.  
  
### <a name="remarks"></a>Hinweise  
 In einem Listenfeld mit Mehrfachauswahl ist das Anchor-Element der ersten bzw. letzten Element in einem Block zusammenhängender ausgewählter Elemente.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #29](../../mfc/codesnippet/cpp/clistbox-class_29.cpp)]  
  
##  <a name="setcaretindex"></a>CListBox::SetCaretIndex  
 Legt Fokusrechtecks auf das Element am angegebenen Index in einem Listenfeld Mehrfachauswahl fest.  
  
```  
int SetCaretIndex(
    int nIndex,  
    BOOL bScroll = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index des Elements, Fokusrechtecks in das Listenfeld zu erhalten.  
  
 *bScroll*  
 Wenn dieser Wert 0 ist, wird das Element Bildlauf durchgeführt werden, bis er vollständig sichtbar ist. Wenn dieser Wert nicht 0 (null) das Element wird durch einen Bildlauf bis er zumindest teilweise sichtbar ist.  
  
### <a name="return-value"></a>Rückgabewert  
 **LB_ERR** , wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Element nicht sichtbar ist, wird es einen Bildlauf angezeigt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #30](../../mfc/codesnippet/cpp/clistbox-class_30.cpp)]  
  
##  <a name="setcolumnwidth"></a>CListBox::SetColumnWidth  
 Legt die Breite in Pixel aller Spalten in einem mehrspaltigen Listenfeld (erstellt mit dem [LBS_MULTICOLUMN](../../mfc/reference/list-box-styles.md) Stil).  
  
```  
void SetColumnWidth(int cxWidth);
```  
  
### <a name="parameters"></a>Parameter  
 `cxWidth`  
 Gibt die Breite in Pixel aller Spalten an.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #31](../../mfc/codesnippet/cpp/clistbox-class_31.cpp)]  
  
##  <a name="setcursel"></a>CListBox::SetCurSel  
 Wählt eine Zeichenfolge, und verschiebt es in der Ansicht bei Bedarf.  
  
```  
int SetCurSel(int nSelect);
```  
  
### <a name="parameters"></a>Parameter  
 `nSelect`  
 Gibt den nullbasierten Index der Zeichenfolge, die ausgewählt werden. Wenn `nSelect` ist-1, keine Auswahl im Listenfeld festgelegt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 `LB_ERR`Wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die neue Zeichenfolge aktiviert ist, die Hervorhebung von im Listenfeld aus der zuvor ausgewählten Zeichenfolge entfernt.  
  
 Verwenden Sie diese Memberfunktion auf, nur mit Mehrfachauswahl-Listenfelder.  
  
 Verwenden Sie zum Festlegen oder entfernen eine Auswahl in einem Mehrfachauswahl-Listenfeld, [CListBox::SetSel](#setsel).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #32](../../mfc/codesnippet/cpp/clistbox-class_32.cpp)]  
  
##  <a name="sethorizontalextent"></a>CListBox:: SetHorizontalExtent  
 Legt die Breite in Pixel, ein Listenfeld horizontal gescrollt werden kann.  
  
```  
void SetHorizontalExtent(int cxExtent);
```  
  
### <a name="parameters"></a>Parameter  
 *cxExtent*  
 Gibt die Anzahl der Pixel, die mit denen im Listenfeld horizontal gescrollt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Größe des Listenfelds kleiner als dieser Wert ist, wird die horizontale Bildlaufleiste Elemente im Listenfeld die horizontale Bildlaufleiste. Wenn das Listenfeld genauso groß oder größer als dieser Wert ist, wird die horizontale Bildlaufleiste ausgeblendet.  
  
 So reagieren Sie auf einen Aufruf von `SetHorizontalExtent`, im Listenfeld wurde muss definiert die [WS_HSCROLL](../../mfc/reference/window-styles.md) Stil.  
  
 Diese Memberfunktion ist nicht für mehrspaltige Listenfelder nützlich. Rufen Sie für den mehrspaltigen Listenfelder, die `SetColumnWidth` Memberfunktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #33](../../mfc/codesnippet/cpp/clistbox-class_33.cpp)]  
  
##  <a name="setitemdata"></a>CListBox::SetItemData  
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
 [!code-cpp[NVC_MFC_CListBox #34](../../mfc/codesnippet/cpp/clistbox-class_34.cpp)]  
  
##  <a name="setitemdataptr"></a>CListBox::SetItemDataPtr  
 Legt den 32-Bit-Wert, der das angegebene Element in einem Listenfeld des angegebenen Zeigers sein zugeordnet ( **"void"\***).  
  
```  
int SetItemDataPtr(
    int nIndex,  
    void* pData);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index des Elements an.  
  
 `pData`  
 Gibt den Mauszeiger, um das Element zugeordnet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 **LB_ERR** , wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 This-Zeiger bleibt gültig, für die Lebensdauer der im Listenfeld, auch wenn das Element relativen Position innerhalb des Listenfelds ändern kann, wie Elemente hinzugefügt oder entfernt werden. Daher kann der Index des Elements in das Feld ändern, aber der Zeiger bleibt zuverlässige.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #35](../../mfc/codesnippet/cpp/clistbox-class_35.cpp)]  
  
##  <a name="setitemheight"></a>CListBox::SetItemHeight  
 Legt die Höhe der Elemente in einem Listenfeld fest.  
  
```  
int SetItemHeight(
    int nIndex,  
    UINT cyItemHeight);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index des Elements im Listenfeld an. Dieser Parameter wird verwendet, nur dann, wenn Sie im Listenfeld die **LBS_OWNERDRAWVARIABLE** formatieren; andernfalls muss auf 0 festgelegt werden.  
  
 `cyItemHeight`  
 Gibt die Höhe des Elements in Pixel an.  
  
### <a name="return-value"></a>Rückgabewert  
 **LB_ERR** , wenn der Index oder der Höhe ungültig ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Listenfeld die [LBS_OWNERDRAWVARIABLE](../../mfc/reference/list-box-styles.md) Stil, diese Funktion legt die Höhe des Elements gemäß `nIndex`. Andernfalls wird diese Funktion die Höhe aller Elemente im Listenfeld.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #36](../../mfc/codesnippet/cpp/clistbox-class_36.cpp)]  
  
##  <a name="setlocale"></a>CListBox::SetLocale  
 Legt den Gebietsschemabezeichner für dieses Listenfelds an.  
  
```  
LCID SetLocale(LCID nNewLocale);
```  
  
### <a name="parameters"></a>Parameter  
 `nNewLocale`  
 Das neue Gebietsschema Gebietsschemabezeichner (LCID) für das Listenfeld festzulegende Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Der vorherige Gebietsschema Gebietsschemabezeichner (LCID) Wert für das Listenfeld.  
  
### <a name="remarks"></a>Hinweise  
 Wenn **SetLocale** nicht aufgerufen wird, die Standardeinstellung Gebietsschema wird vom System abgerufen. Diese Standardgebietsschemas kann geändert werden, mithilfe der Systemsteuerung des regionalen (oder International)-Anwendung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #37](../../mfc/codesnippet/cpp/clistbox-class_37.cpp)]  
  
##  <a name="setsel"></a>CListBox::SetSel  
 Wählt eine Zeichenfolge in einem Mehrfachauswahl-Listenfeld aus.  
  
```  
int SetSel(
    int nIndex,  
    BOOL bSelect = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Enthält den nullbasierten Index der Zeichenfolge festgelegt werden. Wenn-1 und die Auswahl hinzugefügt oder entfernt wird aus allen Zeichenfolgen, abhängig vom Wert des `bSelect`.  
  
 `bSelect`  
 Gibt an, wie die Auswahl. Wenn `bSelect` ist `TRUE`, ausgewählt und hervorgehoben, wenn die Zeichenfolge `FALSE`, wird die Hervorhebung entfernt, und die Zeichenfolge nicht mehr ausgewählt ist. Die angegebene Zeichenfolge ausgewählt ist, und standardmäßig markiert.  
  
### <a name="return-value"></a>Rückgabewert  
 `LB_ERR`Wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Memberfunktion auf, nur mit Mehrfachauswahl-Listenfelder.  
  
 Um ein Element aus einem Einzelauswahl-Listenfeld auswählen möchten, verwenden Sie [CListBox::SetCurSel](#setcursel).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #38](../../mfc/codesnippet/cpp/clistbox-class_38.cpp)]  
  
##  <a name="settabstops"></a>CListBox::SetTabStops  
 Legt die Tabstopp Positionen in einem Listenfeld an.  
  
```  
void SetTabStops();  
BOOL SetTabStops(const int& cxEachStop);

 
BOOL SetTabStops(
    int nTabStops,  
    LPINT rgTabStops);
```  
  
### <a name="parameters"></a>Parameter  
 `cxEachStop`  
 Tabstopps festgelegt sind, bei jedem `cxEachStop` Dialogeinheiten. Finden Sie unter *RgTabStops* für eine Beschreibung des eine Dialogeinheit.  
  
 `nTabStops`  
 Gibt die Anzahl der Tabstopps, haben Sie im Listenfeld.  
  
 `rgTabStops`  
 Verweist auf das erste Element eines Arrays von Ganzzahlen, das die Tabstopp Positionen in Dialogeinheiten enthält. Eine Dialogeinheit ist einen horizontalen oder vertikalen Abstand an. Eine horizontale Dialogeinheit ein Viertel der aktuellen Dialogfeld Basis Breite Einheit entspricht, und eine vertikale Dialogeinheit entspricht einem Achtel des aktuellen Dialogfeld Basis Höhe Komponententest. Die Basis Dialogeinheiten werden basierend auf die Höhe und Breite der aktuellen Systemschriftart berechnet. Die **GetDialogBaseUnits** Windows-Funktion gibt den aktuellen Dialogfeld Basis Einheiten in Pixel. Die Tabstopps müssen in aufsteigender Reihenfolge sortiert werden; Back-Registerkarten sind nicht zulässig.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn alle Registerkarten festgelegt wurden; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die parameterlose Version von dieser Memberfunktion, um die Standardgröße des 2 Dialogeinheiten Tabstopps festzulegen. Rufen Sie zum Festlegen von Tabstopps auf eine Größe als 2, die Version mit der `cxEachStop` Argument.  
  
 Um ein Array von Größen Tabstopps festzulegen, verwenden Sie die Version mit der `rgTabStops` und `nTabStops` Argumente. Für jeden Wert in ein Tabstopp festgelegt `rgTabStops`, bis zur Anzahl von angegebenen `nTabStops`.  
  
 So reagieren Sie auf einen Aufruf der `SetTabStops` Memberfunktion, die im Listenfeld muss erstellt worden mit der [LBS_USETABSTOPS](../../mfc/reference/list-box-styles.md) Stil.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #39](../../mfc/codesnippet/cpp/clistbox-class_39.cpp)]  
  
##  <a name="settopindex"></a>CListBox::SetTopIndex  
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
 Das System führt einen Bildlauf im Listenfeld, bis das durch angegebene Element `nIndex` wird am oberen Rand der Liste im Feld oder den maximalen Bildlaufbereich wurde erreicht.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #-40](../../mfc/codesnippet/cpp/clistbox-class_40.cpp)]  
  
##  <a name="vkeytoitem"></a>CListBox::VKeyToItem  
 Vom Framework aufgerufen, wenn das Listenfeld übergeordneten Fenster empfängt eine `WM_VKEYTOITEM` Nachricht aus dem Listenfeld aus.  
  
```  
virtual int VKeyToItem(
    UINT nKey,  
    UINT nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nKey`  
 Den virtueller Tastencode des Schlüssels hat der Benutzer geklickt. Eine Liste der standardmäßigen virtuellen Tastencodes finden Sie unter Winuser.h  
  
 `nIndex`  
 Die aktuelle Position der Einfügemarke im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt - 2 für die keine weitere Aktion, - 1 für die Standardaktion oder eine nicht negative Zahl, geben Sie einen Index von einem Listenfeldelement, für die Standardaktion für die Tastatureingabe durchführen.  
  
### <a name="remarks"></a>Hinweise  
 Die `WM_VKEYTOITEM` Nachricht vom Listenfeld beim Empfang einer `WM_KEYDOWN` Nachricht aber, nur wenn das Listenfeld beide der folgenden erfüllt:  
  
-   Hat die [LBS_WANTKEYBOARDINPUT](../../mfc/reference/list-box-styles.md) Satz formatieren.  
  
-   Verfügt über mindestens ein Element aus.  
  
 Sie sollten diese Funktion niemals selbst aufrufen. Überschreiben Sie diese Funktion um eine eigene benutzerdefinierte Behandlung tastaturmeldungen bereitzustellen.  
  
 Sie müssen einen Wert für dem Framework angeben, welche Aktion die Außerkraftsetzung ausgeführt zurückkehren. Ein Rückgabewert von - gibt 2 an, dass die Anwendung alle Aspekte behandelt der Auswahl des Elements und keine weitere Aktion vom Listenfeld erfordert. Vor dem Zurückgeben von-2, legen Sie die Auswahl oder Verschieben der Einfügemarke oder beides werden konnte. Verwenden Sie zum Festlegen der Auswahl [SetCurSel](#setcursel) oder [Memberfunktion SetSel](#setsel). Verwenden Sie zum Verschieben der Einfügemarke [SetCaretIndex](#setcaretindex).  
  
 Ein Rückgabewert von - 1 zeigt an, dass im Listenfeld die Default-Aktion als Antwort auf die Tastatureingabe durchführen soll. Die Standardimplementierung gibt - 1.  
  
 Ein Rückgabewert von 0 oder größer gibt den Index eines Elements im Listenfeld an und gibt an, dass im Listenfeld die Standardaktion für die Tastatureingabe auf das angegebene Element durchführen soll.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CListBox #41](../../mfc/codesnippet/cpp/clistbox-class_41.cpp)]  
  
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

