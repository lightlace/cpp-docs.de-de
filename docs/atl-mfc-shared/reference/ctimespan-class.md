---
title: CTimeSpan-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTimeSpan
- ATLTIME/ATL::CTimeSpan
- ATLTIME/ATL::CTimeSpan::CTimeSpan
- ATLTIME/ATL::CTimeSpan::Format
- ATLTIME/ATL::CTimeSpan::GetDays
- ATLTIME/ATL::CTimeSpan::GetHours
- ATLTIME/ATL::CTimeSpan::GetMinutes
- ATLTIME/ATL::CTimeSpan::GetSeconds
- ATLTIME/ATL::CTimeSpan::GetTimeSpan
- ATLTIME/ATL::CTimeSpan::GetTotalHours
- ATLTIME/ATL::CTimeSpan::GetTotalMinutes
- ATLTIME/ATL::CTimeSpan::GetTotalSeconds
- ATLTIME/ATL::CTimeSpan::Serialize64
dev_langs:
- C++
helpviewer_keywords:
- elapsed time, CTimeSpan object
- timespan
- time span
- CTimeSpan class
- shared classes, CTimeSpan
- time, elapsed
ms.assetid: ee1e42f6-1839-477a-8435-fb26ad475140
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6703c177b20230d7308ebd22b3b54edbdb1d2a14
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43758705"
---
# <a name="ctimespan-class"></a>CTimeSpan-Klasse

Eine Zeitspanne, die intern als die Anzahl der Sekunden, in dem Zeitraum gespeichert ist.

## <a name="syntax"></a>Syntax

