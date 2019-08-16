---
title: CCheckListBox-Klasse
ms.date: 11/04/2016
f1_keywords:
- CCheckListBox
- AFXWIN/CCheckListBox
- AFXWIN/CCheckListBox::CCheckListBox
- AFXWIN/CCheckListBox::Create
- AFXWIN/CCheckListBox::DrawItem
- AFXWIN/CCheckListBox::Enable
- AFXWIN/CCheckListBox::GetCheck
- AFXWIN/CCheckListBox::GetCheckStyle
- AFXWIN/CCheckListBox::IsEnabled
- AFXWIN/CCheckListBox::MeasureItem
- AFXWIN/CCheckListBox::OnGetCheckPosition
- AFXWIN/CCheckListBox::SetCheck
- AFXWIN/CCheckListBox::SetCheckStyle
helpviewer_keywords:
- CCheckListBox [MFC], CCheckListBox
- CCheckListBox [MFC], Create
- CCheckListBox [MFC], DrawItem
- CCheckListBox [MFC], Enable
- CCheckListBox [MFC], GetCheck
- CCheckListBox [MFC], GetCheckStyle
- CCheckListBox [MFC], IsEnabled
- CCheckListBox [MFC], MeasureItem
- CCheckListBox [MFC], OnGetCheckPosition
- CCheckListBox [MFC], SetCheck
- CCheckListBox [MFC], SetCheckStyle
ms.assetid: 1dd78438-00e8-441c-b36f-9c4f9ac0d019
ms.openlocfilehash: f8c725ea30754a42ce3045f1160b7a09c4481e39
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507346"
---
# <a name="cchecklistbox-class"></a>CCheckListBox-Klasse

Stellt die Funktionalität eines Windows-Kontrolllistenfelds bereit.

## <a name="syntax"></a>Syntax

