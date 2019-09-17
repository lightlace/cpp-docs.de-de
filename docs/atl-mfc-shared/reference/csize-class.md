---
title: CSize-Klasse
ms.date: 10/18/2018
f1_keywords:
- CSize
- ATLTYPES/ATL::CSize
- ATLTYPES/ATL::CSize::CSize
helpviewer_keywords:
- SIZE
- dimensions, MFC
- dimensions
- CSize class
ms.assetid: fb2cf85a-0bc1-46f8-892b-309c108b52ae
ms.openlocfilehash: 26bb43355f4dff3f77a905068bea83dd1ceaf79c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491656"
---
# <a name="csize-class"></a>CSize-Klasse

Ähnelt der Windows-Struktur [SIZE](/windows/win32/api/windef/ns-windef-size) , bei der eine relative Koordinate oder Position implementiert wird

## <a name="syntax"></a>Syntax

```
class CSize : public tagSIZE
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSize:: CSize](#csize)|Erstellt ein `CSize`-Objekt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CSize:: Operator-](#operator_-)|Subtrahiert zwei Größen.|
|[CSize:: Operator! =](#operator_neq)|Prüft auf Ungleichheit zwischen `CSize` und einer Größe.|
|[CSize:: Operator +](#operator_add)|Addiert zwei Größen.|
|[CSize:: Operator + =](#operator_add_eq)|Fügt eine Größe `CSize`hinzu.|
|[CSize:: Operator-=](#operator_-_eq)|Subtrahiert eine `CSize`Größe von.|
|[CSize:: Operator = =](#operator_eq_eq)|Prüft auf Gleichheit zwischen `CSize` und einer Größe.|

## <a name="remarks"></a>Hinweise

Diese Klasse wird von der `SIZE` -Struktur abgeleitet. Dies bedeutet, dass Sie ein `CSize` -Element in einem Parameter übergeben können `SIZE` , der `CSize`einen aufruft und auf `SIZE` die Datenmember der-Struktur zugreifen können.

Die `cx` - `cy` und- `SIZE` Member von `CSize`(und) sind öffentlich. Außerdem `CSize` implementiert Member-Funktionen, um die `SIZE` Struktur zu bearbeiten.

> [!NOTE]
> Weitere Informationen zu freigegebenen Hilfsprogrammklassen ( `CSize`z. b.) finden Sie unter [Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`tagSIZE`

`CSize`

## <a name="requirements"></a>Anforderungen

**Header:** atltypes. h

##  <a name="csize"></a>CSize:: CSize

Erstellt ein `CSize`-Objekt.

```
CSize() throw();
CSize( int initCX, int initCY) throw();
CSize( SIZE initSize) throw();
CSize( POINT initPt) throw();
CSize( DWORD dwSize) throw();
```

### <a name="parameters"></a>Parameter

*initCX*<br/>
Legt den `cx` -Member für `CSize`den fest.

*initCY*<br/>
Legt den `cy` -Member für `CSize`den fest.

*initSize*<br/>
Die [Größen](/windows/win32/api/windef/ns-windef-size) Struktur `CSize` oder das Objekt, das `CSize`zum Initialisieren verwendet wird.

*initPt*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point)-Struktur oder `CPoint`, Objekt, die bzw. das für die Initialisierung von `CSize` verwendet wurde

*dwSize*<br/>
DWORD, das zum Initialisieren `CSize`von verwendet wird. Das nieder wertige Wort ist `cx` das-Element, und das hochwertige Wort ist der `cy` Member.

### <a name="remarks"></a>Hinweise

Wenn keine Argumente angegeben werden, `cx` werden `cy` und mit 0 (null) initialisiert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#97](../../atl-mfc-shared/codesnippet/cpp/csize-class_1.cpp)]

##  <a name="operator_eq_eq"></a>CSize:: Operator = =

Prüft auf Gleichheit zwischen zwei Größen.

```
BOOL operator==(SIZE size) const throw();
```

### <a name="remarks"></a>Hinweise

Gibt einen Wert ungleich 0 (null) zurück, wenn die Größen gleich sind, otherwize 0

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#98](../../atl-mfc-shared/codesnippet/cpp/csize-class_2.cpp)]

##  <a name="operator_neq"></a>CSize:: Operator! =

Überprüft die Ungleichheit zwischen zwei Größen.

```
BOOL operator!=(SIZE size) const throw();
```

### <a name="remarks"></a>Hinweise

Gibt einen Wert ungleich 0 (null) zurück, wenn die Größen ungleich sind, andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#99](../../atl-mfc-shared/codesnippet/cpp/csize-class_3.cpp)]

##  <a name="operator_add_eq"></a>CSize:: Operator + =

Fügt diesem `CSize`eine Größe hinzu.

```
void operator+=(SIZE size) throw();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#100](../../atl-mfc-shared/codesnippet/cpp/csize-class_4.cpp)]

