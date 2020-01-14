---
title: CFileTimeSpan-Klasse
description: Die cfiletimespan-Klasse Active Template Library (ATL) und Microsoft Foundation Classes (MFC) verwaltet Zeitintervalle in FILETIME-Einheiten.
ms.date: 01/10/2020
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
ms.openlocfilehash: 89d95759b11ff7e52c2a8fa75cf94f7b7b81fa36
ms.sourcegitcommit: c3283062ce4e382aec7f11626d358a37caf8cdbb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2020
ms.locfileid: "75914382"
---
# <a name="cfiletimespan-class"></a>CFileTimeSpan-Klasse

Diese Klasse stellt Methoden zum Verwalten relativer Datums-und Uhrzeitwerte bereit, die einer Datei zugeordnet sind.

## <a name="syntax"></a>Syntax

```cpp
class CFileTimeSpan
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|-Name|Beschreibung|
|----------|-----------------|
|[CFileTimeSpan::CFileTimeSpan](#cfiletimespan)|Der Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|-Name|Beschreibung|
|----------|-----------------|
|[CFileTimeSpan::GetTimeSpan](#gettimespan)|Rufen Sie diese Methode auf, um die Zeitspanne aus dem `CFileTimeSpan`-Objekt abzurufen.|
|[CFileTimeSpan::SetTimeSpan](#settimespan)|Diese Methode wird aufgerufen, um die Zeitspanne des `CFileTimeSpan` Objekts festzulegen.|

### <a name="public-operators"></a>Öffentliche Operatoren

|-Name|Beschreibung|
|----------|-----------------|
|[Cfiletimespan:: Operator-](#operator_-)|Führt Subtraktion für ein `CFileTimeSpan` Objekt aus.|
|[Cfiletimespan:: Operator! =](#operator_neq)|Überprüft zwei `CFileTimeSpan`-Objekte auf Ungleichheit.|
|[Cfiletimespan:: Operator +](#operator_add)|Führt Addition für ein `CFileTimeSpan` Objekt aus.|
|[CFileTimeSpan::operator +=](#operator_add_eq)|Führt Addition für ein `CFileTimeSpan` Objekt aus und weist das Ergebnis dem aktuellen-Objekt zu.|
|[Cfiletimespan:: Operator &lt;](#operator_lt)|Vergleicht zwei `CFileTimeSpan`-Objekte, um die kleinere zu bestimmen.|
|[Cfiletimespan:: Operator &lt;=](#operator_lt_eq)|Vergleicht zwei `CFileTimeSpan`-Objekte, um die Gleichheit zu bestimmen.|
|[CFileTimeSpan::operator =](#operator_eq)|Der Zuweisungs Operator.|
|[Cfiletimespan:: Operator-=](#operator_-_eq)|Führt Subtraktion für ein `CFileTimeSpan` Objekt aus und weist das Ergebnis dem aktuellen-Objekt zu.|
|[CFileTimeSpan::operator ==](#operator_eq_eq)|Überprüft zwei `CFileTimeSpan`-Objekte auf Gleichheit.|
|[Cfiletimespan:: Operator &gt;](#operator_gt)|Vergleicht zwei `CFileTimeSpan`-Objekte, um die größere zu ermitteln.|
|[Cfiletimespan:: Operator &gt;=](#operator_gt_eq)|Vergleicht zwei `CFileTimeSpan`-Objekte, um die Gleichheit zu bestimmen oder die größere.|

## <a name="remarks"></a>Hinweise

Die `CFileTimeSpan`-Klasse stellt Methoden bereit, um relative Zeiträume in den vom Dateisystem verwendeten Einheiten zu verarbeiten. Diese Einheiten werden häufig in Datei Vorgängen verwendet, z. b. beim Erstellen einer Datei, beim letzten Zugriff oder bei der letzten Änderung. Die Methoden dieser Klasse werden häufig in Verbindung mit [cfiletime-Klassen](../../atl-mfc-shared/reference/cfiletime-class.md) Objekten verwendet.

## <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [cfiletime:: millisecond](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond).

## <a name="requirements"></a>-Anforderungen

**Header:** atltime. h

## <a name="cfiletimespan"></a>Cfiletimespan:: cfiletimespan

Der Konstruktor.

```cpp
CFileTimeSpan() throw();
CFileTimeSpan(const CFileTimeSpan& span) throw();
CFileTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>Parameters

*Span* -\
Ein vorhandenes `CFileTimeSpan`-Objekt.

*nspan* -\
Eine Zeitspanne in FILETIME-Einheiten.

### <a name="remarks"></a>Hinweise

Das `CFileTimeSpan`-Objekt kann mithilfe eines vorhandenen `CFileTimeSpan` Objekts oder als 64-Bit-Wert in 100-Nanosecond-FILETIME-Einheiten erstellt werden. Weitere Informationen finden Sie unter [cfiletime](cfiletime-class.md). Der Standardkonstruktor legt die Zeitspanne auf 0 fest.

## <a name="gettimespan"></a>Cfiletimespan:: GetTimeSpan

