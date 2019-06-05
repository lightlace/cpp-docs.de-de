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
ms.openlocfilehash: 63c2971f5d55cb5198925650bcf90b2f1a8b0958
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503227"
---
# <a name="coledatetime-class"></a>COleDateTime-Klasse

Kapselt die `DATE` -Datentyp, der in der OLE-Automatisierung verwendet wird.

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
|[COleDateTime::Format](#format)|Generiert eine formatierte Zeichenfolgendarstellung einer `COleDateTime` Objekt.|
|[COleDateTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|Rufen Sie diese Methode zum Abrufen der Zeit in die `COleDateTime` als Objekt ein `DBTIMESTAMP` Datenstruktur.|
|[COleDateTime::GetAsSystemTime](#getassystemtime)|Rufen Sie diese Methode zum Abrufen der Zeit in die `COleDateTime` als Objekt ein [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) Datenstruktur.|
|[COleDateTime::GetAsUDATE](#getasudate)|Rufen Sie diese Methode zum Abrufen der Zeit in die `COleDateTime` als eine `UDATE` Datenstruktur.|
|[COleDateTime::GetCurrentTime](#getcurrenttime)|Erstellt eine `COleDateTime` -Objekt, das die aktuelle Uhrzeit (statische Memberfunktion) darstellt.|
|[COleDateTime::GetDay](#getday)|Gibt den Tag dies `COleDateTime` Objekt darstellt (1-31).|
|[COleDateTime::GetDayOfWeek](#getdayofweek)|Gibt den Tag der Woche zurück dies `COleDateTime` -Objekt darstellt, die (Sonntag = 1).|
|[COleDateTime::GetDayOfYear](#getdayofyear)|Gibt den Tag des Jahres zurück dies `COleDateTime` -Objekt darstellt, die (1. Januar = 1).|
|[COleDateTime::GetHour](#gethour)|Gibt die Stunde dies `COleDateTime` -Objekt darstellt (0 - 23).|
|[COleDateTime::GetMinute](#getminute)|Gibt die Minute zurück, dies `COleDateTime` -Objekt darstellt (0 - 59).|
|[COleDateTime::GetMonth](#getmonth)|Gibt den Monat zurück, dies `COleDateTime` Objekt darstellt (1-12).|
|[COleDateTime::GetSecond](#getsecond)|Gibt die Sekunde zurück, dies `COleDateTime` -Objekt darstellt (0 - 59).|
|[COleDateTime::GetStatus](#getstatus)|Ruft ab, der den Status (Gültigkeit) `COleDateTime` Objekt.|
|[COleDateTime::GetYear](#getyear)|Gibt dem Jahr dies `COleDateTime` -Objekt darstellt.|
|[COleDateTime::ParseDateTime](#parsedatetime)|Liest einen Datum/Uhrzeit-Wert aus einer Zeichenfolge und legt den Wert der `COleDateTime`.|
|[COleDateTime::SetDate](#setdate)|Legt den Wert dieses `COleDateTime` Objekt mit dem angegebenen DATEONLY-Wert.|
|[COleDateTime::SetDateTime](#setdatetime)|Legt den Wert dieses `COleDateTime` Objekt, das die angegebenen Datums-/Zeitwert entspricht.|
|[COleDateTime::SetStatus](#setstatus)|Legt den Status (Gültigkeit) dieses `COleDateTime` Objekt.|
|[COleDateTime::SetTime](#settime)|Legt den Wert dieses `COleDateTime` Objekt mit dem angegebenen nur-Wert.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[COleDateTime:: Operator ==, COleDateTime:: Operator < usw..](#coledatetime_relational_operators)|Vergleichen Sie zwei `COleDateTime` Werte.|
|[COleDateTime:: Operator +, COleDateTime:: Operator-](#operator_add_-)|Addition und Subtraktion `COleDateTime` Werte.|
|[COleDateTime::operator +=, COleDateTime::operator -=](#operator_add_eq_-_eq)|Addition und Subtraktion ein `COleDateTime` Wert aus diesem `COleDateTime` Objekt.|
|[COleDateTime::operator =](#operator_eq)|Kopiert ein `COleDateTime` Wert.|
|[COleDateTime:: Operator, Datum, Datum des COleDateTime:: Operator *](#operator_date)|Konvertiert eine `COleDateTime` -Wert in eine `DATE` oder `DATE*`.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COleDateTime::m_dt](#m_dt)|Enthält die zugrunde liegende `DATE` für diesen `COleDateTime` Objekt.|
|[COleDateTime::m_status](#m_status)|Enthält den Status dieser `COleDateTime` Objekt.|

## <a name="remarks"></a>Hinweise

`COleDateTime` eine Basisklasse keinen.

Es ist eine der möglichen Typen für die [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) -Datentyp der OLE-Automatisierung. Ein `COleDateTime` Wert darstellt, ein absolutes Datum und Uhrzeit-Wert.

Die `DATE` Typ wird als Gleitkommawert implementiert. Tage werden aus dem 30. Dezember 1899 wieder, um Mitternacht gemessen. Die folgende Tabelle zeigt einige Daten und die zugehörigen Werte an:

|Datum|Wert|
|----------|-----------|
|Am 29. Dezember 1899 Mitternacht|-1.0|
|29. Dezember 1899, 6 Uhr an|-1.25|
|Dem 30. Dezember 1899 wieder, Mitternacht|0.0|
|Am 31. Dezember 1899 Mitternacht|1.0|
|1. Januar 1900, 6 Uhr morgens|2.25|

> [!CAUTION]
> In der obigen Tabelle Obwohl die Tageswerte vor dem 30. Dezember 1899 wieder, Mitternacht negativ werden nicht Zeit des Tages Werte. 06:00 Uhr wird z. B. immer durch einen Teilwert 0,25 unabhängig davon, ob die ganze Zahl, die den Tag darstellt (nach dem 30. Dezember 1899 wieder) positiv oder negativ (vor dem 30. Dezember 1899 wieder) dargestellt. Dies bedeutet, dass versehentlich ein einfachen floating-Point-Vergleich sortieren würde eine `COleDateTime` für 6:00 auf 12/29/1899 als **später** , die als 7:00 Uhr am selben Tag darstellt.

Die `COleDateTime` Klasse verarbeitet Datumsangaben ab dem 1. Januar 100 bis zum 31. Dezember 9999. Die `COleDateTime` Klasse verwendet den gregorianischen Kalender; julianischen wird nicht unterstützt. `COleDateTime` Sommerzeit wird ignoriert. (Finden Sie unter [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).)

> [!NOTE]
> Sie können die `%y` Format, um eine zweistellige Jahresangabe nur für Datumsangaben beginnend mit 1900 abzurufen. Bei Verwendung der `%y` Format in ein Datum vor 1900, den Code generiert einen Assertionsfehler.

Dieser Typ wird auch verwendet, um nur das Datum oder ausschließlich zeitbezogene Werte darzustellen. Gemäß der Konvention das Datum 0 (30. Dezember 1899) wird verwendet, nur Werte aus, und Zeitpunkt 00:00 (Mitternacht) ist für ausschließlich datumsbezogene Werte verwendet.

Bei der Erstellung einer `COleDateTime` Objekt ein Datum mit weniger als 100 ist, das Datum wird akzeptiert, aber nachfolgende Aufrufe von `GetYear`, `GetMonth`, `GetDay`, `GetHour`, `GetMinute`, und `GetSecond` fehl, und geben-1 zurück. Früher zweistellige Datumsangaben können, aber die Datumsangaben liegen müssen, 100 oder größer in MFC 4.2 und höher.

Um Probleme zu vermeiden, geben Sie ein Datum für die vier Ziffern. Zum Beispiel:

[!code-cpp[NVC_ATLMFC_Utilities#1](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_1.cpp)]

Grundlegende arithmetische Operationen für die `COleDateTime` Werte verwenden Sie die begleitende Klasse [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md). `COleDateTimeSpan` definieren ein bestimmten Zeitintervalls. Die Beziehung zwischen diesen Klassen ist ähnlich der zwischen [CTime](../../atl-mfc-shared/reference/ctime-class.md) und [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).

Weitere Informationen zu den `COleDateTime` und `COleDateTimeSpan` Klassen finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

## <a name="requirements"></a>Anforderungen

**Header:** ATLComTime.h

##  <a name="coledatetime_relational_operators"></a>  COleDateTime-Operatoren (Relational)

Vergleichsoperatoren.

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
>  Ein ATLASSERT treten auf, wenn eine der beiden Operanden ist ungültig.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#13](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_2.cpp)]

### <a name="example"></a>Beispiel

Die Operatoren **>=** , **\< =** , **>** , und **<** , Wenn bestätigt die `COleDateTime` Objekts wird festgelegt auf Null.

[!code-cpp[NVC_ATLMFC_Utilities#170](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_3.cpp)]

##  <a name="coledatetime"></a>  COleDateTime::COleDateTime

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
Eine vorhandene `COleDateTime` Objekt, das in die neue kopiert werden `COleDateTime` Objekt.

*varSrc*<br/>
Eine vorhandene `VARIANT` Datenstruktur (möglicherweise eine `COleVariant` Objekt) in einen Datum/Uhrzeit-Wert (VT_DATE) konvertiert werden, und kopiert in das neue `COleDateTime` Objekt.

*dtSrc*<br/>
Eine Datum/Uhrzeit (`DATE`) Wert, der in die neue kopiert werden `COleDateTime` Objekt.

*timeSrc*<br/>
Ein `time_t` oder `__time64_t` Wert in einen Datum/Uhrzeit-Wert konvertiert werden, und kopiert in das neue `COleDateTime` Objekt.

*systimeSrc*<br/>
Ein `SYSTEMTIME` Struktur in einen Datum/Uhrzeit-Wert konvertiert werden, und kopiert in das neue `COleDateTime` Objekt.

*filetimeSrc*<br/>
Ein `FILETIME` Struktur in einen Datum/Uhrzeit-Wert konvertiert werden, und kopiert in das neue `COleDateTime` Objekt. Ein `FILETIME` verwendet die koordinierte Weltzeit (UTC), also wenn Sie eine lokale Zeit in der Struktur übergeben, die Ergebnisse nicht korrekt. Finden Sie unter [Dateizeitangaben](/windows/desktop/SysInfo/file-times) im Windows SDK für Weitere Informationen.

*nYear*, *nMonth*, *nDay*, *nHour*, *nMin*, *nSec*<br/>
Geben Sie Werte für Datum und Uhrzeit in die neue kopiert werden `COleDateTime` Objekt.

*wDosDate*, *wDosTime*<br/>
MS-DOS-Datum und Uhrzeit-Werte in einen Datum/Uhrzeit-Wert konvertiert werden, und kopiert in das neue `COleDateTime` Objekt.

*timeStamp*<br/>
Ein Verweis auf eine [DBTimeStamp](/dotnet/api/system.data.oledb.oledbtype) Struktur, die die aktuelle lokale Uhrzeit enthält.

### <a name="remarks"></a>Hinweise

Alle diese Konstruktoren erstellen neue `COleDateTime` Objekte, die auf den angegebenen Wert initialisiert. Die folgende Tabelle zeigt die gültigen Bereiche für die einzelnen Komponenten für Datum und Uhrzeit:

|Datum/Uhrzeit-Komponente|Gültiger Bereich|
|--------------------------|-----------------|
|Jahr|100 - 9999|
|Monat|0 - 12|
|Tag|0 - 31|
|Stunde|0 - 23|
|Minute|0 - 59|
|second|0 - 59|

Beachten Sie, die die tatsächlichen Obergrenze für die Komponente "Tag" variiert basierend auf den Monat und Jahr-Komponenten. Weitere Informationen finden Sie unter den `SetDate` oder `SetDateTime` Memberfunktionen.

Es folgt eine kurze Beschreibung jeder Konstruktor:

- `COleDateTime(` **)** Erstellt eine `COleDateTime` Objekt mit 0 (Mitternacht am 30. Dezember 1899) initialisiert.

- `COleDateTime(` `dateSrc` **)** Erstellt eine `COleDateTime` -Objekt aus einem vorhandenen `COleDateTime` Objekt.

- `COleDateTime(` *VarSrc* **)** erstellt eine `COleDateTime` Objekt. Versucht, Konvertieren einer `VARIANT` Struktur oder [COleVariant](../../mfc/reference/colevariant-class.md) Objekt, das einen Datum/Uhrzeit ( `VT_DATE`) Wert. Wenn die Konvertierung erfolgreich ist, wird der konvertierte Wert in die neue kopiert `COleDateTime` Objekt. Ist dies nicht der Fall, den Wert des der `COleDateTime` Objekt auf 0 (Mitternacht am 30. Dezember 1899) und dessen Status als ungültig festgelegt ist.

- `COleDateTime(` `dtSrc` **)** Erstellt eine `COleDateTime` -Objekt aus einem `DATE` Wert.

- `COleDateTime(` `timeSrc` **)** Erstellt eine `COleDateTime` -Objekt aus einem `time_t` Wert.

- `COleDateTime(` *SystimeSrc* **)** erstellt eine `COleDateTime` -Objekt aus einem `SYSTEMTIME` Wert.

- `COleDateTime(` `filetimeSrc` **)** Erstellt eine `COleDateTime` -Objekt aus einem `FILETIME` Wert. sein. Ein `FILETIME` verwendet die koordinierte Weltzeit (UTC), also wenn Sie eine lokale Zeit in der Struktur übergeben, die Ergebnisse nicht korrekt. Weitere Informationen finden Sie unter [Dateizeitangaben](/windows/desktop/SysInfo/file-times) im Windows SDK.

- `COleDateTime(` `nYear``nMonth`, `nDay`, `nHour`, `nMin`, `nSec` **)** Erstellt eine `COleDateTime` Objekt aus der angegebenen numerischen Werte.

- `COleDateTime(` `wDosDate``wDosTime` **)** Erstellt eine `COleDateTime` Objekt aus der angegebenen Werte von MS-DOS-Datum und Uhrzeit.

Weitere Informationen zu den `time_t` -Datentyp, finden Sie die [Zeit](../../c-runtime-library/reference/time-time32-time64.md) Funktion in der *Run-Time Library Reference*.

Weitere Informationen finden Sie unter den [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) und [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) Strukturen im Windows SDK.

Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

> [!NOTE]
> Der Konstruktor mit `DBTIMESTAMP` Parameter ist nur verfügbar, wenn "OleDb.h" enthalten ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#2](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_4.cpp)]

##  <a name="format"></a>  COleDateTime::Format

Erstellt eine formatierte Darstellung des Datum/Uhrzeit-Werts.

```
CString Format(DWORD dwFlags = 0,  LCID lcid = LANG_USER_DEFAULT) const;
CString Format(LPCTSTR lpszFormat) const;
CString Format(UINT nFormatID) const;
```

### <a name="parameters"></a>Parameter

*dwFlags*<br/>
Gibt an, um eine der folgenden Gebietsschemas:

- LOCALE_NOUSEROVERRIDE verwenden die Standardeinstellungen des Systems Gebietsschema, anstelle von benutzerdefinierten Einstellungen.

- VAR_TIMEVALUEONLY ignorieren den Datumsteil während der Analyse.

- VAR_DATEVALUEONLY ignorieren den Time-Teil, bei der Analyse.

*lcid*<br/>
Gibt die Gebietsschema-ID, für die Konvertierung verwendet. Weitere Informationen zu Sprachen-IDs finden Sie unter [Sprachen-IDs](/windows/desktop/Intl/language-identifiers).

*lpszFormat*<br/>
Eine Formatierungszeichenfolge ähnelt der `printf` Formatierungszeichenfolge. Jede Formatieren von Code, der Prozentsatz vorangestellt ( `%`) anmelden, wird mit den entsprechenden ersetzt `COleDateTime` Komponente. Andere Zeichen in der Formatierungszeichenfolge werden auf die zurückgegebene Zeichenfolge unverändert kopiert. Weitere Informationen finden Sie die Laufzeitfunktion [Strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md). Der Wert und die Bedeutung der Formatierungscodes für `Format` sind:

- `%H` In den aktuellen Tag Stunden

- `%M` In der aktuellen Stunde Minuten

- `%S` In der aktuellen Minute Sekunden

- `%%` Prozentzeichen

*nFormatID*<br/>
Die Ressourcen-ID für die Format-Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Ein `CString` , enthält die formatierte Datums-/Zeitwert entspricht.

### <a name="remarks"></a>Hinweise

Wenn der Status dieser `COleDateTime` Objekt null ist. der zurückgegebene Wert ist eine leere Zeichenfolge. Wenn der Status ungültig ist, wird die zurückgegebene Zeichenfolge durch die Zeichenfolgenressource ATL_IDS_DATETIME_INVALID angegeben.

Eine kurze Beschreibung der drei Formen für diese Funktion folgt:

`Format`( *dwFlags*, *lcid*)<br/>
Dieses Formular formatiert den Wert mithilfe der Spezifikationen der Berichtsdefinitionssprache (Gebietsschema-IDs) für Datum und Uhrzeit. Verwenden die Standardparameter, wird das Datum und die Uhrzeit, Drucken des Formulars ausgeführt, wenn der Uhrzeitanteil 0 (Mitternacht ist), in diesem Fall es nur das Datum gibt oder der Datumsteil 0 (30. Dezember 1899 ist) in diesem Fall wird nur zum Zeitpunkt drucken. Wenn der Datum/Uhrzeit-Wert 0 (am 30. Dezember 1899 Mitternacht) ist, wird dieses Formular aus, wobei die Standardparameter Mitternacht ausgegeben.

`Format`( *lpszFormat*)<br/>
Dieses Formular formatiert den Wert mit der Formatzeichenfolge das spezielle Formatierungscodes enthält, die ein Prozentzeichen (%) vorangestellt werden, wie in `printf`. Die Formatierungszeichenfolge wird als Parameter an die Funktion übergeben. Weitere Informationen zu den Formatierungscodes, finden Sie unter [Strftime, Wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) in der Run-Time Library Reference.

`Format`( *nFormatID*)<br/>
Dieses Formular formatiert den Wert mit der Formatzeichenfolge das spezielle Formatierungscodes enthält, die ein Prozentzeichen (%) vorangestellt werden, wie in `printf`. Die Formatierungszeichenfolge ist eine Ressource. Die ID der Ressource, diese Zeichenfolge wird als Parameter übergeben. Weitere Informationen zu den Formatierungscodes, finden Sie unter [Strftime, Wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) in die *Run-Time Library Reference*.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#3](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_5.cpp)]

##  <a name="getasdbtimestamp"></a>  COleDateTime::GetAsDBTIMESTAMP

Rufen Sie diese Methode zum Abrufen der Zeit in die `COleDateTime` als Objekt ein `DBTIMESTAMP` Datenstruktur.

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& timeStamp) const throw();
```

### <a name="parameters"></a>Parameter

*timeStamp*<br/>
Ein Verweis auf eine [DBTimeStamp](/dotnet/api/system.data.oledb.oledbtype) Struktur.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Speichert die resultierende Uhrzeit in der referenzierten *Zeitstempel* Struktur. Die `DBTIMESTAMP` Datenstruktur, die von dieser Funktion initialisiert hat seine `fraction` Member auf 0 (null) festgelegt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#4](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_6.cpp)]

##  <a name="getassystemtime"></a>  COleDateTime::GetAsSystemTime

Rufen Sie diese Methode zum Abrufen der Zeit in die `COleDateTime` als Objekt ein `SYSTEMTIME` Datenstruktur.

```
bool GetAsSystemTime(SYSTEMTIME& sysTime) const throw();
```

### <a name="parameters"></a>Parameter

*sysTime*<br/>
Ein Verweis auf eine [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) Struktur zum Empfangen der konvertierte Datums-/Uhrzeitwert aus der `COleDateTime` Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn erfolgreich; "False", wenn die Konvertierung schlägt fehl, oder wenn die `COleDateTime` Objekt ist NULL oder ungültig.

### <a name="remarks"></a>Hinweise

`GetAsSystemTime` Speichert die resultierende Uhrzeit in der referenzierten *SysTime* Objekt. Die `SYSTEMTIME` Datenstruktur, die von dieser Funktion initialisiert hat seine `wMilliseconds` Member auf 0 (null) festgelegt.

Für Weitere Informationen zu den Statusinformationen gespeichert eine `COleDateTime` Objekt, finden Sie unter [GetStatus](#getstatus).

##  <a name="getasudate"></a>  COleDateTime::GetAsUDATE

Rufen Sie diese Methode zum Abrufen der Zeit in die `COleDateTime` als Objekt ein `UDATE` Datenstruktur.

```
bool GetAsUDATE(UDATE& uDate) const throw();
```

### <a name="parameters"></a>Parameter

*uDate*<br/>
Ein Verweis auf eine `UDATE` Struktur zum Empfangen der konvertierte Datums-/Uhrzeitwert aus der `COleDateTime` Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn erfolgreich; "False", wenn die Konvertierung schlägt fehl, oder wenn die `COleDateTime` Objekt ist NULL oder ungültig.

### <a name="remarks"></a>Hinweise

Ein `UDATE` -Struktur stellt ein "lose" Datum dar.

##  <a name="getcurrenttime"></a>  COleDateTime::GetCurrentTime

Rufen Sie diese statischen Member-Funktion, um das aktuelle Datum/Uhrzeit-Wert zurückgeben.

```
static COleDateTime WINAPI GetCurrentTime() throw();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#5](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_7.cpp)]

##  <a name="getday"></a>  COleDateTime::GetDay

Ruft den Tag des Monats, dargestellt durch die diesem Datums-/Zeitwert entspricht.

```
int GetDay() const throw();
```

### <a name="return-value"></a>Rückgabewert

Der Tag des Monats, dargestellt durch den Wert dieses `COleDateTime` Objekt oder `COleDateTime::error` , wenn der Tag nicht abgerufen werden konnte.

### <a name="remarks"></a>Hinweise

Gültige Rückgabewerte Bereich zwischen 1 und 31.

Informationen zu anderen Memberfunktionen, die den Wert dieser Abfragen `COleDateTime` Objekt, finden Sie unter den folgenden Member-Funktionen:

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#6](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_8.cpp)]

##  <a name="getdayofweek"></a>  COleDateTime::GetDayOfWeek

Ruft den Tag des Monats, dargestellt durch die diesem Datums-/Zeitwert entspricht.

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>Rückgabewert

Der Tag des Wochentags, dargestellt durch den Wert dieses `COleDateTime` Objekt oder `COleDateTime::error` Wenn der Tag der Woche konnte nicht abgerufen werden.

### <a name="remarks"></a>Hinweise

Gültige Rückgabe mögliche Werte liegen zwischen 1 und 7, wobei 1 = Sonntag, 2 = Montag und so weiter.

Informationen zu anderen Memberfunktionen, die den Wert dieser Abfragen `COleDateTime` Objekt, finden Sie unter den folgenden Member-Funktionen:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#7](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_9.cpp)]

##  <a name="getdayofyear"></a>  COleDateTime::GetDayOfYear

Ruft den Tag des Jahres durch diesen Wert für Datum und Uhrzeit dargestellt.

```
int GetDayOfYear() const throw();
```

### <a name="return-value"></a>Rückgabewert

Der Tag des Jahres durch den Wert dieses dargestellt `COleDateTime` Objekt oder `COleDateTime::error` Wenn der Tag des Jahres konnte nicht abgerufen werden.

### <a name="remarks"></a>Hinweise

Gültige Rückgabe Werte liegen zwischen 1 und 366, in dem 1. Januar = 1.

Informationen zu anderen Memberfunktionen, die den Wert dieser Abfragen `COleDateTime` Objekt, finden Sie unter den folgenden Member-Funktionen:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#8](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_10.cpp)]

##  <a name="gethour"></a>  COleDateTime::GetHour

Ruft ab, der von diesem Datums-/Uhrzeitwert dargestellte Stunde angezeigt.

```
int GetHour() const throw();
```

### <a name="return-value"></a>Rückgabewert

Der durch den Wert dieses dargestellte Stunde `COleDateTime` Objekt oder `COleDateTime::error` Wenn die Stunde konnte nicht abgerufen werden.

### <a name="remarks"></a>Hinweise

Gültige Rückgabewerte Bereich zwischen 0 und 23.

Informationen zu anderen Memberfunktionen, die den Wert dieser Abfragen `COleDateTime` Objekt, finden Sie unter den folgenden Member-Funktionen:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#9](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_11.cpp)]

##  <a name="getminute"></a>  COleDateTime::GetMinute

Ruft ab, der Minute, die durch diesen Wert für Datum und Uhrzeit dargestellt.

```
int GetMinute() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Minute, dargestellt durch den Wert dieses `COleDateTime` Objekt oder `COleDateTime::error` Wenn Minute nicht abgerufen werden konnte.

### <a name="remarks"></a>Hinweise

Gültige Rückgabewerte Bereich zwischen 0 und 59.

Informationen zu anderen Memberfunktionen, die den Wert dieser Abfragen `COleDateTime` Objekt, finden Sie unter den folgenden Member-Funktionen:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Beispiel

Siehe das Beispiel für [GetHour](#gethour).

##  <a name="getmonth"></a>  COleDateTime::GetMonth

Ruft ab die Monats, dargestellt durch die diesem Datums-/Zeitwert entspricht.

```
int GetMonth() const throw();
```

### <a name="return-value"></a>Rückgabewert

Monats, dargestellt durch den Wert dieses `COleDateTime` Objekt oder `COleDateTime::error` Wenn Monats konnte nicht abgerufen werden.

### <a name="remarks"></a>Hinweise

Gültige Rückgabewerte Bereich zwischen 1 und 12.

Informationen zu anderen Memberfunktionen, die den Wert dieser Abfragen `COleDateTime` Objekt, finden Sie unter den folgenden Member-Funktionen:

- [GetDay](#getday)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Beispiel

Siehe das Beispiel für [GetDay](#getday).

##  <a name="getsecond"></a>  COleDateTime::GetSecond

Ruft ab, der zweite durch diesen Wert für Datum und Uhrzeit dargestellt.

```
int GetSecond() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die zweite, dargestellt durch den Wert dieses `COleDateTime` Objekt oder `COleDateTime::error` Wenn die zweite konnte nicht abgerufen werden.

### <a name="remarks"></a>Hinweise

Gültige Rückgabewerte Bereich zwischen 0 und 59.

> [!NOTE]
>  Die `COleDateTime` Schaltsekunden-Klasse nicht unterstützt.

Weitere Informationen über die Implementierung für `COleDateTime`, finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

Informationen zu anderen Memberfunktionen, die den Wert dieser Abfragen `COleDateTime` Objekt, finden Sie unter den folgenden Member-Funktionen:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Beispiel

Siehe das Beispiel für [GetHour](#gethour).

##  <a name="getstatus"></a>  COleDateTime::GetStatus

Ruft den Status (Gültigkeit) ab einem bestimmten `COleDateTime` Objekt.

```
DateTimeStatus GetStatus() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Status dieses `COleDateTime` Wert. Wenn Sie aufrufen `GetStatus` auf eine `COleDateTime` Objekt erstellt hat den Standardwert, wird zurückgegeben, die ungültig. Aufrufen `GetStatus` auf eine `COleDateTime` Objekt mit dem Konstruktor auf null initialisiert `GetStatus` gibt null zurück.

### <a name="remarks"></a>Hinweise

Der Rückgabewert wird definiert, durch die `DateTimeStatus` Enumerationstyp, der in definiert ist die `COleDateTime` Klasse.

```
enum DateTimeStatus
{
   error = -1,
   valid = 0,
   invalid = 1,    // Invalid date (out of range, etc.)
   null = 2,       // Literally has no value
};
```

Eine kurze Beschreibung dieser Status-Werte finden Sie in der folgenden Liste:

- `COleDateTime::error` Gibt an, dass beim Versuch, die Teil der Datum/Uhrzeit-Wert zu erhalten, ist ein Fehler aufgetreten.

- `COleDateTime::valid` Gibt an, das von diesem `COleDateTime` Objekt gültig ist.

- `COleDateTime::invalid` Gibt an, das von diesem `COleDateTime` Objekt ist ungültig; d. h. der Wert möglicherweise nicht korrekt.

- `COleDateTime::null` Gibt an, das von diesem `COleDateTime` Objekt null ist, d. h., dass für dieses Objekt kein Wert angegeben wurde. (Dies ist "null", in dem Sinne Database "kein Wert, wenn" im Gegensatz zu den C++-NULL).

Der Status einer `COleDateTime` Objekt ist ungültig. in den folgenden Fällen:

- Wenn der Wert festgelegt ist, aus einem `VARIANT` oder `COleVariant` -Wert, der nicht in einen Datum/Uhrzeit-Wert konvertiert werden kann.

- Wenn der Wert festgelegt ist, aus einem `time_t`, `SYSTEMTIME`, oder `FILETIME` -Wert, der nicht auf einen gültigen Datum-/Zeit-Wert konvertiert werden konnten.

- Wenn der Wert, indem festgelegt ist `SetDateTime` mit ungültigen Parameterwerten.

- Wenn dieses Objekt, einem Überlauf oder Unterlauf während eines arithmetischen Zuweisung, nämlich aufgetreten sind `+=` oder `-=`.

- Wenn ein ungültiger Wert für dieses Objekt zugewiesen wurde.

- Wenn der Status dieses Objekts explizit festgelegt wurde, um ungültige mit `SetStatus`.

Weitere Informationen zu den Vorgängen, die den Status ungültige, finden Sie unter den folgenden Member-Funktionen festgelegt werden können:

- [COleDateTime](#coledatetime)

- [SetDateTime](#setdatetime)

- [operator +, -](#operator_add_-)

- [operator +=, -=](#operator_add_eq_-_eq)

Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#10](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_12.cpp)]

##  <a name="getyear"></a>  COleDateTime::GetYear

Ruft ab, von diesem Datum/Uhrzeit-Wert dargestellt wird.

```
int GetYear() const throw();
```

### <a name="return-value"></a>Rückgabewert

Das Jahr, dargestellt durch den Wert dieses `COleDateTime` Objekt oder `COleDateTime::error` Wenn das Jahr konnte nicht abgerufen werden.

### <a name="remarks"></a>Hinweise

Gültige Rückgabewerte Bereich zwischen 100 und 9999, enthält das Jahrhundert.

Informationen zu anderen Memberfunktionen, die den Wert dieser Abfragen `COleDateTime` Objekt, finden Sie unter den folgenden Member-Funktionen:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Beispiel

Siehe das Beispiel für [GetDay](#getday).

##  <a name="m_dt"></a>  COleDateTime::m_dt

Die zugrunde liegende `DATE` Struktur für diese `COleDateTime` Objekt.

```
DATE m_dt;
```

### <a name="remarks"></a>Hinweise

> [!CAUTION]
>  Ändern des Werts in der `DATE` Zugriff auf der Zeiger verweist, die von dieser Funktion zurückgegebenen Objekts ändert sich den Wert dieser `COleDateTime` Objekt. Er ändert nicht den Status dieses `COleDateTime` Objekt.

Weitere Informationen zur Implementierung der `DATE` Objekt, finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

##  <a name="m_status"></a>  COleDateTime::m_status

Enthält den Status dieser `COleDateTime` Objekt.

```
DateTimeStatus m_status;
```

### <a name="remarks"></a>Hinweise

Der Typ dieses Datenelements ist den enumerierten Typ `DateTimeStatus`, definiert in der `COleDateTime` Klasse. Weitere Informationen finden Sie unter [COleDateTime::GetStatus](#getstatus).

> [!CAUTION]
>  Dieses Datenelement ist für erweiterte programmierungssituationen. Sie sollten die Inline-Memberfunktionen verwenden [GetStatus](#getstatus) und [SetStatus](#setstatus). Finden Sie unter `SetStatus` für weitere Punkte in Bezug auf die dieses Datenelement explizit festlegen.

##  <a name="operator_eq"></a>  COleDateTime:: Operator =

Kopiert ein `COleDateTime` Wert.

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

Diese überladenen Zuweisungsoperatoren kopieren Sie den Source-Datum/Uhrzeit-Wert in diesen `COleDateTime` Objekt. Eine kurze Beschreibung jeder dieser überladenen Zuweisung Operatoren folgt:

- **Operator = (** `dateSrc` **)** den Wert und Status des Operanden werden in diese kopiert `COleDateTime` Objekt.

- **Operator = (** *VarSrc* **)** Wenn die Konvertierung der [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) Wert (oder [COleVariant](../../mfc/reference/colevariant-class.md) Objekt) um einen Datums-/Uhrzeitwert (VT_ Datum) erfolgreich ist, lautet der konvertierte Wert wird in diese kopiert `COleDateTime` -Objekt und seinen Status zu ungültig festgelegt ist. Wenn die Konvertierung nicht erfolgreich ist, wird der Wert dieses Objekts auf Null (am 30. Dezember 1899 Mitternacht) festgelegt und dessen Status als ungültig.

- **Operator = (** `dtSrc` **)** der `DATE` Wert wird in diese kopiert `COleDateTime` -Objekt und seinen Status zu ungültig festgelegt ist.

- **Operator = (** `timeSrc` **)** der `time_t` oder `__time64_t` Wert konvertiert und in diese kopiert `COleDateTime` Objekt. Wenn die Konvertierung erfolgreich ist, wird der Status des Objekts gültig auf festgelegt. Wenn dies nicht gelingt, sie festgelegt ist, ungültig.

- **Operator = (** *SystimeSrc* **)** der [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) Wert konvertiert und in diese kopiert `COleDateTime` Objekt. Wenn die Konvertierung erfolgreich ist, wird der Status des Objekts gültig auf festgelegt. Wenn dies nicht gelingt, sie festgelegt ist, ungültig.

- **Operator = (** `uDate` **)** der `UDATE` Wert konvertiert und in diese kopiert `COleDateTime` Objekt. Wenn die Konvertierung erfolgreich ist, wird der Status des Objekts gültig auf festgelegt. Wenn dies nicht gelingt, sie festgelegt ist, ungültig. Ein `UDATE` -Struktur stellt ein "lose" Datum dar. Weitere Informationen finden Sie in der Funktion [VarDateFromUdate](/windows/desktop/api/oleauto/nf-oleauto-vardatefromudate).

- **Operator = (** `filetimeSrc` **)** der [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) Wert konvertiert und in diese kopiert `COleDateTime` Objekt. Wenn die Konvertierung erfolgreich ist, wird der Status des Objekts gültig auf festgelegt. andernfalls als ungültig. `FILETIME` Koordinierte Weltzeit (UTC) verwendet, wenn Sie eine UTC-Zeit in der Struktur übergeben, die Ergebnisse von UTC-Zeit in die Ortszeit konvertiert und als variant-Zeit gespeichert werden. Dieses Verhalten ist der gleiche wie in Visual C++ 6.0 und Visual C++ .NET 2003 Service Pack 2. Weitere Informationen finden Sie unter [Dateizeitangaben](/windows/desktop/SysInfo/file-times) im Windows SDK.

Weitere Informationen finden Sie unter den [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) Eintrag in das Windows SDK.

Weitere Informationen zu den `time_t` -Datentyp, finden Sie die [Zeit](../../c-runtime-library/reference/time-time32-time64.md) Funktion in der *Run-Time Library Reference*.

Weitere Informationen finden Sie unter den [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) und [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) Strukturen im Windows SDK.

Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

##  <a name="operator_add_-"></a>  COleDateTime:: Operator +, -

Addition und Subtraktion `ColeDateTime` Werte.

```
COleDateTime operator+(COleDateTimeSpan dateSpan) const throw();
COleDateTime operator-(COleDateTimeSpan dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTime& date) const throw();
```

### <a name="remarks"></a>Hinweise

`COleDateTime` -Objekte stellen die absolute Zeiten dar. [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md) Objekte stellen die relative Häufigkeit dar. Die ersten beiden Operatoren können Sie von Addition und Subtraktion ein `COleDateTimeSpan` Wert aus einer `COleDateTime` Wert. Der dritte Operator können Sie eine zu subtrahieren `COleDateTime` Wert von einem anderen ergibt eine `COleDateTimeSpan` Wert.

Wenn einer der Operanden null ist, ist den Status des resultierenden `COleDateTime` Wert ist null.

Wenn die resultierende `COleDateTime` Wert liegt außerhalb des zulässigen Werte, der Status dieser `COleDateTime` Wert ist ungültig.

Wenn es sich bei den Operanden ist ungültig, und die andere ist nicht null ist, den Status des resultierenden `COleDateTime` Wert ist ungültig.

Die **+** und **-** Operatoren werden bestätigt, wenn die `COleDateTime` Objekts wird festgelegt auf Null. Finden Sie unter [COleDateTime-Operatoren (Relational)](#coledatetime_relational_operators) verdeutlicht.

Weitere Informationen zu den gültigen, Ungültiger und null-Status-Werte, finden Sie unter den [M_status](#m_status) Membervariablen gespeichert.

Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#12](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_13.cpp)]

##  <a name="operator_add_eq_-_eq"></a>  COleDateTime:: Operator +=, =

Addition und Subtraktion ein `ColeDateTime` Wert aus diesem `COleDateTime` Objekt.

```
COleDateTime& operator+=(COleDateTimeSpan dateSpan) throw();
COleDateTime& operator-=(COleDateTimeSpan dateSpan) throw();
```

### <a name="remarks"></a>Hinweise

Diese Operatoren können Sie von Addition und Subtraktion ein `COleDateTimeSpan` Wert zu und aus diesem `COleDateTime`. Wenn einer der Operanden null ist, ist den Status des resultierenden `COleDateTime` Wert ist null.

Wenn die resultierende `COleDateTime` Wert liegt außerhalb des zulässigen Werte, der den Status `COleDateTime` festgelegt ist, ungültig.

Wenn es sich bei den Operanden ist ungültig und andere nicht null ist, den Status des resultierenden `COleDateTime` Wert ist ungültig.

Weitere Informationen zu den gültigen, Ungültiger und null-Status-Werte, finden Sie unter den [M_status](#m_status) Membervariablen gespeichert.

Die **+=** und **-=** Operatoren werden bestätigt, wenn die `COleDateTime` Objekts wird festgelegt auf Null. Finden Sie unter [COleDateTime-Operatoren (Relational)](#coledatetime_relational_operators) verdeutlicht.

Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

##  <a name="operator_date"></a>  COleDateTime:: Operator, Datum

Konvertiert eine `ColeDateTime` -Wert in eine `DATE`.

```
operator DATE() const throw();
```

### <a name="remarks"></a>Hinweise

Dieser Operator gibt einen `DATE` -Objekt, dessen Wert wird aus dieser kopiert `COleDateTime` Objekt. Weitere Informationen zur Implementierung der `DATE` Objekt, finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

Die `DATE` Operator wird bestätigt, wenn die `COleDateTime` Objekts wird festgelegt auf Null. Finden Sie unter [COleDateTime-Operatoren (Relational)](#coledatetime_relational_operators) verdeutlicht.

##  <a name="parsedatetime"></a>  COleDateTime::ParseDateTime

Analysiert eine Zeichenfolge zum Lesen eines Datum/Uhrzeit-Werts.

```
bool ParseDateTime(
    LPCTSTR lpszDate,
    DWORD dwFlags = 0,
    LCID lcid = LANG_USER_DEFAULT) throw();
```

### <a name="parameters"></a>Parameter

*lpszDate*<br/>
Ein Zeiger auf die Null-terminierte Zeichenfolge, die analysiert werden soll. Einzelheiten finden Sie unter "Hinweise".

*dwFlags*<br/>
Gibt Flags für die Einstellungen für Gebietsschema und die Analyse an. Eine oder mehrere der folgenden Flags:

- LOCALE_NOUSEROVERRIDE verwenden Sie den Standard-gebietsschemaeinstellungen für System, anstelle von benutzerdefinierten Einstellungen.

- VAR_TIMEVALUEONLY ignorieren den Datumsteil während der Analyse.

- VAR_DATEVALUEONLY ignorieren den Time-Teil, bei der Analyse.

*lcid*<br/>
Gibt die Gebietsschema-ID, für die Konvertierung verwendet.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn die Zeichenfolge erfolgreich konvertiert wurde, um einen Datums-/Zeitwert entspricht, andernfalls "false".

### <a name="remarks"></a>Hinweise

Wenn die Zeichenfolge erfolgreich in einen Datums-/Uhrzeitwert konvertiert wurde, den Wert dieses `COleDateTime` Objekt auf diesen Wert und ihren Status auf ungültig festgelegt ist.

> [!NOTE]
>  Werte für das Jahr müssen zwischen 100 und 9999 liegen.

Die *LpszDate* Parameter kann verschiedene Formate haben. Beispielsweise enthalten die folgenden Zeichenfolgen zulässige Datum/Uhrzeit-Formate:

`"25 January 1996"`

`"8:30:00"`

`"20:30:00"`

`"January 25, 1996 8:30:00"`

`"8:30:00 Jan. 25, 1996"`

`"1/25/1996 8:30:00"  // always specify the full year, even in a 'short date' format`

Die Gebietsschema-ID wirkt sich auch, ob das Format der Zeichenfolge für die Konvertierung in einen Datum/Uhrzeit-Wert zulässig ist.

Im Fall von VAR_DATEVALUEONLY wird der Zeitwert, den Zeitpunkt von 0 oder Mitternacht festgelegt. Im Fall von VAR_TIMEVALUEONLY wird der Datumswert Datum 0, d. h. am 30. Dezember 1899 festgelegt.

Wenn die Zeichenfolge nicht in einen Datum/Uhrzeit-Wert konvertiert werden konnte oder gab es einem numerischen Überlauf, der den Status `COleDateTime` Objekt ist ungültig.

Weitere Informationen zu den Grenzen und die Implementierung für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

##  <a name="setdate"></a>  COleDateTime::SetDate

Legt das Datum dieser `COleDateTime` Objekt.

```
int SetDate(
    int nYear,
    int nMonth,
    int nDay) throw();
```

### <a name="parameters"></a>Parameter

*nYear*, *nMonth*, *nDay*<br/>
Geben Sie die Datumskomponenten in diese kopiert werden `COleDateTime` Objekt.

### <a name="return-value"></a>Rückgabewert

NULL, wenn der Wert dieser `COleDateTime` Objekt festgelegt wurde erfolgreich ist; andernfalls 1. Dieser Rückgabewert wird basierend auf den `DateTimeStatus` Enumerationstyp. Weitere Informationen finden Sie unter den [SetStatus](#setstatus) Member-Funktion.

### <a name="remarks"></a>Hinweise

Das Datum wird auf die angegebenen Werte festgelegt. Die Zeit wird zum Zeitpunkt 0, Mitternacht festgelegt.

Finden Sie in der folgenden Tabelle für die Grenzen für die Parameterwerte:

|Parameter|Grenzen|
|---------------|------------|
|*nYear*|100 - 9999|
|*nMonth*|1 - 12|
|*nDay*|0 - 31|

Wenn der Tag des Monats überläuft, wird eine Konvertierung in den richtigen Tag des nächsten Monats und den Monat bzw. Jahr entsprechend erhöht wird. Ein Wert für den Tag 0 (null) gibt an, den letzten Tag des vorherigen Monats. Das Verhalten ist identisch mit `SystemTimeToVariantTime`.

Wenn der Date-Wert, der von den Parametern angegebenen nicht gültig ist, wird der Status des Objekts zu festgelegt `COleDateTime::invalid`. Verwenden Sie [GetStatus](#getstatus) überprüft die Gültigkeit der `DATE` Wert und darf nicht davon ausgehen, die den Wert der [M_dt](#m_dt) bleiben unverändert.

Hier sind einige Beispiele für die Date-Werten:

|*nYear*|*nMonth*|*nDay*|Wert|
|-------------|--------------|------------|-----------|
|2000|2|29|29. Februar 2000|
|1776|7|4|4 Juli 1776|
|1925|4|35|35 April 1925 (ungültiges Datum)|
|10000|1|1|1. Januar 10000 (ungültiges Datum)|

Um sowohl Datums-als auch festgelegt werden, finden Sie unter [COleDateTime::SetDateTime](#setdatetime).

Informationen zum Member-Funktionen, die den Wert dieser Abfragen `COleDateTime` Objekt, finden Sie unter den folgenden Member-Funktionen:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#11](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_14.cpp)]

##  <a name="setdatetime"></a>  COleDateTime::SetDateTime

Legt das Datum und Uhrzeit dieser `COleDateTime` Objekt.

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

*nYear*, *nMonth*, *nDay*, *nHour*, *nMin*, *nSec*<br/>
Angeben der Datums- und Zeitkomponenten in diese kopiert werden `COleDateTime` Objekt.

### <a name="return-value"></a>Rückgabewert

NULL, wenn der Wert dieser `COleDateTime` Objekt festgelegt wurde erfolgreich ist; andernfalls 1. Dieser Rückgabewert wird basierend auf den `DateTimeStatus` Enumerationstyp. Weitere Informationen finden Sie unter den [SetStatus](#setstatus) Member-Funktion.

### <a name="remarks"></a>Hinweise

Finden Sie in der folgenden Tabelle für die Grenzen für die Parameterwerte:

|Parameter|Grenzen|
|---------------|------------|
|*nYear*|100 - 9999|
|*nMonth*|1 - 12|
|*nDay*|0 - 31|
|*nHour*|0 - 23|
|*nMin*|0 - 59|
|*nSec*|0 - 59|

Wenn der Tag des Monats überläuft, wird eine Konvertierung in den richtigen Tag des nächsten Monats und den Monat bzw. Jahr entsprechend erhöht wird. Ein Wert für den Tag 0 (null) gibt an, den letzten Tag des vorherigen Monats. Das Verhalten ist identisch mit [SystemTimeToVariantTime](/windows/desktop/api/oleauto/nf-oleauto-systemtimetovarianttime).

Wenn der von den Parametern angegebenen Datum oder Uhrzeit-Wert ist nicht gültig ist, wird der Status des Objekts ungültig und der Wert dieses Objekts festgelegt ist, wird nicht geändert.

Hier sind einige Beispiele für die Time-Werten:

|*nHour*|*nMin*|*nSec*|Wert|
|-------------|------------|------------|-----------|
|1|3|3|01:03:03|
|23|45|0|23:45:00|
|25|30|0|Ungültig|
|9|60|0|Ungültig|

Hier sind einige Beispiele für die Date-Werten:

|*nYear*|*nMonth*|*nDay*|Wert|
|-------------|--------------|------------|-----------|
|1995|4|15|15. April 1995|
|1789|7|14|17 Juli 1789|
|1925|2|30|Ungültig|
|10000|1|1|Ungültig|

Um nur das Datum festzulegen, finden Sie unter [COleDateTime::SetDate](#setdate). Um nur die Uhrzeit festzulegen, finden Sie unter [COleDateTime::SetTime](#settime).

Informationen zum Member-Funktionen, die den Wert dieser Abfragen `COleDateTime` Objekt, finden Sie unter den folgenden Member-Funktionen:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Beispiel

Siehe das Beispiel für [GetStatus](#getstatus).

##  <a name="setstatus"></a>  COleDateTime::SetStatus

Legt den Status dieser `COleDateTime` Objekt.

```
void SetStatus(DateTimeStatus status) throw();
```

### <a name="parameters"></a>Parameter

*Status*<br/>
Der neue Statuswert für diesen `COleDateTime` Objekt.

### <a name="remarks"></a>Hinweise

Die *Status* Parameterwert wird definiert, indem die `DateTimeStatus` Enumerationstyp, der in definiert ist die `COleDateTime` Klasse. Finden Sie unter [COleDateTime::GetStatus](#getstatus) Details.

> [!CAUTION]
>  Diese Funktion ist für die erweiterte programmierungssituationen. Diese Funktion wird die Daten in dieses Objekt nicht geändert. Dieser wird den meisten Fällen verwendet, legen Sie den Status auf **null** oder **ungültige**. Der Zuweisungsoperator ([Operator =](#operator_eq)) und [SetDateTime](#setdatetime) führen Sie den Status des Objekts basierend auf den Werten der Datenquelle festgelegt.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [GetStatus](#getstatus).

##  <a name="settime"></a>  COleDateTime::SetTime

Legt die Uhrzeit dieser `COleDateTime` Objekt.

```
int SetTime(
    int nHour,
    int nMin,
    int nSec) throw();
```

### <a name="parameters"></a>Parameter

*nHour*, *nMin*, *nSec*<br/>
Geben Sie die Zeitkomponenten in diese kopiert werden `COleDateTime` Objekt.

### <a name="return-value"></a>Rückgabewert

NULL, wenn der Wert dieser `COleDateTime` Objekt festgelegt wurde erfolgreich ist; andernfalls 1. Dieser Rückgabewert wird basierend auf den `DateTimeStatus` Enumerationstyp. Weitere Informationen finden Sie unter den [SetStatus](#setstatus) Member-Funktion.

### <a name="remarks"></a>Hinweise

Die Zeit, die auf die angegebenen Werte festgelegt ist. Das Datum wird in Datum 0, d. h. am 30. Dezember 1899 festgelegt.

Finden Sie in der folgenden Tabelle für die Grenzen für die Parameterwerte:

|Parameter|Grenzen|
|---------------|------------|
|*nHour*|0 - 23|
|*nMin*|0 - 59|
|*nSec*|0 - 59|

Wenn die Zeit, die durch den Parameter angegebene Wert nicht gültig ist, ist der Status des Objekts ungültig und der Wert dieses Objekts festgelegt ist, wird nicht geändert.

Hier sind einige Beispiele für die Time-Werten:

|*nHour*|*nMin*|*nSec*|Wert|
|-------------|------------|------------|-----------|
|1|3|3|01:03:03|
|23|45|0|23:45:00|
|25|30|0|Ungültig|
|9|60|0|Ungültig|

Um sowohl Datums-als auch festgelegt werden, finden Sie unter [COleDateTime::SetDateTime](#setdatetime).

Informationen zum Member-Funktionen, die den Wert dieser Abfragen `COleDateTime` Objekt, finden Sie unter den folgenden Member-Funktionen:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Beispiel

Siehe das Beispiel für [SetDate](#setdate).

## <a name="see-also"></a>Siehe auch

[COleVariant-Klasse](../../mfc/reference/colevariant-class.md)<br/>
[CTime-Klasse](../../atl-mfc-shared/reference/ctime-class.md)<br/>
[CTimeSpan-Klasse](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)
