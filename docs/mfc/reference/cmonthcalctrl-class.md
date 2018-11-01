---
title: CMonthCalCtrl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl::CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl::Create
- AFXDTCTL/CMonthCalCtrl::GetCalendarBorder
- AFXDTCTL/CMonthCalCtrl::GetCalendarCount
- AFXDTCTL/CMonthCalCtrl::GetCalendarGridInfo
- AFXDTCTL/CMonthCalCtrl::GetCalID
- AFXDTCTL/CMonthCalCtrl::GetColor
- AFXDTCTL/CMonthCalCtrl::GetCurrentView
- AFXDTCTL/CMonthCalCtrl::GetCurSel
- AFXDTCTL/CMonthCalCtrl::GetFirstDayOfWeek
- AFXDTCTL/CMonthCalCtrl::GetMaxSelCount
- AFXDTCTL/CMonthCalCtrl::GetMaxTodayWidth
- AFXDTCTL/CMonthCalCtrl::GetMinReqRect
- AFXDTCTL/CMonthCalCtrl::GetMonthDelta
- AFXDTCTL/CMonthCalCtrl::GetMonthRange
- AFXDTCTL/CMonthCalCtrl::GetRange
- AFXDTCTL/CMonthCalCtrl::GetSelRange
- AFXDTCTL/CMonthCalCtrl::GetToday
- AFXDTCTL/CMonthCalCtrl::HitTest
- AFXDTCTL/CMonthCalCtrl::IsCenturyView
- AFXDTCTL/CMonthCalCtrl::IsDecadeView
- AFXDTCTL/CMonthCalCtrl::IsMonthView
- AFXDTCTL/CMonthCalCtrl::IsYearView
- AFXDTCTL/CMonthCalCtrl::SetCalendarBorder
- AFXDTCTL/CMonthCalCtrl::SetCalendarBorderDefault
- AFXDTCTL/CMonthCalCtrl::SetCalID
- AFXDTCTL/CMonthCalCtrl::SetCenturyView
- AFXDTCTL/CMonthCalCtrl::SetColor
- AFXDTCTL/CMonthCalCtrl::SetCurrentView
- AFXDTCTL/CMonthCalCtrl::SetCurSel
- AFXDTCTL/CMonthCalCtrl::SetDayState
- AFXDTCTL/CMonthCalCtrl::SetDecadeView
- AFXDTCTL/CMonthCalCtrl::SetFirstDayOfWeek
- AFXDTCTL/CMonthCalCtrl::SetMaxSelCount
- AFXDTCTL/CMonthCalCtrl::SetMonthDelta
- AFXDTCTL/CMonthCalCtrl::SetMonthView
- AFXDTCTL/CMonthCalCtrl::SetRange
- AFXDTCTL/CMonthCalCtrl::SetSelRange
- AFXDTCTL/CMonthCalCtrl::SetToday
- AFXDTCTL/CMonthCalCtrl::SetYearView
- AFXDTCTL/CMonthCalCtrl::SizeMinReq
- AFXDTCTL/CMonthCalCtrl::SizeRectToMin
helpviewer_keywords:
- CMonthCalCtrl [MFC], CMonthCalCtrl
- CMonthCalCtrl [MFC], Create
- CMonthCalCtrl [MFC], GetCalendarBorder
- CMonthCalCtrl [MFC], GetCalendarCount
- CMonthCalCtrl [MFC], GetCalendarGridInfo
- CMonthCalCtrl [MFC], GetCalID
- CMonthCalCtrl [MFC], GetColor
- CMonthCalCtrl [MFC], GetCurrentView
- CMonthCalCtrl [MFC], GetCurSel
- CMonthCalCtrl [MFC], GetFirstDayOfWeek
- CMonthCalCtrl [MFC], GetMaxSelCount
- CMonthCalCtrl [MFC], GetMaxTodayWidth
- CMonthCalCtrl [MFC], GetMinReqRect
- CMonthCalCtrl [MFC], GetMonthDelta
- CMonthCalCtrl [MFC], GetMonthRange
- CMonthCalCtrl [MFC], GetRange
- CMonthCalCtrl [MFC], GetSelRange
- CMonthCalCtrl [MFC], GetToday
- CMonthCalCtrl [MFC], HitTest
- CMonthCalCtrl [MFC], IsCenturyView
- CMonthCalCtrl [MFC], IsDecadeView
- CMonthCalCtrl [MFC], IsMonthView
- CMonthCalCtrl [MFC], IsYearView
- CMonthCalCtrl [MFC], SetCalendarBorder
- CMonthCalCtrl [MFC], SetCalendarBorderDefault
- CMonthCalCtrl [MFC], SetCalID
- CMonthCalCtrl [MFC], SetCenturyView
- CMonthCalCtrl [MFC], SetColor
- CMonthCalCtrl [MFC], SetCurrentView
- CMonthCalCtrl [MFC], SetCurSel
- CMonthCalCtrl [MFC], SetDayState
- CMonthCalCtrl [MFC], SetDecadeView
- CMonthCalCtrl [MFC], SetFirstDayOfWeek
- CMonthCalCtrl [MFC], SetMaxSelCount
- CMonthCalCtrl [MFC], SetMonthDelta
- CMonthCalCtrl [MFC], SetMonthView
- CMonthCalCtrl [MFC], SetRange
- CMonthCalCtrl [MFC], SetSelRange
- CMonthCalCtrl [MFC], SetToday
- CMonthCalCtrl [MFC], SetYearView
- CMonthCalCtrl [MFC], SizeMinReq
- CMonthCalCtrl [MFC], SizeRectToMin
ms.assetid: a42f6bd6-ab5c-4335-82f8-839982fc64a2
ms.openlocfilehash: 26a0feadfd6603f74ce222e4850f0da9cf71e7d1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509588"
---
# <a name="cmonthcalctrl-class"></a>CMonthCalCtrl-Klasse

Kapselt die Funktionalität eines Monatskalender-Steuerelements.

## <a name="syntax"></a>Syntax

