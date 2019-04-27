---
title: CTime-Klasse
ms.date: 10/18/2018
f1_keywords:
- CTime
- ATLTIME/ATL::CTime
- ATLTIME/ATL::CTime::CTime
- ATLTIME/ATL::CTime::Format
- ATLTIME/ATL::CTime::FormatGmt
- ATLTIME/ATL::CTime::GetAsDBTIMESTAMP
- ATLTIME/ATL::CTime::GetAsSystemTime
- ATLTIME/ATL::CTime::GetCurrentTime
- ATLTIME/ATL::CTime::GetDay
- ATLTIME/ATL::CTime::GetDayOfWeek
- ATLTIME/ATL::CTime::GetGmtTm
- ATLTIME/ATL::CTime::GetHour
- ATLTIME/ATL::CTime::GetLocalTm
- ATLTIME/ATL::CTime::GetMinute
- ATLTIME/ATL::CTime::GetMonth
- ATLTIME/ATL::CTime::GetSecond
- ATLTIME/ATL::CTime::GetTime
- ATLTIME/ATL::CTime::GetYear
- ATLTIME/ATL::CTime::Serialize64
helpviewer_keywords:
- CTime class
- shared classes, CTime
ms.assetid: 0a299544-485b-48dc-9d3c-fdc30f57d612
ms.openlocfilehash: df86d35e52ea386d2750a4af7357e66a8d08f79f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62200351"
---
# <a name="ctime-class"></a>CTime-Klasse

Stellt eine absolute Zeit und Datum dar.

## <a name="syntax"></a>Syntax

