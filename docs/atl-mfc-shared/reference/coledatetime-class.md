---
title: COleDateTime-Klasse
ms.date: 03/27/2019
f1_keywords:
- COleDateTime
- ATLCOMTIME/ATL::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::Format
- ATLCOMTIME/ATL::COleDateTime::GetAsDBTIMESTAMP
- ATLCOMTIME/ATL::COleDateTime::GetAsSystemTime
- ATLCOMTIME/ATL::COleDateTime::GetAsUDATE
- ATLCOMTIME/ATL::COleDateTime::GetCurrentTime
- ATLCOMTIME/ATL::COleDateTime::GetDay
- ATLCOMTIME/ATL::COleDateTime::GetDayOfWeek
- ATLCOMTIME/ATL::COleDateTime::GetDayOfYear
- ATLCOMTIME/ATL::COleDateTime::GetHour
- ATLCOMTIME/ATL::COleDateTime::GetMinute
- ATLCOMTIME/ATL::COleDateTime::GetMonth
- ATLCOMTIME/ATL::COleDateTime::GetSecond
- ATLCOMTIME/ATL::COleDateTime::GetStatus
- ATLCOMTIME/ATL::COleDateTime::GetYear
- ATLCOMTIME/ATL::COleDateTime::ParseDateTime
- ATLCOMTIME/ATL::COleDateTime::SetDate
- ATLCOMTIME/ATL::COleDateTime::SetDateTime
- ATLCOMTIME/ATL::COleDateTime::SetStatus
- ATLCOMTIME/ATL::COleDateTime::SetTime
- ATLCOMTIME/ATL::COleDateTime::m_dt
- ATLCOMTIME/ATL::COleDateTime::m_status
helpviewer_keywords:
- shared classes, COleDateTime
- time-only values
- Date data type, MFC encapsulation of
- COleDateTime class
- dates, handling in MFC
- time, handling in MFC
ms.assetid: e718f294-16ec-4649-88b6-a4dbae5178fb
ms.openlocfilehash: a254019d1efe916365799affa3d2c5271883bafb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491261"
---
# <a name="coledatetime-class"></a>COleDateTime-Klasse

Kapselt den `DATE` Datentyp, der in der OLE-Automatisierung verwendet wird.

## <a name="syntax"></a>Syntax