```
class CMonthCalCtrl : public CWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMonthCalCtrl::CMonthCalCtrl](#cmonthcalctrl)|Erstellt ein `CMonthCalCtrl`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMonthCalCtrl::Create](#create)|Erstellt ein Monatskalender-Steuerelement, und fügt es der `CMonthCalCtrl` Objekt.|
|[CMonthCalCtrl::GetCalendarBorder](#getcalendarborder)|Ruft die Breite des Rahmens des aktuellen Monatskalender-Steuerelements ab.|
|[CMonthCalCtrl::GetCalendarCount](#getcalendarcount)|Ruft die Anzahl der in der aktuellen Monatskalender-Steuerelement angezeigten Kalender ab.|
|[CMonthCalCtrl::GetCalendarGridInfo](#getcalendargridinfo)|Ruft Informationen zu den aktuellen Monatskalender-Steuerelement ab.|
|[CMonthCalCtrl::GetCalID](#getcalid)|Ruft das Kalender-ID für die aktuelle Monatskalender-Steuerelement ab.|
|[CMonthCalCtrl::GetColor](#getcolor)|Ruft die Farbe von einem angegebenen Bereich von einem Monatskalender-Steuerelement.|
|[CMonthCalCtrl::GetCurrentView](#getcurrentview)|Ruft ab, die an, die derzeit von der aktuellen Monatskalender-Steuerelement angezeigt wird.|
|[CMonthCalCtrl::GetCurSel](#getcursel)|Ruft die Systemzeit ab, wie durch das derzeit ausgewählte Datum angezeigt.|
|[CMonthCalCtrl::GetFirstDayOfWeek](#getfirstdayofweek)|Ruft den ersten Tag der Woche, die in der am weitesten links stehende Spalte des Kalenders angezeigt werden.|
|[CMonthCalCtrl::GetMaxSelCount](#getmaxselcount)|Ruft die aktuelle maximale Anzahl von Tagen, die in einem Monatskalender-Steuerelement ausgewählt werden können.|
|[CMonthCalCtrl::GetMaxTodayWidth](#getmaxtodaywidth)|Ruft die maximale Breite der Zeichenfolge "Today" für die aktuelle Monatskalender-Steuerelement ab.|
|[CMonthCalCtrl::GetMinReqRect](#getminreqrect)|Ruft die minimale Größe erforderlich, um ein vollständiger Monat in einem Monatskalender-Steuerelement ab.|
|[CMonthCalCtrl::GetMonthDelta](#getmonthdelta)|Ruft die Bildlaufrate für ein Monatskalender-Steuerelement ab.|
|[CMonthCalCtrl::GetMonthRange](#getmonthrange)|Ruft das Datum, Informationen, die die oberen und unteren Grenzwerte der Anzeige für ein Monatskalender-Steuerelement des darstellt.|
|[CMonthCalCtrl::GetRange](#getrange)|Ruft die aktuellen minimalen und maximalen Datumsangaben legen Sie in einem Monatskalender-Steuerelement ab.|
|[CMonthCalCtrl::GetSelRange](#getselrange)|Ruft die aktuelle Informationen, die die obere und untere Grenzwerte zurzeit vom Benutzer ausgewählten Datumsbereich darstellt.|
|[CMonthCalCtrl::GetToday](#gettoday)|Ruft ab, die Datumsinformationen für das Datum, die als "heute" für ein Monatskalender-Steuerelement angegeben.|
|[CMonthCalCtrl::HitTest](#hittest)|Bestimmt, welcher Abschnitt der einem Monatskalender-Steuerelement zu einem bestimmten Zeitpunkt auf dem Bildschirm.|
|[CMonthCalCtrl::IsCenturyView](#iscenturyview)|Gibt an, ob die aktuelle Ansicht des die aktuelle Monatskalender-Steuerelement die Jahrhundert Ansicht.|
|[CMonthCalCtrl::IsDecadeView](#isdecadeview)|Gibt an, ob die aktuelle Ansicht des aktuellen Monats Kalender-Steuerelements zehn Jahren ist.|
|[CMonthCalCtrl::IsMonthView](#ismonthview)|Gibt an, ob die aktuelle Ansicht des die aktuelle Monatskalender-Steuerelement im Monat angezeigt wird.|
|[CMonthCalCtrl::IsYearView](#isyearview)|Gibt an, ob die aktuelle Ansicht des aktuellen Monats Kalender-Steuerelements Jahr ist.|
|[CMonthCalCtrl::SetCalendarBorder](#setcalendarborder)|Legt die Breite des Rahmens des aktuellen Monatskalender-Steuerelements fest.|
|[CMonthCalCtrl::SetCalendarBorderDefault](#setcalendarborderdefault)|Legt die Standardbreite des Rahmens des aktuellen Monatskalender-Steuerelements fest.|
|[CMonthCalCtrl::SetCalID](#setcalid)|Legt fest, die Kalender-ID für die aktuelle Monatskalender-Steuerelement.|
|[CMonthCalCtrl::SetCenturyView](#setcenturyview)|Legt den aktuellen Monatskalender-Steuerelement zum Anzeigen der Ansicht Jahrhundert fest.|
|[CMonthCalCtrl::SetColor](#setcolor)|Legt die Farbe der einem angegebenen Bereich von einem Monatskalender-Steuerelement fest.|
|[CMonthCalCtrl::SetCurrentView](#setcurrentview)|Legt den aktuellen Monatskalender-Steuerelement zum Anzeigen der angegebenen Ansicht fest.|
|[CMonthCalCtrl::SetCurSel](#setcursel)|Legt fest, das derzeit ausgewählte Datum für ein Monatskalender-Steuerelement.|
|[CMonthCalCtrl:: SetDayState](#setdaystate)|Legt die Anzeige die Tage in einem Monatskalender-Steuerelement fest.|
|[CMonthCalCtrl::SetDecadeView](#setdecadeview)|Legt den aktuellen Monatskalender-Steuerelement für die zehn Jahren-Ansicht.|
|[CMonthCalCtrl::SetFirstDayOfWeek](#setfirstdayofweek)|Legt fest, den Tag der Woche, die in der am weitesten links stehende Spalte des Kalenders angezeigt werden.|
|[CMonthCalCtrl::SetMaxSelCount](#setmaxselcount)|Legt die maximale Anzahl von Tagen an, die in einem Monatskalender-Steuerelement ausgewählt werden können.|
|[CMonthCalCtrl::SetMonthDelta](#setmonthdelta)|Legt die Bildlaufrate für ein Monatskalender-Steuerelement fest.|
|[CMonthCalCtrl::SetMonthView](#setmonthview)|Legt den aktuellen Monatskalender-Steuerelement zum Anzeigen der Monatsansicht fest.|
|[CMonthCalCtrl::SetRange](#setrange)|Legt fest, die minimale und maximale zulässige Datum für ein Monatskalender-Steuerelement.|
|[CMonthCalCtrl::SetSelRange](#setselrange)|Legt die Auswahl für ein Monatskalender-Steuerelement auf einem bestimmten Zeitraum.|
|[CMonthCalCtrl::SetToday](#settoday)|Legt das Kalender-Steuerelement für den aktuellen Tag fest.|
|[CMonthCalCtrl::SetYearView](#setyearview)|Legt den aktuellen Monatskalender-Steuerelement auf Jahr anzeigen.|
|[CMonthCalCtrl::SizeMinReq](#sizeminreq)|Zeichnet die Monatskalender-Steuerelement auf die minimale und ein-Monats-Größe.|
|[CMonthCalCtrl::SizeRectToMin](#sizerecttomin)|Für die aktuelle Monatskalender-Steuerelement berechnet das kleinste Rechteck befindet, das allen Kalendern enthalten kann, die in einem angegebenen Rechteck zu passen.|

## <a name="remarks"></a>Hinweise

Im Monatskalender-Steuerelement bietet dem Benutzer eine einfache Kalender-Schnittstelle, von der der Benutzer ein Datum auswählen kann. Der Benutzer kann die Anzeige von ändern:

- Bildlauf rückwärts und Vorwärts, von Monat zu Monat an.

- Klicken Sie auf den Text der heute, um den aktuellen Tag anzeigen (falls es sich um eine styl MCS_NOTODAY nicht verwendet wird).

- Wählen einen Monat oder ein Jahr im Dropdown-Menü.

Sie können anpassen, den Monat Monatskalender-Steuerelements durch eine Vielzahl von Formaten auf das Objekt anwenden, bei der Erstellung. Diese Formate werden in beschrieben [Month Calendar-Steuerelement-Stile](/windows/desktop/Controls/month-calendar-control-styles) im Windows SDK.

Im Monatskalender-Steuerelement kann mehr als einen Monat, und es kann spezielle Tagen (z. B. an Feiertagen) angeben, indem in Fettdruck zu setzen das Datum.

Weitere Informationen zur Verwendung der im Monatskalender-Steuerelements finden Sie unter [Verwenden von CMonthCalCtrl](../../mfc/using-cmonthcalctrl.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CMonthCalCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxdtctl.h

##  <a name="cmonthcalctrl"></a>  CMonthCalCtrl::CMonthCalCtrl

Erstellt ein `CMonthCalCtrl`-Objekt.

```
CMonthCalCtrl();
```

### <a name="remarks"></a>Hinweise

Rufen Sie `Create` nach dem Erstellen des Objekts.

##  <a name="create"></a>  CMonthCalCtrl::Create

Erstellt ein Monatskalender-Steuerelement, und fügt es der `CMonthCalCtrl` Objekt.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);

virtual BOOL Create(
    DWORD dwStyle,
    const POINT& pt,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Gibt die Kombination von Windows-Formatvorlagen auf den Monatskalender-Steuerelement angewendet. Finden Sie unter [Month Calendar-Steuerelement-Stile](/windows/desktop/Controls/month-calendar-control-styles) im Windows SDK für Weitere Informationen zu den Stilen.

*Rect*<br/>
Ein Verweis auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur. Enthält die Position und Größe der im Monatskalender-Steuerelement.

*pt*<br/>
Ein Verweis auf eine [Punkt](https://msdn.microsoft.com/library/windows/desktop/dd162805) Struktur, die den Speicherort der im Monatskalender-Steuerelement bezeichnet.

*pParentWnd*<br/>
Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster der im Monatskalender-Steuerelement ist. Es darf nicht NULL sein.

*nID*<br/>
Gibt an, im Monatskalender-Steuerelement des Steuerelement-ID.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Initialisierung erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Erstellen Sie einen Monat Monatskalender-Steuerelement in zwei Schritten:

1. Rufen Sie [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) zum Erstellen einer `CMonthCalCtrl` Objekt.

1. Rufen Sie diese Memberfunktion, die einem Monatskalender-Steuerelement erstellt, und fügt es der `CMonthCalCtrl` Objekt.

Beim Aufruf `Create`, die allgemeinen Steuerelemente werden initialisiert. Die Version des `Create` Sie Aufruf bestimmt, wie sie die Größe festgelegt ist:

- Um automatisch die Größe des Steuerelements einen Monat MFC die Überschreibung, die verwendet die *pt* Parameter.

- Um die Größe des Steuerelements selbst, die Überschreibung dieser Funktion, verwendet der *Rect* Parameter.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CMonthCalCtrl#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_1.cpp)]

##  <a name="getcalendarborder"></a>  CMonthCalCtrl::GetCalendarBorder

Ruft die Breite des Rahmens des aktuellen Monatskalender-Steuerelements ab.

```
int GetCalendarBorder() const;
```

### <a name="return-value"></a>Rückgabewert

Die Breite des den Rahmen des Steuerelements in Pixel.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [MCM_GETCALENDARBORDER](/windows/desktop/Controls/mcm-getcalendarborder) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="getcalendarcount"></a>  CMonthCalCtrl::GetCalendarCount

Ruft die Anzahl der in der aktuellen Monatskalender-Steuerelement angezeigten Kalender ab.

```
int GetCalendarCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Kalender, die derzeit in der im Monatskalender-Steuerelement angezeigt werden soll. Die maximale zulässige Anzahl der Kalender ist 12.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [MCM_GETCALENDARCOUNT](/windows/desktop/Controls/mcm-getcalendarcount) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="getcalendargridinfo"></a>  CMonthCalCtrl::GetCalendarGridInfo

