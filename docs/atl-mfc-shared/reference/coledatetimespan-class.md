---
title: COleDateTimeSpan-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::Format
- ATLCOMTIME/ATL::COleDateTimeSpan::GetDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::GetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::SetDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::SetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::m_span
- ATLCOMTIME/ATL::COleDateTimeSpan::m_status
helpviewer_keywords:
- timespan
- time span
- shared classes, COleDateTimeSpan
- Date data type, MFC encapsulation of
- COleDateTimeSpan class
ms.assetid: 7441526d-a30a-4019-8fb3-3fee6f897cbe
ms.openlocfilehash: 7bcf4c50577cf7211f90415143edac9fd0df1d5b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509330"
---
# <a name="coledatetimespan-class"></a>COleDateTimeSpan-Klasse

Stellt einen relativen Zeitpunkt, eine Zeitspanne dar.

## <a name="syntax"></a>Syntax

```
class COleDateTimeSpan
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleDateTimeSpan::COleDateTimeSpan](#coledatetimespan)|Erstellt ein `COleDateTimeSpan`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleDateTimeSpan::Format](#format)|Generiert eine formatierte Zeichenfolgendarstellung einer `COleDateTimeSpan` Objekt.|
|[COleDateTimeSpan::GetDays](#getdays)|Gibt dem Tagteil von der Spanne zurück, dies `COleDateTimeSpan` -Objekt darstellt.|
|[COleDateTimeSpan::GetHours](#gethours)|Gibt dem Stundenteil der Spanne zurück, dies `COleDateTimeSpan` -Objekt darstellt.|
|[COleDateTimeSpan::GetMinutes](#getminutes)|Gibt dem Minutenteil der Spanne zurück, dies `COleDateTimeSpan` -Objekt darstellt.|
|[COleDateTimeSpan::GetSeconds](#getseconds)|Gibt dem zweiten Teil der Spanne zurück, dies `COleDateTimeSpan` -Objekt darstellt.|
|[COleDateTimeSpan::GetStatus](#getstatus)|Ruft ab, der den Status (Gültigkeit) `COleDateTimeSpan` Objekt.|
|[COleDateTimeSpan::GetTotalDays](#gettotaldays)|Gibt der Anzahl der Tage dies `COleDateTimeSpan` -Objekt darstellt.|
|[COleDateTimeSpan::GetTotalHours](#gettotalhours)|Gibt der Anzahl der Stunden dies `COleDateTimeSpan` -Objekt darstellt.|
|[COleDateTimeSpan::GetTotalMinutes](#gettotalminutes)|Gibt der Anzahl der Minuten dies `COleDateTimeSpan` -Objekt darstellt.|
|[COleDateTimeSpan::GetTotalSeconds](#gettotalseconds)|Gibt der Anzahl der Sekunden zurück, dies `COleDateTimeSpan` -Objekt darstellt.|
|[COleDateTimeSpan::SetDateTimeSpan](#setdatetimespan)|Legt den Wert dieses `COleDateTimeSpan` Objekt.|
|[COleDateTimeSpan::SetStatus](#setstatus)|Legt den Status (Gültigkeit) dieses `COleDateTimeSpan` Objekt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|||
|-|-|
|[Operator +, -](#operator_add_-)|Hinzufügen, subtrahiert werden soll, und ändern Sie das Zeichen für `COleDateTimeSpan` Werte.|
|[Operator +=, =](#operator_add_eq_-_eq)|Addition und Subtraktion ein `COleDateTimeSpan` Wert aus diesem `COleDateTimeSpan` Wert.|
|[operator =](#operator_eq)|Kopiert ein `COleDateTimeSpan` Wert.|
|[Operator ==, <, < =](#coledatetimespan_relational_operators)|Vergleichen Sie zwei `COleDateTimeSpan` Werte.|
|[Operator double](#operator_double)|Konvertiert diese `COleDateTimeSpan` -Werts in einen **doppelte**.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COleDateTimeSpan::m_span](#m_span)|Enthält die zugrunde liegende **doppelte** für diesen `COleDateTimeSpan` Objekt.|
|[COleDateTimeSpan::m_status](#m_status)|Enthält den Status dieser `COleDateTimeSpan` Objekt.|

## <a name="remarks"></a>Hinweise

`COleDateTimeSpan` eine Basisklasse keinen.

Ein `COleDateTimeSpan` behält Zeit in Tagen.

`COleDateTimeSpan` wird verwendet, mit dessen Begleitklasse [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md). `COleDateTime` Kapselt die `DATE` -Datentyp der OLE-Automatisierung. `COleDateTime` Stellt die absolute Zeitwerte dar. Alle `COleDateTime` Berechnungen umfassen `COleDateTimeSpan` Werte. Die Beziehung zwischen diesen Klassen ist analog zu der eine zweite Grenze zwischen [CTime](../../atl-mfc-shared/reference/ctime-class.md) und [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).

Weitere Informationen zu den `COleDateTime` und `COleDateTimeSpan` Klassen finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

## <a name="requirements"></a>Anforderungen

**Header:** "atlcomtime.h"

##  <a name="coledatetimespan_relational_operators"></a>  COleDateTimeSpan-Operatoren (Relational)

Vergleichsoperatoren.

```
bool operator==(const COleDateTimeSpan& dateSpan) const throw();
bool operator!=(const COleDateTimeSpan& dateSpan) const throw();
bool operator<(const COleDateTimeSpan& dateSpan) const throw();
bool operator>(const COleDateTimeSpan& dateSpan) const throw();
bool operator<=(const COleDateTimeSpan& dateSpan) const throw();
bool operator>=(const COleDateTimeSpan& dateSpan) const throw();
```

### <a name="parameters"></a>Parameter

*dateSpan*<br/>
Der zu vergleichende `COleDateTimeSpan`.

### <a name="return-value"></a>Rückgabewert

Diese Operatoren vergleichen zwei Werte für Datum/Uhrzeit-Spanne und gibt TRUE zurück, wenn die Bedingung true ist; andernfalls "false".

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Ein ATLASSERT treten auf, wenn ein Operand ungültig ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#25](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_1.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#26](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_2.cpp)]

##  <a name="coledatetimespan"></a>  COleDateTimeSpan::COleDateTimeSpan

Erstellt ein `COleDateTimeSpan`-Objekt.

```
COleDateTimeSpan() throw();
COleDateTimeSpan(double dblSpanSrc) throw();
COleDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```

### <a name="parameters"></a>Parameter

*dblSpanSrc*<br/>
Die Anzahl der Tage, die in die neue kopiert werden `COleDateTimeSpan` Objekt.

*lDays*, *nHours*, *nMins*, *nSecs*<br/>
Geben Sie den Tag und Werte in die neue kopiert werden `COleDateTimeSpan` Objekt.

### <a name="remarks"></a>Hinweise

Alle diese Konstruktoren erstellen neue `COleDateTimeSpan` Objekte, die auf den angegebenen Wert initialisiert. Eine kurze Beschreibung jeder dieser Konstruktoren folgt:

- **COleDateTimeSpan ()** erstellt eine `COleDateTimeSpan` Objekt mit 0 initialisiert.

- **COleDateTimeSpan (** `dblSpanSrc` **)** erstellt eine `COleDateTimeSpan` Objekt aus einem Gleitkomma-Wert.

- **COleDateTimeSpan (** `lDays` **,** `nHours` **,** `nMins` **,** `nSecs` **)**  Erstellt eine `COleDateTimeSpan` Objekt mit den angegebenen numerischen Werten initialisiert.

Der Status der neuen `COleDateTimeSpan` Objekt zu ungültig festgelegt ist.

Weitere Informationen über die Grenzen für `COleDateTimeSpan` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#14](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_3.cpp)]

##  <a name="format"></a>  COleDateTimeSpan::Format

Generiert eine formatierte Zeichenfolgendarstellung einer `COleDateTimeSpan` Objekt.

```
CString Format(LPCTSTR pFormat) const;
CString Format(UINT nID) const;
```

### <a name="parameters"></a>Parameter

*pFormat*<br/>
Eine Formatierungszeichenfolge ähnelt der `printf` Formatierungszeichenfolge. Formatierungscodes Prozentsatz vorangestellt (`%`) anmelden, werden mit den entsprechenden ersetzt `COleDateTimeSpan` Komponente. Andere Zeichen in der Formatierungszeichenfolge werden auf die zurückgegebene Zeichenfolge unverändert kopiert. Der Wert und die Bedeutung der Formatierungscodes für `Format` sind nachfolgend aufgeführt:

- **%H** Stunden in den aktuellen Tag

- **%M** Minuten in der aktuellen Stunde

- **%S** Sekunden in der aktuellen Minute

- **%%** Prozentzeichen

Die vier oben aufgeführten Formatcodes sind die einzige Codes, die Format akzeptiert.

-

*nID*<br/>
Die Ressourcen-ID für die Format-Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Ein `CString` , die den formatierten Wert für Datum/Uhrzeit-Spanne enthält.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktionen um eine formatierte Darstellung des Werts Zeitspanne zu erstellen. Wenn der Status dieser `COleDateTimeSpan` Objekt null ist. der zurückgegebene Wert ist eine leere Zeichenfolge. Wenn der Status ungültig ist, wird die zurückgegebene Zeichenfolge durch die Zeichenfolgenressource IDS_INVALID_DATETIMESPAN angegeben.

Eine kurze Beschreibung der Formate für diese Funktion folgt:

**Format (** *pFormat* **)**<br/>
Dieses Formular formatiert den Wert, der mit der Formatzeichenfolge, die spezielle Formatierungscodes enthält, die ein Prozentzeichen (%) vorangestellt werden, wie in `printf`. Die Formatierungszeichenfolge wird als Parameter an die Funktion übergeben.

**Format (** *nID* **)**<br/>
Dieses Formular formatiert den Wert, der mit der Formatzeichenfolge, die spezielle Formatierungscodes enthält, die ein Prozentzeichen (%) vorangestellt werden, wie in `printf`. Die Formatierungszeichenfolge ist eine Ressource. Die ID der Ressource, diese Zeichenfolge wird als Parameter übergeben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#15](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_4.cpp)]

##  <a name="getdays"></a>  COleDateTimeSpan::GetDays

Ruft den Tagteil von diesen Wert für Datum/Uhrzeit-Spanne ab.

```
LONG GetDays() const throw();
```

### <a name="return-value"></a>Rückgabewert

Der Tagteil dieses Werts für Datum/Uhrzeit-Spanne.

### <a name="remarks"></a>Hinweise

Die Rückgabe Werte aus dieser Funktion zwischen ca. - 3,615,000 und 3,615,000.

Für andere Funktionen, die den Wert der Abfrage eine `COleDateTimeSpan` Objekt, finden Sie unter den folgenden Member-Funktionen:

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#16](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_5.cpp)]

##  <a name="gethours"></a>  COleDateTimeSpan::GetHours

Ruft den Stundenteil dieses Werts für Datum/Uhrzeit-Spanne ab.

```
LONG GetHours() const throw();
```

### <a name="return-value"></a>Rückgabewert

Der Stunden Teil dieser Wert für Datum/Uhrzeit-Spanne.

### <a name="remarks"></a>Hinweise

Die Rückgabewerte von dieser Funktion zwischen - 23 und 23.

Für andere Funktionen, die den Wert der Abfrage eine `COleDateTimeSpan` Objekt, finden Sie unter den folgenden Member-Funktionen:

- [GetDays](#getdays)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#17](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_6.cpp)]

##  <a name="getminutes"></a>  COleDateTimeSpan::GetMinutes

Ruft den Minutenteil dieses Werts für Datum/Uhrzeit-Spanne ab.

```
LONG GetMinutes() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Minuten Teil dieser Wert für Datum/Uhrzeit-Spanne.