```
class CTime
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CTime::CTime](#ctime)|Erstellt `CTime` Objekte auf unterschiedliche Weise.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CTime::Format](#format)|Konvertiert eine `CTime` Objekt in eine formatierte Zeichenfolge – basierend auf der lokalen Zeitzone.|
|[CTime::FormatGmt](#formatgmt)|Konvertiert eine `CTime` Objekt in eine formatierte Zeichenfolge – basierend auf UTC.|
|[CTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|Die gespeicherten Uhrzeitinformationen konvertiert die `CTime` Objekt in eine Win32-kompatibles DBTIMESTAMP-Struktur.|
|[CTime::GetAsSystemTime](#getassystemtime)|Die gespeicherten Uhrzeitinformationen konvertiert die `CTime` Objekt in ein Win32-kompatibles [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) Struktur.|
|[CTime::GetCurrentTime](#getcurrenttime)|Erstellt eine `CTime` -Objekt, das die aktuelle Uhrzeit (statische Memberfunktion) darstellt.|
|[CTime::GetDay](#getday)|Gibt den Tag darstellt, durch die `CTime` Objekt.|
|[CTime::GetDayOfWeek](#getdayofweek)|Gibt den Tag des Wochentags, dargestellt durch die `CTime` Objekt.|
|[CTime::GetGmtTm](#getgmttm)|Unterteilt eine `CTime` Objekt in Komponenten – basierend auf UTC.|
|[CTime::GetHour](#gethour)|Gibt die Stunde, dargestellt durch die `CTime` Objekt.|
|[CTime::GetLocalTm](#getlocaltm)|Unterteilt eine `CTime` Objekt in Komponenten – basierend auf der lokalen Zeitzone.|
|[CTime::GetMinute](#getminute)|Gibt zurück, die Minute, dargestellt durch die `CTime` Objekt.|
|[CTime::GetMonth](#getmonth)|Gibt zurück, Monats, dargestellt durch die `CTime` Objekt.|
|[CTime::GetSecond](#getsecond)|Gibt zurück, das zweite, dargestellt durch die `CTime` Objekt.|
|[CTime::GetTime](#gettime)|Gibt eine **__time64_t** Wert für den angegebenen `CTime` Objekt.|
|[CTime::GetYear](#getyear)|Gibt zurück, dargestellt durch die `CTime` Objekt.|
|[CTime::Serialize64](#serialize64)|Serialisiert Daten in oder aus einem Archiv an.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator + -](#operator_add_-)|Diese Operatoren, Addition und Subtraktion `CTimeSpan` und `CTime` Objekte.|
|[operator +=, -=](#operator_add_eq_-_eq)|Diese Operatoren, Addition und Subtraktion ein `CTimeSpan` Objekt auf und aus diesem `CTime` Objekt.|
|[operator =](#operator_eq)|Der Zuweisungsoperator.|
|[operator ==, < , etc.](#ctime_comparison_operators)|Vergleichsoperatoren.|

## <a name="remarks"></a>Hinweise

`CTime` eine Basisklasse keinen.

`CTime` Werte basieren auf koordinierte Weltzeit (UTC), die koordinierte Weltzeit (Greenwich Mean Time, GMT) entspricht. Finden Sie unter [Uhrzeitverwaltung](../../c-runtime-library/time-management.md) Informationen wie die Zeitzone festgelegt wird.

Bei der Erstellung einer `CTime` -Objekts die `nDST` Parameter auf 0, um anzugeben, dass die Normalzeit gilt, oder auf einen Wert größer als 0, um anzugeben, Sommerzeit gilt, oder ein Wert kleiner als 0 (null), damit die C-Laufzeitbibliothek Code mputerkonto e, ob Normalzeit oder Sommerzeit wirksam ist. `tm_isdst` ist ein Pflichtfeld. Wenn nicht festgelegt ist, dessen Wert nicht definiert ist und der Rückgabewert von [Mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md) ist unvorhersehbar. Wenn `timeptr` verweist auf eine tm-Struktur, die von einem vorherigen Aufruf zurückgegebene [Asctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md), [_gmtime_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md), oder [Localtime_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md), `tm_isdst` Feld enthält den richtige Wert.

Eine Begleitklasse [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md), stellt ein Zeitintervall dar.

Die `CTime` und `CTimeSpan` Klassen sind nicht für die Ableitung ausgelegt. Da es keine virtuellen Funktionen, die Größe des sind `CTime` und `CTimeSpan` Objekte wird genau 8 Bytes. Die meisten Memberfunktionen werden Inline.

> [!NOTE]
>  Datumslimit für die die Obergrenze ist 12/31/3000. Die untere Grenze ist 1/1/1970 12:00:00 Uhr GMT.

Weitere Informationen zur Verwendung von `CTime`, finden Sie in den Artikeln [Datums- /](../../atl-mfc-shared/date-and-time.md), und [Uhrzeitverwaltung](../../c-runtime-library/time-management.md) in der Run-Time Library Reference.

> [!NOTE]
>  Die `CTime` Struktur, die von MFC 7.1 in MFC 8.0 geändert. Wenn Sie serialisieren eine `CTime` -Struktur unter Verwendung der **Operator <<** unter MFC 8.0 oder höher, die resultierende Datei nicht gelesen werden unter älteren Versionen von MFC.

## <a name="requirements"></a>Anforderungen

**Header:** atltime.h

##  <a name="ctime_comparison_operators"></a>  CTime-Vergleichsoperatoren

Vergleichsoperatoren.

```
bool operator==(CTime time) const throw();
bool operator!=(CTime time) const throw();
bool operator<(CTime time) const throw();
bool operator>(CTime time) const throw();
bool operator<=(CTime time) const throw();
bool operator>=(CTime time) const throw();
```

### <a name="parameters"></a>Parameter

*time*<br/>
Das zu vergleichende `CTime`-Objekt.

### <a name="return-value"></a>Rückgabewert

Diese Operatoren vergleichen zwei absolute Zeiten und gibt TRUE zurück, wenn die Bedingung true ist; andernfalls "false".

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#161](../../atl-mfc-shared/codesnippet/cpp/ctime-class_1.cpp)]

##  <a name="ctime"></a>  CTime:: CTime

Erstellt ein neues `CTime` Initialisiert mit dem angegebenen Objekt.

```
CTime() throw();
CTime(__time64_t time) throw();
CTime(int nYear, int nMonth, int nDay,
      int nHour, int nMin, int nSec, int nDST = -1);