Ruft Informationen zu den aktuellen Monatskalender-Steuerelement ab.

```
BOOL GetCalendarGridInfo(PMCGRIDINFO pmcGridInfo) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*pmcGridInfo*|[out] Zeiger auf eine [MCGRIDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagmcgridinfo) -Struktur, die Informationen über die aktuellen Monatskalender-Steuerelement empfängt. Der Aufrufer ist verantwortlich für das zuordnen und diese Struktur zu initialisieren.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [MCM_GETCALENDARGRIDINFO](/windows/desktop/Controls/mcm-getcalendargridinfo) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_monthCalCtrl`, d. h. mit der im Monatskalender-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die `GetCalendarGridInfo` Methode, um das Kalenderdatum abzurufen, die im aktuellen Monatskalender-Steuerelement anzeigt.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_3.cpp)]

##  <a name="getcalid"></a>  CMonthCalCtrl::GetCalID

Ruft das Kalender-ID für die aktuelle Monatskalender-Steuerelement ab.

```
CALID GetCalID() const;
```

### <a name="return-value"></a>Rückgabewert

Eines der [Kalender-ID](/windows/desktop/Intl/calendar-identifiers) Konstanten.

### <a name="remarks"></a>Hinweise

Ein Kalender-Bezeichner kennzeichnet regionsspezifische Kalender, z. B. den gregorianischen (lokalisierte), Japanisch oder Hijri Kalender. Die Anwendung kann eine Kalender-ID verwenden, die verschiedenen Sprach-Funktionen zu unterstützen.

Diese Methode sendet die [MCM_GETCALID](/windows/desktop/Controls/mcm-getcalid) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="getcolor"></a>  CMonthCalCtrl::GetColor

Ruft die Farbe eines Bereichs des Monats Monatskalender-Steuerelements, die anhand des *nRegion*.

```
COLORREF GetColor(int nRegion) const;
```

### <a name="parameters"></a>Parameter

