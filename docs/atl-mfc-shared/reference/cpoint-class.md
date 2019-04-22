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
ms.openlocfilehash: 85e469e1f52a22917580ce8616aaba5ff57d08ed
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58768028"
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
|[CPoint::Offset](#offset)|Addiert die Werte, die `x` und `y` Mitglied der `CPoint`.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CPoint::operator-](#operator_-)|Gibt die Differenz zwischen einer `CPoint` und eine Größe oder die Negation der einen Punkt oder die Differenz der Größe zwischen zwei Punkten der Erde oder den Offset von einer negativen Größe.|
|[CPoint::operator !=](#operator_neq)|Prüft auf Ungleichheit zwischen zwei Punkten.|
|[CPoint::operator +](#operator_add)|Gibt die Summe der ein `CPoint` und eine Größe oder ein Punkt oder ein `CRect` um eine Größe verringert.|
|[CPoint::operator +=](#operator_add_eq)|Offsets `CPoint` einen Größe oder den Punkt hinzufügen.|
|[CPoint::operator -=](#operator_-_eq)|Offsets `CPoint` durch Subtrahieren eine Größe oder den Punkt.|
|[CPoint::operator ==](#operator_eq_eq)|Prüft auf Gleichheit zwischen zwei Punkten.|

## <a name="remarks"></a>Hinweise

Es enthält auch Member-Funktionen zum Bearbeiten von `CPoint` und [Punkt](/windows/desktop/api/windef/ns-windef-tagpoint) Strukturen.

Ein `CPoint` Objekt kann es sich immer verwendet eine `POINT` Struktur verwendet wird. Die Operatoren dieser Klasse, die Interaktion mit einem "Size" akzeptiert beide [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekte oder [Größe](/windows/desktop/api/windef/ns-windef-tagsize) strukturiert werden, da die beiden austauschbar sind.

> [!NOTE]
>  Diese Klasse ist abgeleitet von der `tagPOINT` Struktur. (Der Name `tagPOINT` weniger häufig verwendeter Name ist für die `POINT` Struktur.) Dies bedeutet, dass die Datenmember des der `POINT` Struktur `x` und `y`, sind die zugänglichen Datenmember `CPoint`.

> [!NOTE]
>  Weitere Informationen zu freigegebenen hilfsprogrammklassen (z. B. `CPoint`), finden Sie unter [gemeinsam genutzten Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`tagPOINT`

`CPoint`

## <a name="requirements"></a>Anforderungen

**Header:** atltypes.h

##  <a name="cpoint"></a>  CPoint::CPoint

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

*initY*<br/>
Gibt den Wert des `y`-Members von `CPoint` an.

*initPt*<br/>
[Punkt](/windows/desktop/api/windef/ns-windef-tagpoint) Struktur oder `CPoint` , die angibt, dass die Werte zum Initialisieren verwendet `CPoint`.

*initSize*<br/>
[Größe](/windows/desktop/api/windef/ns-windef-tagsize) Struktur oder [CSize](../../atl-mfc-shared/reference/csize-class.md) , die angibt, dass die Werte zum Initialisieren verwendet `CPoint`.

*dwPoint*<br/>
Legt die `x` Member das niederwertige Wort *DwPoint* und `y` Member das höherwertige Word des *DwPoint*.

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

##  <a name="offset"></a>  CPoint::Offset

Addiert die Werte, die `x` und `y` Mitglied der `CPoint`.

```
void Offset(int xOffset, int yOffset) throw();
void Offset(POINT point) throw();
void Offset(SIZE size) throw();
```

### <a name="parameters"></a>Parameter

*xOffset*<br/>
Gibt an, der Betrag, um die `x` Mitglied der `CPoint`.

*yOffset*<br/>
Gibt an, der Betrag, um die `y` Mitglied der `CPoint`.

*point*<br/>
Gibt an, wie ( [Punkt](/windows/desktop/api/windef/ns-windef-tagpoint) oder `CPoint`) für den offset der `CPoint`.

*size*<br/>
Gibt an, wie ( [Größe](/windows/desktop/api/windef/ns-windef-tagsize) oder [CSize](../../atl-mfc-shared/reference/csize-class.md)) für den offset der `CPoint`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#28](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_1.cpp)]

##  <a name="operator_eq_eq"></a>  CPoint::operator ==

Prüft auf Gleichheit zwischen zwei Punkten.

```
BOOL operator==(POINT point) const throw();
```

### <a name="parameters"></a>Parameter

*point*<br/>
Enthält eine [Punkt](/windows/desktop/api/windef/ns-windef-tagpoint) Struktur oder `CPoint` Objekt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Punkte gleich sind; andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#29](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_2.cpp)]

##  <a name="operator_neq"></a>  CPoint::operator! =

Prüft auf Ungleichheit zwischen zwei Punkten.

```
BOOL operator!=(POINT point) const throw();
```

### <a name="parameters"></a>Parameter

*point*<br/>
Enthält eine [Punkt](/windows/desktop/api/windef/ns-windef-tagpoint) Struktur oder `CPoint` Objekt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Punkte ungleich sind; andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#30](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_3.cpp)]

##  <a name="operator_add_eq"></a>  CPoint::operator +=

Die erste Überladung fügt eine Größe, auf die `CPoint`.

```
void operator+=(SIZE size) throw();
void operator+=(POINT point) throw();
```

### <a name="parameters"></a>Parameter

*size*<br/>
Enthält eine [Größe](/windows/desktop/api/windef/ns-windef-tagsize) Struktur oder [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.

*point*<br/>
Enthält eine [Punkt](/windows/desktop/api/windef/ns-windef-tagpoint) Struktur oder [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Objekt.

### <a name="remarks"></a>Hinweise

Die zweite Überladung fügt einen Punkt in der `CPoint`.

In beiden Fällen erfolgt die Addition durch Hinzufügen der `x` (oder `cx`) Mitglied der Rechte Operand, der die `x` Mitglied der `CPoint` und Hinzufügen der `y` (oder `cy`) Mitglied der Rechte Operand, der die `y` Mitglied der `CPoint`.

Z. B. Hinzufügen von `CPoint(5, -7)` auf eine Variable enthält `CPoint(30, 40)` ändert sich die Variable `CPoint(35, 33)`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#31](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_4.cpp)]

##  <a name="operator_-_eq"></a>  CPoint::operator =

Die erste Überladung subtrahiert eine Größe aus der `CPoint`.

```
void operator-=(SIZE size) throw();
void operator-=(POINT point) throw();
```

### <a name="parameters"></a>Parameter

*size*<br/>
Enthält eine [Größe](/windows/desktop/api/windef/ns-windef-tagsize) Struktur oder [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.

*point*<br/>
Enthält eine [Punkt](/windows/desktop/api/windef/ns-windef-tagpoint) Struktur oder [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Objekt.

### <a name="remarks"></a>Hinweise

Die zweite Überladung subtrahiert einen Punkt aus dem `CPoint`.

In beiden Fällen erfolgt durch Subtrahieren der Subtraktion der `x` (oder `cx`) Member des rechten Operanden aus der `x` Mitglied der `CPoint` und Subtrahieren von der `y` (oder `cy`) Mitglied der rechten Seite Operanden aus der `y` Mitglied der `CPoint`.

Subtrahieren Sie z. B. `CPoint(5, -7)` aus einer Variablen mit `CPoint(30, 40)` ändert sich die Variable `CPoint(25, 47)`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#32](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_5.cpp)]

##  <a name="operator_add"></a>  CPoint::operator +

Verwenden Sie diesen Operator für den offset `CPoint` durch eine `CPoint` oder `CSize` Objekt oder für den offset ein `CRect` durch eine `CPoint`.

```
CPoint operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="parameters"></a>Parameter

*size*<br/>
Enthält eine [Größe](/windows/desktop/api/windef/ns-windef-tagsize) Struktur oder [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.

*point*<br/>
Enthält eine [Punkt](/windows/desktop/api/windef/ns-windef-tagpoint) Struktur oder [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Objekt.

*lpRect*<br/>
Enthält einen Zeiger auf eine [RECT](/windows/desktop/api/windef/ns-windef-tagrect) Struktur oder [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt.

### <a name="return-value"></a>Rückgabewert

Ein `CPoint` , versetzt wird, indem Sie eine Größe aus, eine `CPoint` , die durch einen Punkt, versetzt wird oder ein `CRect` durch einen Punkt ausgeglichen.

### <a name="remarks"></a>Hinweise

Verwenden Sie eine der ersten beiden Überladungen beispielsweise für den offset des Punkts `CPoint(25, -19)` durch einen Punkt `CPoint(15, 5)` oder Größe `CSize(15, 5)` gibt den Wert `CPoint(40, -14)`.

Hinzufügen von Rechtecken zu einem Zeitpunkt gibt das Rechteck zurück, nachdem durch ausgeglichen wird die `x` und `y` Werte, die im Punkt angegeben. Verwenden Sie beispielsweise die letzte Überladung für den offset eines Rechtecks `CRect(125, 219, 325, 419)` durch einen Punkt `CPoint(25, -19)` gibt `CRect(150, 200, 350, 400)`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#33](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_6.cpp)]

##  <a name="operator_-"></a>  CPoint::operator-

Verwenden Sie eine der ersten beiden Überladungen subtrahiert einen `CPoint` oder `CSize` -Sitzungsobjekts `CPoint`.

```
CSize operator-(POINT point) const throw();
CPoint operator-(SIZE size) const throw();
CRect operator-(const RECT* lpRect) const throw();
CPoint operator-() const throw();
```

### <a name="parameters"></a>Parameter

*point*<br/>
Ein [Punkt](/windows/desktop/api/windef/ns-windef-tagpoint) Struktur oder [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Objekt.

*size*<br/>
Ein [Größe](/windows/desktop/api/windef/ns-windef-tagsize) Struktur oder [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.

*lpRect*<br/>
Ein Zeiger auf eine [RECT](/windows/desktop/api/windef/ns-windef-tagrect) Struktur oder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt.

### <a name="return-value"></a>Rückgabewert

Ein `CSize` , den Unterschied zwischen zwei Punkten einer `CPoint` , versetzt wird, mithilfe der Negation des eine Größe aus, eine `CRect` , die mithilfe der Negation eines Punkts, versetzt wird oder ein `CPoint` d. h. die Negation eines Punkts.

### <a name="remarks"></a>Hinweise

Die dritte Überladung Offsets eine `CRect` mithilfe der Negation des `CPoint`. Verwenden Sie abschließend den unäroperator um zu negierende `CPoint`.

Verwenden Sie beispielsweise die erste Überladung finden Sie den Unterschied zwischen zwei Punkten `CPoint(25, -19)` und `CPoint(15, 5)` gibt `CSize(10, -24)`.

Subtrahiert eine `CSize` aus `CPoint` ist die gleiche Berechnung wie oben beschrieben, gibt jedoch eine `CPoint` -Objekt und keine `CSize` Objekt. Verwenden Sie beispielsweise die zweite Überladung finden Sie den Unterschied zwischen dem `CPoint(25, -19)` und die Größe des `CSize(15, 5)` gibt `CPoint(10, -24)`.

Subtrahieren eines Rechtecks von einem Punkt gibt den Offset des Rechtecks zurück, indem die negative der der `x` und `y` Werte, die im Punkt angegeben. Verwenden Sie beispielsweise die letzte Überladung für den offset des Rechtecks `CRect(125, 200, 325, 400)` vom Punkt `CPoint(25, -19)` gibt `CRect(100, 219, 300, 419)`.

Verwenden Sie den unäroperator, um einen Punkt zu negieren. Verwenden Sie beispielsweise den unäroperator, mit dem Punkt `CPoint(25, -19)` gibt `CPoint(-25, 19)`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#34](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_7.cpp)]

## <a name="see-also"></a>Siehe auch

[MDI MFC-Beispiel](../../overview/visual-cpp-samples.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[POINT-Struktur](/windows/desktop/api/windef/ns-windef-tagpoint)<br/>
[CRect-Klasse](../../atl-mfc-shared/reference/crect-class.md)<br/>
[CSize-Klasse](../../atl-mfc-shared/reference/csize-class.md)
