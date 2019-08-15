---
title: CPoint-Klasse
ms.date: 11/04/2016
f1_keywords:
- CPoint
- ATLTYPES/ATL::CPoint
- ATLTYPES/ATL::CPoint::CPoint
- ATLTYPES/ATL::CPoint::Offset
helpviewer_keywords:
- LPPOINT structure
- POINT structure
- CPoint class
ms.assetid: a6d4db93-35cc-444d-9221-c3e160f6edaa
ms.openlocfilehash: b7c13ef8b9656c5c2fa6a90fefca0d9babbe1c84
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491227"
---
# <a name="cpoint-class"></a>CPoint-Klasse

Ähnlich der Windows-Struktur `POINT` .

## <a name="syntax"></a>Syntax

```
class CPoint : public tagPOINT
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CPoint::CPoint](#cpoint)|Erstellt ein Objekt vom Typ `CPoint`.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CPoint::Offset](#offset)|Fügt dem-Element `x` und `y` dem-Element `CPoint`des-Werts Werte hinzu.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CPoint:: Operator-](#operator_-)|Gibt den Unterschied zwischen `CPoint` einem und einer Größe oder der Negation eines Punkts oder dem Größenunterschied zwischen zwei Punkten oder dem Offset durch eine negative Größe zurück.|
|[CPoint:: Operator! =](#operator_neq)|Überprüft die Ungleichheit zwischen zwei Punkten.|
|[CPoint:: Operator +](#operator_add)|Gibt die Summe von a `CPoint` und eine Größe oder einen Punkt oder einen `CRect` Offset um eine Größe zurück.|
|[CPoint::operator +=](#operator_add_eq)|Offsets `CPoint` durch Hinzufügen einer Größe oder eines Punkts.|
|[CPoint::operator -=](#operator_-_eq)|Offsets `CPoint` durch Subtraktion einer Größe oder eines Punkts.|
|[CPoint::operator ==](#operator_eq_eq)|Überprüft die Gleichheit zwischen zwei Punkten.|

## <a name="remarks"></a>Hinweise

Sie enthält außerdem Element Funktionen zum Bearbeiten `CPoint` und [zeigen](/windows/win32/api/windef/ns-windef-point) von Strukturen.

Ein `CPoint` -Objekt kann überall dort verwendet `POINT` werden, wo eine-Struktur verwendet wird. Die Operatoren dieser Klasse, die mit einer "Größe" interagieren, akzeptieren entweder [CSize](../../atl-mfc-shared/reference/csize-class.md) -Objekte oder [Größen](/windows/win32/api/windef/ns-windef-size) Strukturen, da beide austauschbar sind.

> [!NOTE]
>  Diese Klasse wird von der `tagPOINT` -Struktur abgeleitet. (Der Name `tagPOINT` ist ein Name für die `POINT` Struktur, der weniger häufig verwendet wird.) Dies bedeutet, dass die Datenmember `POINT` der Struktur, `x` und `y`, auf `CPoint`die Datenmember zugreifen können.

> [!NOTE]
>  Weitere Informationen zu freigegebenen Hilfsprogrammklassen ( `CPoint`z. b.) finden Sie unter [Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`tagPOINT`

`CPoint`

## <a name="requirements"></a>Anforderungen

**Header:** atltypes. h

##  <a name="cpoint"></a>CPoint:: CPoint

Erstellt ein `CPoint`-Objekt.

```
CPoint() throw();
CPoint(int initX, int initY) throw();
CPoint(POINT initPt) throw();
CPoint(SIZE initSize) throw();
CPoint(LPARAM dwPoint) throw();
```

### <a name="parameters"></a>Parameter

*initX*<br/>
Gibt den Wert des `x`-Members von `CPoint` an.

*zung*<br/>
Gibt den Wert des `y`-Members von `CPoint` an.

*initPt*<br/>
[Punkt](/windows/win32/api/windef/ns-windef-point) Struktur oder `CPoint` , die die Werte angibt, die zum `CPoint`Initialisieren von verwendet werden.

*initSize*<br/>
[Größen](/windows/win32/api/windef/ns-windef-size) Struktur oder [CSize](../../atl-mfc-shared/reference/csize-class.md) , die die Werte angibt, die zum `CPoint`Initialisieren von verwendet werden.

*dwPoint*<br/>
Legt den `x` -Member auf das nieder wertige Wort von *dwpoint* und den `y` -Member auf das hochwertige Wort von *dwpoint*fest.

### <a name="remarks"></a>Hinweise

Wenn keine Argumente angegeben werden, werden die `x`- und `y`-Member auf 0 festgelegt.

### <a name="example"></a>Beispiel

```cpp
CPoint   ptTopLeft(0, 0);
// works from a POINT, too

POINT   ptHere;
ptHere.x = 35;
ptHere.y = 95;

CPoint   ptMFCHere(ptHere);

