---
title: Cfiletime-Klasse
ms.date: 10/18/2018
f1_keywords:
- CFileTime
- ATLTIME/ATL::CFileTime
- ATLTIME/ATL::CFileTime::CFileTime
- ATLTIME/ATL::CFileTime::GetCurrentTime
- ATLTIME/ATL::CFileTime::GetTime
- ATLTIME/ATL::CFileTime::LocalToUTC
- ATLTIME/ATL::CFileTime::SetTime
- ATLTIME/ATL::CFileTime::UTCToLocal
- ATLTIME/ATL::CFileTime::Day
- ATLTIME/ATL::CFileTime::Hour
- ATLTIME/ATL::CFileTime::Millisecond
- ATLTIME/ATL::CFileTime::Minute
- ATLTIME/ATL::CFileTime::Second
- ATLTIME/ATL::CFileTime::Week
helpviewer_keywords:
- CFileTime class
- shared classes, CFileTime
ms.assetid: 1a358a65-1383-4124-b0d4-59b026e6860f
ms.openlocfilehash: b24d1e4d3e670a820c41735617b7db6780ff137c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491487"
---
# <a name="cfiletime-class"></a>Cfiletime-Klasse

Diese Klasse stellt Methoden zum Verwalten der Datums-und Uhrzeitwerte bereit, die einer Datei zugeordnet sind.

## <a name="syntax"></a>Syntax