### <a name="remarks"></a>Hinweise

Die Rückgabewerte von dieser Funktion zwischen - 59 und 59.

Für andere Funktionen, die den Wert der Abfrage eine `COleDateTimeSpan` Objekt, finden Sie unter den folgenden Member-Funktionen:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#18](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_7.cpp)]

##  <a name="getseconds"></a>  COleDateTimeSpan::GetSeconds

Ruft den zweiten Teil dieses Werts für Datum/Uhrzeit-Spanne ab.

```
LONG GetSeconds() const throw();
```

### <a name="return-value"></a>Rückgabewert

Der Sekundenteil dieses Werts für Datum/Uhrzeit-Spanne.

### <a name="remarks"></a>Hinweise

Die Rückgabewerte von dieser Funktion zwischen - 59 und 59.

Für andere Funktionen, die den Wert der Abfrage eine `COleDateTimeSpan` Objekt, finden Sie unter den folgenden Member-Funktionen:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#19](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_8.cpp)]

##  <a name="getstatus"></a>  COleDateTimeSpan::GetStatus

Ruft ab, der den Status (Gültigkeit) `COleDateTimeSpan` Objekt.

```
DateTimeSpanStatus GetStatus() const throw();
```

### <a name="return-value"></a>Rückgabewert

Der Status dieser `COleDateTimeSpan` Wert.