*nRegion*<br/>
Der Bereich des im Monatskalender-Steuerelement aus dem die Farbe abgerufen werden. Eine Liste von Werten, finden Sie unter den *nRegion* Parameter [SetColor](#setcolor).

### <a name="return-value"></a>Rückgabewert

Ein [COLORREF](/windows/desktop/gdi/colorref) Wert, der den Teil des Monatskalender-Steuerelements, zugeordnete bei erfolgreicher Ausführung angibt. Diese Memberfunktion gibt, andernfalls-1 zurück.

##  <a name="getcurrentview"></a>  CMonthCalCtrl::GetCurrentView

Ruft ab, die an, die derzeit von der aktuellen Monatskalender-Steuerelement angezeigt wird.

```
DWORD GetCurrentView() const;
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle Ansicht, die von einem der folgenden Werte angegeben wird:

|Wert|Bedeutung|
|-----------|-------------|
|MCMV_MONTH|Monatliche Ansicht|
|MCMV_YEAR|Jährliche anzeigen|
|MCMV_DECADE|Zehn Jahre anzeigen|
|MCMV_CENTURY|Jahrhundert anzeigen|

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [MCM_GETCURRENTVIEW](/windows/desktop/Controls/mcm-getcurrentview) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_monthCalCtrl`, d. h. mit der im Monatskalender-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Beispiel

Die folgenden Code-Beispiel-Berichte anzeigen Monatskalender-Steuerelement derzeit zeigt.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_4.cpp)]

##  <a name="getcursel"></a>  CMonthCalCtrl::GetCurSel

Ruft die Systemzeit ab, wie durch das derzeit ausgewählte Datum angezeigt.

```
BOOL GetCurSel(COleDateTime& refDateTime) const;  BOOL GetCurSel(CTime& refDateTime) const;

BOOL GetCurSel(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>Parameter

*refDateTime*<br/>
Ein Verweis auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt oder ein [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt. Empfängt die aktuelle Uhrzeit an.

*pDateTime*<br/>
Ein Zeiger auf eine [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) -Struktur, die die derzeit ausgewählte Datumsinformationen erhält. Dieser Parameter muss eine gültige Adresse sein und darf nicht NULL sein.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL Wenn erfolgreich; Otherwize 0.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_GETCURSEL](/windows/desktop/Controls/mcm-getcursel), wie im Windows SDK beschrieben.

> [!NOTE]
>  Diese Memberfunktion schlägt fehl, wenn das Format MCS_MULTISELECT festgelegt ist.

In MFC Implementierung von `GetCurSel`, können Sie angeben, ein `COleDateTime` Nutzung, ein `CTime` Nutzung oder ein `SYSTEMTIME` Nutzung zu strukturieren.

##  <a name="getfirstdayofweek"></a>  CMonthCalCtrl::GetFirstDayOfWeek

Ruft den ersten Tag der Woche, die in der am weitesten links stehende Spalte des Kalenders angezeigt werden.

```
int GetFirstDayOfWeek(BOOL* pbLocal = NULL) const;
```

### <a name="parameters"></a>Parameter

*pbLocal*<br/>
Ein Zeiger auf einen Booleschen Wert. Wenn der Wert ungleich NULL ist, entspricht die Einstellung der Steuerelements nicht die Einstellung in der Systemsteuerung.

### <a name="return-value"></a>Rückgabewert

Ein ganzzahliger Wert, der den ersten Tag der Woche darstellt. Finden Sie unter **"Hinweise"** für Weitere Informationen zu was diese ganzen Zahlen darstellen.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_GETFIRSTDAYOFWEEK](/windows/desktop/Controls/mcm-getfirstdayofweek), wie im Windows SDK beschrieben. Die Wochentage werden als ganze Zahlen, wie folgt dargestellt.

|Wert|Tag der Woche|
|-----------|---------------------|
|0|Montag|
|1|Dienstag|
|2|Mittwoch|
|3|Donnerstag|
|4|Freitag|
|5|Samstag|
|6|Sonntag|

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMonthCalCtrl::SetFirstDayOfWeek](#setfirstdayofweek).

##  <a name="getmaxselcount"></a>  CMonthCalCtrl::GetMaxSelCount

Ruft die aktuelle maximale Anzahl von Tagen, die in einem Monatskalender-Steuerelement ausgewählt werden können.

```
int GetMaxSelCount() const;
```

### <a name="return-value"></a>Rückgabewert

Ein ganzzahliger Wert, der die Gesamtzahl der Tage, die ausgewählt werden, können für das Steuerelement darstellt.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_GETMAXSELCOUNT](/windows/desktop/Controls/mcm-getmaxselcount), wie im Windows SDK beschrieben. Verwenden Sie diese Memberfunktion auf, für die Steuerelemente mit festgelegtem Format MCS_MULTISELECT.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMonthCalCtrl::SetMaxSelCount](#setmaxselcount).

##  <a name="getmaxtodaywidth"></a>  CMonthCalCtrl::GetMaxTodayWidth

Ruft die maximale Breite der Zeichenfolge "Today" für die aktuelle Monatskalender-Steuerelement ab.

```
DWORD GetMaxTodayWidth() const;
```

### <a name="return-value"></a>Rückgabewert

Die Breite der Zeichenfolge "Today", in Pixel.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_monthCalCtrl`, d. h. mit der im Monatskalender-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird veranschaulicht, die `GetMaxTodayWidth` Methode.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_5.cpp)]

### <a name="remarks"></a>Hinweise

Der Benutzer kann auf das aktuelle Datum zurückgeben, indem Sie auf die Zeichenfolge "Today", die am unteren Rand des Monatskalender-Steuerelements angezeigt wird. Die Zeichenfolge "Today" enthält Bezeichnungstext sowie den Date-Text.

Diese Methode sendet die [MCM_GETMAXTODAYWIDTH](/windows/desktop/Controls/mcm-getmaxtodaywidth) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="getminreqrect"></a>  CMonthCalCtrl::GetMinReqRect

Ruft die minimale Größe erforderlich, um ein vollständiger Monat in einem Monatskalender-Steuerelement ab.

```
BOOL GetMinReqRect(RECT* pRect) const;
```

### <a name="parameters"></a>Parameter

*pRect*<br/>
Ein Zeiger auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die umgebenden Rechteck-Informationen erhält. Dieser Parameter muss eine gültige Adresse sein und darf nicht NULL sein.

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, diese Memberfunktion ungleich NULL zurückgibt und `lpRect` empfängt die entsprechende umgebende Informationen. Die Memberfunktion gibt 0 zurück, wenn nicht erfolgreich.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_GETMINREQRECT](/windows/desktop/Controls/mcm-getminreqrect), wie im Windows SDK beschrieben.

##  <a name="getmonthdelta"></a>  CMonthCalCtrl::GetMonthDelta

Ruft die Bildlaufrate für ein Monatskalender-Steuerelement ab.

```
int GetMonthDelta() const;
```

### <a name="return-value"></a>Rückgabewert

Die Bildlaufrate für den Monatskalender-Steuerelement. Die Bildlaufrate ist die Anzahl der Monate, dass das Steuerelement die Anzeige klickt der Benutzer eine Bildlaufschaltfläche einmal verschoben wird.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_GETMONTHDELTA](/windows/desktop/Controls/mcm-getmonthdelta), wie im Windows SDK beschrieben.

##  <a name="getmonthrange"></a>  CMonthCalCtrl::GetMonthRange

Ruft das Datum, Informationen, die die oberen und unteren Grenzwerte der Anzeige für ein Monatskalender-Steuerelement des darstellt.

