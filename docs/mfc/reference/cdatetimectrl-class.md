---
title: CDateTimeCtrl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CloseMonthCal
- AFXDTCTL/CDateTimeCtrl::Create
- AFXDTCTL/CDateTimeCtrl::GetDateTimePickerInfo
- AFXDTCTL/CDateTimeCtrl::GetIdealSize
- AFXDTCTL/CDateTimeCtrl::GetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::GetMonthCalCtrl
- AFXDTCTL/CDateTimeCtrl::GetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::GetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::GetRange
- AFXDTCTL/CDateTimeCtrl::GetTime
- AFXDTCTL/CDateTimeCtrl::SetFormat
- AFXDTCTL/CDateTimeCtrl::SetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::SetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::SetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::SetRange
- AFXDTCTL/CDateTimeCtrl::SetTime
helpviewer_keywords:
- CDateTimeCtrl [MFC], CDateTimeCtrl
- CDateTimeCtrl [MFC], CloseMonthCal
- CDateTimeCtrl [MFC], Create
- CDateTimeCtrl [MFC], GetDateTimePickerInfo
- CDateTimeCtrl [MFC], GetIdealSize
- CDateTimeCtrl [MFC], GetMonthCalColor
- CDateTimeCtrl [MFC], GetMonthCalCtrl
- CDateTimeCtrl [MFC], GetMonthCalFont
- CDateTimeCtrl [MFC], GetMonthCalStyle
- CDateTimeCtrl [MFC], GetRange
- CDateTimeCtrl [MFC], GetTime
- CDateTimeCtrl [MFC], SetFormat
- CDateTimeCtrl [MFC], SetMonthCalColor
- CDateTimeCtrl [MFC], SetMonthCalFont
- CDateTimeCtrl [MFC], SetMonthCalStyle
- CDateTimeCtrl [MFC], SetRange
- CDateTimeCtrl [MFC], SetTime
ms.assetid: 7113993b-5d37-4148-939f-500a190c5bdc
ms.openlocfilehash: cff81b7d260749d5be344edf3e0401a473b4f9e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508822"
---
# <a name="cdatetimectrl-class"></a>CDateTimeCtrl-Klasse

Kapselt die Funktionalität eines Steuerelements für die Datums- und Zeitauswahl.

## <a name="syntax"></a>Syntax

