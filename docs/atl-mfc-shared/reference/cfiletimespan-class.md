---
title: Cfiletimespan-Klasse
ms.date: 10/18/2018
f1_keywords:
- CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::GetTimeSpan
- ATLTIME/ATL::CFileTimeSpan::SetTimeSpan
helpviewer_keywords:
- shared classes, CFileTimeSpan
- CFileTimeSpan class
ms.assetid: 5856fb39-9c82-4027-8ccf-8760890491ec
ms.openlocfilehash: f9bb42ba4c142f671a83dcfa7e99cff940fff047
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491289"
---
# <a name="cfiletimespan-class"></a>Cfiletimespan-Klasse

Diese Klasse stellt Methoden zum Verwalten relativer Datums-und Uhrzeitwerte bereit, die einer Datei zugeordnet sind.

## <a name="syntax"></a>Syntax

```
class CFileTimeSpan
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CFileTimeSpan::CFileTimeSpan](#cfiletimespan)|Der Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CFileTimeSpan::GetTimeSpan](#gettimespan)|Rufen Sie diese Methode auf, um die Zeitspanne `CFileTimeSpan` aus dem-Objekt abzurufen.|
|[CFileTimeSpan::SetTimeSpan](#settimespan)|Mit dieser Methode wird die Zeitspanne des `CFileTimeSpan` -Objekts festgelegt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[Cfiletimespan:: Operator-](#operator_-)|Führt Subtraktion für ein `CFileTimeSpan` -Objekt aus.|
|[Cfiletimespan:: Operator! =](#operator_neq)|Überprüft zwei `CFileTimeSpan`-Objekte auf Ungleichheit.|
|[Cfiletimespan:: Operator +](#operator_add)|Führt Addition für ein `CFileTimeSpan` -Objekt aus.|
|[CFileTimeSpan::operator +=](#operator_add_eq)|Führt Addition für ein `CFileTimeSpan` -Objekt aus und weist das Ergebnis dem aktuellen-Objekt zu.|
|[Cfiletimespan::-Operator&lt;](#operator_lt)|Vergleicht zwei `CFileTimeSpan` -Objekte, um die kleinere zu bestimmen.|
|[Cfiletimespan::-Operator&lt;=](#operator_lt_eq)|Vergleicht zwei `CFileTimeSpan` -Objekte, um die Gleichheit zu bestimmen oder die kleinere.|
|[CFileTimeSpan::operator =](#operator_eq)|Der Zuweisungs Operator.|
|[Cfiletimespan:: Operator-=](#operator_-_eq)|Führt Subtraktion für ein `CFileTimeSpan` -Objekt aus und weist das Ergebnis dem aktuellen-Objekt zu.|
|[CFileTimeSpan::operator ==](#operator_eq_eq)|Überprüft zwei `CFileTimeSpan`-Objekte auf Gleichheit.|
|[Cfiletimespan::-Operator&gt;](#operator_gt)|Vergleicht zwei `CFileTimeSpan` -Objekte, um die größere zu ermitteln.|
|[Cfiletimespan::-Operator&gt;=](#operator_gt_eq)|Vergleicht zwei `CFileTimeSpan` -Objekte, um die Gleichheit oder die größere zu bestimmen.|

## <a name="remarks"></a>Hinweise

Diese Klasse stellt Methoden zur Verwaltung relativer Zeiträume bereit, die häufig beim Ausführen von Vorgängen zum Zeitpunkt der Erstellung einer Datei, des letzten Zugriffs oder der letzten Änderung auftreten. Die Methoden dieser Klasse werden häufig in Verbindung mit [cfiletime-Klassen](../../atl-mfc-shared/reference/cfiletime-class.md) Objekten verwendet.

## <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [cfiletime:: millisecond](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond).

## <a name="requirements"></a>Anforderungen

**Header:** atltime. h

##  <a name="cfiletimespan"></a>Cfiletimespan:: cfiletimespan

Der Konstruktor.

```
CFileTimeSpan() throw();
CFileTimeSpan(const CFileTimeSpan& span) throw();
CFileTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Ein vorhandenes `CFileTimeSpan`-Objekt.

*nSpan*<br/>
Eine Zeitspanne in Millisekunden.

### <a name="remarks"></a>Hinweise

Das `CFileTimeSpan` -Objekt kann mit einem vorhandenen `CFileTimeSpan` -Objekt erstellt oder als 64-Bit-Wert ausgedrückt werden. Der Standardkonstruktor legt die Zeitspanne auf 0 fest.