Rufen Sie diese Methode auf, um die Zeitspanne aus dem `CFileTimeSpan`-Objekt abzurufen.

```cpp
LONGLONG GetTimeSpan() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Zeitspanne in 100-Nanosekunden-FILETIME-Einheiten zurück. Weitere Informationen finden Sie unter [cfiletime](cfiletime-class.md).

## <a name="operator_-"></a>Cfiletimespan:: Operator-

Führt Subtraktion für ein `CFileTimeSpan` Objekt aus.

```cpp
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameters

*Span* -\
Ein `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt ein `CFileTimeSpan` Objekt zurück, das das Ergebnis der Differenz zwischen zwei Zeitspannen darstellt.

## <a name="operator_neq"></a>Cfiletimespan:: Operator! =

Überprüft zwei `CFileTimeSpan`-Objekte auf Ungleichheit.

```cpp
bool operator!=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameters

*Span* -\
Das zu vergleichende `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das verglichene Element nicht gleich dem `CFileTimeSpan` Objekt ist. andernfalls false.

## <a name="operator_add"></a>Cfiletimespan:: Operator +

Führt Addition für ein `CFileTimeSpan` Objekt aus.

```cpp
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameters

*Span* -\
Ein `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt ein `CFileTimeSpan` Objekt zurück, das die Summe der beiden Zeitspannen enthält.

## <a name="operator_add_eq"></a>Cfiletimespan:: Operator + =

Führt Addition für ein `CFileTimeSpan` Objekt aus und weist das Ergebnis dem aktuellen-Objekt zu.

```cpp
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parameters

*Span* -\
Ein `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt das aktualisierte `CFileTimeSpan` Objekt zurück, das die Summe der beiden Zeitspannen enthält.

## <a name="operator_lt"></a>Cfiletimespan:: Operator &lt;

Vergleicht zwei `CFileTimeSpan`-Objekte, um die kleinere zu bestimmen.

```cpp
bool operator<(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameters

*Span* -\
Das zu vergleichende `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das erste Objekt kleiner ist (d. h. einen kürzeren Zeitraum darstellt) als das zweite, andernfalls false.

## <a name="operator_lt_eq"></a>Cfiletimespan:: Operator &lt;=

Vergleicht zwei `CFileTimeSpan`-Objekte, um die Gleichheit zu bestimmen.

```cpp
bool operator<=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameters

*Span* -\
Das zu vergleichende `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das erste Objekt kleiner als (d. h. ein kürzerer Zeitraum darstellt) oder gleich dem zweiten ist, andernfalls false.

## <a name="operator_eq"></a>Cfiletimespan:: Operator =

Der Zuweisungs Operator.

```cpp
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```

### <a name="parameters"></a>Parameters

*Span* -\
Ein `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt das aktualisierte `CFileTimeSpan` Objekt zurück.

## <a name="operator_-_eq"></a>Cfiletimespan:: Operator-=

Führt Subtraktion für ein `CFileTimeSpan` Objekt aus und weist das Ergebnis dem aktuellen-Objekt zu.

```cpp
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parameters

*Span* -\
Ein `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt das aktualisierte `CFileTimeSpan` Objekt zurück.

## <a name="operator_eq_eq"></a>Cfiletimespan:: Operator = =

Überprüft zwei `CFileTimeSpan`-Objekte auf Gleichheit.

```cpp
bool operator==(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameters

*Span* -\
Das zu vergleichende `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Objekte gleich sind, andernfalls false.

## <a name="operator_gt"></a>Cfiletimespan:: Operator &gt;

Vergleicht zwei `CFileTimeSpan`-Objekte, um die größere zu ermitteln.

```cpp
bool operator>(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameters

*Span* -\
Das zu vergleichende `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das erste Objekt größer als das zweite ist (d. h. einen längeren Zeitraum darstellt), andernfalls false.

## <a name="operator_gt_eq"></a>Cfiletimespan:: Operator &gt;=

Vergleicht zwei `CFileTimeSpan`-Objekte, um die Gleichheit zu bestimmen oder die größere.

```cpp
bool operator>=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parameters

*Span* -\
Das zu vergleichende `CFileTimeSpan`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das erste Objekt größer als (d. h. ein längerer Zeitraum darstellt) oder gleich dem zweiten ist, andernfalls false.

## <a name="settimespan"></a>Cfiletimespan:: SetTimeSpan

Diese Methode wird aufgerufen, um die Zeitspanne des `CFileTimeSpan` Objekts festzulegen.

```cpp
void SetTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>Parameters

*nspan* -\
Der neue Wert für die Zeitspanne in 100-Nanosekunden-FILETIME-Einheiten. Weitere Informationen finden Sie unter [cfiletime](cfiletime-class.md).

## <a name="see-also"></a>Siehe auch

[FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) -\
[Cfiletime-Klasse](cfiletime-class.md)\
[Hierarchie Diagramm](../../mfc/hierarchy-chart.md)\
[Gemeinsam genutzte ATL/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)