```
class CDateTimeCtrl : public CWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CDateTimeCtrl::CDateTimeCtrl](#cdatetimectrl)|Erstellt ein `CDateTimeCtrl`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDateTimeCtrl::CloseMonthCal](#closemonthcal)|Schließt den aktuelle Datums- / Zeitauswahl-Steuerelement.|
|[CDateTimeCtrl::Create](#create)|Die Datums- / Zeitauswahl-Steuerelement erstellt, und fügt es der `CDateTimeCtrl` Objekt.|
|[CDateTimeCtrl::GetDateTimePickerInfo](#getdatetimepickerinfo)|Ruft Informationen über die aktuellen Datums- / Zeitauswahl-Steuerelement ab.|
|[CDateTimeCtrl::GetIdealSize](#getidealsize)|Gibt zurück, die ideale Größe der Datums- / Zeitauswahl-Steuerelement, das erforderlich sind, um das aktuelle Datum oder Uhrzeit anzuzeigen.|
|[CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor)|Ruft die Farbe für einen bestimmten Teil der im Monatskalender innerhalb der Datums- / Zeitauswahl-Steuerelement ab.|
|[CDateTimeCtrl:: GetMonthCalCtrl](#getmonthcalctrl)|Ruft die `CMonthCalCtrl` Objekt, das Datums- / Zeitauswahl-Steuerelement zugeordnet.|
|[CDateTimeCtrl::GetMonthCalFont](#getmonthcalfont)|Ruft die derzeit von das Datum und Uhrzeit Datumsauswahl-Steuerelement untergeordnete Monatskalender-Steuerelement verwendete Schriftart ab.|
|[CDateTimeCtrl::GetMonthCalStyle](#getmonthcalstyle)|Ruft den Stil der die aktuellen Datums- / Zeitauswahl-Steuerelement ab.|
|[CDateTimeCtrl::GetRange](#getrange)|Ruft die aktuellen minimalen und maximalen zulässig Systemzeiten für einen Datums- / Zeitauswahl-Steuerelement ab.|
|[CDateTimeCtrl::GetTime](#gettime)|Ruft die derzeit ausgewählte Zeit aus einem Datums- / Zeitauswahl-Steuerelement ab und fügt es in einem angegebenen `SYSTEMTIME` Struktur.|
|[CDateTimeCtrl:: setFormat initialisiert](#setformat)|Legt fest, die Anzeige der ein Datums- / Zeitauswahl-Steuerelement in Übereinstimmung mit einer Zeichenfolge angegebenen Format.|
|[CDateTimeCtrl::SetMonthCalColor](#setmonthcalcolor)|Legt die Farbe für einen bestimmten Teil der im Monatskalender in einem Datums- / Zeitauswahl-Steuerelement fest.|
|[CDateTimeCtrl:: SetMonthCalFont](#setmonthcalfont)|Wird die Schriftart, die das Datum und Uhrzeit-Auswahl des Steuerelements untergeordneten Monatskalender-Steuerelement verwendet wird.|
|[CDateTimeCtrl::SetMonthCalStyle](#setmonthcalstyle)|Legt fest, der die Darstellung der aktuellen Datums- / Zeitauswahl-Steuerelement.|
|[CDateTimeCtrl::SetRange](#setrange)|Legt die minimalen und maximalen zulässigen Systemzeiten für einen Datums- / Zeitauswahl-Steuerelement fest.|
|[CDateTimeCtrl::SetTime](#settime)|Legt die Zeit in einem Datums- / Zeitauswahl-Steuerelement fest.|

## <a name="remarks"></a>Hinweise

Die Datums- / Zeitauswahl-Steuerelement (DTP-Steuerelement) bietet eine einfache Schnittstelle zum Austauschen von Informationen über Datum und Uhrzeit mit einem Benutzer. Diese Schnittstelle enthält Felder, von die jede einen Teil der Datum und Uhrzeit-Informationen, die in das Steuerelement gespeichert werden angezeigt. Der Benutzer kann die Informationen in das Steuerelement gespeichert werden, ändern Sie den Inhalt der Zeichenfolge in einem bestimmten Feld ändern. Der Benutzer kann von Feld zu Feld mit der Maus oder Tastatur navigieren.

Sie können den Datums- / Zeitauswahl-Steuerelement anpassen, indem Sie eine Vielzahl von Formaten auf das Objekt angewendet werden, bei der Erstellung. Finden Sie unter [Datums- und Uhrzeitformate Zeitauswahl-Steuerelement](/windows/desktop/Controls/date-and-time-picker-control-styles) im Windows SDK für Weitere Informationen zu Stilen, die spezifisch für die Datums- / Zeitauswahl-Steuerelement. Sie können das Anzeigeformat des DTP-Steuerelements mit Datenformate festlegen. Diese Stile Format werden unter "Format-Stile" beschrieben, in dem Windows SDK-Thema [Datums- und Uhrzeitformate Zeitauswahl-Steuerelement](/windows/desktop/Controls/date-and-time-picker-control-styles).

Die Datums- / Zeitauswahl-Steuerelement außerdem Benachrichtigungen und Rückrufe, die in beschriebenen verwendet [Verwenden von CDateTimeCtrl](../../mfc/using-cdatetimectrl.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CDateTimeCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxdtctl.h

##  <a name="cdatetimectrl"></a>  CDateTimeCtrl::CDateTimeCtrl

Erstellt ein `CDateTimeCtrl`-Objekt.

```
CDateTimeCtrl();
```

##  <a name="closemonthcal"></a>  CDateTimeCtrl::CloseMonthCal

Schließt den aktuelle Datums- / Zeitauswahl-Steuerelement.

```
void CloseMonthCal() const;
```

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [DTM_CLOSEMONTHCAL](/windows/desktop/Controls/dtm-closemonthcal) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable *M_dateTimeCtrl*, d. h. verwendet, um die Datums- / Zeitauswahl-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die Dropdown-Kalender für die aktuellen Datums- / Zeitauswahl-Steuerelement geschlossen.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_2.cpp)]

##  <a name="create"></a>  CDateTimeCtrl::Create

Die Datums- / Zeitauswahl-Steuerelement erstellt, und fügt es der `CDateTimeCtrl` Objekt.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Gibt die Kombination aus Datum Uhrzeit Stile von Listensteuerelementen an. Finden Sie unter [Datums- und Uhrzeitformate Zeitauswahl-Steuerelement](/windows/desktop/Controls/date-and-time-picker-control-styles) im Windows SDK für Weitere Informationen zu Datums- / Zeitauswahl-Stilen.

*Rect*<br/>
Ein Verweis auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die die Position und Größe von den Datums- / Zeitauswahl-Steuerelement ist.

*pParentWnd*<br/>
Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster von der Datums- / Zeitauswahl-Steuerelement ist. Es darf nicht NULL sein.

*nID*<br/>
Gibt an, die Datums- / Zeitauswahl-Steuerelements Steuerelement-ID.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Erstellung erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

##### <a name="to-create-a-date-and-time-picker-control"></a>Um einen Datums- / Zeitauswahl-Steuerelement zu erstellen.

1. Rufen Sie [CDateTimeCtrl](#cdatetimectrl) zum Erstellen einer `CDateTimeCtrl` Objekt.

1. Rufen Sie diese Memberfunktion, die die Windows-Datums- / Zeitauswahl-Steuerelement erstellt, und fügt es der `CDateTimeCtrl` Objekt.

Beim Aufruf `Create`, die allgemeinen Steuerelemente werden initialisiert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CDateTimeCtrl#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_3.cpp)]

##  <a name="getdatetimepickerinfo"></a>  CDateTimeCtrl::GetDateTimePickerInfo

Ruft Informationen über die aktuellen Datums- / Zeitauswahl-Steuerelement ab.

```
BOOL GetDateTimePickerInfo(LPDATETIMEPICKERINFO pDateTimePickerInfo) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*pDateTimePickerInfo*|[out] Ein Zeiger auf eine [DATETIMEPICKERINFO](/windows/desktop/api/commctrl/ns-commctrl-tagdatetimepickerinfo) Struktur, die eine Beschreibung der aktuellen Datums- / Zeitauswahl-Steuerelement empfängt.<br /><br /> Der Aufrufer ist verantwortlich für die Zuordnung von dieser Struktur. Aber diese Methode initialisiert die *CbSize* Member der Struktur.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [DTM_GETDATETIMEPICKERINFO](/windows/desktop/Controls/dtm-getdatetimepickerinfo) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable *M_dateTimeCtrl*, d. h. verwendet, um die Datums- / Zeitauswahl-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>Beispiel