```
class CFileTime :  public FILETIME
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CFileTime::CFileTime](#cfiletime)|Der Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CFileTime::GetCurrentTime](#getcurrenttime)|Rufen Sie diese statische Funktion auf, `CFileTime` um ein-Objekt abzurufen, das das aktuelle Systemdatum und-Uhrzeit darstellt.|
|[CFileTime::GetTime](#gettime)|Rufen Sie diese Methode auf, um die Uhrzeit `CFileTime` aus dem-Objekt abzurufen.|
|[CFileTime::LocalToUTC](#localtoutc)|Mit dieser Methode wird eine lokale Datei Zeit auf Grundlage der koordinierten Weltzeit (UTC) in eine Datei Zeit konvertiert.|
|[CFileTime::SetTime](#settime)|Mit dieser Methode können Sie das Datum und die Uhrzeit festlegen, `CFileTime` die vom-Objekt gespeichert werden.|
|[CFileTime::UTCToLocal](#utctolocal)|Mit dieser Methode können Sie die Zeit auf der Grundlage der koordinierten Weltzeit (UTC) in die lokale Dateizeit konvertieren.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[Cfiletime:: Operator-](#operator_-)|Dieser Operator wird verwendet, um Subtraktion für ein `CFileTime` - `CFileTimeSpan` oder-Objekt auszuführen.|
|[Cfiletime:: Operator! =](#operator_neq)|Dieser Operator vergleicht zwei `CFileTime` -Objekte auf Ungleichheit.|
|[Cfiletime:: Operator +](#operator_add)|Dieser Operator wird verwendet, um Addition für ein `CFileTimeSpan`-Objekt auszuführen.|
|[Cfiletime:: Operator + =](#operator_add_eq)|Dieser Operator wird verwendet, um Addition für ein `CFileTimeSpan`-Objekt auszuführen und das Ergebnis dem aktuellen Objekt zuzuweisen.|
|[Cfiletime::-Operator&lt;](#operator_lt)|Dieser Operator vergleicht zwei `CFileTime`-Objekte, um das kleinere zu bestimmen.|
|[Cfiletime::-Operator&lt;=](#operator_lt_eq)|Dieser Operator vergleicht zwei `CFileTime`-Objekte, um zu bestimmen, ob sie gleich sind oder welches kleiner ist.|
|[Cfiletime:: Operator =](#operator_eq)|Der Zuweisungs Operator.|
|[Cfiletime:: Operator-=](#operator_-_eq)|Dieser Operator wird verwendet, um Subtraktion für ein `CFileTimeSpan` -Objekt auszuführen und das Ergebnis dem aktuellen-Objekt zuzuweisen.|
|[Cfiletime:: Operator = =](#operator_eq_eq)|Dieser Operator überprüft zwei `CFileTime`-Objekte auf Gleichheit.|
|[Cfiletime::-Operator&gt;](#operator_gt)|Dieser Operator vergleicht zwei `CFileTime`-Objekte, um das größere zu bestimmen.|
|[Cfiletime::-Operator&gt;=](#operator_gt_eq)|Dieser Operator vergleicht zwei `CFileTime`-Objekte, um zu bestimmen, ob sie gleich sind oder welches größer ist.|

### <a name="public-constants"></a>Öffentliche Konstanten

|Name|Beschreibung|
|----------|-----------------|
|[CFileTime::Day](#day)|Ein statischer Datenmember, der die Anzahl der 100-Nanosekunden-Intervalle speichert, die einen Tag ausmachen.|
|[CFileTime::Hour](#hour)|Ein statischer Datenmember, der die Anzahl der 100-Nanosekunden-Intervalle speichert, die eine Stunde ausmachen.|
|[CFileTime::Millisecond](#millisecond)|Ein statischer Datenmember, der die Anzahl der 100-Nanosekunden-Intervalle speichert, die eine Millisekunde ausmachen.|
|[CFileTime::Minute](#minute)|Ein statischer Datenmember, der die Anzahl der 100-Nanosekunden-Intervalle speichert, die eine Minute ausmachen.|
|[CFileTime::Second](#second)|Ein statischer Datenmember, der die Anzahl der 100-Nanosekunden-Intervalle speichert, die eine Sekunde ausmachen.|
|[Cfiletime:: Week](#week)|Ein statischer Datenmember, der die Anzahl der 100-Nanosekunden-Intervalle speichert, die eine Woche bilden.|

## <a name="remarks"></a>Hinweise

Diese Klasse stellt Methoden zum Verwalten der Datums-und Uhrzeitwerte bereit, die der Erstellung, dem Zugriff und der Änderung von Dateien zugeordnet sind. Die Methoden und Daten dieser Klasse werden häufig in Verbindung mit `CFileTimeSpan` -Objekten verwendet, die relative Uhrzeitwerte behandeln.

Der Datums-und Uhrzeitwert wird als 64-Bit-Wert gespeichert, der die Anzahl der 100-Nanosecond-Intervalle seit dem 1. Januar 1601 darstellt. Dies ist das Format der koordinierten Weltzeit (UTC).

Die folgenden statischen Konstanten Element Variablen werden bereitgestellt, um Berechnungen zu vereinfachen:

|Member-Variable|Anzahl der 100-Nanosekunden-Intervalle|
|---------------------|-----------------------------------------|
|Millisecond|10,000|
|Zweimal|Millisekunde \* 1.000|
|Minute|Sekunde \* 60|
|Hour|Minute \* 60|
|Day|Stunde \* 24|
|Woche|Tag \* 7|

**Hinweis** Nicht alle Dateisysteme können die Erstellung und den Zeitpunkt des letzten Zugriffs aufzeichnen, und nicht alle Dateisysteme zeichnen Sie auf die gleiche Weise auf. Beispielsweise hat die Erstellungszeit auf dem Windows NT FAT-Dateisystem eine Auflösung von 10 Millisekunden, die Schreibzeit eine Auflösung von 2 Sekunden und die Zugriffszeit eine Auflösung von 1 Tag (das Zugriffs Datum). Bei NTFS hat die Zugriffszeit eine Auflösung von 1 Stunde. Außerdem werden in der lokalen Zeit in FAT Zeiten auf dem Datenträger aufgezeichnet, aber NTFS zeichnet Zeiten auf dem Datenträger in UTC auf. Weitere Informationen finden Sie unter [Datei Zeiten](/windows/win32/SysInfo/file-times).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`FILETIME`

`CFileTime`

## <a name="requirements"></a>Anforderungen

**Header:** atltime. h

##  <a name="cfiletime"></a>Cfiletime:: cfiletime

Der Konstruktor.

```
CFileTime() throw();
CFileTime(const FILETIME& ft) throw();
CFileTime(ULONGLONG nTime) throw();
```

### <a name="parameters"></a>Parameter

*ft*<br/>
Eine [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) -Struktur.

*nTime*<br/>
Das Datum und die Uhrzeit, die als 64-Bit-Wert ausgedrückt werden.

### <a name="remarks"></a>Hinweise

Das `CFileTime` -Objekt kann mithilfe eines vorhandenen Datums und einer Uhrzeit aus einer `FILETIME` -Struktur erstellt oder als 64-Bit-Wert (im UTC-Zeitformat (local) oder koordinierte Weltzeit) ausgedrückt werden. Der Standardkonstruktor legt die Zeit auf 0 (null) fest.

##  <a name="day"></a>Cfiletime::D ay

Ein statischer Datenmember, der die Anzahl der 100-Nanosekunden-Intervalle speichert, die einen Tag ausmachen.

```
static const ULONGLONG Day = Hour* 24;
```

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [cfiletime:: millisecond](#millisecond).

##  <a name="getcurrenttime"></a>Cfiletime:: GetCurrentTime

Rufen Sie diese statische Funktion auf, `CFileTime` um ein-Objekt abzurufen, das das aktuelle Systemdatum und-Uhrzeit darstellt.

```
static CFileTime GetCurrentTime() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt das aktuelle Systemdatum und die aktuelle Systemzeit im UTC-Format (koordinierte Weltzeit) zurück.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#41](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_1.cpp)]