```
class COleDateTime
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleDateTime::COleDateTime](#coledatetime)|Erstellt ein `COleDateTime`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleDateTime::Format](#format)|Generiert eine formatierte Zeichen folgen Darstellung `COleDateTime` eines-Objekts.|
|[COleDateTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|Rufen Sie diese Methode auf, um die Zeit `COleDateTime` im Objekt `DBTIMESTAMP` als Datenstruktur zu erhalten.|
|[COleDateTime::GetAsSystemTime](#getassystemtime)|Rufen Sie diese Methode auf, um die Zeit `COleDateTime` im-Objekt als [System Time](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) -Datenstruktur zu erhalten.|
|[COleDateTime::GetAsUDATE](#getasudate)|Rufen Sie diese Methode auf, um die Zeit `COleDateTime` in der `UDATE` als Datenstruktur zu erhalten.|
|[COleDateTime::GetCurrentTime](#getcurrenttime)|Erstellt ein `COleDateTime` -Objekt, das die aktuelle Uhrzeit darstellt (statische Member-Funktion).|
|[COleDateTime::GetDay](#getday)|Gibt den Tag zurück `COleDateTime` , den dieses-Objekt darstellt (1-31).|
|[COleDateTime::GetDayOfWeek](#getdayofweek)|Gibt den Wochentag zurück, den dieses `COleDateTime` Objekt darstellt (Sonntag = 1).|
|[COleDateTime::GetDayOfYear](#getdayofyear)|Gibt den Tag des Jahres zurück, `COleDateTime` den dieses Objekt darstellt (Jan 1 = 1).|
|[COleDateTime::GetHour](#gethour)|Gibt die Stunde zurück `COleDateTime` , die dieses-Objekt darstellt (0-23).|
|[COleDateTime::GetMinute](#getminute)|Gibt die Minute zurück `COleDateTime` , die dieses-Objekt darstellt (0-59).|
|[COleDateTime::GetMonth](#getmonth)|Gibt den Monat zurück `COleDateTime` , den dieses Objekt darstellt (1-12).|
|[COleDateTime::GetSecond](#getsecond)|Gibt die zweite zurück `COleDateTime` , die dieses-Objekt darstellt (0-59).|
|[COleDateTime::GetStatus](#getstatus)|Ruft den Status (Gültigkeit) dieses `COleDateTime` -Objekts ab.|
|[COleDateTime::GetYear](#getyear)|Gibt das Jahr zurück `COleDateTime` , das dieses Objekt darstellt.|
|[COleDateTime::ParseDateTime](#parsedatetime)|Liest einen Datums-/Uhrzeitwert aus einer Zeichenfolge und legt `COleDateTime`den Wert von fest.|
|[COleDateTime::SetDate](#setdate)|Legt den Wert dieses `COleDateTime` -Objekts auf den angegebenen datumsbasierten Wert fest.|
|[COleDateTime::SetDateTime](#setdatetime)|Legt den Wert dieses `COleDateTime` -Objekts auf den angegebenen Datums-/Uhrzeitwert fest.|
|[COleDateTime::SetStatus](#setstatus)|Legt den Status (Gültigkeit) dieses `COleDateTime` Objekts fest.|
|[COleDateTime::SetTime](#settime)|Legt den Wert dieses `COleDateTime` -Objekts auf den angegebenen Zeit reinen Wert fest.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[COleDateTime:: Operator = =, COleDateTime:: Operator < usw.](#coledatetime_relational_operators)|Vergleicht zwei `COleDateTime` Werte.|
|[COleDateTime:: Operator +, COleDateTime:: Operator-](#operator_add_-)|Werte hinzufügen und `COleDateTime` subtrahieren.|
|[COleDateTime:: Operator + =, COleDateTime:: Operator-=](#operator_add_eq_-_eq)|Fügen Sie einen `COleDateTime` Wert zu diesem `COleDateTime` Objekt hinzu, und subtrahieren Sie|
|[COleDateTime::operator =](#operator_eq)|Kopiert einen `COleDateTime` Wert.|
|[COleDateTime:: Operator Date, COleDateTime:: Operator Date *](#operator_date)|Konvertiert einen `COleDateTime` Wert in ein `DATE` oder einen `DATE*`.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COleDateTime::m_dt](#m_dt)|Enthält den zugrunde `DATE` liegenden für `COleDateTime` dieses Objekt.|
|[COleDateTime::m_status](#m_status)|Enthält den Status dieses `COleDateTime` Objekts.|

## <a name="remarks"></a>Hinweise

`COleDateTime`weist keine Basisklasse auf.

Dies ist einer der möglichen Typen für den [Variant](/windows/win32/api/oaidl/ns-oaidl-variant) -Datentyp der OLE-Automatisierung. Ein `COleDateTime` -Wert stellt einen absoluten Datums-und Uhrzeitwert dar.

Der `DATE` Typ wird als Gleit Komma Wert implementiert. Tage werden ab dem 30. Dezember 1899 und Mitternacht gemessen. In der folgenden Tabelle werden einige Datumsangaben und deren zugeordnete Werte angezeigt:

|date|Wert|
|----------|-----------|
|29. Dezember 1899, Mitternacht|-1.0|
|29. Dezember 1899, 6 A. M|-1.25|
|30. Dezember 1899, Mitternacht|0.0|
|31. Dezember 1899, Mitternacht|1.0|
|1\. Januar 1900, 6 Uhr|2.25|

> [!CAUTION]
> In der obigen Tabelle werden Tageswerte nicht am 30. Dezember 1899, sondern auch vor Mitternacht negativ. 6:00 am wird z. b. immer durch einen Bruch Wert von 0,25 dargestellt, unabhängig davon, ob die ganze Zahl, die den Tag darstellt, positiv ist (nach dem 30. Dezember 1899) oder negativ (vor dem 30. Dezember 1899). Dies bedeutet, dass bei einem einfachen Gleit Komma Vergleich fälschlicherweise eine `COleDateTime` , die 6:00 am 12/29/1899 darstellt, **so sortiert wird, als wäre** es eine, die am selben Tag 7:00 Uhr darstellt.

Die `COleDateTime` -Klasse verarbeitet Datumsangaben vom 1. Januar 100 bis zum 31. Dezember 9999. Die `COleDateTime` Klasse verwendet den gregorianischen Kalender; Sie unterstützt keine Julischen Datumsangaben. `COleDateTime`ignoriert die Sommerzeit. (Siehe [Datum und Uhrzeit: Automation-](../../atl-mfc-shared/date-and-time-automation-support.md)Unterstützung.)

> [!NOTE]
> Sie können das `%y` Format verwenden, um eine zweistellige Jahres Angabe nur für Datumsangaben ab 1900 abzurufen. Wenn Sie das `%y` Format für ein Datum vor 1900 verwenden, generiert der Code einen Assert-Fehler.

Dieser Typ wird auch verwendet, um Datums-oder Uhrzeit Werte darzustellen. Gemäß der Konvention wird das Datum 0 (Dezember 1899) für reine Zeit Werte verwendet, und die Uhrzeit 00:00 (Mitternacht) wird für Datums-/Uhrzeitwerte verwendet.

Wenn Sie `COleDateTime` ein-Objekt mithilfe eines Datums kleiner als 100 erstellen, wird das Datum akzeptiert, aber nachfolgende Aufrufe `GetYear`von `GetMonth`, `GetDay`, `GetHour`, `GetMinute`, und `GetSecond` schlagen fehl, und geben-1 zurück. Zuvor konnten Sie zweistellige Datumsangaben verwenden, aber Datumsangaben müssen in MFC 4,2 und höher 100 oder größer sein.

Um Probleme zu vermeiden, geben Sie ein vierstelliges Datum an. Beispiel:

[!code-cpp[NVC_ATLMFC_Utilities#1](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_1.cpp)]

Grundlegende arithmetische Operationen `COleDateTime` für die Werte verwenden die Begleit Klasse [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md). `COleDateTimeSpan`Werte definieren ein Zeitintervall. Die Beziehung zwischen diesen Klassen ähnelt der Beziehung zwischen [ctime](../../atl-mfc-shared/reference/ctime-class.md) und [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).

Weitere Informationen zu den `COleDateTime` -und- `COleDateTimeSpan` Klassen finden Sie im [Artikel Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

## <a name="requirements"></a>Anforderungen

**Header:** ATLComTime.h

##  <a name="coledatetime_relational_operators"></a>Relationale COleDateTime-Operatoren

Vergleichs Operatoren.

```
bool operator==(const COleDateTime& date) const throw();
bool operator!=(const COleDateTime& date) const throw();
bool operator<(const COleDateTime& date) const throw();
bool operator>(const COleDateTime& date) const throw();
bool operator<=(const COleDateTime& date) const throw();
bool operator>=(const COleDateTime& date) const throw();
```

### <a name="parameters"></a>Parameter

*date*<br/>
Das zu vergleichende `COleDateTime`-Objekt.

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Ein ATLASSERT-Vorgang tritt auf, wenn einer der beiden Operanden ungültig ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#13](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_2.cpp)]

### <a name="example"></a>Beispiel

Die **>=** Operatoren **\< =** **<,,** und bestätigen, dass das`COleDateTime` -Objekt auf NULL festgelegt ist. **>**

[!code-cpp[NVC_ATLMFC_Utilities#170](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_3.cpp)]

##  <a name="coledatetime"></a>COleDateTime:: COleDateTime

Erstellt ein `COleDateTime`-Objekt.

```
COleDateTime() throw();
COleDateTime(const VARIANT& varSrc) throw();
COleDateTime(DATE dtSrc) throw();
COleDateTime(time_t timeSrc) throw();
COleDateTime(__time64_t timeSrc) throw();
COleDateTime(const SYSTEMTIME& systimeSrc) throw();
COleDateTime(const FILETIME& filetimeSrc) throw();

COleDateTime(int nYear,
    int nMonth,
    int nDay,
    int nHour,
    int nMin,
    int nSec) throw();

COleDateTime(WORD wDosDate,
    WORD wDosTime) throw();