Das folgende Codebeispiel gibt an, ob sie erfolgreich Ruft Informationen über die aktuellen Datums- / Zeitauswahl-Steuerelement ab.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_4.cpp)]

##  <a name="getmonthcalcolor"></a>  CDateTimeCtrl::GetMonthCalColor

Ruft die Farbe für einen bestimmten Teil der im Monatskalender innerhalb der Datums- / Zeitauswahl-Steuerelement ab.

```
COLORREF GetMonthCalColor(int iColor) const;
```

### <a name="parameters"></a>Parameter

*iColor*<br/>
Ein **Int** Wert, der die Farbbereich des abzurufenden Monatskalenders angibt. Eine Liste von Werten, finden Sie unter den *iColor* -Parameter für [SetMonthCalColor](#setmonthcalcolor).

### <a name="return-value"></a>Rückgabewert

Eine COLORREF-Wert, der die Farbe-Einstellung für den angegebenen Teil des Monatskalender-Steuerelements im Erfolgsfall darstellt. Die Funktion gibt-1 zurück, wenn der Vorgang fehlschlägt.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_GETMCCOLOR](/windows/desktop/Controls/dtm-getmccolor), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CDateTimeCtrl#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_5.cpp)]

##  <a name="getmonthcalctrl"></a>  CDateTimeCtrl:: GetMonthCalCtrl