```
class CCheckListBox : public CListBox
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CCheckListBox::CCheckListBox](#cchecklistbox)|Erstellt ein `CCheckListBox`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CCheckListBox::Create](#create)|Erstellt das Fenster Prüfliste für Windows und fügt `CCheckListBox` es an das-Objekt an.|
|[CCheckListBox::DrawItem](#drawitem)|Wird von Framework aufgerufen, wenn sich ein visueller Aspekt eines Listen Felds für das Besitzer Zeichen ändert.|
|[CCheckListBox::Enable](#enable)|Aktiviert oder deaktiviert ein Prüfliste-Feld Element.|
|[CCheckListBox::GetCheck](#getcheck)|Ruft den Zustand des Kontrollkästchens eines Elements ab.|
|[CCheckListBox::GetCheckStyle](#getcheckstyle)|Ruft den Stil der Kontrollkästchen des-Steuer Elements ab.|
|[CCheckListBox::IsEnabled](#isenabled)|Bestimmt, ob ein Element aktiviert ist.|
|[CCheckListBox::MeasureItem](#measureitem)|Wird von Framework aufgerufen, wenn ein Listenfeld mit einer Art von Besitzer Zeichenfolge erstellt wird.|
|[CCheckListBox::OnGetCheckPosition](#ongetcheckposition)|Wird von Framework aufgerufen, um die Position des Kontrollkästchens eines Elements zu erhalten.|
|[CCheckListBox::SetCheck](#setcheck)|Legt den Zustand des Kontrollkästchens eines Elements fest.|
|[CCheckListBox::SetCheckStyle](#setcheckstyle)|Legt den Stil der Kontrollkästchen des-Steuer Elements fest.|

## <a name="remarks"></a>Hinweise

Im Feld "Prüfliste" wird eine Liste von Elementen, z. b. Dateinamen, angezeigt. Jedes Element in der Liste enthält ein Kontrollkästchen neben dem Element, das der Benutzer überprüfen oder deaktivieren kann.

`CCheckListBox`gilt nur für Steuerelemente, die vom Besitzer gezeichnet werden, da die Liste mehr als Text Zeichenfolgen enthält. Im einfachsten Fall enthält ein Prüfliste Text Zeichenfolgen und Kontrollkästchen, aber Sie müssen nicht über Text verfügen. Beispielsweise können Sie über eine Liste kleiner Bitmaps mit einem Kontrollkästchen neben jedem Element verfügen.

Um ein eigenes Prüfliste zu erstellen, müssen Sie eine eigene Klasse `CCheckListBox`von ableiten. Wenn Sie eine eigene Klasse ableiten möchten, schreiben Sie einen Konstruktor für die abgeleitete `Create`Klasse, und geben Sie dann ein.

Wenn Sie die von einem Listenfeld gesendeten Windows-Benachrichtigungs Meldungen an das übergeordnete Element (in der Regel eine von [CDialog](../../mfc/reference/cdialog-class.md)abgeleitete Klasse) verarbeiten möchten, fügen Sie der übergeordneten Klasse für jede Nachricht einen Nachrichten Zuordnungs Eintrag und eine nachrichtenhandlermember-Funktion hinzu.

Jeder Nachrichten Zuordnungs Eintrag hat die folgende Form:

**Bei\_** _Benachrichtigung_ **(** _ID_, _mitgliedungsfxn_ **)**

Where `id` gibt die untergeordnete Fenster-ID des Steuer Elements an, `memberFxn` das die Benachrichtigung sendet, und ist der Name der übergeordneten Element Funktion, die Sie zum Verarbeiten der Benachrichtigung geschrieben haben.

Der Prototyp der übergeordneten Funktion ist wie folgt:

`afx_msg void memberFxn();`

Es gibt nur einen Meldungs Zuordnungs Eintrag, der sich speziell `CCheckListBox` auf bezieht (es werden jedoch auch die Meldungs Zuordnungs Einträge für [CListBox](../../mfc/reference/clistbox-class.md)angezeigt):

- ON_CLBN_CHKCHANGE der Benutzer hat den Status des Kontrollkästchens eines Elements geändert.

Wenn es sich bei der Prüfliste um ein Standard Prüfliste handelt (eine Liste von Zeichen folgen mit den standardmäßigen Kontrollkästchen auf der linken Seite), können Sie das Kontrollkästchen Standardwert für " [CCheckListBox::D rawitem](#drawitem) " verwenden, um das Prüfliste zu zeichnen. Andernfalls müssen Sie die [CListBox:: compareitem](../../mfc/reference/clistbox-class.md#compareitem) -Funktion und die [CCheckListBox::D rawitem](#drawitem) -und [CCheckListBox:: MeasureItem](#measureitem) -Funktionen überschreiben.

Sie können ein Prüfliste entweder aus einer Dialogfeld Vorlage oder direkt im Code erstellen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListBox](../../mfc/reference/clistbox-class.md)

`CCheckListBox`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="cchecklistbox"></a>CCheckListBox:: CCheckListBox

Erstellt ein `CCheckListBox`-Objekt.

```
CCheckListBox();
```

### <a name="remarks"></a>Hinweise

Sie erstellen ein `CCheckListBox` -Objekt in zwei Schritten. Definieren Sie zunächst eine von `CCheckListBox`abgeleitete Klasse, und klicken Sie `Create`dann auf, wodurch das Fenster Prüfliste für `CCheckListBox` Windows initialisiert und an das-Objekt angehängt wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCControlLadenDialog#60](../../mfc/codesnippet/cpp/cchecklistbox-class_1.cpp)]

##  <a name="create"></a>CCheckListBox:: Create

Erstellt das Fenster Prüfliste für Windows und fügt `CCheckListBox` es an das-Objekt an.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Gibt die Art der Prüfliste an. Der Stil muss LBS_HASSTRINGS lauten und entweder LBS_OWNERDRAWFIXED (alle Elemente in der Liste haben dieselbe Höhe) oder LBS_OWNERDRAWVARIABLE (Elemente in der Liste weisen eine unterschiedliche Höhe auf). Dieser Stil kann mit anderen [Listenfeld Stilen](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) mit Ausnahme von LBS_USETABSTOPS kombiniert werden.

*Rect*<br/>
Gibt die Größe und Position der Prüfliste an. Kann entweder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt oder eine [Rect](/windows/win32/api/windef/ns-windef-rect) -Struktur sein.

*pParentWnd*<br/>
Gibt das übergeordnete Fenster der Prüfliste an `CDialog` (normalerweise ein-Objekt). Er darf nicht NULL sein.

*nID*<br/>
Gibt die Steuerelement-ID der Prüfliste an.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Sie erstellen ein `CCheckListBox` -Objekt in zwei Schritten. Definieren Sie zunächst eine von `CcheckListBox` abgeleitete Klasse, und klicken Sie `Create`dann auf, wodurch das Fenster Prüfliste für Windows `CCheckListBox`initialisiert und an die angefügt wird. Ein Beispiel finden Sie unter [CCheckListBox:: CCheckListBox](#cchecklistbox) .

Wenn `Create` ausgeführt wird, sendet Windows die [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate)-, [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate)-, [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)-und [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) -Nachrichten an das CheckBox-Steuerelement.

Diese Nachrichten werden standardmäßig von den Element Funktionen " [onnccreate](../../mfc/reference/cwnd-class.md#onnccreate)", " [OnCreate](../../mfc/reference/cwnd-class.md#oncreate)", " [onnccalcsize](../../mfc/reference/cwnd-class.md#onnccalcsize)" und " [ongetminmaxinfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) " in der `CWnd` Basisklasse verarbeitet. Um die standardmäßige Meldungs Behandlung zu erweitern, fügen Sie der abgeleiteten Klasse eine Meldungs Zuordnung hinzu, und überschreiben Sie die zuvor genannten nachrichtenhandlerelementfunktionen. Über `OnCreate`schreiben Sie z. b., um die erforderliche Initialisierung für eine neue Klasse auszuführen.

Anwenden der folgenden [Fenster Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles) auf ein checkprüfliste-Steuerelement:

- WS_CHILD immer

- WS_VISIBLE normalerweise

- WS_DISABLED selten

- WS_VSCROLL zum Hinzufügen einer vertikalen Scrollleiste

- WS_HSCROLL zum Hinzufügen einer horizontalen Scrollleiste

- WS_GROUP zum Gruppieren von Steuerelementen

- WS_TABSTOP, um die Tabstopps für dieses Steuerelement zuzulassen

##  <a name="drawitem"></a>CCheckListBox::D rawitem

Wird von Framework aufgerufen, wenn sich ein visueller Aspekt eines von einem Besitzer gezeichneten Prüfliste ändert.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parameter

*lpDrawItemStruct*<br/>
Ein langer Zeiger auf eine [drawitemstruct](/windows/win32/api/winuser/ns-winuser-drawitemstruct) -Struktur, die Informationen über den erforderlichen Zeichentyp enthält.

### <a name="remarks"></a>Hinweise

Die `itemAction` - `itemState` und-Member `DRAWITEMSTRUCT` der-Struktur definieren die Zeichnungs Aktion, die ausgeführt werden soll.

Standardmäßig zeichnet diese Funktion eine Standard-CheckBox-Liste, die aus einer Liste von Zeichen folgen mit jeweils einem standardmäßigen Kontrollkästchen auf der linken Seite besteht. Die Liste der Kontrollkästchen ist die in [Create](#create)angegebene Größe.

Überschreiben Sie diese Member-Funktion, um das Zeichnen von Prüfliste für das Erstellen von Besitzern zu implementieren, bei denen es sich nicht um die Standardwerte handelt, z. b. Prüfliste mit Listen, die keine Zeichen folgen sind, mit Elementen variabler Höhe oder mit Kontrollkästchen Die Anwendung sollte alle GDI-Objekte (Graphics Device Interface), die für den in *lpdrawitemstruct* angegebenen Anzeige Kontext ausgewählt wurden, vor der Beendigung dieser Element Funktion wiederherstellen.

Wenn Prüfliste Elemente nicht die gleiche Höhe aufweisen, muss der Stil der Prüfliste `Create`(angegeben in) * * LBS_OWNERVARIABLE sein, und Sie müssen die [MeasureItem](#measureitem) -Funktion überschreiben.

##  <a name="enable"></a>CCheckListBox:: enable

Mit dieser Funktion können Sie ein Checklisten Element aktivieren oder deaktivieren.

```
void Enable(
    int nIndex,
    BOOL bEnabled = TRUE);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des zu aktivierenden Prüfliste-Elements.