CTime(WORD wDosDate, WORD wDosTime, int nDST = -1);
CTime(const SYSTEMTIME& st, int nDST = - 1) throw();
CTime(const FILETIME& ft, int nDST = - 1);
CTime(const DBTIMESTAMP& dbts, int nDST = -1) throw();
```

### <a name="parameters"></a>Parameter

*timeSrc*<br/>
Gibt eine `CTime` -Objekt, das bereits vorhanden ist.

*time*<br/>
Ein `__time64_t` Time-Werten, die die Anzahl der Sekunden an, nach dem 1. Januar 1970 UTC ist. Beachten Sie, dass dies in die lokale Zeit angepasst wird. Angenommen, Sie befinden sich in New York, und erstellen eine `CTime` -Objekt durch Übergeben eines Parameters von 0 (null) [CTime::GetMonth](#getmonth) 12 zurück.

*nYear*, *nMonth*, *nDay*, *nHour*, *nMin*, *nSec*<br/>
Gibt den Wert für Datum und Uhrzeit in die neue kopiert werden `CTime` Objekt.

*nDST*<br/>
Gibt an, ob die Sommerzeit wirksam ist. Dabei kann es sich um einen von drei Werten haben:

- *nDST* 0Standard Zeit ist aktiviert.

- *nDST* auf einen Wert größer als 0Daylight Winterzeit gilt festgelegt.

- *nDST* auf einen Wert kleiner als 0The standardmäßig festgelegt. Wird automatisch berechnet, ob Normalzeit oder Sommerzeit wirksam ist.

*wDosDate*, *wDosTime*<br/>
MS-DOS-Datum und Uhrzeit-Werte in einen Datum/Uhrzeit-Wert konvertiert werden, und kopiert in das neue `CTime` Objekt.

*st*<br/>
Ein [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) Struktur in einen Datum/Uhrzeit-Wert konvertiert werden, und kopiert in das neue `CTime` Objekt.

*ft*<br/>
Ein [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) Struktur in einen Datum/Uhrzeit-Wert konvertiert werden, und kopiert in das neue `CTime` Objekt.

*dbts*<br/>
Ein Verweis auf eine DBTIMESTAMP-Struktur, die die aktuelle lokale Uhrzeit enthält.

### <a name="remarks"></a>Hinweise

Jeder Konstruktor lautet wie folgt:

- `CTime();` Erstellt ein nicht initialisiertes `CTime` Objekt. Dieser Konstruktor ermöglicht Ihnen, definieren `CTime` -Objekt des Arrays. Sie sollten solche Arrays mit gültigen Zeiten vor der Verwendung initialisieren.

- `CTime( const CTime& );` Erstellt eine `CTime` Objekt von einem anderen `CTime` Wert.

- `CTime( __time64_t );` Erstellt eine `CTime` -Objekt aus einem **__time64_t** Typ. Dieser Konstruktor erwartet, dass eine UTC-Zeit und das Ergebnis in die lokale Zeit konvertiert, bevor Sie das Ergebnis speichert.

- `CTime( int, int, ...);` Erstellt eine `CTime` Objekt aus der lokalen Zeitkomponenten für jede Komponente beschränkt, die den folgenden Bereichen:

   |Komponente|Bereich|
   |---------------|-----------|
   |*nYear*|1970-3000|
   |*nMonth*|1-12|
   |*nDay*|1-31|
   |*nHour*|0-23|
   |*nMin*|0-59|
   |*nSec*|0-59|

   Dieser Konstruktor wird die entsprechende Konvertierung in UTC. Die Debugversion der Microsoft Foundation Class-Bibliothek bestätigt wird, wenn eine oder mehrere die Zeitkomponenten werden außerhalb des gültigen Bereichs. Sie müssen die Argumente vor dem Aufruf überprüfen. Dieser Konstruktor erwartet, dass eine lokale Zeit.

- `CTime( WORD, WORD );` Erstellt eine `CTime` Objekt aus der angegebenen Werte von MS-DOS-Datum und Uhrzeit. Dieser Konstruktor erwartet, dass eine lokale Zeit.

- `CTime( const SYSTEMTIME& );` Erstellt eine `CTime` -Objekt aus einem `SYSTEMTIME` Struktur. Dieser Konstruktor erwartet, dass eine lokale Zeit.

- `CTime( const FILETIME& );` Erstellt eine `CTime` -Objekt aus einem `FILETIME` Struktur. Verwenden Sie wahrscheinlich nicht `CTime FILETIME` -Initialisierung direkt. Bei Verwendung einer `CFile` Objekt, das eine Datei zu manipulieren `CFile::GetStatus` Ruft den Zeitstempel der Datei für Sie durch eine `CTime` Objekt initialisiert wird, mit eine `FILETIME` Struktur. Dieser Konstruktor wird als Zeit, die basierend auf UTC und konvertiert automatisch den Wert in die lokale Zeit vor dem Speichern der Ergebnisse.

   > [!NOTE]
   > Der Konstruktor mit `DBTIMESTAMP` Parameter ist nur verfügbar, wenn "OleDb.h" enthalten ist.

Weitere Informationen finden Sie unter den [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) und [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) Struktur im Windows SDK. Siehe auch die [MS-DOS-Datum und Uhrzeit](/windows/desktop/SysInfo/ms-dos-date-and-time) Eintrag in das Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#148](../../atl-mfc-shared/codesnippet/cpp/ctime-class_2.cpp)]

##  <a name="format"></a>  CTime::Format

Rufen Sie diese Memberfunktion, um eine formatierte Darstellung des DateTime-Werts zu erstellen.

```
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nFormatID) const;
```

### <a name="parameters"></a>Parameter

*pszFormat*<br/>
Eine Formatierungszeichenfolge ähnelt der `printf` Formatierungszeichenfolge. Formatierungscodes Prozentsatz vorangestellt (`%`) anmelden, werden mit den entsprechenden ersetzt `CTime` Komponente. Andere Zeichen in der Formatierungszeichenfolge werden auf die zurückgegebene Zeichenfolge unverändert kopiert. Finden Sie unter der Run-Time-Funktion [Strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) eine Liste der Formatierungscodes.

*nFormatID*<br/>
Die ID der Zeichenfolge, die dieses Format identifiziert.

### <a name="return-value"></a>Rückgabewert

Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , die die formatierte Zeit enthält.

### <a name="remarks"></a>Hinweise

Wenn der Status dieser `CTime` Objekt null ist. der zurückgegebene Wert ist eine leere Zeichenfolge.

Diese Methode löst eine Ausnahme aus, wenn es sich bei der zu formatierenden Datum / Uhrzeit-Wert nicht von Mitternacht, 1. Januar 1970 bis 31. Dezember 3000 reichen ist Universal Coordinated Time (UTC).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#149](../../atl-mfc-shared/codesnippet/cpp/ctime-class_3.cpp)]

##  <a name="formatgmt"></a>  CTime::FormatGmt

Generiert eine formatierte Zeichenfolge, die dies entspricht `CTime` Objekt.

```
CString FormatGmt(LPCTSTR pszFormat) const;
CString FormatGmt(UINT nFormatID) const;
```

### <a name="parameters"></a>Parameter

*pszFormat*<br/>
Gibt an, eine Formatierungszeichenfolge, die ähnlich wie die `printf` Formatierungszeichenfolge. Finden Sie unter der Run-Time-Funktion [Strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) Details.

*nFormatID*<br/>
Die ID der Zeichenfolge, die dieses Format identifiziert.

### <a name="return-value"></a>Rückgabewert

Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , die die formatierte Zeit enthält.

### <a name="remarks"></a>Hinweise

Der Zeitwert wird nicht konvertiert, und gibt daher UTC.

Diese Methode löst eine Ausnahme aus, wenn es sich bei der zu formatierenden Datum / Uhrzeit-Wert nicht von Mitternacht, 1. Januar 1970 bis 31. Dezember 3000 reichen ist Universal Coordinated Time (UTC).

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CTime::Format](#format).

##  <a name="getasdbtimestamp"></a>  CTime::GetAsDBTIMESTAMP

Rufen Sie diese Memberfunktion zum Konvertieren der gespeicherten Uhrzeitinformationen dem `CTime` Objekt in eine Win32-kompatibles DBTIMESTAMP-Struktur.

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```