##  <a name="gettimespan"></a>Cfiletimespan:: GetTimeSpan

Rufen Sie diese Methode auf, um die Zeitspanne `CFileTimeSpan` aus dem-Objekt abzurufen.

```
LONGLONG GetTimeSpan() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Zeitspanne in Millisekunden zurück.

##  <a name="operator_-"></a>Cfiletimespan:: Operator-

Führt Subtraktion für ein `CFileTimeSpan` -Objekt aus.

```
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Ein `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt ein `CFileTimeSpan` -Objekt zurück, das das Ergebnis der Differenz zwischen zwei Zeitspannen darstellt.

##  <a name="operator_neq"></a>Cfiletimespan:: Operator! =

Überprüft zwei `CFileTimeSpan`-Objekte auf Ungleichheit.

```
bool operator!=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Das zu vergleichende `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das verglichene Element nicht gleich `CFileTimeSpan` dem-Objekt ist, andernfalls false.

##  <a name="operator_add"></a>Cfiletimespan:: Operator +

Führt Addition für ein `CFileTimeSpan` -Objekt aus.

```
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Ein `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt ein `CFileTimeSpan` -Objekt zurück, das die Summe der beiden Zeitspannen enthält.

##  <a name="operator_add_eq"></a>Cfiletimespan:: Operator + =

Führt Addition für ein `CFileTimeSpan` -Objekt aus und weist das Ergebnis dem aktuellen-Objekt zu.

```
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Ein `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt das aktualisierte `CFileTimeSpan` Objekt zurück, das die Summe der beiden Zeitspannen enthält.

##  <a name="operator_lt"></a>Cfiletimespan::-Operator&lt;

Vergleicht zwei `CFileTimeSpan` -Objekte, um die kleinere zu bestimmen.

```
bool operator<(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Das zu vergleichende `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das erste Objekt kleiner ist (d. h. einen kürzeren Zeitraum darstellt) als das zweite, andernfalls false.

##  <a name="operator_lt_eq"></a>Cfiletimespan::-Operator&lt;=

Vergleicht zwei `CFileTimeSpan` -Objekte, um die Gleichheit zu bestimmen oder die kleinere.

```
bool operator<=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Das zu vergleichende `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das erste Objekt kleiner als (d. h. ein kürzerer Zeitraum darstellt) oder gleich dem zweiten ist, andernfalls false.

##  <a name="operator_eq"></a>Cfiletimespan:: Operator =

Der Zuweisungs Operator.

```
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Ein `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt das aktualisierte `CFileTimeSpan` Objekt zurück.

##  <a name="operator_-_eq"></a>Cfiletimespan:: Operator-=

Führt Subtraktion für ein `CFileTimeSpan` -Objekt aus und weist das Ergebnis dem aktuellen-Objekt zu.

```
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Ein `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt das aktualisierte `CFileTimeSpan` Objekt zurück.

##  <a name="operator_eq_eq"></a>Cfiletimespan:: Operator = =

Überprüft zwei `CFileTimeSpan`-Objekte auf Gleichheit.

```
bool operator==(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Das zu vergleichende `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Objekte gleich sind, andernfalls false.

##  <a name="operator_gt"></a>Cfiletimespan::-Operator&gt;

Vergleicht zwei `CFileTimeSpan` -Objekte, um die größere zu ermitteln.

```
bool operator>(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Das zu vergleichende `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das erste Objekt größer als das zweite ist (d. h. einen längeren Zeitraum darstellt), andernfalls false.

##  <a name="operator_gt_eq"></a>Cfiletimespan::-Operator&gt;=

Vergleicht zwei `CFileTimeSpan` -Objekte, um die Gleichheit oder die größere zu bestimmen.

```
bool operator>=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Das zu vergleichende `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das erste Objekt größer als (d. h. ein längerer Zeitraum darstellt) oder gleich dem zweiten ist, andernfalls false.

##  <a name="settimespan"></a>Cfiletimespan:: SetTimeSpan

Mit dieser Methode wird die Zeitspanne des `CFileTimeSpan` -Objekts festgelegt.

```
void SetTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>Parameter

*nSpan*<br/>
Der neue Wert für die Zeitspanne in Millisekunden.

## <a name="see-also"></a>Siehe auch

[FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime)<br/>
[CFileTime-Klasse](../../atl-mfc-shared/reference/cfiletime-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Gemeinsam genutzte ATL/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)