### <a name="remarks"></a>Hinweise

Der Rückgabewert wird definiert, durch die `DateTimeSpanStatus` Enumerationstyp, der in definiert ist die `COleDateTimeSpan` Klasse.

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
};
```

Eine kurze Beschreibung dieser Status-Werte finden Sie in der folgenden Liste:

- `COleDateTimeSpan::valid` Gibt an, das von diesem `COleDateTimeSpan` Objekt gültig ist.

- `COleDateTimeSpan::invalid` Gibt an, das von diesem `COleDateTimeSpan` Objekt ist ungültig; d. h. der Wert möglicherweise nicht korrekt.

- `COleDateTimeSpan::null` Gibt an, das von diesem `COleDateTimeSpan` Objekt null ist, d. h., dass für dieses Objekt kein Wert angegeben wurde. (Dies ist "null", in dem Sinne Database "kein Wert, wenn" im Gegensatz zu den C++-NULL).

Der Status einer `COleDateTimeSpan` Objekt ist ungültig. in den folgenden Fällen:

- Wenn dieses Objekt, einem Überlauf oder Unterlauf während eines arithmetischen Zuweisung, nämlich aufgetreten sind `+=` oder `-=`.

- Wenn ein ungültiger Wert für dieses Objekt zugewiesen wurde.

- Wenn der Status dieses Objekts explizit festgelegt wurde, um ungültige mit `SetStatus`.

Weitere Informationen zu den Vorgängen, die den Status als ungültig festlegen können, finden Sie unter [COleDateTimeSpan::operator +, -](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) und [COleDateTimeSpan::operator +=, -=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).

Weitere Informationen über die Grenzen für `COleDateTimeSpan` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

##  <a name="gettotaldays"></a>  COleDateTimeSpan::GetTotalDays

Ruft diesen Wert Datum/Uhrzeit-Spanne in Tagen ab.

```
double GetTotalDays() const throw();
```

### <a name="return-value"></a>Rückgabewert

Dieses Datum/Uhrzeit-Span-Wert in Tagen angegeben. Obwohl diese Funktion Prototyp, um einen Double-Wert zurückzugeben ist, wird immer einen ganzzahliger Wert zurückgegeben.

### <a name="remarks"></a>Hinweise

Die Rückgabewerte von dieser Funktion zwischen ca. - 3.65e6 und 3.65e6.

Für andere Funktionen, die den Wert der Abfrage eine `COleDateTimeSpan` Objekt, finden Sie unter den folgenden Member-Funktionen:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#20](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_9.cpp)]

##  <a name="gettotalhours"></a>  COleDateTimeSpan::GetTotalHours

Ruft ab diesem Datum/Uhrzeit-Span-Wert, der in Stunden ausgedrückt.

```
double GetTotalHours() const throw();
```

### <a name="return-value"></a>Rückgabewert

Dieses Datum/Uhrzeit-Span-Wert, der in Stunden ausgedrückt wird. Obwohl diese Funktion Prototyp, um einen Double-Wert zurückzugeben ist, wird immer einen ganzzahliger Wert zurückgegeben.

### <a name="remarks"></a>Hinweise

Die Rückgabewerte von dieser Funktion zwischen ca. - 8.77e7 und 8.77e7.

Für andere Funktionen, die den Wert der Abfrage eine `COleDateTimeSpan` Objekt, finden Sie unter den folgenden Member-Funktionen:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Beispiel

Siehe das Beispiel für [GetTotalDays](#gettotaldays).

##  <a name="gettotalminutes"></a>  COleDateTimeSpan::GetTotalMinutes

Ruft diesen Wert Datum/Zeitspanne in Minuten ab.

```
double GetTotalMinutes() const throw();
```

### <a name="return-value"></a>Rückgabewert

Dieses Datum/Uhrzeit-Spanne-Wert, ausgedrückt in Minuten. Obwohl diese Funktion Prototyp, um einen Double-Wert zurückzugeben ist, wird immer einen ganzzahliger Wert zurückgegeben.

### <a name="remarks"></a>Hinweise

Die Rückgabewerte von dieser Funktion zwischen ca. - 5.26e9 und 5.26e9.

Für andere Funktionen, die den Wert der Abfrage eine `COleDateTimeSpan` Objekt, finden Sie unter den folgenden Member-Funktionen:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Beispiel

Siehe das Beispiel für [GetTotalDays](#gettotaldays).

##  <a name="gettotalseconds"></a>  COleDateTimeSpan::GetTotalSeconds

Ruft diesen Wert Datum/Zeitspanne in Sekunden ab.

```
double GetTotalSeconds() const throw();
```

### <a name="return-value"></a>Rückgabewert

Dieses Datum/Uhrzeit-Span-Wert in Sekunden angegeben. Obwohl diese Funktion Prototyp, um einen Double-Wert zurückzugeben ist, wird immer einen ganzzahliger Wert zurückgegeben.

### <a name="remarks"></a>Hinweise

Die Rückgabewerte von dieser Funktion liegen zwischen ca. – 3.16e11 zu 3.16e11.

Für andere Funktionen, die den Wert der Abfrage eine `COleDateTimeSpan` Objekt, finden Sie unter den folgenden Member-Funktionen:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

### <a name="example"></a>Beispiel

Siehe das Beispiel für [GetTotalDays](#gettotaldays).

##  <a name="m_span"></a>  COleDateTimeSpan::m_span

Die zugrunde liegende **doppelte** Wert für diesen `COleDateTime` Objekt.

```
double m_span;
```

### <a name="remarks"></a>Hinweise

Dieser Wert drückt aus, der Datum/Zeitraum in Tagen.

> [!CAUTION]
>  Ändern des Werts in der **doppelte** Datenmember ändert sich den Wert dieser `COleDateTimeSpan` Objekt. Er ändert nicht den Status dieses `COleDateTimeSpan` Objekt.

##  <a name="m_status"></a>  COleDateTimeSpan::m_status

Der Typ für dieses Datenelement ist den enumerierten Typ `DateTimeSpanStatus`, definiert in der `COleDateTimeSpan` Klasse.

```
DateTimeSpanStatus m_status;
```

### <a name="remarks"></a>Hinweise

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
   };
```