### <a name="parameters"></a>Parameter

*dbts*<br/>
Ein Verweis auf eine DBTIMESTAMP-Struktur, die die aktuelle lokale Uhrzeit enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Speichert die resultierende Uhrzeit in der referenzierten *Dbts* Struktur. Die `DBTIMESTAMP` Datenstruktur, die von dieser Funktion initialisiert hat seine `fraction` Member auf 0 (null) festgelegt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#150](../../atl-mfc-shared/codesnippet/cpp/ctime-class_4.cpp)]

##  <a name="getassystemtime"></a>  CTime::GetAsSystemTime

Rufen Sie diese Memberfunktion zum Konvertieren der gespeicherten Uhrzeitinformationen dem `CTime` Objekt in ein Win32-kompatibles [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) Struktur.

```
bool GetAsSystemTime(SYSTEMTIME& st) const throw();
```

### <a name="parameters"></a>Parameter

*timeDest*<br/>
Ein Verweis auf eine [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) Struktur, die den konvertierten Datum/Uhrzeit-Wert, der enthalten, wird die `CTime` Objekt.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls FALSE.

### <a name="remarks"></a>Hinweise

`GetAsSystemTime` Speichert die resultierende Uhrzeit in der referenzierten *TimeDest* Struktur. Die `SYSTEMTIME` Datenstruktur, die von dieser Funktion initialisiert hat seine `wMilliseconds` Member auf 0 (null) festgelegt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#151](../../atl-mfc-shared/codesnippet/cpp/ctime-class_5.cpp)]