```
int GetMonthRange(
    COleDateTime& refMinRange,
    COleDateTime& refMaxRange,
    DWORD dwFlags) const;

int GetMonthRange(
    CTime& refMinRange,
    CTime& refMaxRange,
    DWORD dwFlags) const;

int GetMonthRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange,
    DWORD dwFlags) const;
```

### <a name="parameters"></a>Parameter

*refMinRange*<br/>
Ein Verweis auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) oder [CTime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, enthält das kleinstmögliche Datum zulässig.

*refMaxRange*<br/>
Ein Verweis auf eine `COleDateTime` oder `CTime` -Objekt, das das maximal zulässige Datum enthält.

*pMinRange*<br/>
Ein Zeiger auf eine [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, die das Datum am niedrigsten Ende des Bereichs enthält.

*pMaxRange*<br/>
Ein Zeiger auf eine `SYSTEMTIME` Struktur, die das Datum am höchsten Ende des Bereichs enthält.

*dwFlags*<br/>
Wert, die Angabe des Bereichs der die Bereichsgrenzen abgerufen werden sollen. Dieser Wert muss eine der folgenden sein.

|Wert|Bedeutung|
|-----------|-------------|
|GMR_DAYSTATE|Einschließen von vorangestellten und nachfolgenden Monate des sichtbaren Bereichs, die nur teilweise angezeigt werden.|
|GMR_VISIBLE|Sind Sie nur diese Monate an, die vollständig angezeigt werden.|

### <a name="return-value"></a>Rückgabewert

Eine Ganzzahl, Bereich, in Monaten darstellt, über die beiden Grenzwerte erstreckt, erkennbar *RefMinRange* und *RefMaxRange* in den ersten und zweiten Versionen, oder *pMinRange* und *pMaxRange* in der dritten Version.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_GETMONTHRANGE](/windows/desktop/Controls/mcm-getmonthrange), wie im Windows SDK beschrieben. In MFC Implementierung von `GetMonthRange`, können Sie angeben, `COleDateTime` Nutzung ein `CTime` Nutzung oder ein `SYSTEMTIME` Nutzung zu strukturieren.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMonthCalCtrl:: SetDayState](#setdaystate).

##  <a name="getrange"></a>  CMonthCalCtrl::GetRange

Ruft die aktuellen minimalen und maximalen Datumsangaben legen Sie in einem Monatskalender-Steuerelement ab.

```
DWORD GetRange(
    COleDateTime* pMinRange,
    COleDateTime* pMaxRange) const;

DWORD GetRange(
    CTime* pMinRange,
    CTime* pMaxRange) const;

DWORD GetRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange) const;
```

### <a name="parameters"></a>Parameter

*pMinRange*<br/>
Ein Zeiger auf eine `COleDateTime` Objekt eine `CTime` Objekt oder [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, die das Datum am niedrigsten Ende des Bereichs enthält.

*pMaxRange*<br/>
Ein Zeiger auf eine `COleDateTime` Objekt eine `CTime` Objekt oder [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, die das Datum am höchsten Ende des Bereichs enthält.

### <a name="return-value"></a>Rückgabewert

Einen DWORD-Wert, der 0 (null) sein kann (es werden keine Beschränkungen festgelegt) oder eine Kombination der folgenden Werte, die Grenze angeben.

|Wert|Bedeutung|
|-----------|-------------|
|GDTR_MAX|Eine Obergrenze ist für das Steuerelement festlegen; *pMaxRange* gültig ist und die entsprechenden Datumsinformationen enthält.|
|GDTR_MIN|Es wird eine Mindestanzahl für das Steuerelement festlegen; *pMinRange* gültig ist und die entsprechenden Datumsinformationen enthält.|

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_GETRANGE](/windows/desktop/Controls/mcm-getrange), wie im Windows SDK beschrieben. In MFC Implementierung von `GetRange`, können Sie angeben, ein `COleDateTime` Nutzung, ein `CTime` Nutzung oder ein `SYSTEMTIME` Nutzung zu strukturieren.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CMonthCalCtrl#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_6.cpp)]

##  <a name="getselrange"></a>  CMonthCalCtrl::GetSelRange

Ruft die aktuelle Informationen, die die obere und untere Grenzwerte zurzeit vom Benutzer ausgewählten Datumsbereich darstellt.

```
BOOL GetSelRange(
    COleDateTime& refMinRange,
    COleDateTime& refMaxRange) const;

BOOL GetSelRange(
    CTime& refMinRange,
    CTime& refMaxRange) const;

BOOL GetSelRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange) const;
```

### <a name="parameters"></a>Parameter

*refMinRange*<br/>
Ein Verweis auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) oder [CTime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, enthält das kleinstmögliche Datum zulässig.

*refMaxRange*<br/>
Ein Verweis auf eine `COleDateTime` oder `CTime` -Objekt, das das maximal zulässige Datum enthält.

*pMinRange*<br/>
Ein Zeiger auf eine [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, die das Datum am niedrigsten Ende des Bereichs enthält.

*pMaxRange*<br/>
Ein Zeiger auf eine `SYSTEMTIME` Struktur, die das Datum am höchsten Ende des Bereichs enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_GETSELRANGE](/windows/desktop/Controls/mcm-getselrange), wie im Windows SDK beschrieben. `GetSelRange` schlägt fehl, wenn auf einem Monatskalender-Steuerelement angewendet, die nicht den MCS_MULTISELECT-Stil verwendet wird.

In MFC Implementierung von `GetSelRange`, können Sie angeben, `COleDateTime` Nutzung ein `CTime` Nutzung oder ein `SYSTEMTIME` Nutzung zu strukturieren.

##  <a name="gettoday"></a>  CMonthCalCtrl::GetToday

Ruft ab, die Datumsinformationen für das Datum, die als "heute" für ein Monatskalender-Steuerelement angegeben.

```
BOOL GetToday(COleDateTime& refDateTime) const;  BOOL GetToday(COleDateTime& refDateTime) const;

BOOL GetToday(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>Parameter

*refDateTime*<br/>
Ein Verweis auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) oder [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt, das den aktuellen Tag angibt.

*pDateTime*<br/>
Ein Zeiger auf eine [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) -Struktur, die die Datumsinformationen erhält. Dieser Parameter muss eine gültige Adresse sein und darf nicht NULL sein.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_GETTODAY](/windows/desktop/Controls/mcm-gettoday), wie im Windows SDK beschrieben. In MFC Implementierung von `GetToday`, können Sie angeben, ein `COleDateTime` Nutzung, ein `CTime` Nutzung oder ein `SYSTEMTIME` Nutzung zu strukturieren.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CMonthCalCtrl#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_7.cpp)]

##  <a name="hittest"></a>  CMonthCalCtrl::HitTest

Bestimmt, welche Monatskalender-Steuerelement, ob vorhanden, an der angegebenen Position.

```
DWORD HitTest(PMCHITTESTINFO pMCHitTest);
```

### <a name="parameters"></a>Parameter

*pMCHitTest*<br/>
Ein Zeiger auf eine [MCHITTESTINFO](/windows/desktop/api/commctrl/ns-commctrl-mchittestinfo) Struktur mit Treffertests für die Monatskalender-Steuerelement verweist.

### <a name="return-value"></a>Rückgabewert

Ein DWORD-Wert. Entspricht der **uHit** Mitglied der `MCHITTESTINFO` Struktur.

### <a name="remarks"></a>Hinweise

`HitTest` verwendet die `MCHITTESTINFO` -Struktur, die Informationen zu den Treffertest enthält.

##  <a name="iscenturyview"></a>  CMonthCalCtrl::IsCenturyView

Gibt an, ob die aktuelle Ansicht des die aktuelle Monatskalender-Steuerelement die Jahrhundert Ansicht.

```
BOOL IsCenturyView() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn die aktuelle Ansicht Jahrhundert ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [MCM_GETCURRENTVIEW](/windows/desktop/Controls/mcm-getcurrentview) -Nachricht, die im Windows SDK beschrieben wird. Wenn diese Nachricht MCMV_CENTURY zurückgibt, gibt diese Methode "true" zurück.

##  <a name="isdecadeview"></a>  CMonthCalCtrl::IsDecadeView

Gibt an, ob die aktuelle Ansicht des aktuellen Monats Kalender-Steuerelements zehn Jahren ist.

```
BOOL IsDecadeView() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn die aktuelle Ansicht die zehn Jahren ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [MCM_GETCURRENTVIEW](/windows/desktop/Controls/mcm-getcurrentview) -Nachricht, die im Windows SDK beschrieben wird. Wenn diese Nachricht MCMV_DECADE zurückgibt, gibt diese Methode "true" zurück.

##  <a name="ismonthview"></a>  CMonthCalCtrl::IsMonthView

Gibt an, ob die aktuelle Ansicht des die aktuelle Monatskalender-Steuerelement im Monat angezeigt wird.

```
BOOL IsMonthView() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn die aktuelle Ansicht im Monat angezeigt. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [MCM_GETCURRENTVIEW](/windows/desktop/Controls/mcm-getcurrentview) -Nachricht, die im Windows SDK beschrieben wird. Wenn diese Nachricht MCMV_MONTH zurückgibt, gibt diese Methode "true" zurück.

##  <a name="isyearview"></a>  CMonthCalCtrl::IsYearView

Gibt an, ob die aktuelle Ansicht des aktuellen Monats Kalender-Steuerelements Jahr ist.

```
BOOL IsYearView() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn die aktuelle Ansicht Jahr ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [MCM_GETCURRENTVIEW](/windows/desktop/Controls/mcm-getcurrentview) -Nachricht, die im Windows SDK beschrieben wird. Wenn diese Nachricht MCMV_YEAR zurückgibt, gibt diese Methode "true" zurück.

##  <a name="setcalendarborder"></a>  CMonthCalCtrl::SetCalendarBorder

Legt die Breite des Rahmens des aktuellen Monatskalender-Steuerelements fest.

```
void SetCalendarBorder(int cxyBorder);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*cxyBorder*|[in] Die Breite des Rahmens, in Pixel.|

### <a name="remarks"></a>Hinweise

Wenn diese Methode erfolgreich ist, wird die Breite des Rahmens legen Sie auf die *CxyBorder* Parameter. Andernfalls wird die Breite des Rahmens auf den Standardwert, der vom aktuellen angegeben wird zurückgesetzt [Design](/windows/desktop/Controls/visual-styles-overview), oder NULL, wenn Designs nicht verwendet werden.

Diese Methode sendet die [MCM_SETCALENDARBORDER](/windows/desktop/Controls/mcm-setcalendarborder) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_monthCalCtrl`, d. h. mit der im Monatskalender-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Beispiel

Das folgenden Codebeispiel wird die Rahmenbreite des Monatskalender auf acht Pixel zu steuern. Verwenden der [CMonthCalCtrl::GetCalendarBorder](#getcalendarborder) Methode, um zu bestimmen, ob diese Methode erfolgreich ausgeführt wurde.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_8.cpp)]

##  <a name="setcalendarborderdefault"></a>  CMonthCalCtrl::SetCalendarBorderDefault

Legt die Standardbreite des Rahmens des aktuellen Monatskalender-Steuerelements fest.

```
void SetCalendarBorderDefault();
```

### <a name="remarks"></a>Hinweise

Die Breite des Rahmens nastaven NA hodnotu angegebene vom aktuellen Standardwert [Design](/windows/desktop/Controls/visual-styles-overview), oder NULL, wenn Designs nicht verwendet werden.

Diese Methode sendet die [MCM_SETCALENDARBORDER](/windows/desktop/Controls/mcm-setcalendarborder) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="setcalid"></a>  CMonthCalCtrl::SetCalID

Legt fest, die Kalender-ID für die aktuelle Monatskalender-Steuerelement.

```
BOOL SetCalID(CALID calid);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*calid*|[in] Eines der [Kalender-ID](/windows/desktop/Intl/calendar-identifiers) Konstanten.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Eine Kalender-ID angibt, regionale Kalender, z. B. den gregorianischen (lokalisierte), Japanisch oder Hijri Kalender. Verwenden der `SetCalID` Methode, um einen Kalender anzeigen, indem angegeben wird, die *Calid* -Parameters, wenn das Gebietsschema, das dem Kalender auf Ihrem Computer installiert ist.

Diese Methode sendet die [MCM_SETCALID](/windows/desktop/Controls/mcm-setcalid) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_monthCalCtrl`, d. h. mit der im Monatskalender-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Beispiel

Das folgende Codebeispiel legt fest, im Monatskalender-Steuerelement den Kalender Japan Zeitraum anzeigen. Die `SetCalID` Methode erfolgreich ist, nur, wenn Sie diesen Kalender auf Ihrem Computer installiert ist.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_9.cpp)]

##  <a name="setcenturyview"></a>  CMonthCalCtrl::SetCenturyView

Legt den aktuellen Monatskalender-Steuerelement zum Anzeigen der Ansicht Jahrhundert fest.

```
BOOL SetCenturyView();
```

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode verwendet die [CMonthCalCtrl::SetCurrentView](#setcurrentview) Methode, um die Ansicht festgelegt wird, um `MCMV_CENTURY`, steht für die Sicht Jahrhundert.

##  <a name="setcolor"></a>  CMonthCalCtrl::SetColor

Legt die Farbe der einem angegebenen Bereich von einem Monatskalender-Steuerelement fest.

```
COLORREF SetColor(
    int nRegion,
    COLORREF ref);
```

### <a name="parameters"></a>Parameter

*nRegion*<br/>
Ein ganzzahliger-Wert, der die Farbe des Monats-Kalender festlegen angibt. Dieser Wert kann eine der folgenden sein.

|Wert|Bedeutung|
|-----------|-------------|
|MCSC_BACKGROUND|Die Hintergrundfarbe, die zwischen den Monaten angezeigt.|
|MCSC_MONTHBK|Die Hintergrundfarbe des Monats angezeigt.|
|MCSC_TEXT|Die Farbe zum Anzeigen von Text in einem Monat.|
|MCSC_TITLEBK|Die Hintergrundfarbe des Kalenders Titel angezeigt wird.|
|MCSC_TITLETEXT|Die Farbe zum Anzeigen von Text innerhalb des Kalenders Titel.|
|MCSC_TRAILINGTEXT|Die Farbe zum Anzeigen von Kopf- und nachfolgende-Tage-Text. Header und die nachfolgenden Tage werden die Tage aus den vorherigen und folgenden Monaten, die auf dem aktuellen Kalender angezeigt werden.|

*ref*<br/>
Eine COLORREF-Wert für die neue Farbe-Einstellung für den angegebenen Teil des Monatskalender-Steuerelements.

### <a name="return-value"></a>Rückgabewert

Eine COLORREF-Wert, die vorherige Farbe-Einstellung für den angegebenen Teil des Monatskalender-Steuerelements, wenn erfolgreich darstellt. Andernfalls gibt diese Nachricht-1 zurück.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_SETCOLOR](/windows/desktop/Controls/mcm-setcolor), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CMonthCalCtrl#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_10.cpp)]

##  <a name="setcurrentview"></a>  CMonthCalCtrl::SetCurrentView

Legt den aktuellen Monatskalender-Steuerelement zum Anzeigen der angegebenen Ansicht fest.

```
BOOL SetCurrentView(DWORD dwNewView);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*dwNewView*|[in] Einer der folgenden Werte, der angibt, ein monatlich, jährlich, zehn oder Jahrhundert anzeigen.<br /><br /> MCMV_MONTH: Monatsansicht der<br /><br /> MCMV_YEAR: Jährliche Ansicht<br /><br /> MCMV_DECADE: Jahrzehnt anzeigen<br /><br /> MCMV_CENTURY: Jahrhundert anzeigen|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [MCM_SETCURRENTVIEW](/windows/desktop/Controls/mcm-setcurrentview) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="setcursel"></a>  CMonthCalCtrl::SetCurSel

Legt fest, das derzeit ausgewählte Datum für ein Monatskalender-Steuerelement.

```
BOOL SetCurSel(const COleDateTime& refDateTime);
BOOL SetCurSel(const CTime& refDateTime);
  BOOL SetCurSel(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>Parameter

*refDateTime*<br/>
Ein Verweis auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) oder [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt, das das aktuell ausgewählte Monatskalender-Steuerelement angibt.

*pDateTime*<br/>
Zeiger auf eine [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) -Struktur, enthält das Datum an, wie die aktuelle Auswahl festgelegt werden.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_SETCURSEL](/windows/desktop/Controls/mcm-setcursel), wie im Windows SDK beschrieben. In MFC Implementierung von `SetCurSel`, können Sie angeben, ein `COleDateTime` Nutzung, ein `CTime` Nutzung oder ein `SYSTEMTIME` Nutzung zu strukturieren.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CMonthCalCtrl#5](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_11.cpp)]

##  <a name="setdaystate"></a>  CMonthCalCtrl:: SetDayState

Legt die Anzeige die Tage in einem Monatskalender-Steuerelement fest.

```
BOOL SetDayState(
    int nMonths,
    LPMONTHDAYSTATE pStates);
```

### <a name="parameters"></a>Parameter

*nMonths*<br/>
Wert, der angibt, wie viele Elemente im Array enthalten sind, die *pStates* verweist auf.

*pStates*<br/>
Ein Zeiger auf eine [MONTHDAYSTATE](/windows/desktop/Controls/monthdaystate) Array von Werten, die definieren, wie im Monatskalender-Steuerelement, jeden Tag in die Anzeige gezeichnet wird. Der Datentyp MONTHDAYSTATE ist ein Bitfeld, wobei jedes Bit (1 bis 31) den Status eines Tages in einem Monat darstellt. Wenn eine Bit aktiviert ist, wird der entsprechenden Tag angezeigt werden fett; Andernfalls wird es mit keine Hervorhebung angezeigt.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_SETDAYSTATE](/windows/desktop/Controls/mcm-setdaystate), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CMonthCalCtrl#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_12.cpp)]

##  <a name="setdecadeview"></a>  CMonthCalCtrl::SetDecadeView

Legt den aktuellen Monatskalender-Steuerelement für die zehn Jahren-Ansicht.

```
BOOL SetDecadeView();
```

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode verwendet die [CMonthCalCtrl::SetCurrentView](#setcurrentview) Methode, um die Ansicht festgelegt wird, um `MCMV_DECADE`, steht für die zehn Jahren-Ansicht.

##  <a name="setfirstdayofweek"></a>  CMonthCalCtrl::SetFirstDayOfWeek

Legt fest, den Tag der Woche, die in der am weitesten links stehende Spalte des Kalenders angezeigt werden.

```
BOOL SetFirstDayOfWeek(
    int iDay,
    int* lpnOld = NULL);
```

### <a name="parameters"></a>Parameter

*iDay*<br/>
Ein ganzzahliger-Wert, der darstellt, der Tag als erster Tag der Woche festgelegt werden. Dieser Wert muss eine der Nummern der Tag sein. Finden Sie unter [GetFirstDayOfWeek](#getfirstdayofweek) für eine Beschreibung für die Tageszahlen.

*lpnOld*<br/>
Ein Zeiger auf eine ganze Zahl, der angibt, des ersten Tages der Woche zuvor festgelegt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die vorherigen, ersten Tag der Woche auf einen anderen Wert als der LOCALE_IFIRSTDAYOFWEEK festgelegt ist, ist der Tag, die in der Einstellung der Steuerelement-Bereich angegeben. Andernfalls gibt diese Funktion 0 zurück.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_SETFIRSTDAYOFWEEK](/windows/desktop/Controls/mcm-setfirstdayofweek), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CMonthCalCtrl#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_13.cpp)]

##  <a name="setmaxselcount"></a>  CMonthCalCtrl::SetMaxSelCount

Legt die maximale Anzahl von Tagen an, die in einem Monatskalender-Steuerelement ausgewählt werden können.

```
BOOL SetMaxSelCount(int nMax);
```

### <a name="parameters"></a>Parameter

*nmax.*<br/>
Der Wert, der festgelegt wird, um die maximale Anzahl von auswählbaren Tage darzustellen.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_SETMAXSELCOUNT](/windows/desktop/Controls/mcm-setmaxselcount), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CMonthCalCtrl#8](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_14.cpp)]

##  <a name="setmonthdelta"></a>  CMonthCalCtrl::SetMonthDelta

Legt die Bildlaufrate für ein Monatskalender-Steuerelement fest.

```
int SetMonthDelta(int iDelta);
```

### <a name="parameters"></a>Parameter

*iDelta*<br/>
Die Anzahl der Monate, die als Bildlaufrate des Steuerelements festgelegt werden. Wenn dieser Wert 0 (null) ist, wird das Delta Monat mit dem Standard zurückgesetzt, die Anzahl der Monate, die im Steuerelement angezeigt wird.

### <a name="return-value"></a>Rückgabewert

Die vorherigen Bildlaufrate. Wenn die Bildlaufrate nicht zuvor festgelegt wurde, ist der Rückgabewert 0.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_SETMONTHDELTA](/windows/desktop/Controls/mcm-setmonthdelta), wie im Windows SDK beschrieben.

##  <a name="setmonthview"></a>  CMonthCalCtrl::SetMonthView

Legt den aktuellen Monatskalender-Steuerelement zum Anzeigen der Monatsansicht fest.

```
BOOL SetMonthView();
```

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode verwendet die [CMonthCalCtrl::SetCurrentView](#setcurrentview) Methode für die Ansicht MCMV_MONTH, festzulegen, die die Monatsansicht darstellt.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_monthCalCtrl`, d. h. mit der im Monatskalender-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Beispiel

Das folgende Codebeispiel legt fest, im Monatskalender-Steuerelement, dem Monat, Jahr, Jahrzehnt und Jahrhundert Ansichten anzuzeigen.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_15.cpp)]