// works from a SIZE
SIZE   sHowBig;
sHowBig.cx = 300;
sHowBig.cy = 10;

CPoint ptMFCBig(sHowBig);
// or from a DWORD

DWORD   dwSize;
dwSize = MAKELONG(35, 95);

CPoint ptFromDouble(dwSize);
ASSERT(ptFromDouble == ptMFCHere);
```

##  <a name="offset"></a>CPoint:: Offset

Fügt dem-Element `x` und `y` dem-Element `CPoint`des-Werts Werte hinzu.

```
void Offset(int xOffset, int yOffset) throw();
void Offset(POINT point) throw();
void Offset(SIZE size) throw();
```

### <a name="parameters"></a>Parameter

*xOffset*<br/>
Gibt den Betrag an, um `x` den der Member `CPoint`von versetzt werden soll.

*yOffset*<br/>
Gibt den Betrag an, um `y` den der Member `CPoint`von versetzt werden soll.

*point*<br/>
Gibt den Betrag ( [Punkt](/windows/win32/api/windef/ns-windef-point) oder `CPoint`) an, um `CPoint`den versetzt werden soll.

*size*<br/>
Gibt den Betrag ( [Größe](/windows/win32/api/windef/ns-windef-size) oder [CSize](../../atl-mfc-shared/reference/csize-class.md)) an, um `CPoint`den versetzt werden soll.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#28](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_1.cpp)]

##  <a name="operator_eq_eq"></a>CPoint:: Operator = =

Überprüft die Gleichheit zwischen zwei Punkten.

```
BOOL operator==(POINT point) const throw();
```

### <a name="parameters"></a>Parameter

*point*<br/>
Enthält eine [Punkt](/windows/win32/api/windef/ns-windef-point) Struktur oder `CPoint` ein Objekt.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Punkte gleich sind. andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#29](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_2.cpp)]

##  <a name="operator_neq"></a>CPoint:: Operator! =

Überprüft die Ungleichheit zwischen zwei Punkten.

```
BOOL operator!=(POINT point) const throw();
```

### <a name="parameters"></a>Parameter

*point*<br/>
Enthält eine [Punkt](/windows/win32/api/windef/ns-windef-point) Struktur oder `CPoint` ein Objekt.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Punkte nicht gleich sind. andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#30](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_3.cpp)]

##  <a name="operator_add_eq"></a>CPoint:: Operator + =

Die erste Überladung fügt dem `CPoint`eine Größe hinzu.

```
void operator+=(SIZE size) throw();
void operator+=(POINT point) throw();
```

### <a name="parameters"></a>Parameter

*size*<br/>
Enthält eine [Größen](/windows/win32/api/windef/ns-windef-size) Struktur oder ein [CSize](../../atl-mfc-shared/reference/csize-class.md) -Objekt.

*point*<br/>
Enthält eine [Punkt](/windows/win32/api/windef/ns-windef-point) Struktur oder ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) -Objekt.

### <a name="remarks"></a>Hinweise

Die zweite Überladung fügt der `CPoint`einen Punkt hinzu.

In beiden Fällen erfolgt die Addition durch Hinzufügen `x` des Members (oder `cx`) des rechten Operanden `CPoint` zum `x` -Member der und durch Hinzufügen des `y` -Elements (oder `cy`) des rechten Operanden zum `y` Member`CPoint`von.

Beispielsweise wird durch `CPoint(5, -7)` das Hinzufügen zu einer `CPoint(30, 40)` Variablen, die enthält `CPoint(35, 33)`, die-Variable in geändert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#31](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_4.cpp)]

##  <a name="operator_-_eq"></a>CPoint:: Operator-=

Die erste Überladung Subtrahiert eine `CPoint`Größe vom.

```
void operator-=(SIZE size) throw();
void operator-=(POINT point) throw();
```

### <a name="parameters"></a>Parameter

*size*<br/>
Enthält eine [Größen](/windows/win32/api/windef/ns-windef-size) Struktur oder ein [CSize](../../atl-mfc-shared/reference/csize-class.md) -Objekt.

*point*<br/>
Enthält eine [Punkt](/windows/win32/api/windef/ns-windef-point) Struktur oder ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) -Objekt.

### <a name="remarks"></a>Hinweise

Die zweite Überladung subtrahiert einen `CPoint`Punkt vom.

In beiden Fällen erfolgt die `x` Subtraktion durch Subtraktion des Members (oder `cx`) des rechten Operanden `CPoint` vom `x` `y` Member der und Subtraktion des Members (oder `cy`) von der rechten Seite. Operand aus dem `y` -Member `CPoint`von.

Beispielsweise wird durch Subtrahieren `CPoint(5, -7)` von einer Variablen, die enthält `CPoint(30, 40)` , `CPoint(25, 47)`die Variable in geändert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#32](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_5.cpp)]

##  <a name="operator_add"></a>CPoint:: Operator +

Verwenden Sie diesen Operator, `CPoint` um ein `CPoint` - `CSize` oder-Objekt zu versetzen oder `CRect` um ein `CPoint`durch ein-Objekt zu versetzen.

```
CPoint operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="parameters"></a>Parameter