##  <a name="getcurrenttime"></a>  CTime:: GetCurrentTime

Gibt eine `CTime` -Objekt, das die aktuelle Uhrzeit darstellt.

```
static CTime WINAPI GetCurrentTime() throw();
```

### <a name="remarks"></a>Hinweise

Gibt das aktuelle Systemdatum und die Uhrzeit in Coordinated Universal Time (UTC) zurück.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#152](../../atl-mfc-shared/codesnippet/cpp/ctime-class_6.cpp)]

##  <a name="getday"></a>  CTime::GetDay

Gibt den Tag darstellt, durch die `CTime` Objekt.

```
int GetDay() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Tag des Monats basierend auf der Ortszeit oder im Bereich von 1 bis 31 zurück.

### <a name="remarks"></a>Hinweise

Diese Funktion ruft `GetLocalTm`, verwendet einen interne, statisch zugeordneten Puffer. Die Daten in diesem Puffer werden aufgrund von Aufrufen von anderen überschrieben `CTime` Memberfunktionen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#153](../../atl-mfc-shared/codesnippet/cpp/ctime-class_7.cpp)]

##  <a name="getdayofweek"></a>  CTime::GetDayOfWeek

Gibt den Tag des Wochentags, dargestellt durch die `CTime` Objekt.

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Wochentag basierend auf der Ortszeit zurück. 1 = Sonntag, 2 = Montag, 7 = Samstag.

### <a name="remarks"></a>Hinweise

Diese Funktion ruft `GetLocalTm`, die statisch eine interne verwendet zugeordneten Puffer. Die Daten in diesem Puffer werden aufgrund von Aufrufen von anderen überschrieben `CTime` Memberfunktionen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#154](../../atl-mfc-shared/codesnippet/cpp/ctime-class_8.cpp)]

##  <a name="getgmttm"></a>  CTime::GetGmtTm

Ruft eine **Struct tm** , enthält eine Aufgliederung der enthalten, die in dieser Zeit `CTime` Objekt.

```
struct tm* GetGmtTm(struct tm* ptm) const;
```

### <a name="parameters"></a>Parameter

*ptm*<br/>
Verweist auf einen Puffer, der die Zeitdaten erhält. Wenn dieser Zeiger NULL ist, wird eine Ausnahme ausgelöst.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine ausgefüllt **Struct tm** wie in der Includedatei Zeit definiert. H. Finden Sie unter [Gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) für das Strukturlayout.

### <a name="remarks"></a>Hinweise

`GetGmtTm` Gibt die UTC zurück.

*Ptm* darf nicht NULL sein. Wenn Sie das alte Verhalten verwenden, in denen zurücksetzen möchten *Ptm* kann NULL sein, um anzugeben, dass eine interne, statisch zugewiesenen Puffer verwendet werden sollte, dann heben Sie die Definition _SECURE_ATL.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#155](../../atl-mfc-shared/codesnippet/cpp/ctime-class_9.cpp)]

##  <a name="gethour"></a>  CTime::GetHour

Gibt die Stunde, dargestellt durch die `CTime` Objekt.

```
int GetHour() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Stunde, basierend auf der Ortszeit oder im Bereich von 0 bis 23 zurück.