Ruft die `CMonthCalCtrl` Objekt, das Datums- / Zeitauswahl-Steuerelement zugeordnet.

```
CMonthCalCtrl* GetMonthCalCtrl() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) Objekt, oder NULL, wenn der Vorgang fehlschlägt oder wenn das Fenster nicht sichtbar ist.

### <a name="remarks"></a>Hinweise

Datums- und Zeitauswahlsteuerelemente erstellen Monatskalender-Steuerelement ein untergeordnetes Element, klickt der Benutzer den Dropdown-Pfeil. Wenn die `CMonthCalCtrl` Objekt nicht mehr erforderlich ist, werden sie zerstört wird, damit Ihre Anwendung nicht angewiesen, zum Speichern von das Objekt, das die Datums-/ Zeitauswahl-Steuerelement die untergeordneten-Monats-Kalender darstellt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CDateTimeCtrl#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_6.cpp)]

##  <a name="getmonthcalfont"></a>  CDateTimeCtrl::GetMonthCalFont

Ruft die derzeit durch das Datum und die Monatskalender-Steuerelement für die Zeitauswahl Steuerelement verwendete Schriftart ab.

```
CFont* GetMonthCalFont() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine [CFont](../../mfc/reference/cfont-class.md) Objekt, oder NULL, wenn der Vorgang fehlschlägt.

### <a name="remarks"></a>Hinweise

Die `CFont` Objekt der Rückgabewert ist ein temporäres Objekt und während der nächsten Verarbeitung Leerlaufzeit zerstört wird.

##  <a name="getmonthcalstyle"></a>  CDateTimeCtrl::GetMonthCalStyle

Ruft den Stil des im Dropdown-Monatskalender-Steuerelement, das die aktuellen Datums- / Zeitauswahl-Steuerelement zugeordnet ist.

```
DWORD GetMonthCalStyle() const;
```

### <a name="return-value"></a>Rückgabewert

Der Stil, der im Dropdown-Monatskalender-Steuerelement, das eine bitweise Kombination ist (oder) von Datums- und Zeitformaten der Datumsauswahl-Steuerelement. Weitere Informationen finden Sie unter [Month Calendar-Steuerelement-Stile](/windows/desktop/Controls/month-calendar-control-styles).

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [DTM_GETMCSTYLE](/windows/desktop/Controls/dtm-getmcstyle) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="getrange"></a>  CDateTimeCtrl::GetRange

Ruft die aktuellen minimalen und maximalen zulässig Systemzeiten für einen Datums- / Zeitauswahl-Steuerelement ab.

```
DWORD GetRange(
    COleDateTime* pMinRange,
    COleDateTime* pMaxRange) const;

DWORD GetRange(
    CTime* pMinRange,
    CTime* pMaxRange) const;
```

### <a name="parameters"></a>Parameter