Eine kurze Beschreibung dieser Status-Werte finden Sie in der folgenden Liste:

- `COleDateTimeSpan::valid` Gibt an, das von diesem `COleDateTimeSpan` Objekt gültig ist.

- `COleDateTimeSpan::invalid` Gibt an, das von diesem `COleDateTimeSpan` Objekt ist ungültig; d. h. der Wert möglicherweise nicht korrekt.

- `COleDateTimeSpan::null` Gibt an, das von diesem `COleDateTimeSpan` Objekt null ist, d. h., dass für dieses Objekt kein Wert angegeben wurde. (Dies ist "null", in dem Sinne Database "kein Wert, wenn" im Gegensatz zu den C++-NULL).

Der Status einer `COleDateTimeSpan` Objekt ist ungültig. in den folgenden Fällen:

- Wenn dieses Objekt, einem Überlauf oder Unterlauf während eines arithmetischen Zuweisung, nämlich aufgetreten sind `+=` oder `-=`.

- Wenn ein ungültiger Wert für dieses Objekt zugewiesen wurde.

- Wenn der Status dieses Objekts explizit festgelegt wurde, um ungültige mit [SetStatus](#setstatus).

Weitere Informationen zu den Vorgängen, die den Status als ungültig festlegen können, finden Sie unter [COleDateTimeSpan::operator +, -](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) und [COleDateTimeSpan::operator +=, -=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).

> [!CAUTION]
>  Dieses Datenelement ist für erweiterte programmierungssituationen. Sie sollten die Inline-Memberfunktionen verwenden [GetStatus](#getstatus) und [SetStatus](#setstatus). Finden Sie unter `SetStatus` für weitere Punkte in Bezug auf die dieses Datenelement explizit festlegen.

Weitere Informationen über die Grenzen für `COleDateTimeSpan` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).

##  <a name="operator_eq"></a>  COleDateTimeSpan::operator =

Kopiert ein `COleDateTimeSpan` Wert.

```
COleDateTimeSpan& operator=(double dblSpanSrc) throw();
```

### <a name="remarks"></a>Hinweise

Dieser überladenen Zuweisungsoperator kopiert den Wert des Datums-/Zeitspanne, in diese `COleDateTimeSpan` Objekt.

##  <a name="operator_add_-"></a>  COleDateTimeSpan::operator +, -

Hinzufügen, subtrahiert werden soll, und ändern Sie das Zeichen für `COleDateTimeSpan` Werte.

```
COleDateTimeSpan operator+(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-() const throw();
```

### <a name="remarks"></a>Hinweise

Die ersten beiden Operatoren können Sie die Addition und Subtraktion von Datum/Uhrzeit-Bereich Werte. Die dritte können Sie die Vorzeichen eines Datum/Uhrzeit-Span-Werts zu ändern.

Wenn einer der Operanden null ist, ist den Status des resultierenden `COleDateTimeSpan` Wert ist null.

Wenn es sich bei den Operanden ist ungültig, und die andere ist nicht null ist, den Status des resultierenden `COleDateTimeSpan` Wert ist ungültig.

Weitere Informationen zu den gültigen, Ungültiger und null-Status-Werte, finden Sie unter den [M_status](#m_status) Membervariablen gespeichert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#23](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_10.cpp)]

##  <a name="operator_add_eq_-_eq"></a>  COleDateTimeSpan::operator +=, =

Addition und Subtraktion ein `COleDateTimeSpan` Wert aus diesem `COleDateTimeSpan` Wert.

```
COleDateTimeSpan& operator+=(const COleDateTimeSpan dateSpan) throw();
COleDateTimeSpan& operator-=(const COleDateTimeSpan dateSpan) throw();
```

### <a name="remarks"></a>Hinweise

Diese Operatoren können Sie die Addition und Subtraktion von Datums-/Zeitspanne Werte aus dieser `COleDateTimeSpan` Objekt. Wenn einer der Operanden null ist, ist den Status des resultierenden `COleDateTimeSpan` Wert ist null.

Wenn es sich bei den Operanden ist ungültig, und die andere ist nicht null ist, den Status des resultierenden `COleDateTimeSpan` Wert ist ungültig.

Weitere Informationen zu den gültigen, Ungültiger und null-Status-Werte, finden Sie unter den [M_status](#m_status) Membervariablen gespeichert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#24](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_11.cpp)]

##  <a name="operator_double"></a>  Doppelte COleDateTimeSpan::operator

Konvertiert diese `COleDateTimeSpan` -Werts in einen **doppelte**.

```
operator double() const throw();
```

### <a name="remarks"></a>Hinweise

Dieser Operator gibt den Wert dieses `COleDateTimeSpan` Wert als Gleitkommazahl von Tagen.

##  <a name="setdatetimespan"></a>  COleDateTimeSpan::SetDateTimeSpan

Legt den Wert dieses Werts für Datum/Uhrzeit-Spanne.

```
void SetDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```

### <a name="parameters"></a>Parameter

*lDays*, *nHours*, *nMins*, *nSecs*<br/>
Zeigen die Werte für Datum-Span und Zeitspanne, die in diese kopiert werden `COleDateTimeSpan` Objekt.

### <a name="remarks"></a>Hinweise

Für Funktionen, die den Wert der Abfrage eine `COleDateTimeSpan` Objekt, finden Sie unter den folgenden Member-Funktionen:

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#21](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_12.cpp)]

##  <a name="setstatus"></a>  COleDateTimeSpan::SetStatus

Legt den Status (Gültigkeit) dieses `COleDateTimeSpan` Objekt.

```
void SetStatus(DateTimeSpanStatus status) throw();
```

### <a name="parameters"></a>Parameter

*Status*<br/>
Der neue Statuswert für diesen `COleDateTimeSpan` Objekt.

### <a name="remarks"></a>Hinweise

Die *Status* Parameterwert wird definiert, indem die `DateTimeSpanStatus` Enumerationstyp, der in definiert ist die `COleDateTimeSpan` Klasse.

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
   };
```

Eine kurze Beschreibung dieser Status-Werte finden Sie in der folgenden Liste:

- `COleDateTimeSpan::valid` Gibt an, das von diesem `COleDateTimeSpan` Objekt gültig ist.

- `COleDateTimeSpan::invalid` Gibt an, das von diesem `COleDateTimeSpan` Objekt ist ungültig; d. h. der Wert möglicherweise nicht korrekt.

- `COleDateTimeSpan::null` Gibt an, das von diesem `COleDateTimeSpan` Objekt null ist, d. h., dass für dieses Objekt kein Wert angegeben wurde. (Dies ist "null", in dem Sinne Database "kein Wert, wenn" im Gegensatz zu den C++-NULL).

   > [!CAUTION]
   > Diese Funktion ist für die erweiterte programmierungssituationen. Diese Funktion wird die Daten in dieses Objekt nicht geändert. Dieser wird den meisten Fällen verwendet, legen Sie den Status auf **null** oder **ungültige**. Beachten Sie, dass der Zuweisungsoperator ( [Operator =](#eq)) und [SetDateTimeSpan](#setdatetimespan) führen Sie den Status des Objekts basierend auf den Werten der Datenquelle festgelegt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#22](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_13.cpp)]

## <a name="see-also"></a>Siehe auch

[COleDateTime-Klasse](../../atl-mfc-shared/reference/coledatetime-class.md)<br/>
[CTime-Klasse](../../atl-mfc-shared/reference/ctime-class.md)<br/>
[CTimeSpan-Klasse](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)