### <a name="remarks"></a>Hinweise

Diese Funktion ruft `GetLocalTm`, die statisch eine interne verwendet zugeordneten Puffer. Die Daten in diesem Puffer werden aufgrund von Aufrufen von anderen überschrieben `CTime` Memberfunktionen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#156](../../atl-mfc-shared/codesnippet/cpp/ctime-class_10.cpp)]

##  <a name="getlocaltm"></a>  CTime::GetLocalTm

Ruft eine **Struct tm** Zerlegen der in dieser Zeit mit `CTime` Objekt.

```
struct tm* GetLocalTm(struct tm* ptm) const;
```

### <a name="parameters"></a>Parameter

*ptm*<br/>
Verweist auf einen Puffer, der die Zeitdaten erhält. Wenn dieser Zeiger NULL ist, wird eine Ausnahme ausgelöst.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine ausgefüllt **Struct tm** wie in der Includedatei Zeit definiert. H. Finden Sie unter [Gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) für das Strukturlayout.

### <a name="remarks"></a>Hinweise

`GetLocalTm` Gibt die Ortszeit zurück.

*Ptm* darf nicht NULL sein. Wenn Sie das alte Verhalten verwenden, in denen zurücksetzen möchten *Ptm* kann NULL sein, um anzugeben, dass eine interne, statisch zugewiesenen Puffer verwendet werden sollte, dann heben Sie die Definition _SECURE_ATL.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#157](../../atl-mfc-shared/codesnippet/cpp/ctime-class_11.cpp)]

##  <a name="getminute"></a>  CTime::GetMinute

Gibt zurück, die Minute, dargestellt durch die `CTime` Objekt.

```
int GetMinute() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Minute, basierend auf der Ortszeit oder im Bereich von 0 bis 59 zurück.

### <a name="remarks"></a>Hinweise

Diese Funktion ruft `GetLocalTm`, die statisch eine interne verwendet zugeordneten Puffer. Die Daten in diesem Puffer werden aufgrund von Aufrufen von anderen überschrieben `CTime` Memberfunktionen.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [GetHour](#gethour).

##  <a name="getmonth"></a>  CTime::GetMonth

Gibt zurück, Monats, dargestellt durch die `CTime` Objekt.

```
int GetMonth() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Monat, basierend auf der Ortszeit oder im Bereich von 1 bis 12 (1 = Januar).

### <a name="remarks"></a>Hinweise