```
class CTimeSpan
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CTimeSpan::CTimeSpan](#ctimespan)|Erstellt `CTimeSpan` Objekte auf unterschiedliche Weise.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CTimeSpan::Format](#format)|Konvertiert eine `CTimeSpan` in eine formatierte Zeichenfolge.|
|[CTimeSpan::GetDays](#getdays)|Gibt einen Wert, der die Anzahl der vollständigen Tage in diesem darstellt `CTimeSpan`.|
|[CTimeSpan::GetHours](#gethours)|Gibt einen Wert, der die Anzahl der Stunden in den aktuellen Tag (-23 bis 23) darstellt.|
|[CTimeSpan::GetMinutes](#getminutes)|Gibt einen Wert, der die Anzahl der Minuten in der aktuellen Stunde (-59 bis 59) darstellt.|
|[CTimeSpan::GetSeconds](#getseconds)|Gibt einen Wert, der die Anzahl der Sekunden in der aktuellen Minute (-59 bis 59) darstellt.|
|[CTimeSpan::GetTimeSpan](#gettimespan)|Gibt den Wert des der `CTimeSpan` Objekt.|
|[CTimeSpan::GetTotalHours](#gettotalhours)|Gibt einen Wert, der die Gesamtzahl der vollständige Stunden in diesem darstellt `CTimeSpan`.|
|[CTimeSpan::GetTotalMinutes](#gettotalminutes)|Gibt einen Wert, der die Gesamtzahl der Minuten. in diesem darstellt `CTimeSpan`.|
|[CTimeSpan::GetTotalSeconds](#gettotalseconds)|Gibt einen Wert, der die Gesamtzahl der vollständige Sekunden in diesem darstellt `CTimeSpan`.|
|[CTimeSpan::Serialize64](#serialize64)|Serialisiert Daten in oder aus einem Archiv an.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[Operator + -](#operator_add_-)|Fügt und subtrahiert `CTimeSpan` Objekte.|
|[Operator += =](#operator_add_eq_-_eq)|Fügt und subtrahiert einen `CTimeSpan` Objekt auf und aus diesem `CTimeSpan`.|
|[Operator == < usw..](#ctimespan_comparison_operators)|Vergleicht zwei Werte für relative Zeit.|

## <a name="remarks"></a>Hinweise

`CTimeSpan` eine Basisklasse keinen.

`CTimeSpan` Funktionen konvertieren Sekunden, um verschiedene Kombinationen von Tagen, Stunden, Minuten und Sekunden.

Die `CTimeSpan` Objekt befindet sich in einem **__time64_t** -Struktur, die 8 Bytes ist.

Eine Begleitklasse [CTime](../../atl-mfc-shared/reference/ctime-class.md), eine absolute Zeit darstellt.

Die `CTime` und `CTimeSpan` Klassen sind nicht für die Ableitung ausgelegt. Da es keine virtuellen Funktionen, die Größe beider sind `CTime` und `CTimeSpan` Objekte wird genau 8 Bytes. Die meisten Memberfunktionen werden Inline.

Weitere Informationen zur Verwendung von `CTimeSpan`, finden Sie in den Artikeln [Datums- /](../../atl-mfc-shared/date-and-time.md), und [Uhrzeitverwaltung](../../c-runtime-library/time-management.md) in die *Run-Time Library Reference*.

## <a name="requirements"></a>Anforderungen

**Header:** atltime.h

##  <a name="ctimespan_comparison_operators"></a>  CTimeSpan-Vergleichsoperatoren

Vergleichsoperatoren.

```
bool operator==(CTimeSpan span) const throw();
bool operator!=(CTimeSpan span) const throw();
bool operator<(CTimeSpan span) const throw();
bool operator>(CTimeSpan span) const throw();
bool operator<=(CTimeSpan span) const throw();
bool operator>=(CTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameter

*umfassen*

Das zu vergleichende Objekt.

### <a name="return-value"></a>Rückgabewert

Diese Operatoren vergleichen zwei relative Zeitwerte. Sie "true" zurückgegeben wird, wenn die Bedingung erfüllt ist. andernfalls "false".

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#169](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_1.cpp)]

##  <a name="ctimespan"></a>  CTimeSpan::CTimeSpan

Erstellt `CTimeSpan` Objekte auf unterschiedliche Weise.

```
CTimeSpan() throw();
CTimeSpan(__time64_t time) throw();

CTimeSpan(  
LONG lDays,
int nHours,
int nMins,
int nSecs) throw();
```

### <a name="parameters"></a>Parameter

*timeSpanSrc*  
Ein `CTimeSpan` -Objekt, das bereits vorhanden ist.

*time*  
Ein **__time64_t** Time-Werten, die die Anzahl der Sekunden, in dem Zeitraum ist.

*lDays*, *nHours*, *nMins*, *nSecs*  
Tage, Stunden, Minuten und Sekunden, bzw.

### <a name="remarks"></a>Hinweise

Alle diese Konstruktoren erstellen ein neues `CTimeSpan` Objekt, mit dem angegebenen relativen initialisiert wurde. Jeder Konstruktor lautet wie folgt:

- `CTimeSpan( );` Erstellt ein nicht initialisiertes `CTimeSpan` Objekt.

- `CTimeSpan( const CTimeSpan& );` Erstellt eine `CTimeSpan` Objekt von einem anderen `CTimeSpan` Wert.

- `CTimeSpan( __time64_t );` Erstellt eine `CTimeSpan` -Objekt aus einem **__time64_t** Typ.

- `CTimeSpan( LONG, int, int, int );` Erstellt eine `CTimeSpan` Objekt von Komponenten mit den einzelnen Komponenten eingeschränkt, die den folgenden Bereichen:

    |Komponente|Bereich|  
    |---------------|-----------|  
    |*lDays*|0 bis 25.000 Objekte (ungefähr)|  
    |*nHours*|0-23|  
    |*nMins*|0-59|  
    |*nSecs*|0-59|

Beachten Sie, dass die Debugversion der Microsoft Foundation Class-Bibliothek bestätigt wird, wenn eine oder mehrere Tage Zeit Komponenten außerhalb des Bereichs. Es ist Ihre Aufgabe, die die Argumente vor dem Aufruf zu überprüfen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#162](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_2.cpp)]

##  <a name="format"></a>  CTimeSpan::Format

Generiert eine formatierte Zeichenfolge, die dies entspricht `CTimeSpan`.

```
CString Format(LPCSTR pFormat) const;
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nID) const;
```

### <a name="parameters"></a>Parameter

*pFormat*, *PszFormat*  
Eine Formatierungszeichenfolge ähnelt der `printf` Formatierungszeichenfolge. Formatierungscodes Prozentsatz vorangestellt (`%`) anmelden, werden mit den entsprechenden ersetzt `CTimeSpan` Komponente. Andere Zeichen in der Formatierungszeichenfolge werden auf die zurückgegebene Zeichenfolge unverändert kopiert. Der Wert und die Bedeutung der Formatierungscodes für `Format` sind nachfolgend aufgeführt:

- **%D** Tage in diesem gesamt `CTimeSpan`

- **%H** Stunden in den aktuellen Tag

- **%M** Minuten in der aktuellen Stunde

- **%S** Sekunden in der aktuellen Minute

- **%%** Prozentzeichen

*nID*  
Die ID der Zeichenfolge, die dieses Format identifiziert.

### <a name="return-value"></a>Rückgabewert

Ein `CString` -Objekt, das den formatierten Zeitpunkt enthält.

### <a name="remarks"></a>Hinweise

Die Debugversion der Bibliothek der Formatierungscodes überprüft und bestätigt wird, wenn der Code nicht in der obigen Liste enthalten ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#163](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_3.cpp)]

##  <a name="getdays"></a>  CTimeSpan::GetDays

Gibt einen Wert, der die Anzahl der vollständigen Tage in diesem darstellt `CTimeSpan`.

```
LONGLONG GetDays() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der vollständigen 24-Stunden-Tagen in dem Zeitraum zurück. Dieser Wert möglicherweise negativ, wenn die Zeitspanne negativ ist.

### <a name="remarks"></a>Hinweise

Beachten Sie, die Sommerzeit verursachen können `GetDays` potenziell überraschenden Ergebnis zurückgegeben. Z. B. wenn Sommerzeit gültig ist, `GetDays` meldet die Anzahl der Tage zwischen dem 1. April bis 1. Mai als 29, nicht 30, einen Tag im April wird von einer Stunde verkürzt und aus diesem Grund wird nicht als Tag abgeschlossen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#164](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_4.cpp)]

##  <a name="gethours"></a>  CTimeSpan::GetHours

Gibt einen Wert, der die Anzahl der Stunden in den aktuellen Tag (-23 bis 23) darstellt.

```
LONG GetHours() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Stunden in den aktuellen Tag zurück. Der Bereich ist-23 bis 23.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#165](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_5.cpp)]

##  <a name="getminutes"></a>  CTimeSpan::GetMinutes

Gibt einen Wert, der die Anzahl der Minuten in der aktuellen Stunde (-59 bis 59) darstellt.

```
LONG GetMinutes() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Minuten in der aktuellen Stunde zurück. Der Bereich ist-59 bis 59.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [GetHours](#gethours).

##  <a name="getseconds"></a>  CTimeSpan::GetSeconds

Gibt einen Wert, der die Anzahl der Sekunden in der aktuellen Minute (-59 bis 59) darstellt.

```
LONG GetSeconds() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Sekunden in der aktuellen Minute zurück. Der Bereich ist-59 bis 59.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [GetHours](#gethours).

##  <a name="gettimespan"></a>  CTimeSpan::GetTimeSpan

Gibt den Wert des der `CTimeSpan` Objekt.

```
__ time64_t GetTimeSpan() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den aktuellen Wert von der `CTimeSpan` Objekt.

##  <a name="gettotalhours"></a>  CTimeSpan::GetTotalHours

Gibt einen Wert, der die Gesamtzahl der vollständige Stunden in diesem darstellt `CTimeSpan`.

```
LONGLONG GetTotalHours() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Gesamtzahl der Stunden der vollständigen in diesem `CTimeSpan`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#166](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_6.cpp)]

##  <a name="gettotalminutes"></a>  CTimeSpan::GetTotalMinutes

Gibt einen Wert, der die Gesamtzahl der Minuten. in diesem darstellt `CTimeSpan`.

```
LONGLONG GetTotalMinutes() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Gesamtzahl der Minuten. in diesem `CTimeSpan`.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [GetTotalHours](#gettotalhours).

##  <a name="gettotalseconds"></a>  CTimeSpan::GetTotalSeconds

Gibt einen Wert, der die Gesamtzahl der vollständige Sekunden in diesem darstellt `CTimeSpan`.

```
LONGLONG GetTotalSeconds() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Gesamtanzahl der vollständige Sekunden in diesem `CTimeSpan`.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [GetTotalHours](#gettotalhours).

##  <a name="operator_add_-"></a>  CTimeSpan::operator +, -

Fügt und subtrahiert `CTimeSpan` Objekte.

```
CTimeSpan operator+(CTimeSpan span) const throw();
CTimeSpan operator-(CTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameter

*umfassen*  
Der Wert, der zum Hinzufügen der `CTimeSpan` Objekt.

### <a name="return-value"></a>Rückgabewert

Ein `CTimeSpan` Objekt, das das Ergebnis des Vorgangs darstellt.

### <a name="remarks"></a>Hinweise

Diese beiden Operatoren können Sie von Addition und Subtraktion `CTimeSpan` Objekte in und aus jeder anderen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#167](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_7.cpp)]

##  <a name="operator_add_eq_-_eq"></a>  CTimeSpan::operator +=, =

Fügt und subtrahiert einen `CTimeSpan` Objekt auf und aus diesem `CTimeSpan`.

```
CTimeSpan& operator+=(CTimeSpan span) throw();
CTimeSpan& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>Parameter

*umfassen*  
Der Wert, der zum Hinzufügen der `CTimeSpan` Objekt.

### <a name="return-value"></a>Rückgabewert

Die aktualisierte `CTimeSpan` Objekt.

### <a name="remarks"></a>Hinweise

Diese Operatoren können Sie von Addition und Subtraktion ein `CTimeSpan` Objekt auf und aus diesem `CTimeSpan`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#168](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_8.cpp)]

##  <a name="serialize64"></a>  CTimeSpan::Serialize64

> [!NOTE]
>  Diese Methode ist nur in MFC-Projekten verfügbar.

Serialisiert die Membervariable in oder aus einem Archiv zugeordneten Daten.

```
CArchive& Serialize64(CArchive& ar);
```

### <a name="parameters"></a>Parameter

*ar*  
Die `CArchive` -Objekt, das Sie aktualisieren möchten.

### <a name="return-value"></a>Rückgabewert

Die aktualisierte `CArchive` Objekt.

## <a name="see-also"></a>Siehe auch

[asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
[_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
[gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
[localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
[strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
[time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
[Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)

