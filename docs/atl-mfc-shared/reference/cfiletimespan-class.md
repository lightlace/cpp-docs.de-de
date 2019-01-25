---
title: CFileTimeSpan-Klasse
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
ms.openlocfilehash: 8d384ced5de588a348eb72b9852697694b370ee4
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2019
ms.locfileid: "54894158"
---
# <a name="cfiletimespan-class"></a>CFileTimeSpan-Klasse

Diese Klasse stellt Methoden zum Verwalten von relative Datum- und Zeitwerte, die einer Datei zugeordnet.

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
|[CFileTimeSpan::GetTimeSpan](#gettimespan)|Rufen Sie diese Methode zum Abrufen der Zeitspanne, die von der `CFileTimeSpan` Objekt.|
|[CFileTimeSpan::SetTimeSpan](#settimespan)|Rufen Sie diese Methode zum Festlegen der Zeitspanne der `CFileTimeSpan` Objekt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CFileTimeSpan::operator -](#operator_-)|Führt Subtraktionen aus auf eine `CFileTimeSpan` Objekt.|
|[CFileTimeSpan::operator !=](#operator_neq)|Überprüft zwei `CFileTimeSpan`-Objekte auf Ungleichheit.|
|[CFileTimeSpan::operator +](#operator_add)|Außerdem führt ein `CFileTimeSpan` Objekt.|
|[CFileTimeSpan::operator +=](#operator_add_eq)|Führt außerdem eine `CFileTimeSpan` Objekt aus, und das Ergebnis mit dem aktuellen Objekt zuzuweisen.|
|[CFileTimeSpan::operator &lt;](#operator_lt)|Vergleicht zwei `CFileTimeSpan` -Objekten, das kleinere zu bestimmen.|
|[CFileTimeSpan::operator &lt;=](#operator_lt_eq)|Vergleicht zwei `CFileTimeSpan` Objekte auf Gleichheit oder das kleinere zu bestimmen.|
|[CFileTimeSpan::operator =](#operator_eq)|Der Zuweisungsoperator.|
|[CFileTimeSpan::operator -=](#operator_-_eq)|Führt Subtraktionen aus auf eine `CFileTimeSpan` Objekt aus, und das Ergebnis mit dem aktuellen Objekt zuzuweisen.|
|[CFileTimeSpan::operator ==](#operator_eq_eq)|Überprüft zwei `CFileTimeSpan`-Objekte auf Gleichheit.|
|[CFileTimeSpan::operator &gt;](#operator_gt)|Vergleicht zwei `CFileTimeSpan` -Objekten, das größere zu bestimmen.|
|[CFileTimeSpan::operator &gt;=](#operator_gt_eq)|Vergleicht zwei `CFileTimeSpan` Objekte auf Gleichheit oder die größere zu bestimmen.|

## <a name="remarks"></a>Hinweise

Diese Klasse stellt Methoden für die Verwaltung von relativen Zeiträume Zeitspanne häufig auftreten, wenn das Ausführen von Vorgängen, die bei der Anwendung eine Datei erstellt, des letzten Zugriffs auf oder zuletzt geändert wurde. Die Methoden dieser Klasse werden häufig in Verbindung mit verwendet [CFileTime-Klasse](../../atl-mfc-shared/reference/cfiletime-class.md) Objekte.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [CFileTime::Millisecond](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond).

## <a name="requirements"></a>Anforderungen

**Header:** atltime.h

##  <a name="cfiletimespan"></a>  CFileTimeSpan::CFileTimeSpan

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
Ein Zeitraum in Millisekunden.

### <a name="remarks"></a>Hinweise

Die `CFileTimeSpan` Objekt kann erstellt werden, mithilfe eines vorhandenen `CFileTimeSpan` Objekt, oder als 64-Bit-Wert. Der Standardkonstruktor legt die Zeitspanne auf 0 fest.

##  <a name="gettimespan"></a>  CFileTimeSpan::GetTimeSpan

Rufen Sie diese Methode zum Abrufen der Zeitspanne, die von der `CFileTimeSpan` Objekt.

```
LONGLONG GetTimeSpan() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Zeitspanne in Millisekunden an.

##  <a name="operator_-"></a>  CFileTimeSpan::operator-

Führt Subtraktionen aus auf eine `CFileTimeSpan` Objekt.

```
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Ein `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt eine `CFileTimeSpan` Objekt, das das Ergebnis des Unterschieds zwischen zwei Zeitspannen darstellt.

##  <a name="operator_neq"></a>  CFileTimeSpan::operator! =

Überprüft zwei `CFileTimeSpan`-Objekte auf Ungleichheit.

```
bool operator!=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Das zu vergleichende `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn das Element mit dem verglichen wird, nicht gleich ist die `CFileTimeSpan` Objekt; andernfalls "false".

##  <a name="operator_add"></a>  CFileTimeSpan::operator +

Außerdem führt ein `CFileTimeSpan` Objekt.

```
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Ein `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt eine `CFileTimeSpan` Objekt mit der Summe der beiden Zeit umfasst.

##  <a name="operator_add_eq"></a>  CFileTimeSpan::operator +=

Führt außerdem eine `CFileTimeSpan` -Objekt und weist das Ergebnis mit dem aktuellen Objekt.

```
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Ein `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt die aktualisierte `CFileTimeSpan` Objekt mit der Summe der beiden Zeit umfasst.

##  <a name="operator_lt"></a>  CFileTimeSpan::operator &lt;

Vergleicht zwei `CFileTimeSpan` -Objekten, das kleinere zu bestimmen.

```
bool operator<(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Das zu vergleichende `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn das erste Objekt kleiner ist (d. h. einen kürzeren Zeitraum stellt) als das zweite ist, andernfalls "false".

##  <a name="operator_lt_eq"></a>  CFileTimeSpan::operator &lt;=

Vergleicht zwei `CFileTimeSpan` Objekte auf Gleichheit oder das kleinere zu bestimmen.

```
bool operator<=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Das zu vergleichende `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt "true", wenn das erste Objekt kleiner als (d. h. einen kürzeren Zeitraum stellt) oder gleich dem zweiten ist, andernfalls "false".

##  <a name="operator_eq"></a>  CFileTimeSpan::operator =

Der Zuweisungsoperator.

```
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Ein `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt die aktualisierte `CFileTimeSpan` Objekt.

##  <a name="operator_-_eq"></a>  CFileTimeSpan::operator =

Führt Subtraktionen aus auf eine `CFileTimeSpan` -Objekt und weist das Ergebnis mit dem aktuellen Objekt.

```
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Ein `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt die aktualisierte `CFileTimeSpan` Objekt.

##  <a name="operator_eq_eq"></a>  CFileTimeSpan::operator ==

Überprüft zwei `CFileTimeSpan`-Objekte auf Gleichheit.

```
bool operator==(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Das zu vergleichende `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn die Objekte gleich, andernfalls "false sind".

##  <a name="operator_gt"></a>  CFileTimeSpan::operator &gt;

Vergleicht zwei `CFileTimeSpan` -Objekten, das größere zu bestimmen.

```
bool operator>(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Das zu vergleichende `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn das erste Objekt größer ist (d. h. stellt einen längeren Zeitraum) als das zweite ist, andernfalls "false".

##  <a name="operator_gt_eq"></a>  CFileTimeSpan::operator &gt;=

Vergleicht zwei `CFileTimeSpan` Objekte auf Gleichheit oder die größere zu bestimmen.

```
bool operator>=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameter

*span*<br/>
Das zu vergleichende `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn das erste Objekt größer ist (d. h. stellt einen längeren Zeitraum) oder gleich dem zweiten ist, andernfalls "false".

##  <a name="settimespan"></a>  CFileTimeSpan::SetTimeSpan

Rufen Sie diese Methode zum Festlegen der Zeitspanne der `CFileTimeSpan` Objekt.

```
void SetTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>Parameter

*nSpan*<br/>
Der neue Wert für die Zeitspanne in Millisekunden.

## <a name="see-also"></a>Siehe auch

[FILETIME-ELEMENT](/windows/desktop/api/minwinbase/ns-minwinbase-filetime)<br/>
[CFileTime-Klasse](../../atl-mfc-shared/reference/cfiletime-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)