Diese Funktion ruft `GetLocalTm`, die statisch eine interne verwendet zugeordneten Puffer. Die Daten in diesem Puffer werden aufgrund von Aufrufen von anderen überschrieben `CTime` Memberfunktionen.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [GetDay](#getday).

##  <a name="getsecond"></a>  CTime::GetSecond

Gibt zurück, das zweite, dargestellt durch die `CTime` Objekt.

```
int GetSecond() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt zurück, das zweite, basierend auf der Ortszeit oder im Bereich von 0 bis 59.

### <a name="remarks"></a>Hinweise

Diese Funktion ruft `GetLocalTm`, die statisch eine interne verwendet zugeordneten Puffer. Die Daten in diesem Puffer werden aufgrund von Aufrufen von anderen überschrieben `CTime` Memberfunktionen.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [GetHour](#gethour).

##  <a name="gettime"></a>  CTime::GetTime

Gibt eine **__time64_t** Wert für den angegebenen `CTime` Objekt.

```
__time64_t GetTime() const throw();
```

### <a name="return-value"></a>Rückgabewert

`GetTime` Gibt die Anzahl der Sekunden zwischen dem aktuellen `CTime` -Objekt und dem 1. Januar 1970.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#158](../../atl-mfc-shared/codesnippet/cpp/ctime-class_12.cpp)]

##  <a name="getyear"></a>  CTime::GetYear

Gibt zurück, dargestellt durch die `CTime` Objekt.

```
int GetYear();
```

### <a name="return-value"></a>Rückgabewert

Gibt das Jahr, basierend auf der Ortszeit oder im Bereich von Januar 1,1970, um am 18. Januar 2038 (inklusiv).

### <a name="remarks"></a>Hinweise

Diese Funktion ruft `GetLocalTm`, die statisch eine interne verwendet zugeordneten Puffer. Die Daten in diesem Puffer werden aufgrund von Aufrufen von anderen überschrieben `CTime` Memberfunktionen.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [GetDay](#getday).

##  <a name="operator_eq"></a>  CTime::operator =

Der Zuweisungsoperator.

```
CTime& operator=(__time64_t time) throw();
```

### <a name="parameters"></a>Parameter

*time*<br/>
Die neuen Datums-/Uhrzeit-Wert.

### <a name="return-value"></a>Rückgabewert

Die aktualisierte `CTime` Objekt.

### <a name="remarks"></a>Hinweise

Dieser überladenen Zuweisungsoperator kopiert die Uhrzeit der Quelle in diese `CTime` Objekt. Der interne Zeit Speicher eine `CTime` Objekt ist unabhängig von der Zeitzone. Zeitzonenkonvertierung ist nicht erforderlich, bei der Zuordnung.

##  <a name="operator_add_-"></a>  CTime::operator +, -

Diese Operatoren, Addition und Subtraktion `CTimeSpan` und `CTime` Objekte.

```
CTime operator+(CTimeSpan timeSpan) const throw();
CTime operator-(CTimeSpan timeSpan) const throw();
CTimeSpan operator-(CTime time) const throw();
```

### <a name="parameters"></a>Parameter

*timeSpan*<br/>
Die `CTimeSpan` Objekt, das hinzugefügt oder entfernt werden.

*time*<br/>
Die `CTime` Objekt, das subtrahiert werden soll.

### <a name="return-value"></a>Rückgabewert

Ein `CTime` oder `CTimeSpan` Objekt, das das Ergebnis des Vorgangs darstellt.

### <a name="remarks"></a>Hinweise

`CTime` Objekte darstellen absoluten Zeitpunkt `CTimeSpan` Objekte darstellen, relative Zeit. Die ersten beiden Operatoren können Sie von Addition und Subtraktion `CTimeSpan` Objekte in und aus `CTime` Objekte. Der dritte Operator können Sie eine zu subtrahieren `CTime` Objekt von einem anderen ergibt eine `CTimeSpan` Objekt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#159](../../atl-mfc-shared/codesnippet/cpp/ctime-class_13.cpp)]

##  <a name="operator_add_eq_-_eq"></a>  CTime::operator +=, =

Diese Operatoren, Addition und Subtraktion ein `CTimeSpan` Objekt auf und aus diesem `CTime` Objekt.

```
CTime& operator+=(CTimeSpan span) throw();
CTime& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Die `CTimeSpan` Objekt, das hinzugefügt oder entfernt werden.

### <a name="return-value"></a>Rückgabewert

Die aktualisierte `CTime` Objekt.

### <a name="remarks"></a>Hinweise

Diese Operatoren können Sie von Addition und Subtraktion ein `CTimeSpan` Objekt auf und aus diesem `CTime` Objekt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#160](../../atl-mfc-shared/codesnippet/cpp/ctime-class_14.cpp)]

##  <a name="serialize64"></a>  CTime::Serialize64

> [!NOTE]
> Diese Methode ist nur in MFC-Projekten verfügbar.

Serialisiert die Membervariable in oder aus einem Archiv zugeordneten Daten.

```
CArchive& Serialize64(CArchive& ar);
```

### <a name="parameters"></a>Parameter

*ar*<br/>
Die `CArchive` -Objekt, das Sie aktualisieren möchten.

### <a name="return-value"></a>Rückgabewert

Die aktualisierte `CArchive` Objekt.

## <a name="see-also"></a>Siehe auch

[asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)<br/>
[_ftime_s, _ftime32_s, _ftime64_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)<br/>
[CTimeSpan-Klasse](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)