##  <a name="operator_-_eq"></a>CSize:: Operator-=

Subtrahiert eine Größe `CSize`von dieser.

```
void operator-=(SIZE size) throw();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#101](../../atl-mfc-shared/codesnippet/cpp/csize-class_5.cpp)]

##  <a name="operator_add"></a>CSize:: Operator +

Diese Operatoren fügen `CSize` diesen Wert dem Wert des-Parameters hinzu.

```
CSize operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="remarks"></a>Hinweise

Sehen Sie sich die folgenden Beschreibungen der einzelnen Operatoren an:

- **Operator + (** *Größe* **)**

  Dieser Vorgang fügt zwei `CSize` Werte hinzu.

- **Operator + (** *Punkt* **)**

  Mit diesem Vorgang wird ein [Punkt](/previous-versions/dd162805\(v=vs.85\)) -(oder [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)-) Wert mit diesem `CSize` Wert Offsets (verschoben). Die `cx` - `cy` und-Member `CSize` dieses Werts werden dem `x` -Datenmember und dem- `POINT` Datenmember des- `y` Werts hinzugefügt. Dies entspricht der Version von [CPoint:: Operator +](../../atl-mfc-shared/reference/cpoint-class.md#operator_add) , die einen [size](/windows/win32/api/windef/ns-windef-size) -Parameter annimmt.

- **Operator + (** *lprect* **)**

   Mit diesem Vorgang wird ein [Rect](/previous-versions/dd162897\(v=vs.85\)) -Wert (oder [CRect](../../atl-mfc-shared/reference/crect-class.md)) mit diesem `CSize` Wert Offsets (verschoben). Die `cx` - `cy` und-Member `CSize` dieses Werts werden den `left`Datenmembern `right`, `top`, `bottom` und des `RECT` -Werts hinzugefügt. Dies entspricht der Version von [CRect:: Operator +](../../atl-mfc-shared/reference/crect-class.md#operator_add) , die einen [size](/windows/win32/api/windef/ns-windef-size) -Parameter annimmt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#102](../../atl-mfc-shared/codesnippet/cpp/csize-class_6.cpp)]

##  <a name="operator_-"></a>CSize:: Operator-

Die ersten drei dieser Operatoren subtrahieren diesen `CSize` Wert zum Wert des-Parameters.

```
CSize operator-(SIZE size) const throw();
CPoint operator-(POINT point) const throw();
CRect operator-(const RECT* lpRect) const throw();
CSize operator-() const throw();
```

### <a name="remarks"></a>Hinweise

Der vierte Operator, das unäre Minuszeichen, ändert das Vorzeichen des `CSize` Werts. Sehen Sie sich die folgenden Beschreibungen der einzelnen Operatoren an:

- **Operator-(** *Größe* **)**

  Dieser Vorgang Subtrahiert zwei `CSize` Werte.

- **Operator-(** *Punkt* **)**

  Mit diesem Vorgang wird ein [Punkt](/previous-versions/dd162805\(v=vs.85\)) -oder [cpointwert](../../atl-mfc-shared/reference/cpoint-class.md) durch den Additiven umgekehrten Wert dieses `CSize` Werts Offsets (verschoben). Der `cx` und `x` `y` dieses Werts werden von den-und-Datenmembern des- `POINT` Werts subtrahiert. `CSize` `cy` Dies entspricht der Version von [CPoint:: Operator](../../atl-mfc-shared/reference/cpoint-class.md#operator_-) , die einen [size](/windows/win32/api/windef/ns-windef-size) -Parameter annimmt.

- **Operator-(** *lprect* **)**

  Mit diesem Vorgang wird ein [Rect](/previous-versions/dd162897\(v=vs.85\)) -oder [CRect](../../atl-mfc-shared/reference/crect-class.md) -Wert durch den Additiven umgekehrten Wert dieses `CSize` Werts Offsets (verschoben). Die `cx` - `cy` und-Member `CSize` dieses Werts werden von den `left`Datenmembern `right`, `top`, `bottom` und des `RECT` -Werts subtrahiert. Dies entspricht der Version von [CRect:: Operator](../../atl-mfc-shared/reference/crect-class.md#operator_-) , die einen [size](/windows/win32/api/windef/ns-windef-size) -Parameter annimmt.

- **operator -()**

  Dieser Vorgang gibt den Additiven umgekehrten Wert `CSize` dieses Werts zurück.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#103](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel-MDI](../../overview/visual-cpp-samples.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CRect-Klasse](../../atl-mfc-shared/reference/crect-class.md)<br/>
[CPoint-Klasse](../../atl-mfc-shared/reference/cpoint-class.md)