*benabled*<br/>
Gibt an, ob das Element aktiviert oder deaktiviert ist.

##  <a name="getcheck"></a>CCheckListBox:: getcheck

Ruft den Zustand des angegebenen Kontrollkästchens ab.

```
int GetCheck(int nIndex);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der null basierte Index eines Kontrollkästchens, das im Listenfeld enthalten ist.

### <a name="return-value"></a>Rückgabewert

Der Zustand des angegebenen Kontrollkästchens. In der folgenden Tabelle sind die möglichen Werte aufgeführt.

|Wert|Beschreibung|
|-----------|-----------------|
|BST_CHECKED|Das Kontrollkästchen ist aktiviert.|
|BST_UNCHECKED|Das Kontrollkästchen ist nicht aktiviert.|
|BST_INDETERMINATE|Der Kontrollkästchen Zustand ist unbestimmt.|

##  <a name="getcheckstyle"></a>CCheckListBox:: getcheckstyle

Mit dieser Funktion können Sie den Stil der Prüfliste abrufen.

```
UINT GetCheckStyle();
```

### <a name="return-value"></a>Rückgabewert

Der Stil der Kontrollkästchen des Steuer Elements.

### <a name="remarks"></a>Hinweise

Informationen zu möglichen Stilen finden Sie unter [setcheckstyle](#setcheckstyle).

##  <a name="isenabled"></a>CCheckListBox:: isaktivierte

Mit dieser Funktion können Sie feststellen, ob ein Element aktiviert ist.

```
BOOL IsEnabled(int nIndex);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des Elements.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn das Element aktiviert ist. andernfalls 0.