*size*<br/>
Enthält eine [Größen](/windows/win32/api/windef/ns-windef-size) Struktur oder ein [CSize](../../atl-mfc-shared/reference/csize-class.md) -Objekt.

*point*<br/>
Enthält eine [Punkt](/windows/win32/api/windef/ns-windef-point) Struktur oder ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) -Objekt.

*lpRect*<br/>
Enthält einen Zeiger auf eine [Rect](/windows/win32/api/windef/ns-windef-rect) -Struktur oder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt.

### <a name="return-value"></a>Rückgabewert

Ein `CPoint` , der um eine Größe versetzt wird, `CPoint` ein, der um einen Punkt versetzt wird, `CRect` oder ein Offset um einen Punkt.

### <a name="remarks"></a>Hinweise

Wenn Sie z. b. eine der ersten zwei über Ladungen verwenden, um `CPoint(25, -19)` den Punkt um `CPoint(15, 5)` einen Punkt `CSize(15, 5)` oder eine Größe `CPoint(40, -14)`zu versetzen, wird der Wert zurückgegeben.

Durch das Hinzufügen eines Rechtecks zu einem Punkt wird das Rechteck `x` nach `y` dem Offset durch die Werte und angegeben, die am Punkt angegeben sind. Wenn beispielsweise die letzte Überladung verwendet wird, um `CRect(125, 219, 325, 419)` ein Rechteck um `CPoint(25, -19)` einen `CRect(150, 200, 350, 400)`Punkt zu versetzen, wird zurückgegeben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#33](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_6.cpp)]

##  <a name="operator_-"></a>CPoint:: Operator-

Verwenden Sie eine der ersten beiden über Ladungen, um ein `CPoint` -oder `CSize` -Objekt von `CPoint`zu subtrahieren.

```
CSize operator-(POINT point) const throw();
CPoint operator-(SIZE size) const throw();
CRect operator-(const RECT* lpRect) const throw();
CPoint operator-() const throw();
```

### <a name="parameters"></a>Parameter

*point*<br/>
Eine [Punkt](/windows/win32/api/windef/ns-windef-point) Struktur oder ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) -Objekt.

*size*<br/>
Eine [Größen](/windows/win32/api/windef/ns-windef-size) Struktur oder ein [CSize](../../atl-mfc-shared/reference/csize-class.md) -Objekt.

*lpRect*<br/>
Ein Zeiger auf eine [Rect](/windows/win32/api/windef/ns-windef-rect) -Struktur oder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt.

### <a name="return-value"></a>Rückgabewert

Ein `CSize` , der die Differenz zwischen zwei Punkten ist, `CPoint` ein, der durch die Negation einer Größe versetzt wird, `CRect` ein, der durch die Negation eines Punkts versetzt wird, oder `CPoint` ein, der die Negation eines Punkts ist.

### <a name="remarks"></a>Hinweise

Die dritte Überladung versetzt eine `CRect` durch die Negation von `CPoint`. Verwenden Sie abschließend den unären Operator, um zu `CPoint`negieren.

Verwenden Sie beispielsweise die erste Überladung, um den Unterschied zwischen `CPoint(25, -19)` zwei `CPoint(15, 5)` Punkten `CSize(10, -24)`zu ermitteln, und gibt zurück.

`CSize` Das Subtrahieren `CPoint` von aus führt dieselbe Berechnung wie oben aus, `CPoint` gibt jedoch `CSize` ein-Objekt zurück, kein-Objekt. Verwenden Sie beispielsweise die zweite Überladung, um den Unterschied zwischen `CPoint(25, -19)` dem Punkt und `CSize(15, 5)` der `CPoint(10, -24)`Größe zu ermitteln.

Durch das Subtrahieren eines Rechtecks von einem Punkt wird das Rechteck Offset `x` um `y` die negativen Werte der Werte des-Werts und des-Werts zurückgegeben. Wenn Sie z `CRect(125, 200, 325, 400)` `CRect(100, 219, 300, 419)`. b. die letzte Überladung verwenden, um das `CPoint(25, -19)` Rechteck um den Punkt zu versetzen, wird die

Verwenden Sie den unären Operator, um einen Punkt zu negieren. Beispielsweise wird mit dem unären Operator mit dem Punkt `CPoint(25, -19)` zurück `CPoint(-25, 19)`gegeben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#34](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_7.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel-MDI](../../overview/visual-cpp-samples.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Punkt Struktur](/windows/win32/api/windef/ns-windef-point)<br/>
[CRect-Klasse](../../atl-mfc-shared/reference/crect-class.md)<br/>
[CSize-Klasse](../../atl-mfc-shared/reference/csize-class.md)