COleDateTime(const DBTIMESTAMP& timeStamp) throw();
```

### <a name="parameters"></a>Parameter

*dateSrc*<br/>
Ein vorhandenes `COleDateTime` -Objekt, das in das `COleDateTime` neue-Objekt kopiert werden soll.

*varSrc*<br/>
Eine vorhandene `VARIANT` Datenstruktur (möglicherweise `COleVariant` ein-Objekt), die in einen Datums-/Uhrzeitwert (VT_DATE) konvertiert und `COleDateTime` in das neue-Objekt kopiert werden soll.

*dtSrc*<br/>
Ein Datums-/Uhrzeitwert (`DATE`), der in das neue `COleDateTime` -Objekt kopiert werden soll.

*timeSrc*<br/>
Ein `time_t` - `__time64_t` oder-Wert, der in einen Datums-/Uhrzeitwert konvertiert und `COleDateTime` in das neue-Objekt kopiert werden soll.

*systimeSrc*<br/>
Eine `SYSTEMTIME` -Struktur, die in einen Datums-/Uhrzeitwert konvertiert und in `COleDateTime` das neue-Objekt kopiert werden soll.

*filetimeSrc*<br/>
Eine `FILETIME` -Struktur, die in einen Datums-/Uhrzeitwert konvertiert und in `COleDateTime` das neue-Objekt kopiert werden soll. Ein `FILETIME` verwendet Universal koordinierte Zeit (UTC). Wenn Sie also eine lokale Zeit in der Struktur übergeben, sind die Ergebnisse falsch. Weitere Informationen finden Sie unter [Datei Zeiten](/windows/win32/SysInfo/file-times) in der Windows SDK.

*nyear*, *nmonth*, *NDAY*, *nHour*, *nmin*, *nsec*<br/>
Geben Sie die Datums-und Uhrzeitwerte an, die `COleDateTime` in das neue-Objekt kopiert werden.

*wDosDate*, *wDosTime*<br/>
MS-und Time-Werte, die in einen Datums-/Uhrzeitwert konvertiert und in `COleDateTime` das neue-Objekt kopiert werden.

*timeStamp*<br/>
Ein Verweis auf eine [DBTIMESTAMP](/dotnet/api/system.data.oledb.oledbtype) -Struktur, die die aktuelle lokale Uhrzeit enthält.

### <a name="remarks"></a>Hinweise

Alle diese Konstruktoren erstellen neue `COleDateTime` Objekte, die mit dem angegebenen Wert initialisiert werden. In der folgenden Tabelle werden gültige Bereiche für jede Datums-und Uhrzeit Komponente angezeigt:

|Datums-/Uhrzeitkomponente|Gültiger Bereich|
|--------------------------|-----------------|
|Jahr|100 - 9999|
|Monat|0 - 12|
|Tag|0 - 31|
|geöffneten|0 - 23|
|tiges|0 - 59|
|second|0 - 59|

Beachten Sie, dass die tatsächliche obere Grenze für die Tages Komponente basierend auf den Komponenten month und Year variiert. Weitere Informationen finden Sie unter `SetDate` den `SetDateTime` -oder-Member-Funktionen.

Im folgenden finden Sie eine kurze Beschreibung der einzelnen Konstruktoren:

- `COleDateTime(` **)** Erstellt ein `COleDateTime` -Objekt, das mit 0 (Mitternacht, 30. Dezember 1899) initialisiert wird.

- `COleDateTime(`) Erstellt ein `COleDateTime` -Objekt aus einem `COleDateTime` vorhandenen-Objekt. `dateSrc`

- `COleDateTime(`*varSrc* **)** Erstellt ein `COleDateTime` -Objekt. Versucht, eine `VARIANT` Struktur oder ein [COleVariant](../../mfc/reference/colevariant-class.md) -Objekt in einen Datums-/Uhrzeitwert ( `VT_DATE`) zu konvertieren. Wenn diese Konvertierung erfolgreich ist, wird der konvertierte Wert in das neue `COleDateTime` -Objekt kopiert. Wenn dies nicht der Fall ist, wird der `COleDateTime` Wert des-Objekts auf 0 (Mitternacht, 30. Dezember 1899) und seinen Status auf ungültig festgelegt.

- `COleDateTime(`) Erstellt ein `COleDateTime` -Objekt aus `DATE` einem Wert. `dtSrc`

- `COleDateTime(`) Erstellt ein `COleDateTime` -Objekt aus `time_t` einem Wert. `timeSrc`

- `COleDateTime(`*systimesrc* **)** Erstellt ein `COleDateTime` -Objekt aus `SYSTEMTIME` einem Wert.

- `COleDateTime(`) Erstellt ein `COleDateTime` -Objekt aus `FILETIME` einem Wert. `filetimeSrc` . Ein `FILETIME` verwendet Universal koordinierte Zeit (UTC). Wenn Sie also eine lokale Zeit in der Struktur übergeben, sind die Ergebnisse falsch. Weitere Informationen finden Sie unter [Datei Zeiten](/windows/win32/SysInfo/file-times) in der Windows SDK.

- `COleDateTime(``nYear`, ,,`nDay`,,) Erstellt ein -`COleDateTime` Objekt aus den angegebenen numerischen Werten. `nHour` `nMonth` `nMin` `nSec`

- `COleDateTime(``wDosDate`, )`wDosTime` Erstellt ein`COleDateTime` -Objekt anhand der angegebenen Datums-und Uhrzeitwerte für MS-DOS.

Weitere Informationen `time_t` zum-Datentyp finden Sie unter der [time](../../c-runtime-library/reference/time-time32-time64.md) -Funktion in der *Lauf Zeit Bibliotheks Referenz*.

Weitere Informationen finden Sie in den Strukturen [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) und [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) in der Windows SDK.

Weitere Informationen zu den Begrenzungen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

> [!NOTE]
> Der Konstruktor, `DBTIMESTAMP` der den Parameter verwendet, ist nur verfügbar, wenn "OleDb. h" enthalten ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#2](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_4.cpp)]

##  <a name="format"></a>COleDateTime:: Format

Erstellt eine formatierte Darstellung des Datums-/Uhrzeitwerts.

```
CString Format(DWORD dwFlags = 0,  LCID lcid = LANG_USER_DEFAULT) const;
CString Format(LPCTSTR lpszFormat) const;
CString Format(UINT nFormatID) const;
```

### <a name="parameters"></a>Parameter

*dwFlags*<br/>
Gibt eines der folgenden locale-Flags an:

- LOCALE_NOUSEROVERRIDE verwenden Sie anstelle der benutzerdefinierten Benutzereinstellungen die Standardeinstellungen für das System Gebiets Schema.

- VAR_TIMEVALUEONLY ignoriert den Datums Teil während der Verarbeitung.

- VAR_DATEVALUEONLY ignoriert den Zeitabschnitt während der-Verarbeitung.

*lcid*<br/>
Gibt die für die Konvertierung zu verwendende Gebiets Schema-ID an. Weitere Informationen zu sprach bezeichlern finden Sie unter [sprach](/windows/win32/Intl/language-identifiers)Bezeichner.

*lpszFormat*<br/>
Eine Formatierungs Zeichenfolge `printf` ähnlich der Formatierungs Zeichenfolge. Jeder Formatierungs Code, dem ein Prozentzeichen `%`() vorangestellt ist, wird durch `COleDateTime` die entsprechende Komponente ersetzt. Andere Zeichen in der Formatierungs Zeichenfolge werden unverändert in die zurückgegebene Zeichenfolge kopiert. Weitere Informationen finden Sie unter der Lauf Zeitfunktion " [strinf Time](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)". Der Wert und die Bedeutung der Formatierungscodes `Format` für lauten:

- `%H`Stunden des aktuellen Tages

- `%M`Minuten in der aktuellen Stunde

- `%S`Sekunden in der aktuellen Minute

- `%%`Prozentzeichen

*nFormatID*<br/>
Die Ressourcen-ID für die Format Steuerelement Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Ein `CString` , der den formatierten Datums-/Uhrzeitwert enthält.

### <a name="remarks"></a>Hinweise

Wenn der Status dieses `COleDateTime` Objekts NULL ist, ist der Rückgabewert eine leere Zeichenfolge. Wenn der Status ungültig ist, wird die Rückgabe Zeichenfolge durch die Zeichen folgen Ressource ATL_IDS_DATETIME_INVALID angegeben.

Eine kurze Beschreibung der drei Formen für diese Funktion folgt:

`Format`( *dwFlags*, *LCID*)<br/>
Dieses Formular formatiert den Wert unter Verwendung der Sprachspezifikationen (Gebiets Schema-IDs) für Datum und Uhrzeit. Mithilfe der Standardparameter druckt dieses Formular das Datum und die Uhrzeit, es sei denn, der Uhrzeit Teil ist 0 (Mitternacht). in diesem Fall wird nur das Datum gedruckt, oder der Datums Teil ist 0 (30. Dezember 1899). in diesem Fall wird nur die Zeit gedruckt. Wenn der Datums-/Uhrzeitwert 0 (30. Dezember 1899, Mitternacht) ist, druckt dieses Formular mit den Standardparametern Mitternacht.

`Format`( *lpszFormat*)<br/>
Dieses Formular formatiert den Wert mit der Format Zeichenfolge, die spezielle Formatierungscodes enthält, denen ein Prozentzeichen (%) vorangestellt ist, wie in `printf`. Die Formatierungs Zeichenfolge wird als Parameter an die Funktion übergeben. Weitere Informationen zu den Formatierungscodes finden Sie [unter "in der](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) Lauf Zeit Bibliotheks Referenz" in der Lauf Zeit Bibliotheks Referenz.

`Format`( *nFormatID*)<br/>
Dieses Formular formatiert den Wert mit der Format Zeichenfolge, die spezielle Formatierungscodes enthält, denen ein Prozentzeichen (%) vorangestellt ist, wie in `printf`. Die Formatierungs Zeichenfolge ist eine Ressource. Die ID dieser Zeichen folgen Ressource wird als-Parameter übergeben. Weitere Informationen zu den Formatierungscodes finden Sie [unter "in der](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) *Lauf Zeit Bibliotheks Referenz" in der Lauf Zeit Bibliotheks Referenz*.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#3](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_5.cpp)]

##  <a name="getasdbtimestamp"></a>COleDateTime:: getasdbtimestamp

Rufen Sie diese Methode auf, um die Zeit `COleDateTime` im Objekt `DBTIMESTAMP` als Datenstruktur zu erhalten.

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& timeStamp) const throw();
```

### <a name="parameters"></a>Parameter

*timeStamp*<br/>
Ein Verweis auf eine [DBTIMESTAMP](/dotnet/api/system.data.oledb.oledbtype) -Struktur.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Speichert die resultierende Zeit in der referenzierten Zeit *Stempel* Struktur. Für `DBTIMESTAMP` die Datenstruktur, die von dieser Funktion initialisiert `fraction` wurde, wird der Member auf NULL festgelegt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#4](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_6.cpp)]

##  <a name="getassystemtime"></a>COleDateTime:: getassystemtime

Rufen Sie diese Methode auf, um die Zeit `COleDateTime` im Objekt `SYSTEMTIME` als Datenstruktur zu erhalten.

```
bool GetAsSystemTime(SYSTEMTIME& sysTime) const throw();
```

### <a name="parameters"></a>Parameter

*sysTime*<br/>
Ein Verweis auf eine [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) -Struktur, die den konvertierten Datums-/Uhrzeitwert aus dem `COleDateTime` -Objekt empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn erfolgreich; FALSE, wenn die Konvertierung fehlschlägt oder wenn `COleDateTime` das Objekt NULL oder ungültig ist.

### <a name="remarks"></a>Hinweise

`GetAsSystemTime`speichert die resultierende Zeit im referenzierten *SysTime* -Objekt. Für `SYSTEMTIME` die Datenstruktur, die von dieser Funktion initialisiert `wMilliseconds` wurde, wird der Member auf NULL festgelegt.

Weitere Informationen zu den in einem `COleDateTime` -Objekt gespeicherten Statusinformationen finden Sie unter [GetStatus](#getstatus).

##  <a name="getasudate"></a>COleDateTime:: getasudate

Rufen Sie diese Methode auf, um die Zeit `COleDateTime` im Objekt `UDATE` als Datenstruktur zu erhalten.

```
bool GetAsUDATE(UDATE& uDate) const throw();
```

### <a name="parameters"></a>Parameter

*Update*<br/>
Ein Verweis auf eine `UDATE` -Struktur, die den konvertierten Datums-/Uhrzeitwert aus dem `COleDateTime` -Objekt empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn erfolgreich; FALSE, wenn die Konvertierung fehlschlägt oder wenn `COleDateTime` das Objekt NULL oder ungültig ist.

### <a name="remarks"></a>Hinweise

Eine `UDATE` -Struktur stellt ein "entpackte" Datum dar.

##  <a name="getcurrenttime"></a>COleDateTime:: GetCurrentTime

Diese statische Member-Funktion zum Zurückgeben des aktuellen Datums-/Uhrzeitwerts aufruft.

```
static COleDateTime WINAPI GetCurrentTime() throw();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#5](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_7.cpp)]

##  <a name="getday"></a>COleDateTime:: getDay

Ruft den Tag des Monats ab, der durch diesen Datums-/Uhrzeitwert dargestellt wird.

```
int GetDay() const throw();
```

### <a name="return-value"></a>Rückgabewert

Der Tag des Monats, der durch den Wert dieses `COleDateTime` -Objekts dargestellt wird, oder `COleDateTime::error` , wenn der Tag nicht abgerufen werden konnte.

### <a name="remarks"></a>Hinweise

Gültige Rückgabewerte liegen zwischen 1 und 31.

Informationen zu anderen Element Funktionen, die den Wert dieses `COleDateTime` Objekts Abfragen, finden Sie unter den folgenden Member-Funktionen:

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [Getdayosyear](#getdayofyear)

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#6](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_8.cpp)]

##  <a name="getdayofweek"></a>COleDateTime:: getdayolweek

Ruft den Tag des Monats ab, der durch diesen Datums-/Uhrzeitwert dargestellt wird.

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>Rückgabewert

Der Wochentag, der durch den Wert dieses `COleDateTime` -Objekts dargestellt wird, oder `COleDateTime::error` , wenn der Wochentag nicht abgerufen werden konnte.

### <a name="remarks"></a>Hinweise

Gültige Rückgabewerte liegen zwischen 1 und 7, wobei 1 = Sonntag, 2 = Montag usw.

Informationen zu anderen Element Funktionen, die den Wert dieses `COleDateTime` Objekts Abfragen, finden Sie unter den folgenden Member-Funktionen:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [Getdayosyear](#getdayofyear)

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#7](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_9.cpp)]

##  <a name="getdayofyear"></a>COleDateTime:: getdayosyear

Ruft den Tag des Jahres ab, der durch diesen Datums-/Uhrzeitwert dargestellt wird.

```
int GetDayOfYear() const throw();
```

### <a name="return-value"></a>Rückgabewert

Der Tag des Jahres, der durch den Wert dieses `COleDateTime` -Objekts dargestellt wird, oder `COleDateTime::error` , wenn der Tag des Jahres nicht abgerufen werden konnte.

### <a name="remarks"></a>Hinweise

Gültige Rückgabewerte liegen zwischen 1 und 366, wobei 1. Januar = 1 ist.

Informationen zu anderen Element Funktionen, die den Wert dieses `COleDateTime` Objekts Abfragen, finden Sie unter den folgenden Member-Funktionen:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#8](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_10.cpp)]

##  <a name="gethour"></a>COleDateTime:: GetHour

Ruft die durch diesen Datums-/Uhrzeitwert dargestellte Stunde ab.

```
int GetHour() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Stunde, die durch den Wert dieses `COleDateTime` -Objekts `COleDateTime::error` dargestellt wird, oder, wenn die Stunde nicht abgerufen werden konnte.

### <a name="remarks"></a>Hinweise

Gültige Rückgabewerte liegen zwischen 0 und 23.

Informationen zu anderen Element Funktionen, die den Wert dieses `COleDateTime` Objekts Abfragen, finden Sie unter den folgenden Member-Funktionen:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [Getdayosyear](#getdayofyear)

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#9](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_11.cpp)]

##  <a name="getminute"></a>COleDateTime:: GetMinute

Ruft die durch diesen Datums-/Uhrzeitwert dargestellte Minute ab.

```
int GetMinute() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Minute, die durch den Wert dieses `COleDateTime` -Objekts `COleDateTime::error` dargestellt wird, oder, wenn die Minute nicht abgerufen werden konnte.

### <a name="remarks"></a>Hinweise

Gültige Rückgabewerte liegen zwischen 0 und 59.

Informationen zu anderen Element Funktionen, die den Wert dieses `COleDateTime` Objekts Abfragen, finden Sie unter den folgenden Member-Funktionen:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [Getdayosyear](#getdayofyear)

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [GetHour](#gethour).

##  <a name="getmonth"></a>COleDateTime:: getMonth

Ruft den Monat ab, der durch diesen date/time-Wert dargestellt wird.

```
int GetMonth() const throw();
```

### <a name="return-value"></a>Rückgabewert

Der durch den Wert dieses `COleDateTime` -Objekts dargestellte Monat oder `COleDateTime::error` , wenn der Monat nicht abgerufen werden konnte.

### <a name="remarks"></a>Hinweise

Gültige Rückgabewerte liegen zwischen 1 und 12.

Informationen zu anderen Element Funktionen, die den Wert dieses `COleDateTime` Objekts Abfragen, finden Sie unter den folgenden Member-Funktionen:

- [GetDay](#getday)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [Getdayosyear](#getdayofyear)

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [getDay](#getday).

##  <a name="getsecond"></a>COleDateTime:: GetSecond

Ruft das zweite ab, das durch diesen Datums-/Uhrzeitwert dargestellt wird

```
int GetSecond() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die zweite, die durch den Wert dieses `COleDateTime` -Objekts `COleDateTime::error` dargestellt wird, oder, wenn die zweite nicht abgerufen werden konnte.

### <a name="remarks"></a>Hinweise

Gültige Rückgabewerte liegen zwischen 0 und 59.

> [!NOTE]
>  Die `COleDateTime` -Klasse unterstützt keine Schaltsekunden.

Weitere Informationen zur Implementierung von `COleDateTime`finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

Informationen zu anderen Element Funktionen, die den Wert dieses `COleDateTime` Objekts Abfragen, finden Sie unter den folgenden Member-Funktionen:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetDayOfWeek](#getdayofweek)

- [Getdayosyear](#getdayofyear)

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [GetHour](#gethour).

##  <a name="getstatus"></a>COleDateTime:: GetStatus

Ruft den Status (Gültigkeit) eines angegebenen `COleDateTime` -Objekts ab.

```
DateTimeStatus GetStatus() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Status dieses `COleDateTime` Werts zurück. Wenn Sie für `GetStatus` ein `COleDateTime` -Objekt, das mit dem Standardwert erstellt wurde, aufzurufen, wird gültig zurückgegeben. Wenn Sie für `GetStatus` ein `COleDateTime` -Objekt aufzurufen, das mit dem auf NULL festgelegten `GetStatus` -Konstruktor initialisiert wurde, gibt NULL zurück.

### <a name="remarks"></a>Hinweise

Der Rückgabewert wird durch den `DateTimeStatus` enumerierten Typ definiert, der in der `COleDateTime` -Klasse definiert ist.

```
enum DateTimeStatus
{
   error = -1,
   valid = 0,
   invalid = 1,    // Invalid date (out of range, etc.)
   null = 2,       // Literally has no value
};
```

Eine kurze Beschreibung dieser Statuswerte finden Sie in der folgenden Liste:

- `COleDateTime::error`Gibt an, dass ein Fehler beim Versuch aufgetreten ist, einen Teil des Datums-/Uhrzeitwerts zu erhalten.

- `COleDateTime::valid`Gibt an, `COleDateTime` dass dieses-Objekt gültig ist.

- `COleDateTime::invalid`Gibt an, `COleDateTime` dass dieses-Objekt ungültig ist, d. h., sein Wert ist möglicherweise falsch.

- `COleDateTime::null`Gibt an, `COleDateTime` dass dieses Objekt NULL ist, d. h., es wurde kein Wert für dieses Objekt angegeben. (Dies ist "Null", wenn kein Wert vorhanden ist, und nicht C++ NULL.)

Der Status eines `COleDateTime` -Objekts ist in den folgenden Fällen ungültig:

- , Wenn der Wert von einem `VARIANT` -Wert oder `COleVariant` -Wert festgelegt wird, der nicht in einen Datums-/Uhrzeitwert konvertiert werden konnte.

- , Wenn der Wert von einem `time_t`-, `SYSTEMTIME`-oder `FILETIME` -Wert festgelegt wird, der nicht in einen gültigen Datums-/Uhrzeitwert konvertiert werden konnte.

- , Wenn der Wert von `SetDateTime` mit ungültigen Parameterwerten festgelegt wird.

- , Wenn bei einem arithmetischen Zuweisungs Vorgang, nämlich oder `+=` `-=`, bei diesem-Objekt ein Überlauf oder Unterlauf aufgetreten ist.

- , Wenn diesem Objekt ein ungültiger Wert zugewiesen wurde.

- , Wenn der Status dieses Objekts mithilfe `SetStatus`von explizit auf ungültig festgelegt wurde.

Weitere Informationen zu den Vorgängen, die den Status als ungültig festlegen können, finden Sie in den folgenden Element Funktionen:

- [COleDateTime](#coledatetime)

- [SetDateTime](#setdatetime)

- [operator +, -](#operator_add_-)

- [operator +=, -=](#operator_add_eq_-_eq)

Weitere Informationen zu den Begrenzungen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#10](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_12.cpp)]

##  <a name="getyear"></a>COleDateTime:: getYear

Ruft das von diesem Datums-/Uhrzeitwert dargestellte Jahr ab.

```
int GetYear() const throw();
```

### <a name="return-value"></a>Rückgabewert

Das Jahr, das durch den Wert dieses `COleDateTime` -Objekts `COleDateTime::error` dargestellt wird, oder, wenn das Jahr nicht abgerufen werden konnte.

### <a name="remarks"></a>Hinweise

Gültige Rückgabewerte liegen zwischen 100 und 9999, einschließlich des Jahrhundert.

Informationen zu anderen Element Funktionen, die den Wert dieses `COleDateTime` Objekts Abfragen, finden Sie unter den folgenden Member-Funktionen:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [Getdayosyear](#getdayofyear)

Weitere Informationen zu den Begrenzungen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [getDay](#getday).

##  <a name="m_dt"></a>COleDateTime:: m_dt

Die zugrunde `DATE` liegende-Struktur `COleDateTime` für dieses-Objekt.

```
DATE m_dt;
```

### <a name="remarks"></a>Hinweise

> [!CAUTION]
>  Durch Ändern des Werts in `DATE` dem Objekt, auf das der von dieser Funktion zurückgegebene Zeiger zugreift, `COleDateTime` wird der Wert dieses Objekts geändert. Der Status dieses `COleDateTime` Objekts wird nicht geändert.

Weitere Informationen zur Implementierung des `DATE` -Objekts finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

##  <a name="m_status"></a>COleDateTime:: m_status

Enthält den Status dieses `COleDateTime` Objekts.

```
DateTimeStatus m_status;
```

### <a name="remarks"></a>Hinweise

Der Typ dieses Datenmembers ist der Enumerationstyp `DateTimeStatus`, der in der `COleDateTime` -Klasse definiert ist. Weitere Informationen finden Sie unter [COleDateTime:: GetStatus](#getstatus).

> [!CAUTION]
>  Dieser Datenmember ist für erweiterte Programmier Situationen vorgesehen. Sie sollten die Inline Member-Funktionen [GetStatus](#getstatus) und [SetStatus](#setstatus)verwenden. Weitere `SetStatus` Vorsichtsmaßnahmen bezüglich der expliziten Festlegung dieses Datenmembers finden Sie unter.

##  <a name="operator_eq"></a>COleDateTime:: Operator =

Kopiert einen `COleDateTime` Wert.

```
COleDateTime& operator=(const VARIANT& varSrc) throw();
COleDateTime& operator=(DATE dtSrc) throw();
COleDateTime& operator=(const time_t& timeSrc) throw();
COleDateTime& operator=(const __time64_t& timeSrc) throw();
COleDateTime& operator=(const SYSTEMTIME& systimeSrc) throw();
COleDateTime& operator=(const FILETIME& filetimeSrc) throw();
COleDateTime& operator=(const UDATE& uDate) throw();
```

### <a name="remarks"></a>Hinweise

Diese überladenen Zuweisungs Operatoren kopieren den Quell Datums- `COleDateTime` /Uhrzeitwert in dieses Objekt. Eine kurze Beschreibung der einzelnen überladenen Zuweisungs Operatoren folgt:

- **Operator = (** `dateSrc` **)** der Wert und der Status des Operanden werden in dieses `COleDateTime` Objekt kopiert.

- **Operator = (** *varSrc* **)** Wenn die Konvertierung des [Variant](/windows/win32/api/oaidl/ns-oaidl-variant) -Werts (oder des [COleVariant](../../mfc/reference/colevariant-class.md) -Objekts) in ein Datum/Uhrzeit-Objekt (VT_DATE) erfolgreich ist, wird der konvertierte Wert in dieses `COleDateTime` Objekt kopiert, und sein Status ist auf "valid" festgelegt. Wenn die Konvertierung nicht erfolgreich ist, wird der Wert dieses Objekts auf NULL (30. Dezember 1899, Mitternacht) und seinen Status auf ungültig festgelegt.

- **Operator = (** `dtSrc` **)** der `DATE` Wert wird in dieses `COleDateTime` Objekt kopiert, und sein Status ist auf "gültig" festgelegt.

- **Operator = (** `timeSrc` **)** der `time_t` - `__time64_t` Wert oder der-Wert wird konvertiert `COleDateTime` und in dieses-Objekt kopiert. Wenn die Konvertierung erfolgreich ist, wird der Status dieses Objekts auf gültig festgelegt. Wenn nicht erfolgreich, wird der Wert auf ungültig festgelegt.

- **Operator = (** *systimesrc* **)** Der [System Time](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) -Wert wird konvertiert und in dieses `COleDateTime` -Objekt kopiert. Wenn die Konvertierung erfolgreich ist, wird der Status dieses Objekts auf gültig festgelegt. Wenn nicht erfolgreich, wird der Wert auf ungültig festgelegt.

- **Operator = (** `uDate` **)** der `UDATE` Wert wird konvertiert und in dieses `COleDateTime` Objekt kopiert. Wenn die Konvertierung erfolgreich ist, wird der Status dieses Objekts auf gültig festgelegt. Wenn nicht erfolgreich, wird der Wert auf ungültig festgelegt. Eine `UDATE` -Struktur stellt ein "entpackte" Datum dar. Weitere Informationen finden Sie unter der Funktion [vardatefromudate](/windows/win32/api/oleauto/nf-oleauto-vardatefromudate).

- **Operator = (** `filetimeSrc` **)** der [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) -Wert wird konvertiert und in dieses `COleDateTime` Objekt kopiert. Wenn die Konvertierung erfolgreich ist, wird der Status dieses Objekts auf gültig festgelegt. Andernfalls ist Sie auf ungültig festgelegt. `FILETIME`verwendet Universal koordinierte Zeit (UTC). Wenn Sie also eine UTC-Zeit in der Struktur übergeben, werden die Ergebnisse von UTC-Zeit in lokale Zeit konvertiert und als Variant-Zeit gespeichert. Dieses Verhalten entspricht dem Verhalten in Visual C++ 6,0 und Visual C++.NET 2003 SP2. Weitere Informationen finden Sie unter [Datei Zeiten](/windows/win32/SysInfo/file-times) in der Windows SDK.

Weitere Informationen finden Sie unter dem [Variant](/windows/win32/api/oaidl/ns-oaidl-variant) -Eintrag in der Windows SDK.

Weitere Informationen `time_t` zum-Datentyp finden Sie unter der [time](../../c-runtime-library/reference/time-time32-time64.md) -Funktion in der *Lauf Zeit Bibliotheks Referenz*.

Weitere Informationen finden Sie in den Strukturen [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) und [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) in der Windows SDK.

Weitere Informationen zu den Begrenzungen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

##  <a name="operator_add_-"></a>COleDateTime:: Operator +,-

Werte hinzufügen und `ColeDateTime` subtrahieren.

```
COleDateTime operator+(COleDateTimeSpan dateSpan) const throw();
COleDateTime operator-(COleDateTimeSpan dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTime& date) const throw();
```

### <a name="remarks"></a>Hinweise

`COleDateTime`-Objekte stellen Absolute Zeiten dar. [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md) -Objekte stellen relative Zeiten dar. Mit den ersten beiden Operatoren können Sie einen `COleDateTimeSpan` Wert hinzufügen und von einem `COleDateTime` Wert subtrahieren. Mit dem dritten Operator können Sie einen `COleDateTime` Wert von einem anderen subtrahieren, um einen `COleDateTimeSpan` Wert zu erhalten.

Wenn einer der Operanden NULL ist, ist der Status des resultierenden `COleDateTime` Werts Null.

Wenn der resultierende `COleDateTime` Wert außerhalb der Grenzen zulässiger Werte liegt, ist der Status dieses `COleDateTime` Werts ungültig.

Wenn einer der Operanden ungültig ist und der andere nicht NULL ist, ist der Status des resultierenden `COleDateTime` Werts ungültig.

Der **+** - **-** Operator und der-Operator `COleDateTime` bestätigen, dass das-Objekt auf NULL festgelegt ist. Ein Beispiel finden Sie unter [COleDateTime relational Operators](#coledatetime_relational_operators) .

Weitere Informationen zu den gültigen, ungültigen und NULL-Status Werten finden Sie in der [m_status](#m_status) Member-Variable.

Weitere Informationen zu den Begrenzungen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#12](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_13.cpp)]

##  <a name="operator_add_eq_-_eq"></a>COleDateTime:: Operator + =,-=

Fügen Sie einen `ColeDateTime` Wert zu diesem `COleDateTime` Objekt hinzu, und subtrahieren Sie

```
COleDateTime& operator+=(COleDateTimeSpan dateSpan) throw();
COleDateTime& operator-=(COleDateTimeSpan dateSpan) throw();
```

### <a name="remarks"></a>Hinweise

Diese Operatoren ermöglichen es Ihnen, einen `COleDateTimeSpan` Wert zu und von diesem `COleDateTime`hinzuzufügen und zu subtrahieren. Wenn einer der Operanden NULL ist, ist der Status des resultierenden `COleDateTime` Werts Null.

Wenn der resultierende `COleDateTime` Wert außerhalb der Grenzen zulässiger Werte liegt, wird der Status dieses `COleDateTime` Werts auf ungültig festgelegt.

Wenn einer der Operanden ungültig ist und der Wert nicht NULL ist, ist der Status des resultierenden `COleDateTime` Werts ungültig.

Weitere Informationen zu den gültigen, ungültigen und NULL-Status Werten finden Sie in der [m_status](#m_status) Member-Variable.

Der **+=** - **-=** Operator und der-Operator `COleDateTime` bestätigen, dass das-Objekt auf NULL festgelegt ist. Ein Beispiel finden Sie unter [COleDateTime relational Operators](#coledatetime_relational_operators) .

Weitere Informationen zu den Begrenzungen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

##  <a name="operator_date"></a>COleDateTime:: Operator Date

Konvertiert einen `ColeDateTime` Wert in einen `DATE`.

```
operator DATE() const throw();
```

### <a name="remarks"></a>Hinweise

Dieser Operator gibt ein `DATE` -Objekt zurück, dessen Wert aus `COleDateTime` diesem-Objekt kopiert wird. Weitere Informationen zur Implementierung des `DATE` -Objekts finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

Der `DATE` Operator bestätigt, wenn das `COleDateTime` Objekt auf NULL festgelegt ist. Ein Beispiel finden Sie unter [COleDateTime relational Operators](#coledatetime_relational_operators) .

##  <a name="parsedatetime"></a>COleDateTime::P arenddatetime

Analysiert eine Zeichenfolge, um einen Datums-/Uhrzeitwert zu lesen.

```
bool ParseDateTime(
    LPCTSTR lpszDate,
    DWORD dwFlags = 0,
    LCID lcid = LANG_USER_DEFAULT) throw();
```

### <a name="parameters"></a>Parameter

*lpszDate*<br/>
Ein Zeiger auf die mit NULL endende Zeichenfolge, die analysiert werden soll. Einzelheiten finden Sie unter "Hinweise".

*dwFlags*<br/>
Gibt Flags für Gebiets Schema Einstellungen und die-Verarbeitung an. Mindestens eines der folgenden Flags:

- LOCALE_NOUSEROVERRIDE verwenden Sie anstelle der benutzerdefinierten Benutzereinstellungen die Standardeinstellungen für das System Gebiets Schema.

- VAR_TIMEVALUEONLY ignoriert den Datums Teil während der Verarbeitung.

- VAR_DATEVALUEONLY ignoriert den Zeitabschnitt während der-Verarbeitung.

*lcid*<br/>
Gibt die für die Konvertierung zu verwendende Gebiets Schema-ID an.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Zeichenfolge erfolgreich in einen Datums-/Uhrzeitwert konvertiert wurde, andernfalls false.

### <a name="remarks"></a>Hinweise

Wenn die Zeichenfolge erfolgreich in einen Datums-/Uhrzeitwert konvertiert wurde, wird `COleDateTime` der Wert dieses Objekts auf diesen Wert und seinen Status auf gültig festgelegt.

> [!NOTE]
>  Jahreswerte müssen zwischen 100 und 9999 (einschließlich) liegen.

Der *lpszdate* -Parameter kann eine Vielzahl von Formaten annehmen. Die folgenden Zeichen folgen enthalten beispielsweise akzeptable Datums-/Uhrzeitformate:

`"25 January 1996"`

`"8:30:00"`

`"20:30:00"`

`"January 25, 1996 8:30:00"`

`"8:30:00 Jan. 25, 1996"`

`"1/25/1996 8:30:00"  // always specify the full year, even in a 'short date' format`

Die Gebiets Schema-ID beeinflusst auch, ob das Zeichen folgen Format für die Konvertierung in einen Datums-/Uhrzeitwert zulässig ist.

Im Fall von VAR_DATEVALUEONLY wird der Uhrzeitwert auf time 0 oder Mitternacht festgelegt. Im Fall von VAR_TIMEVALUEONLY ist der Date-Wert auf Date 0 festgelegt, d. h. 30. Dezember 1899.

Wenn die Zeichenfolge nicht in einen Datums-/Uhrzeitwert konvertiert werden konnte oder ein numerischer Überlauf aufgetreten ist, ist `COleDateTime` der Status dieses Objekts ungültig.

Weitere Informationen zu den Begrenzungen und zur Implementierung von `COleDateTime` Werten finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

##  <a name="setdate"></a>COleDateTime:: setDate

Legt das Datum dieses `COleDateTime` -Objekts fest.

```
int SetDate(
    int nYear,
    int nMonth,
    int nDay) throw();
```

### <a name="parameters"></a>Parameter

*nyear*, *nmonth*, *NDAY*<br/>
Geben Sie die Datums Komponenten an, die in `COleDateTime` dieses Objekt kopiert werden sollen.

### <a name="return-value"></a>Rückgabewert

0 (null), wenn `COleDateTime` der Wert dieses Objekts erfolgreich festgelegt wurde, andernfalls 1. Dieser Rückgabewert basiert auf dem `DateTimeStatus` enumerierten Typ. Weitere Informationen finden Sie unter der [SetStatus](#setstatus) -Member-Funktion.

### <a name="remarks"></a>Hinweise

Das Datum wird auf die angegebenen Werte festgelegt. Die Uhrzeit wird auf die Zeit 0, Mitternacht festgelegt.

In der folgenden Tabelle finden Sie die Grenzen für die Parameterwerte:

|Parameter|Fugen|
|---------------|------------|
|*nYear*|100 - 9999|
|*nMonth*|1 - 12|
|*nDay*|0 - 31|

Wenn der Tag des Monats überschreitet, wird es in den richtigen Tag des nächsten Monats konvertiert, und der Monat und/oder das Jahr wird entsprechend erhöht. Der tagewert 0 (null) gibt den letzten Tag des vorherigen Monats an. Das Verhalten entspricht `SystemTimeToVariantTime`.

Wenn der von den Parametern angegebene Datumswert ungültig ist, wird der Status dieses Objekts auf `COleDateTime::invalid`festgelegt. Sie sollten [GetStatus](#getstatus) verwenden, um die Gültigkeit des `DATE` Werts zu überprüfen. Sie sollten nicht davon ausgehen, dass der Wert von [m_dt](#m_dt) unverändert bleibt.

Im folgenden finden Sie einige Beispiele für Datumswerte:

|*nYear*|*nMonth*|*nDay*|Wert|
|-------------|--------------|------------|-----------|
|2000|2|29|29. Februar 2000|
|1776|7|4|4\. Juli 1776|
|1925|4|35|35. April 1925 (ungültiges Datum)|
|10000|1|1|1\. Januar 10000 (ungültiges Datum)|

Informationen zum Festlegen von Datum und Uhrzeit finden Sie unter [COleDateTime:: SetDateTime](#setdatetime).

Informationen zu Element Funktionen, mit denen der Wert dieses `COleDateTime` Objekts abgefragt wird, finden Sie unter den folgenden Member-Funktionen:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [Getdayosyear](#getdayofyear)

Weitere Informationen zu den Begrenzungen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#11](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_14.cpp)]

##  <a name="setdatetime"></a>COleDateTime:: SetDateTime

Legt das Datum und die Uhrzeit dieses `COleDateTime` -Objekts fest.

```
int SetDateTime(
    int nYear,
    int nMonth,
    int nDay,
    int nHour,
    int nMin,
    int nSec) throw();
```

### <a name="parameters"></a>Parameter

*nyear*, *nmonth*, *NDAY*, *nHour*, *nmin*, *nsec*<br/>
Geben Sie die Datums-und Uhrzeit Komponenten an, die `COleDateTime` in dieses Objekt kopiert werden sollen.

### <a name="return-value"></a>Rückgabewert

0 (null), wenn `COleDateTime` der Wert dieses Objekts erfolgreich festgelegt wurde, andernfalls 1. Dieser Rückgabewert basiert auf dem `DateTimeStatus` enumerierten Typ. Weitere Informationen finden Sie unter der [SetStatus](#setstatus) -Member-Funktion.

### <a name="remarks"></a>Hinweise

In der folgenden Tabelle finden Sie die Grenzen für die Parameterwerte:

|Parameter|Fugen|
|---------------|------------|
|*nYear*|100 - 9999|
|*nMonth*|1 - 12|
|*nDay*|0 - 31|
|*nHour*|0 - 23|
|*nMin*|0 - 59|
|*nSec*|0 - 59|

Wenn der Tag des Monats überschreitet, wird es in den richtigen Tag des nächsten Monats konvertiert, und der Monat und/oder das Jahr wird entsprechend erhöht. Der tagewert 0 (null) gibt den letzten Tag des vorherigen Monats an. Das Verhalten ist identisch mit der [systemtimeto varianttime](/windows/win32/api/oleauto/nf-oleauto-systemtimetovarianttime).

Wenn der von den Parametern angegebene Datums-oder Uhrzeitwert ungültig ist, wird der Status dieses Objekts auf "ungültig" festgelegt, und der Wert dieses Objekts wird nicht geändert.

Im folgenden finden Sie einige Beispiele für Zeit Werte:

|*nHour*|*nMin*|*nSec*|Wert|
|-------------|------------|------------|-----------|
|1|3|3|01:03:03|
|23|45|0|23:45:00|
|25|30|0|Ungültig|
|9|60|0|Ungültig|

Im folgenden finden Sie einige Beispiele für Datumswerte:

|*nYear*|*nMonth*|*nDay*|Wert|
|-------------|--------------|------------|-----------|
|1995|4|15|15. April 1995|
|1789|7|14|17. Juli 1789|
|1925|2|30|Ungültig|
|10000|1|1|Ungültig|

Informationen zum Festlegen des Datums finden Sie unter [COleDateTime:: setDate](#setdate). Informationen zum Festlegen der Zeit, finden Sie unter [COleDateTime:: setTime](#settime).

Informationen zu Element Funktionen, mit denen der Wert dieses `COleDateTime` Objekts abgefragt wird, finden Sie unter den folgenden Member-Funktionen:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [Getdayosyear](#getdayofyear)

Weitere Informationen zu den Begrenzungen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für " [GetStatus](#getstatus)".

##  <a name="setstatus"></a>COleDateTime:: SetStatus

Legt den Status dieses `COleDateTime` Objekts fest.

```
void SetStatus(DateTimeStatus status) throw();
```

### <a name="parameters"></a>Parameter

*Status*<br/>
Der neue Statuswert für dieses `COleDateTime` -Objekt.

### <a name="remarks"></a>Hinweise

Der *Status* Parameterwert wird durch den `DateTimeStatus` enumerierten Typ definiert, der in der `COleDateTime` -Klasse definiert ist. Weitere Informationen finden Sie unter [COleDateTime:: GetStatus](#getstatus) .

> [!CAUTION]
>  Diese Funktion ist für erweiterte Programmier Situationen vorgesehen. Diese Funktion ändert nicht die Daten in diesem-Objekt. Es wird am häufigsten verwendet, um den Status auf **null** oder **ungültig**festzulegen. Der Zuweisungs Operator ([Operator =](#operator_eq)) und [SetDateTime](#setdatetime) legen den Status des Objekts auf der Grundlage der Quell Werte fest.

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für " [GetStatus](#getstatus)".

##  <a name="settime"></a>COleDateTime:: setTime

Legt die Zeit dieses `COleDateTime` -Objekts fest.

```
int SetTime(
    int nHour,
    int nMin,
    int nSec) throw();
```

### <a name="parameters"></a>Parameter

*nstunde*, *nmin*., *nSek* .<br/>
Geben Sie die Zeit Komponenten an, die in `COleDateTime` dieses Objekt kopiert werden sollen.

### <a name="return-value"></a>Rückgabewert

0 (null), wenn `COleDateTime` der Wert dieses Objekts erfolgreich festgelegt wurde, andernfalls 1. Dieser Rückgabewert basiert auf dem `DateTimeStatus` enumerierten Typ. Weitere Informationen finden Sie unter der [SetStatus](#setstatus) -Member-Funktion.

### <a name="remarks"></a>Hinweise

Die Zeit wird auf die angegebenen Werte festgelegt. Das Datum wird auf Date 0 festgelegt, d. h. 30. Dezember 1899.

In der folgenden Tabelle finden Sie die Grenzen für die Parameterwerte:

|Parameter|Fugen|
|---------------|------------|
|*nHour*|0 - 23|
|*nMin*|0 - 59|
|*nSec*|0 - 59|

Wenn der von den Parametern angegebene Zeitwert nicht gültig ist, wird der Status dieses Objekts auf ungültig festgelegt, und der Wert dieses Objekts wird nicht geändert.

Im folgenden finden Sie einige Beispiele für Zeit Werte:

|*nHour*|*nMin*|*nSec*|Wert|
|-------------|------------|------------|-----------|
|1|3|3|01:03:03|
|23|45|0|23:45:00|
|25|30|0|Ungültig|
|9|60|0|Ungültig|

Informationen zum Festlegen von Datum und Uhrzeit finden Sie unter [COleDateTime:: SetDateTime](#setdatetime).

Informationen zu Element Funktionen, mit denen der Wert dieses `COleDateTime` Objekts abgefragt wird, finden Sie unter den folgenden Member-Funktionen:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [Getdayosyear](#getdayofyear)

Weitere Informationen zu den Begrenzungen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [setDate](#setdate).

## <a name="see-also"></a>Siehe auch

[COleVariant-Klasse](../../mfc/reference/colevariant-class.md)<br/>
[CTime-Klasse](../../atl-mfc-shared/reference/ctime-class.md)<br/>
[CTimeSpan-Klasse](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Gemeinsam genutzte ATL/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)