##  <a name="measureitem"></a>CCheckListBox:: MeasureItem

Wird von Framework aufgerufen, wenn ein Prüfliste mit einem nicht standardmäßigen Stil erstellt wird.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Parameter

*lpMeasureItemStruct*<br/>
Ein langer Zeiger auf eine [measureitemstruct](/windows/win32/api/winuser/ns-winuser-measureitemstruct) -Struktur.

### <a name="remarks"></a>Hinweise

Standardmäßig führt diese Member-Funktion keine Aktion aus. Überschreiben Sie diese Member-Funktion, `MEASUREITEMSTRUCT` und füllen Sie die-Struktur aus, um Fenster über die Dimensionen von CheckBox-Elementen zu informieren. Wenn das Prüfliste mit dem Format [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) erstellt wird, ruft das Framework diese Member-Funktion für jedes Element im Listenfeld auf. Andernfalls wird dieser Member nur einmal aufgerufen.

##  <a name="ongetcheckposition"></a>CCheckListBox:: ongetcheckposition

Das Framework ruft diese Funktion auf, um die Position und Größe des Kontrollkästchens in einem Element zu erhalten.

```
virtual CRect OnGetCheckPosition(
    CRect rectItem,
    CRect rectCheckBox);
```

### <a name="parameters"></a>Parameter

*rectItem*<br/>
Die Position und Größe des Listen Elements.

*rectCheckBox*<br/>
Die Standardposition und-Größe des Kontrollkästchens eines Elements.

### <a name="return-value"></a>Rückgabewert

Die Position und Größe des Kontrollkästchens eines Elements.

### <a name="remarks"></a>Hinweise

Die Standard Implementierung gibt nur die Standardposition und-Größe des Kontrollkästchens (`rectCheckBox`) zurück. Standardmäßig wird ein Kontrollkästchen in der oberen linken Ecke eines Elements ausgerichtet und ist die Standardgröße des Kontrollkästchens. Es gibt möglicherweise Fälle, in denen Sie die Kontrollkästchen auf der rechten Seite oder eine größere oder kleinere Kontrollkästchen wünschen. Überschreiben `OnGetCheckPosition` Sie in diesen Fällen, um die Position und Größe des Kontrollkästchens innerhalb des Elements zu ändern.

##  <a name="setcheck"></a>CCheckListBox:: setcheck

Legt den Zustand des angegebenen Kontrollkästchens fest.

```
void SetCheck(
    int nIndex,
    int nCheck);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der null basierte Index eines Kontrollkästchens, das im Listenfeld enthalten ist.

*nCheck*<br/>
Der Schaltflächen Zustand für das angegebene Kontrollkästchen. Mögliche Werte finden Sie im Abschnitt "Hinweise".

### <a name="remarks"></a>Hinweise

In der folgenden Tabelle sind die möglichen Werte für den *ncheck* -Parameter aufgeführt.

|Wert|Beschreibung|
|-----------|-----------------|
|BST_CHECKED|Aktivieren Sie das angegebene Kontrollkästchen.|
|BST_UNCHECKED|Deaktivieren Sie das angegebene Kontrollkästchen.|
|BST_INDETERMINATE|Legen Sie den Zustand des angegebenen Kontrollkästchens auf unbestimmt fest.<br /><br /> Dieser Status ist nur verfügbar, wenn das Kontrollkästchen Format BS_AUTO3STATE oder BS_3STATE lautet. Weitere Informationen finden Sie unter [Schaltflächen Stile](../../mfc/reference/styles-used-by-mfc.md#button-styles).|

##  <a name="setcheckstyle"></a>CCheckListBox:: setcheckstyle

Mit dieser Funktion können Sie den Stil der Kontrollkästchen im Prüfliste festlegen.

```
void SetCheckStyle(UINT nStyle);
```

### <a name="parameters"></a>Parameter

*nStyle*<br/>
Bestimmt die Art der Kontrollkästchen im Prüfliste.

### <a name="remarks"></a>Hinweise

Gültige Stile:

- BS_CHECKBOX

- BS_AUTOCHECKBOX

- BS_AUTO3STATE

- BS_3STATE

Weitere Informationen zu diesen Stilen finden Sie unter [Schalt](../../mfc/reference/styles-used-by-mfc.md#button-styles)Flächen Formate.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel TSTCON](../../overview/visual-cpp-samples.md)<br/>
[CListBox-Klasse](../../mfc/reference/clistbox-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CListBox-Klasse](../../mfc/reference/clistbox-class.md)