*pMinRange*<br/>
Ein Zeiger auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt oder ein [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt mit den frühesten Zeitpunkt innerhalb der `CDateTimeCtrl` Objekt.

*pMaxRange*<br/>
Ein Zeiger auf eine `COleDateTime` Objekt oder ein `CTime` -Objekt, enthält die späteste Uhrzeit, die innerhalb der `CDateTimeCtrl` Objekt.

### <a name="return-value"></a>Rückgabewert

Eine DWORD-Wert, mit der Flags, die angeben, welche Bereiche festgelegt werden. If

`return value & GDTR_MAX` == 0

der zweite Parameter ungültig ist. Auf ähnliche Weise, wenn

`return value & GDTR_MIN` == 0

der erste Parameter ungültig ist.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_GETRANGE](/windows/desktop/Controls/dtm-getrange), wie im Windows SDK beschrieben. In der MFC-Implementierung, geben Sie entweder `COleDateTime` oder `CTime` Verwendungen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CDateTimeCtrl#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_7.cpp)]

##  <a name="gettime"></a>  CDateTimeCtrl::GetTime

Ruft die derzeit ausgewählte Zeit aus einem Datums- / Zeitauswahl-Steuerelement ab und fügt es in einem angegebenen `SYSTEMTIME` Struktur.

```
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;
```

### <a name="parameters"></a>Parameter

*timeDest*<br/>
In der ersten Version, die einen Verweis auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekt, das die Zeitinformationen System erhält. In der zweiten Version, die einen Verweis auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, das die Zeitinformationen System erhält.

*pTimeDest*<br/>
Ein Zeiger auf die [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, um die Systeminformationen für die Zeit zu erhalten. Nicht darf NULL sein.

### <a name="return-value"></a>Rückgabewert

In der ersten Version, die ungleich NULL, wenn die Zeit erfolgreich, um geschrieben wurde die `COleDateTime` -Objekt, andernfalls 0. In den zweiten und dritten-Versionen, ein DWORD-Wert gleich Wert der *DwFlag* Elementgruppe das [NMDATETIMECHANGE](/windows/desktop/api/commctrl/ns-commctrl-tagnmdatetimechange) Struktur. Finden Sie unter den **"Hinweise"** Informationen weiter unten im Abschnitt.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_GETSYSTEMTIME](/windows/desktop/Controls/dtm-getsystemtime), wie im Windows SDK beschrieben. In der MFC-Implementierung von `GetTime`, können Sie `COleDateTime` oder `CTime` Klassen, oder Sie können eine `SYSTEMTIME` Struktur, um die Informationen zu speichern.

Der Rückgabewert DWORD in die zweiten und dritten-Versionen, oben gibt an, und zwar unabhängig davon, ob die Datums- / Zeitauswahl-Steuerelement auf den Status "kein Datum" festgelegt ist wie angegeben in der [NMDATETIMECHANGE](/windows/desktop/api/commctrl/ns-commctrl-tagnmdatetimechange) Strukturmember *DwFlags* . Wenn der zurückgegebene Wert GDT_NONE gleich ist, wird das Steuerelement auf "kein Datum" Status festgelegt ist, und verwendet den DTS_SHOWNONE-Stil. Wenn der zurückgegebene Wert GDT_VALID gleich ist, wird die Systemzeit am Zielspeicherort wurde erfolgreich gespeichert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CDateTimeCtrl#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_8.cpp)]

##  <a name="getidealsize"></a>  CDateTimeCtrl::GetIdealSize

Gibt zurück, die ideale Größe der Datums- / Zeitauswahl-Steuerelement, das erforderlich sind, um das aktuelle Datum oder Uhrzeit anzuzeigen.