##  <a name="setrange"></a>  CMonthCalCtrl::SetRange

Legt die minimalen und maximalen zulässige Datumsangaben für ein Monatskalender-Steuerelement fest.

```
BOOL SetRange(
    const COleDateTime* pMinRange,
    const COleDateTime* pMaxRange);

BOOL SetRange(
    const CTime* pMinRange,
    const CTime* pMaxRange);

BOOL SetRange(
    const LPSYSTEMTIME pMinRange,
    const LPSYSTEMTIME pMaxRange);
```

### <a name="parameters"></a>Parameter

*pMinRange*<br/>
Ein Zeiger auf eine `COleDateTime` Objekt eine `CTime` Objekt oder [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, die das Datum am niedrigsten Ende des Bereichs enthält.

*pMaxRange*<br/>
Ein Zeiger auf eine `COleDateTime` Objekt eine `CTime` Objekt oder `SYSTEMTIME` Struktur, die das Datum am höchsten Ende des Bereichs enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_SETRANGE](/windows/desktop/Controls/mcm-setrange), wie im Windows SDK beschrieben. In MFC Implementierung von `SetRange`, können Sie angeben, `COleDateTime` Nutzung ein `CTime` Nutzung oder ein `SYSTEMTIME` Nutzung zu strukturieren.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMonthCalCtrl::GetRange](#getrange).

##  <a name="setselrange"></a>  CMonthCalCtrl::SetSelRange

Legt die Auswahl für ein Monatskalender-Steuerelement auf einem bestimmten Zeitraum.

```
BOOL SetSelRange(
    const COleDateTime& pMinRange,
    const COleDateTime& pMaxRange);

BOOL SetSelRange(
    const CTime& pMinRange,
    const CTime& pMaxRange);

BOOL SetSelRange(
    const LPSYSTEMTIME pMinRange,
    const LPSYSTEMTIME pMaxRange);
```

### <a name="parameters"></a>Parameter

*pMinRange*<br/>
Ein Zeiger auf eine `COleDateTime` Objekt eine `CTime` Objekt oder [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, die das Datum am niedrigsten Ende des Bereichs enthält.

*pMaxRange*<br/>
Ein Zeiger auf eine `COleDateTime` Objekt eine `CTime` Objekt oder `SYSTEMTIME` Struktur, die das Datum am höchsten Ende des Bereichs enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_SETSELRANGE](/windows/desktop/Controls/mcm-setselrange), wie im Windows SDK beschrieben. In MFC Implementierung von `SetSelRange`, können Sie angeben, `COleDateTime` Nutzung ein `CTime` Nutzung oder ein `SYSTEMTIME` Nutzung zu strukturieren.

##  <a name="settoday"></a>  CMonthCalCtrl::SetToday

Legt das Kalender-Steuerelement für den aktuellen Tag fest.

```
void SetToday(const COleDateTime& refDateTime);
void SetToday(const CTime* pDateTime);
  void SetToday(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>Parameter

*refDateTime*<br/>
Ein Verweis auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekt, das das aktuelle Datum enthält.

*pDateTime*<br/>
In der zweiten Version, ein Zeiger auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt mit Informationen über das aktuelle Datum. In der dritten Version, ein Zeiger auf eine [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) -Struktur, die das aktuelle Datum die Informationen enthält.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_SETTODAY](/windows/desktop/Controls/mcm-settoday), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CMonthCalCtrl::GetToday](#gettoday).

##  <a name="setyearview"></a>  CMonthCalCtrl::SetYearView

Legt den aktuellen Monatskalender-Steuerelement auf Jahr anzeigen.

```
BOOL SetYearView();
```

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode verwendet die [CMonthCalCtrl::SetCurrentView](#setcurrentview) Methode, um die Ansicht repräsentiert die jährlichen Ansicht MCMV_YEAR, fest.

##  <a name="sizeminreq"></a>  CMonthCalCtrl::SizeMinReq

Zeigt zeigt den Monat, die Kalender-Steuerelement, um die minimale Größe, die einen Monat.

```
BOOL SizeMinReq(BOOL bRepaint = TRUE);
```

### <a name="parameters"></a>Parameter

*bRepaint*<br/>
Gibt an, ob das Steuerelement neu gezeichnet wird. Standardmäßig wird "true". Tritt auf, nicht neu gezeichnet, wenn "FALSE".

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn im Monatskalender-Steuerelement auf ein Minimum festgelegt wird; andernfalls 0.

### <a name="remarks"></a>Hinweise

Aufrufen von `SizeMinReq` einwandfrei im gesamten Monatskalender-Steuerelement für ein-Monats-Kalender angezeigt.

##  <a name="sizerecttomin"></a>  CMonthCalCtrl::SizeRectToMin

Für die aktuelle Monatskalender-Steuerelement berechnet das kleinste Rechteck befindet, das allen Kalendern enthalten kann, die in einem angegebenen Rechteck zu passen.

```
LPRECT SizeRectToMin(LPRECT lpRect);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*lpRect*|[in] Zeiger auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die ein Rechteck definiert, die die gewünschte Anzahl von Kalendern enthält.|

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die ein Rechteck definiert, deren Größe kleiner oder gleich dem Rechteck definiert, durch die *LpRect* Parameter.

### <a name="remarks"></a>Hinweise

Diese Methode berechnet, wie viele Kalender eingepasst werden können, in dem Rechteck, das gemäß der *LpRect* -Parameter und gibt anschließend das kleinste Rechteck, das die Anzahl von Kalender enthalten kann. Aktiviert ist, wird diese Methode das angegebene Rechteck angepasst, dass genau die gewünschte Anzahl von Kalendern reduziert.

Diese Methode sendet die [MCM_SIZERECTTOMIN](/windows/desktop/Controls/mcm-sizerecttomin) -Nachricht, die im Windows SDK beschrieben wird.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel CMNCTRL1](../../visual-cpp-samples.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CDateTimeCtrl-Klasse](../../mfc/reference/cdatetimectrl-class.md)