##  <a name="gettime"></a>Cfiletime:: getTime

Rufen Sie diese Methode auf, um die Uhrzeit `CFileTime` aus dem-Objekt abzurufen.

```
ULONGLONG GetTime() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt das Datum und die Uhrzeit als 64-Bit-Zahl zurück, die entweder im lokalen oder im UTC-Format (koordinierte Weltzeit) vorliegen kann.

##  <a name="hour"></a>Cfiletime:: Hour

Ein statischer Datenmember, der die Anzahl der 100-Nanosekunden-Intervalle speichert, die eine Stunde ausmachen.

```
static const ULONGLONG Hour = Minute* 60;
```

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [cfiletime:: millisecond](#millisecond).

##  <a name="localtoutc"></a>Cfiletime:: localtoutc

Mit dieser Methode wird eine lokale Datei Zeit auf Grundlage der koordinierten Weltzeit (UTC) in eine Datei Zeit konvertiert.

```
CFileTime LocalToUTC() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt ein `CFileTime` -Objekt zurück, das die Uhrzeit im UTC-Format enthält.

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [cfiletime:: utctolocal](#utctolocal).

##  <a name="millisecond"></a>Cfiletime:: Millisekunde

Ein statischer Datenmember, der die Anzahl der 100-Nanosekunden-Intervalle speichert, die eine Millisekunde ausmachen.

```
static const ULONGLONG Millisecond = 10000;
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#44](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_2.cpp)]

##  <a name="minute"></a>Cfiletime:: Minute

Ein statischer Datenmember, der die Anzahl der 100-Nanosekunden-Intervalle speichert, die eine Minute ausmachen.

```
static const ULONGLONG Minute = Second* 60;
```

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [cfiletime:: millisecond](#millisecond).

##  <a name="operator_-"></a>Cfiletime:: Operator-

Dieser Operator wird verwendet, um Subtraktion für ein `CFileTime` - `CFileTimeSpan` oder-Objekt auszuführen.

```
CFileTime operator-(CFileTimeSpan span) const throw();
CFileTimeSpan operator-(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Ein `CFileTimeSpan`-Objekt.

*ft*<br/>
Ein `CFileTime`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt ein `CFileTime` -Objekt oder `CFileTimeSpan` ein-Objekt zurück, das das Ergebnis des Zeitunterschieds zwischen den beiden-Objekten darstellt.

##  <a name="operator_neq"></a>Cfiletime:: Operator! =

Dieser Operator vergleicht zwei `CFileTime` -Objekte auf Ungleichheit.

```
bool operator!=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parameter

*ft*<br/>
Das zu vergleichende `CFileTime`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das verglichene Element nicht gleich `CFileTime` dem-Objekt ist, andernfalls false.

##  <a name="operator_add"></a>Cfiletime:: Operator +

Dieser Operator wird verwendet, um Addition für ein `CFileTimeSpan`-Objekt auszuführen.

```
CFileTime operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Ein `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt ein `CFileTime` -Objekt zurück, das das Ergebnis der ursprünglichen Uhrzeit zuzüglich einer relativen Zeit darstellt.

##  <a name="operator_add_eq"></a>Cfiletime:: Operator + =

Dieser Operator wird verwendet, um Addition für ein `CFileTimeSpan`-Objekt auszuführen und das Ergebnis dem aktuellen Objekt zuzuweisen.

```
CFileTime& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Ein `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt das aktualisierte `CFileTime` Objekt zurück, das das Ergebnis der ursprünglichen Uhrzeit zuzüglich einer relativen Zeit darstellt.

##  <a name="operator_lt"></a>Cfiletime::-Operator&lt;

Dieser Operator vergleicht zwei `CFileTime`-Objekte, um das kleinere zu bestimmen.

```
bool operator<(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parameter

*ft*<br/>
Das zu vergleichende `CFileTime`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn das erste Objekt kleiner als das zweite Objekt ist, andernfalls "false".

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#43](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_3.cpp)]

##  <a name="operator_lt_eq"></a>Cfiletime::-Operator&lt;=

Dieser Operator vergleicht zwei `CFileTime`-Objekte, um zu bestimmen, ob sie gleich sind oder welches kleiner ist.

```
bool operator<=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parameter

*ft*<br/>
Das zu vergleichende `CFileTime`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das erste Objekt kleiner als (früher in der Zeit) oder gleich dem zweiten ist, andernfalls false.

##  <a name="operator_eq"></a>Cfiletime:: Operator =

Der Zuweisungs Operator.

```
CFileTime& operator=(const FILETIME& ft) throw();
```

### <a name="parameters"></a>Parameter

*ft*<br/>
Ein `CFileTime` -Objekt, das die neue Uhrzeit und das neue Datum enthält.

### <a name="return-value"></a>Rückgabewert

Gibt das aktualisierte `CFileTime` Objekt zurück.

##  <a name="operator_-_eq"></a>Cfiletime:: Operator-=

Dieser Operator wird verwendet, um Subtraktion für ein `CFileTimeSpan` -Objekt auszuführen und das Ergebnis dem aktuellen-Objekt zuzuweisen.

```
CFileTime& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Ein `CFileTimeSpan` -Objekt, das die zu subtrahierende relative Zeit enthält.

### <a name="return-value"></a>Rückgabewert

Gibt das aktualisierte `CFileTime` Objekt zurück.

##  <a name="operator_eq_eq"></a>Cfiletime:: Operator = =

Dieser Operator überprüft zwei `CFileTime`-Objekte auf Gleichheit.

```
bool operator==(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parameter

*ft*<br/>
Das `CFileTime` zu vergleichende Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Objekte gleich sind, andernfalls false.

##  <a name="operator_gt"></a>Cfiletime::-Operator&gt;

Dieser Operator vergleicht zwei `CFileTime`-Objekte, um das größere zu bestimmen.

```
bool operator>(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parameter

*ft*<br/>
Das zu vergleichende `CFileTime`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das erste Objekt größer als (später) als das zweite Objekt ist, andernfalls false.

##  <a name="operator_gt_eq"></a>Cfiletime::-Operator&gt;=

Dieser Operator vergleicht zwei `CFileTime`-Objekte, um zu bestimmen, ob sie gleich sind oder welches größer ist.

```
bool operator>=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parameter

*ft*<br/>
Das zu vergleichende `CFileTime`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das erste Objekt größer als (später) oder gleich dem zweiten ist, andernfalls false.

##  <a name="second"></a>Cfiletime:: Second

Ein statischer Datenmember, der die Anzahl der 100-Nanosekunden-Intervalle speichert, die einen Tag ausmachen.

```
static const ULONGLONG Second = Millisecond* 1000;
```

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [cfiletime:: millisecond](#millisecond).

##  <a name="settime"></a>Cfiletime:: setTime

Mit dieser Methode können Sie das Datum und die Uhrzeit festlegen, `CFileTime` die vom-Objekt gespeichert werden.

```
void SetTime(ULONGLONG nTime) throw();
```

### <a name="parameters"></a>Parameter

*nTime*<br/>
Der 64-Bit-Wert, der das Datum und die Uhrzeit im UTC-Format (local oder koordinierte Weltzeit) darstellt.

##  <a name="utctolocal"></a>Cfiletime:: utctolocal

Mit dieser Methode können Sie die Zeit auf der Grundlage der koordinierten Weltzeit (UTC) in die lokale Dateizeit konvertieren.

```
CFileTime UTCToLocal() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt ein `CFileTime` -Objekt zurück, das die Uhrzeit im lokalen Datei Zeitformat enthält.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#42](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_4.cpp)]

##  <a name="week"></a>Cfiletime:: Week

Ein statischer Datenmember, der die Anzahl der 100-Nanosekunden-Intervalle speichert, die eine Woche bilden.

```
static const ULONGLONG Week = Day* 7;
```

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [cfiletime:: millisecond](#millisecond).

## <a name="see-also"></a>Siehe auch

[FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime)<br/>
[CFileTimeSpan-Klasse](../../atl-mfc-shared/reference/cfiletimespan-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Gemeinsam genutzte ATL/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)