```
BOOL GetIdealSize(LPSIZE psize) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*psize*|[out] Zeiger auf eine [Größe](https://msdn.microsoft.com/library/windows/desktop/dd145106) -Struktur, die optimale Größe für das Steuerelement enthält.|

### <a name="return-value"></a>Rückgabewert

Der Rückgabewert ist immer "true".

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [DTM_GETIDEALSIZE](/windows/desktop/Controls/dtm-getidealsize) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable *M_dateTimeCtrl*, d. h. verwendet, um die Datums- / Zeitauswahl-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel ruft die optimale Größe zum Anzeigen der Datums- / Zeitauswahl-Steuerelement ab.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_9.cpp)]

##  <a name="setformat"></a>  CDateTimeCtrl:: setFormat initialisiert

Legt fest, die Anzeige der ein Datums- / Zeitauswahl-Steuerelement in Übereinstimmung mit einer Zeichenfolge angegebenen Format.

```
BOOL SetFormat(LPCTSTR pstrFormat);
```

### <a name="parameters"></a>Parameter

*pstrFormat*<br/>
Ein Zeiger auf eine 0 (null) endende Zeichenfolge, die den gewünschten Anzeige definiert. Dieser Parameter auf NULL festlegen, wird das Steuerelement auf die Standardformat-Zeichenfolge für den aktuellen Stil zurückgesetzt.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

> [!NOTE]
>  Erfolg oder Fehler für diesen Aufruf wird der Benutzereingabe nicht ermittelt werden.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_SETFORMAT](/windows/desktop/Controls/dtm-setformat), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CDateTimeCtrl#6](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_10.cpp)]

##  <a name="setmonthcalcolor"></a>  CDateTimeCtrl::SetMonthCalColor

Legt die Farbe für einen bestimmten Teil der im Monatskalender in einem Datums- / Zeitauswahl-Steuerelement fest.

```
COLORREF SetMonthCalColor(
    int iColor,
    COLORREF ref);
```

### <a name="parameters"></a>Parameter

*iColor*<br/>
**Int** Wert, der der Bereich, der im Monatskalender-Steuerelement festlegen angibt. Dieser Wert kann eine der folgenden sein.

|Wert|Bedeutung|
|-----------|-------------|
|MCSC_BACKGROUND|Legen Sie die Hintergrundfarbe, die zwischen den Monaten angezeigt.|
|MCSC_MONTHBK|Legen Sie die Hintergrundfarbe, die innerhalb eines Monats angezeigt.|
|MCSC_TEXT|Legen Sie die Farbe, die zum Anzeigen von Text in einem Monat verwendet.|
|MCSC_TITLEBK|Legen Sie die Hintergrundfarbe des Kalenders Titel angezeigt.|
|MCSC_TITLETEXT|Legen Sie die Farbe, die zum Anzeigen von Text innerhalb des Kalenders Titel verwendet.|
|MCSC_TRAILINGTEXT|Legen Sie die Farbe, die zum Anzeigen von Kopf- und nachfolgende-Tage-Text. Header und die nachfolgenden Tage werden die Tage aus den vorherigen und folgenden Monaten, die auf dem aktuellen Kalender angezeigt werden.|

*ref*<br/>
Ein COLORREF-Wert, der die Farbe, die für den angegebenen Bereich des Monatskalender festgelegt werden darstellt.

### <a name="return-value"></a>Rückgabewert

Eine COLORREF-Wert, der die vorherige Farbe-Einstellung für den angegebenen Teil des Monatskalender-Steuerelements im Erfolgsfall darstellt. Die Nachricht zurückgegeben, andernfalls -1.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_SETMCCOLOR](/windows/desktop/Controls/dtm-setmccolor), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor).

##  <a name="setmonthcalfont"></a>  CDateTimeCtrl:: SetMonthCalFont

Wird die Schriftart, die das Datum und Uhrzeit-Auswahl des Steuerelements untergeordneten Monatskalender-Steuerelement verwendet wird.

```
void SetMonthCalFont(
    HFONT hFont,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parameter

*hFont*<br/>
Handle für die Schriftart, die festgelegt werden.

*bRedraw*<br/>
Gibt an, ob das Steuerelement sofort neu muss beim Festlegen der Schriftartformats gezeichnet werden. Wenn dieser Parameter auf "true" bewirkt, dass das Steuerelement selbst neu zeichnet.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_SETMCFONT](/windows/desktop/Controls/dtm-setmcfont), wie im Windows SDK beschrieben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CDateTimeCtrl#7](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_11.cpp)]

> [!NOTE]
>  Wenn Sie diesen Code verwenden, sollten Sie ein Mitglied, Ihre `CDialog`-abgeleitete Klasse mit dem Namen *M_MonthFont* des Typs `CFont`.

##  <a name="setmonthcalstyle"></a>  CDateTimeCtrl::SetMonthCalStyle

Legt das Format des im Dropdown-Monatskalender-Steuerelement, das die aktuellen Datums- / Zeitauswahl-Steuerelement zugeordnet ist.

```
DWORD SetMonthCalStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*dwStyle*|[in] Einen neuen Monat Monatskalender Steuerelementstil, die eine bitweise Kombination (OR) von Month Calendar-Steuerelement-Stile ist. Weitere Informationen finden Sie unter [Month Calendar-Steuerelement-Stile](/windows/desktop/Controls/month-calendar-control-styles).|

### <a name="return-value"></a>Rückgabewert

Den vorherigen Stil des im Dropdown-Monatskalender-Steuerelement.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [DTM_SETMCSTYLE](/windows/desktop/Controls/dtm-setmcstyle) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable *M_dateTimeCtrl*, d. h. verwendet, um die Datums- / Zeitauswahl-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>Beispiel

Das folgende Codebeispiel legt fest, die Datums- / Zeitauswahl-Steuerelement anzuzeigenden Wochennummern, abgekürzten Namen der Tage der Woche und keinen Indikator für heute.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_12.cpp)]

##  <a name="setrange"></a>  CDateTimeCtrl::SetRange

Legt die minimalen und maximalen zulässigen Systemzeiten für einen Datums- / Zeitauswahl-Steuerelement fest.

```
BOOL SetRange(
    const COleDateTime* pMinRange,
    const COleDateTime* pMaxRange);

BOOL SetRange(
    const CTime* pMinRange,
    const CTime* pMaxRange);
```

### <a name="parameters"></a>Parameter

*pMinRange*<br/>
Ein Zeiger auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt oder ein [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt mit den frühesten Zeitpunkt innerhalb der `CDateTimeCtrl` Objekt.

*pMaxRange*<br/>
Ein Zeiger auf eine `COleDateTime` Objekt oder ein `CTime` -Objekt, enthält die späteste Uhrzeit, die innerhalb der `CDateTimeCtrl` Objekt.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_SETRANGE](/windows/desktop/Controls/dtm-setrange), wie im Windows SDK beschrieben. In der MFC-Implementierung, geben Sie entweder `COleDateTime` oder `CTime` Verwendungen. Wenn die `COleDateTime` Objekt weist den Status NULL, wird der Bereich entfernt. Wenn die `CTime` Zeiger oder die `COleDateTime` Zeiger NULL ist, wird der Bereich entfernt.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CDateTimeCtrl::GetRange](#getrange).

##  <a name="settime"></a>  CDateTimeCtrl::SetTime

Legt die Zeit in einem Datums- / Zeitauswahl-Steuerelement fest.

```
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* pTimeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew = NULL);
```

### <a name="parameters"></a>Parameter

*timeNew*<br/>
Ein Verweis auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt mit der auf dem das Steuerelement festgelegt wird.

*pTimeNew*<br/>
In der zweiten Version über einen Zeiger auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, enthält die Zeit, die auf den das Steuerelement festgelegt werden. In der dritten Version über einen Zeiger auf eine [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) -Struktur, enthält die Zeit, die auf den das Steuerelement festgelegt werden.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_SETSYSTEMTIME](/windows/desktop/Controls/dtm-setsystemtime), wie im Windows SDK beschrieben. In der MFC-Implementierung von `SetTime`, können Sie die `COleDateTime` oder `CTime` Klassen, oder Sie können eine `SYSTEMTIME` Struktur, die Zeitinformationen festlegen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CDateTimeCtrl#8](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_13.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel CMNCTRL1](../../visual-cpp-samples.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CMonthCalCtrl-Klasse](../../mfc/reference/cmonthcalctrl-class.md)
