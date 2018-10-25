---
title: CRect-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRect
- ATLTYPES/ATL::CRect
- ATLTYPES/ATL::CRect::CRect
- ATLTYPES/ATL::CRect::BottomRight
- ATLTYPES/ATL::CRect::CenterPoint
- ATLTYPES/ATL::CRect::CopyRect
- ATLTYPES/ATL::CRect::DeflateRect
- ATLTYPES/ATL::CRect::EqualRect
- ATLTYPES/ATL::CRect::Height
- ATLTYPES/ATL::CRect::InflateRect
- ATLTYPES/ATL::CRect::IntersectRect
- ATLTYPES/ATL::CRect::IsRectEmpty
- ATLTYPES/ATL::CRect::IsRectNull
- ATLTYPES/ATL::CRect::MoveToX
- ATLTYPES/ATL::CRect::MoveToXY
- ATLTYPES/ATL::CRect::MoveToY
- ATLTYPES/ATL::CRect::NormalizeRect
- ATLTYPES/ATL::CRect::OffsetRect
- ATLTYPES/ATL::CRect::PtInRect
- ATLTYPES/ATL::CRect::SetRect
- ATLTYPES/ATL::CRect::SetRectEmpty
- ATLTYPES/ATL::CRect::Size
- ATLTYPES/ATL::CRect::SubtractRect
- ATLTYPES/ATL::CRect::TopLeft
- ATLTYPES/ATL::CRect::UnionRect
- ATLTYPES/ATL::CRect::Width
dev_langs:
- C++
helpviewer_keywords:
- LPCRECT data type
- CRect class
- LPRECT operator
- RECT structure
ms.assetid: dee4e752-15d6-4db4-b68f-1ad65b2ed6ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 729dfa0b7bbe9a553dcc9e0aac78a86c402e8d43
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50065264"
---
# <a name="crect-class"></a>CRect-Klasse

Ähnlich wie eine Windows [RECT](../../mfc/reference/rect-structure.md) Struktur.

## <a name="syntax"></a>Syntax

```
class CRect : public tagRECT
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CRect::CRect](#crect)|Erstellt ein `CRect`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CRect::BottomRight](#bottomright)|Gibt den Punkt unten rechts `CRect`.|
|[CRect::CenterPoint](#centerpoint)|Gibt den Mittelpunkt der `CRect`.|
|[CRect::CopyRect](#copyrect)|Kopiert die Abmessungen des einem Quellrechteck auf `CRect`.|
|[CRect::DeflateRect](#deflaterect)|Verringert die Breite und Höhe des `CRect`.|
|[CRect::EqualRect](#equalrect)|Bestimmt, ob `CRect` ist gleich einem angegebenen Rechteck.|
|[CRect::Height](#height)|Berechnet die Höhe des `CRect`.|
|[CRect::InflateRect](#inflaterect)|Erhöht die Breite und Höhe des `CRect`.|
|[CRect::IntersectRect](#intersectrect)|Legt `CRect` die Schnittmenge zweier Rechtecke gleich.|
|[CRect::IsRectEmpty](#isrectempty)|Bestimmt, ob `CRect` ist leer. `CRect` ist leer, wenn die Breite bzw. Höhe 0 sind.|
|[CRect::IsRectNull](#isrectnull)|Bestimmt, ob die `top`, `bottom`, `left`, und `right` Membervariablen sind alle gleich 0.|
|[CRect::MoveToX](#movetox)|Verschiebt `CRect` an der angegebenen X-Koordinate.|
|[CRect::MoveToXY](#movetoxy)|Verschiebt `CRect` auf den angegebenen x- und y-Koordinaten.|
|[CRect::MoveToY](#movetoy)|Verschiebt `CRect` auf den angegebenen y-Koordinate.|
|[CRect:: NormalizeRect](#normalizerect)|Standardisiert die Höhe und Breite des `CRect`.|
|[CRect::OffsetRect](#offsetrect)|Verschiebt `CRect` durch die angegebenen Offsets.|
|[CRect::PtInRect](#ptinrect)|Bestimmt, ob der angegebene Punkt innerhalb liegt `CRect`.|
|[CRect::SetRect](#setrect)|Gibt die Abmessungen des `CRect`.|
|[CRect::SetRectEmpty](#setrectempty)|Legt `CRect` auf ein leeres Rechteck, das (alle Koordinaten gleich 0).|
|[CRect::Size](#size)|Berechnet die Größe der `CRect`.|
|[CRect::SubtractRect](#subtractrect)|Subtrahiert ein Rechteck von einem anderen.|
|[CRect::TopLeft](#topleft)|Gibt die linke obere Fehlerquelle `CRect`.|
|[CRect::UnionRect](#unionrect)|Legt `CRect` bezüglich der Gesamtmenge von zwei Rechtecke gleich.|
|[CRect::Width](#width)|Berechnet die Breite des `CRect`.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CRect::operator-](#operator_-)|Subtrahiert den angegebenen Offsets von `CRect` oder entleert `CRect` und gibt das resultierende `CRect`.|
|[CRect::operator LPCRECT](#operator_lpcrect)|Konvertiert ein `CRect`-Element in ein `LPCRECT`-Element.|
|[CRect::operator LPRECT](#operator_lprect)|Konvertiert ein `CRect`-Element in ein `LPRECT`-Element.|
|[CRect::operator! =](#operator_neq)|Bestimmt, ob `CRect` entspricht keinem Rechteck.|
|[CRect::operator &amp;](#operator_amp)|Erstellt die Schnittmenge der `CRect` und ein Rechteck und gibt das resultierende `CRect`.|
|[CRect::operator &amp;=](#operator_amp_eq)|Legt `CRect` gleich für die Schnittmenge der `CRect` und ein Rechteck.|
|[CRect::operator |](#operator_or)|Erstellt die Union der `CRect` und ein Rechteck und gibt das resultierende `CRect`.|
|[CRect::operator |=](#operator_or_eq)|Legt `CRect` bezüglich ihrer Gesamtmenge gleich `CRect` und ein Rechteck.|
|[CRect::operator +](#operator_add)|Fügt die angegebenen Offsets zu ILS der `CRect` oder vergrößert `CRect` und gibt das resultierende `CRect`.|
|[CRect::operator +=](#operator_add_eq)|Fügt die angegebenen Offsets `CRect` oder vergrößert `CRect`.|
|[CRect::operator =](#operator_eq)|Kopiert die Abmessungen eines Rechtecks an `CRect`.|
|[CRect::operator =](#operator_-_eq)|Subtrahiert den angegebenen Offsets von `CRect` oder entleert `CRect`.|
|[CRect::operator ==](#operator_eq_eq)|Bestimmt, ob `CRect` entspricht einem Rechteck.|

## <a name="remarks"></a>Hinweise

`CRect` enthält auch Member-Funktionen zum Bearbeiten von `CRect` Objekte und Windows `RECT` Strukturen.

Ein `CRect` Objekt übergeben werden kann, als Funktionsparameter immer eine `RECT` Struktur `LPCRECT`, oder `LPRECT` übergeben werden kann.

> [!NOTE]
>  Diese Klasse ist abgeleitet von der `tagRECT` Struktur. (Der Name `tagRECT` weniger häufig verwendete Name ist für die `RECT` Struktur.) Dies bedeutet, dass die Datenmember (`left`, `top`, `right`, und `bottom`) von der `RECT` Struktur werden die zugänglichen Datenmember `CRect`.

Ein `CRect` Membervariablen, die definieren, der oberen linken und rechten unteren Punkten eines Rechtecks enthält.

Beim Angeben einer `CRect`, achten Sie ihn erstellen, damit es normalisiert wird, anders gesagt, dass der Wert, der die linke Koordinate der rechten Seite und dem oberen unterschreitet ist kleiner als im unteren Bereich. Z. B. eine oben links (10,10) und unten rechts (20,20) definiert eines normalisierten Rechtecks, aber eine oben links (20,20) und unten rechts (10,10) definiert eine nicht normalisierte Rechteck. Wenn das Rechteck ist nicht normalisiert; viele `CRect` Memberfunktionen möglicherweise falsche Ergebnisse zurückgegeben. (Finden Sie unter [CRect:: NormalizeRect](#normalizerect) eine Liste dieser Funktionen.) Bevor Sie eine Funktion, die normalisierte Rechtecke erforderlich sind aufrufen, können Sie Rechtecke nicht normalisierte normalisieren, durch den Aufruf der `NormalizeRect` Funktion.

Seien Sie vorsichtig beim Bearbeiten von einen `CRect` mit der [CDC::DPtoLP](../../mfc/reference/cdc-class.md#dptolp) und [CDC::LPtoDP](../../mfc/reference/cdc-class.md#lptodp) Memberfunktionen. Wenn der Zuordnungsmodus, der einen Anzeigekontext ist, sodass der y-Block negativ ist, wie in `MM_LOENGLISH`, klicken Sie dann `CDC::DPtoLP` transformiert die `CRect` , damit seinen oberen, unteren größer ist. Funktionen wie `Height` und `Size` gibt dann negative Werte für die Höhe des transformierten `CRect`, und das Rechteck wird nicht normalisiert.

Wenn mithilfe von überladenen `CRect` Operatoren, der erste Operand muss ein `CRect`; das zweite kann es sich um eine [RECT](../../mfc/reference/rect-structure.md) Struktur oder ein `CRect` Objekt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`tagRECT`

`CRect`

## <a name="requirements"></a>Anforderungen

**Header:** atltypes.h

##  <a name="bottomright"></a>  CRect::BottomRight

Die Koordinaten werden zurückgegeben, als Verweis auf eine [CPoint](cpoint-class.md) in enthaltene Objekt `CRect`.

```
CPoint& BottomRight() throw();
const CPoint& BottomRight() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Koordinaten des der unteren rechten Ecke des Rechtecks.

### <a name="remarks"></a>Hinweise

Sie können diese Funktion verwenden, zum Abrufen oder Festlegen der unteren rechten Ecke des Rechtecks. Legen Sie die Ecke mit dieser Funktion auf der linken Seite des Zuweisungsoperators.

### <a name="example"></a>Beispiel

```cpp
// use BottomRight() to retrieve the bottom
// right POINT
CRect rect(210, 150, 350, 900);
CPoint ptDown;

ptDown = rect.BottomRight();

// ptDown is now set to (350, 900)
ASSERT(ptDown == CPoint(350, 900));

// or, use BottomRight() to set the bottom
// right POINT
CRect rect2(10, 10, 350, 350);
CPoint ptLow(180, 180);

CRect rect2(10, 10, 350, 350);
CPoint ptLow(180, 180);
rect2.BottomRight() = ptLow;

// rect2 is now (10, 10, 180, 180)
ASSERT(rect2 == CRect(10, 10, 180, 180));
```

##  <a name="centerpoint"></a>  CRect::CenterPoint

Berechnet den Mittelpunkt der `CRect` durch die linken und rechten Werte addiert und geteilt durch zwei, und die oberen und unteren Werte addiert und durch zwei dividiert wird.

```
CPoint CenterPoint() const throw();
```

### <a name="return-value"></a>Rückgabewert

Ein `CPoint` Objekt, das den Mittelpunkt der `CRect`.

### <a name="example"></a>Beispiel

```cpp
// Code from this OnPaint() implementation can be pasted into your own application
// to draw lines that would look like a letter "Y" within your dialog.
void CMyDlg::OnPaint()
{
    CPaintDC dc(this);

    // device context for painting

    // get the size and position of the client area of
    // your window

    CRect rect;
    GetClientRect(&rect);

    // Move the current pen to the top left of the window. We call the
    // TopLeft() member of CRect here and it returns a CPoint object we
    // pass to the override of CDC::MoveTo() that accepts a CPoint.

    dc.MoveTo(rect.TopLeft());

    // Draw a line from the top left to the center of the window.
    // CenterPoint() gives us the middle point of the window as a
    // CPoint, and since CDC::LineTo() has an override that accepts a
    // CPoint, we can just pass it along.

    dc.LineTo(rect.CenterPoint());

    // Now, draw a line to the top right of the window. There's no
    // CRect member which returns a CPoint for the top right of the
    // window, so we'll reference the CPoint members directly and call
    // the CDC::LineTo() override which takes two integers.

    dc.LineTo(rect.right, rect.top);

    // The top part of the "Y" is drawn. Now, we'll draw the stem. We
    // start from the center point.

    dc.MoveTo(rect.CenterPoint());

    // and then draw to the middle of the bottom edge of the window.
    // We'll get the x-coordinate from the x member of the CPOINT
    // returned by CenterPoint(), and the y value comes directly from
    // the rect.

    dc.LineTo(rect.CenterPoint().x, rect.bottom);
}
```

##  <a name="copyrect"></a>  CRect::CopyRect

Kopiert die `lpSrcRect` Rechteck in `CRect`.

```
void CopyRect(LPCRECT lpSrcRect) throw();
```

### <a name="parameters"></a>Parameter

*lpSrcRect*<br/>
Verweist auf die [RECT](../../mfc/reference/rect-structure.md) Struktur oder `CRect` -Objekt, das kopiert werden soll.

### <a name="example"></a>Beispiel

```cpp
CRect rectSource(35, 10, 125, 10);
CRect rectDest;

rectDest.CopyRect(&rectSource);

// rectDest is now set to (35, 10, 125, 10)

RECT rectSource2;
rectSource2.left = 0;
rectSource2.top = 0;
rectSource2.bottom = 480;
rectSource2.right = 640;

rectDest.CopyRect(&rectSource2);

// works against RECT structures, too!
// rectDest is now set to (0, 0, 640, 480)
```

##  <a name="crect"></a>  CRect::CRect

Erstellt ein `CRect`-Objekt.

```
CRect() throw();
CRect(int l, int t, int r, int b) throw();
CRect(const RECT& srcRect) throw();
CRect(LPCRECT lpSrcRect) throw();
CRect(POINT point, SIZE size) throw();
CRect(POINT topLeft, POINT bottomRight) throw();
```

### <a name="parameters"></a>Parameter

*l*<br/>
Gibt an, die linke Position des `CRect`.

*t*<br/>
Gibt an, am Anfang `CRect`.

*r*<br/>
Gibt an, die Rechte Position der `CRect`.

*b*<br/>
Gibt an, am Ende `CRect`.

*srcRect*<br/>
Bezieht sich auf die [RECT](../../mfc/reference/rect-structure.md) Struktur mit den Koordinaten für `CRect`.

*lpSrcRect*<br/>
Verweist auf die `RECT` Struktur mit den Koordinaten für `CRect`.

*Zeigen Sie*<br/>
Gibt den Ausgangspunkt für das Rechteck erstellt werden soll. Entspricht der linken oberen Ecke.

*size*<br/>
Gibt an, die Verschiebung von der linken oberen Ecke der unteren rechten Ecke des Rechtecks erstellt werden soll.

*topLeft*<br/>
Gibt die linke obere Position der `CRect`.

*bottomRight*<br/>
Gibt die Position unten rechts auf der `CRect`.

### <a name="remarks"></a>Hinweise

Wenn keine Argumente angegeben werden, `left`, `top`, `right`, und `bottom` Member nicht initialisiert werden.

Die `CRect`(`const RECT&`) und `CRect`(`LPCRECT`) führen Sie die Konstruktoren eine [CopyRect](#copyrect). Die anderen Konstruktoren initialisieren die Membervariablen des Objekts direkt auf.

### <a name="example"></a>Beispiel

```cpp
// default constructor doesn't initialize!
CRect rectUnknown;

// four-integers are left, top, right, and bottom
CRect rect(0, 0, 100, 50);
ASSERT(rect.Width() == 100);
ASSERT(rect.Height() == 50);

// Initialize from RECT stucture
RECT sdkRect;
sdkRect.left = 0;
sdkRect.top = 0;
sdkRect.right = 100;
sdkRect.bottom = 50;

CRect rect2(sdkRect);
// by reference
CRect rect3(&sdkRect);

// by address
ASSERT(rect2 == rect);
ASSERT(rect3 == rect);

// from a point and a size
CPoint pt(0, 0);
CSize sz(100, 50);
CRect rect4(pt, sz);
ASSERT(rect4 == rect2);

// from two points
CPoint ptBottomRight(100, 50);
CRect rect5(pt, ptBottomRight);
ASSERT(rect5 == rect4);
```

##  <a name="deflaterect"></a>  CRect::DeflateRect

`DeflateRect` entleert `CRect` durch dessen Seiten in Richtung der Mitte verschieben.

```
void DeflateRect(int x, int y) throw();
void DeflateRect(SIZE size) throw();
void DeflateRect(LPCRECT lpRect) throw();
void DeflateRect(int l, int t, int r, int b) throw();
```

### <a name="parameters"></a>Parameter

*w*<br/>
Gibt an, die Anzahl der Einheiten, die zum Verkleinern nach links und rechts vom `CRect`.

*y*<br/>
Gibt die Anzahl der Einheiten, um den oberen und unteren Rand deflate `CRect`.

*size*<br/>
Ein [Größe](https://msdn.microsoft.com/library/windows/desktop/dd145106) oder [CSize](csize-class.md) , angibt, dass die Anzahl der Einheiten, deflate `CRect`. Die `cx` Wert gibt die Anzahl der Einheiten, um den linken und rechten Seite deflate und `cy` Wert gibt die Anzahl der Einheiten, um den oberen und unteren deflate.

*lpRect*<br/>
Verweist auf eine [RECT](../../mfc/reference/rect-structure.md) Struktur oder `CRect` , der die Anzahl der Einheiten, um jede Seite deflate angibt.

*l*<br/>
Gibt die Anzahl der Einheiten, die auf der linken Seite des deflate `CRect`.

*t*<br/>
Gibt die Anzahl der Einheiten, um am Anfang deflate `CRect`.

*r*<br/>
Gibt die Anzahl der Einheiten, die auf der rechten Seite des deflate `CRect`.

*b*<br/>
Gibt die Anzahl der Einheiten, um am Ende deflate `CRect`.

### <a name="remarks"></a>Hinweise

Zu diesem Zweck `DeflateRect` linken und oberen Einheiten hinzugefügt und Einheiten aus dem rechten und unteren subtrahiert. Die Parameter der `DeflateRect` angemeldet sind Werte: positive Werte, die deflate `CRect` und es negative Werte vergrößert werden soll.

Die ersten beiden überladen deflate zwei Paare von gegenüberliegenden Seiten des `CRect` , damit die gesamte Breite von zwei Mal verringert wird *x* (oder `cx`) und die gesamte Höhe ist doppelt so groß wie gesunken *y* () oder `cy`). Die anderen zwei Überladungen deflate, jede Seite der `CRect` unabhängig von den anderen.

### <a name="example"></a>Beispiel

```cpp
   CRect rect(10, 10, 50, 50);
   rect.DeflateRect(1, 2);
   ASSERT(rect.left == 11 && rect.right == 49);
   ASSERT(rect.top == 12 && rect.bottom == 48);

   CRect rect2(10, 10, 50, 50);
   CRect rectDeflate(1, 2, 3, 4);
   rect2.DeflateRect(&rectDeflate);
   ASSERT(rect2.left == 11 && rect2.right == 47);
   ASSERT(rect2.top == 12 && rect2.bottom == 46);
```

##  <a name="equalrect"></a>  CRect::EqualRect

Bestimmt, ob `CRect` ist gleich einem angegebenen Rechteck.

```
BOOL EqualRect(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>Parameter

*lpRect*<br/>
Verweist auf eine [RECT](../../mfc/reference/rect-structure.md) Struktur oder `CRect` -Objekt, das die Koordinaten der oberen linken und rechten unteren Ecke eines Rechtecks enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die zwei Rechtecke der gleichen oben, links, unten und richtige Werte verfügen; andernfalls 0.

> [!NOTE]
>  Die Rechtecke müssen normalisiert werden, oder dieser Funktion kann fehlschlagen. Rufen Sie [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor Sie diese Funktion aufzurufen.

### <a name="example"></a>Beispiel

```cpp
   CRect rect1(35, 150, 10, 25);
   CRect rect2(35, 150, 10, 25);
   CRect rect3(98, 999, 6, 3);
ASSERT(rect1.EqualRect(rect2));
   ASSERT(!rect1.EqualRect(rect3));
// works just fine against RECTs, as well

RECT test;
test.left = 35;
test.top = 150;
test.right = 10;
test.bottom = 25;

ASSERT(rect1.EqualRect(&test));
```

##  <a name="height"></a>  CRect::Height

Berechnet die Höhe des `CRect` durch Subtrahieren der Höchstwert aus den unteren Wert.

```
int Height() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Höhe des `CRect`.

### <a name="remarks"></a>Hinweise

Der resultierende Wert kann negativ sein.

> [!NOTE]
>  Das Rechteck muss normalisiert werden, oder dieser Funktion kann fehlschlagen. Rufen Sie [NormalizeRect](#normalizerect) , das Rechteck zu normalisieren, bevor Sie diese Funktion aufzurufen.

### <a name="example"></a>Beispiel

```cpp
CRect rect(20, 30, 80, 70);
int nHt = rect.Height();

```cpp
   CRect rect(20, 30, 80, 70);
int nHt = rect.Height();

   // nHt is now 40
   ASSERT(nHt == 40);
```

##  <a name="inflaterect"></a>  CRect::InflateRect

`InflateRect` vergrößert `CRect` durch dessen Seiten von der Mitte verschieben.

```
void InflateRect(int x, int y) throw();
void InflateRect(SIZE size) throw();
void InflateRect(LPCRECT lpRect) throw();
void InflateRect(int l, int t, int r,  int b) throw();
```

### <a name="parameters"></a>Parameter

*w*<br/>
Gibt an, die Anzahl der Einheiten, um die Vergrößerung der linken und rechten Seite des Anwendungsfensters `CRect`.

*y*<br/>
Gibt die Anzahl der Einheiten, um den oberen und unteren Rand Vergrößerung `CRect`.

*size*<br/>
Ein [Größe](https://msdn.microsoft.com/library/windows/desktop/dd145106) oder [CSize](csize-class.md) , der angibt, dass der Anzahl der Einheiten, um die Vergrößerung `CRect`. Die `cx` Wert gibt die Anzahl der Einheiten, um den linken und rechten Seite vergrößert werden soll und die `cy` Wert gibt die Anzahl der Einheiten, um den oberen und unteren vergrößert werden soll.

*lpRect*<br/>
Verweist auf eine [RECT](../../mfc/reference/rect-structure.md) Struktur oder `CRect` , der angibt, dass der Anzahl der Einheiten, um jede Seite vergrößert werden soll.

*l*<br/>
Gibt die Anzahl der Einheiten, um die Vergrößerung der linken Seite des `CRect`.

*t*<br/>
Gibt die Anzahl der Einheiten, um am Anfang Vergrößerung `CRect`.

*r*<br/>
Gibt die Anzahl der Einheiten, um die Vergrößerung der rechten Seite des `CRect`.

*b*<br/>
Gibt die Anzahl der Einheiten, um die Vergrößerung Ende `CRect`.

### <a name="remarks"></a>Hinweise

Zu diesem Zweck `InflateRect` subtrahiert Einheiten vom linken und oberen und am rechten und unteren Einheiten hinzugefügt. Die Parameter der `InflateRect` signiert werden positive Werte Vergrößerung Werte `CRect` und negative Werte "Deflate" es.

Die ersten beiden überladen Vergrößerung zwei Paare von gegenüberliegenden Seiten des `CRect` , damit die gesamte Breite von zwei Mal erhöht wird *x* (oder `cx`) und die gesamte Höhe zweimal erhöht *y* () oder `cy`). Die anderen zwei Überladungen Vergrößerung jeder Seite der `CRect` unabhängig von den anderen.

### <a name="example"></a>Beispiel

```cpp
CRect rect(0, 0, 300, 300);
rect.InflateRect(50, 200);

// rect is now (-50, -200, 350, 500)
ASSERT(rect == CRect(-50, -200, 350, 500));
```

##  <a name="intersectrect"></a>  CRect::IntersectRect

Stellt eine `CRect` die Schnittmenge von zwei vorhandenen Rechtecke gleich.

```
BOOL IntersectRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>Parameter

*lpRect1*<br/>
Verweist auf eine [RECT](../../mfc/reference/rect-structure.md) Struktur oder `CRect` Objekt, das einem Quellrechteck enthält.

*lpRect2*<br/>
Verweist auf eine `RECT` Struktur oder `CRect` Objekt, das einem Quellrechteck enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Schnittmenge nicht leer ist; 0, wenn die Schnittmenge leer ist.

### <a name="remarks"></a>Hinweise

Die Schnittmenge ist das größte Rechteck, das in beiden vorhandenen Rechtecke enthalten sind.

> [!NOTE]
>  Die Rechtecke müssen normalisiert werden, oder dieser Funktion kann fehlschlagen. Rufen Sie [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor Sie diese Funktion aufzurufen.

### <a name="example"></a>Beispiel

```cpp
CRect rectOne(125, 0, 150, 200);
CRect rectTwo(0, 75, 350,  95);
CRect rectInter;

```cpp
   CRect rectOne(125,  0, 150, 200);
   CRect rectTwo(0, 75, 350, 95);
   CRect rectInter;

   rectInter.IntersectRect(rectOne, rectTwo);
ASSERT(rectInter == CRect(125, 75, 150, 95));
// operator &= can do the same task:

CRect rectInter2 = rectOne;
rectInter2 &= rectTwo;
ASSERT(rectInter2 == CRect(125, 75, 150, 95));
```

##  <a name="isrectempty"></a>  CRect::IsRectEmpty

Bestimmt, ob `CRect` ist leer.

```
BOOL IsRectEmpty() const throw();
```

### <a name="return-value"></a>Rückgabewert

Einen Wert ungleich NULL `CRect` leer ist; 0 Wenn `CRect` ist nicht leer.

### <a name="remarks"></a>Hinweise

Ein Rechteck ist leer, wenn die Breite bzw. Höhe 0 sind oder negativ sein. Unterscheidet sich von `IsRectNull`, der bestimmt, ob alle Koordinaten des Rechtecks auf 0 (null) sind.

> [!NOTE]
>  Das Rechteck muss normalisiert werden, oder dieser Funktion kann fehlschlagen. Rufen Sie [NormalizeRect](#normalizerect) , das Rechteck zu normalisieren, bevor Sie diese Funktion aufzurufen.

### <a name="example"></a>Beispiel

```cpp
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);

```cpp
   CRect rectNone(0, 0, 0, 0);
   CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectEmpty());
   ASSERT(!rectSome.IsRectEmpty());
CRect rectEmpty(35, 35, 35, 35);
   ASSERT(rectEmpty.IsRectEmpty());
```

##  <a name="isrectnull"></a>  CRect::IsRectNull

Bestimmt, ob es sich bei den oberen, linken nach unten, und Werte von rechten `CRect` sind alle gleich 0.

```
BOOL IsRectNull() const throw();
```

### <a name="return-value"></a>Rückgabewert

Einen Wert ungleich NULL `CRect`des oberen, linken, unteren und rechten Werte sind alle gleich 0, andernfalls 0.

### <a name="remarks"></a>Hinweise

Unterscheidet sich von `IsRectEmpty`, der bestimmt, ob das Rechteck leer ist.

### <a name="example"></a>Beispiel

```cpp
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);

```cpp
   CRect rectNone(0, 0, 0, 0);
   CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectNull());
   ASSERT(!rectSome.IsRectNull());
// note that null means _all_ zeros

CRect rectNotNull(0, 0, 35, 50);
ASSERT(!rectNotNull.IsRectNull());
```

##  <a name="movetox"></a>  CRect::MoveToX

Mit dieser Funktion können Sie das Rechteck verschieben, auf die absolute X-Koordinate gemäß *x*.

```
void MoveToX(int x) throw();
```

### <a name="parameters"></a>Parameter

*w*<br/>
Die absolute X-Koordinate für die linke obere Ecke des Rechtecks.

### <a name="example"></a>Beispiel

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToX(10);

```cpp
   CRect rect(0, 0, 100, 100);
rect.MoveToX(10);

   // rect is now (10, 0, 110, 100);
   ASSERT(rect == CRect(10, 0, 110, 100));
```

##  <a name="movetoxy"></a>  CRect::MoveToXY

Rufen Sie diese Funktion, um das Rechteck auf die absolute X - und y-Koordinaten angegeben zu verschieben.

```
void MoveToXY(int x, int y) throw();
void MoveToXY(POINT point) throw();
```

### <a name="parameters"></a>Parameter

*w*<br/>
Die absolute X-Koordinate für die linke obere Ecke des Rechtecks.

*y*<br/>
Die absolute y-Koordinate für die linke obere Ecke des Rechtecks.

*Zeigen Sie*<br/>
Ein `POINT` -Struktur, die die absolute linke obere Ecke des Rechtecks angibt.

### <a name="example"></a>Beispiel

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToXY(10, 10);

```cpp
   CRect rect(0, 0, 100, 100);
   rect.MoveToXY(10, 10);
// rect is now (10, 10, 110, 110);
   ASSERT(rect == CRect(10, 10, 110, 110));
```

##  <a name="movetoy"></a>  CRect::MoveToY

Mit dieser Funktion können Sie das Rechteck verschieben, auf die absolute y-Koordinate gemäß *y*.

```
void MoveToY(int y) throw();
```

### <a name="parameters"></a>Parameter

*y*<br/>
Die absolute y-Koordinate für die linke obere Ecke des Rechtecks.

### <a name="example"></a>Beispiel

```cpp
   CRect rect(0, 0, 100, 100);
   rect.MoveToY(10);
   // rect is now (0, 10, 100, 110);
   ASSERT(rect == CRect(0, 10, 100, 110));
```

##  <a name="normalizerect"></a>  CRect:: NormalizeRect

Normalisiert `CRect` , damit die Höhe und Breite nicht sicher sind.

```
void NormalizeRect() throw();
```

### <a name="remarks"></a>Hinweise

Das Rechteck wird zum vierten Quadranten zu positionieren, normalisiert die Windows in der Regel verwendet, für die Koordinaten. `NormalizeRect` Vergleicht die oberen und unteren Werte und tauscht diese, wenn oben im unteren Bereich größer ist. Auf ähnliche Weise vertauscht den linken und rechten Werte, wenn der linken Seite größer als der rechten Seite ist. Diese Funktion ist nützlich, beim Umgang mit anderen Zuordnungsmodi und Rechtecke umgekehrt.

> [!NOTE]
> Die folgenden `CRect` Memberfunktionen erfordern normalisierte Rechtecke, damit es einwandfrei funktioniert: [Höhe](#height), [Breite](#width), [Größe](#size), [ IsRectEmpty](#isrectempty), [PtInRect](#ptinrect), [EqualRect](#equalrect), [UnionRect](#unionrect), [IntersectRect](#intersectrect), [ SubtractRect](#subtractrect), [Operator ==](#operator_eq_eq), [Operator! =](#operator_neq), [Operator &#124; ](#operator_or), [Operator &#124;=](#operator_or_eq), [Operator &](#operator_amp), und [Operator & =](#operator_amp_eq).

### <a name="example"></a>Beispiel

```cpp
   CRect rect1(110, 100, 250, 310);
   CRect rect2(250, 310, 110, 100);
   rect1.NormalizeRect();
   rect2.NormalizeRect();
   ASSERT(rect1 == rect2);
```

##  <a name="offsetrect"></a>  CRect::OffsetRect

Verschiebt `CRect` durch die angegebenen Offsets.

```
void OffsetRect(int x, int y) throw();
void OffsetRect(POINT point) throw();
void OffsetRect(SIZE size) throw();
```

### <a name="parameters"></a>Parameter

*w*<br/>
Gibt die Menge, die zum Verschieben von links oder rechts. Sie müssen nach links verschieben negativ sein.

*y*<br/>
Gibt an, der Betrag, um nach oben oder unten zu verschieben. Es muss negativen nach oben zu verschieben.

*Zeigen Sie*<br/>
Enthält eine [Punkt](../../mfc/reference/point-structure.md) Struktur oder [CPoint](cpoint-class.md) Objekt, das beide Dimensionen, um die verschoben angibt.

*size*<br/>
Enthält eine [Größe](https://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder [CSize](csize-class.md) Objekt, das beide Dimensionen, um die verschoben angibt.

### <a name="remarks"></a>Hinweise

Verschiebt `CRect` *x* Einheiten entlang der x-Achse und *y* Einheiten entlang der y-Achse. Die *x* und *y* Parameter sind Werte mit Vorzeichen, also `CRect` können verschoben werden, nach links oder rechts oben oder unten.

### <a name="example"></a>Beispiel

```cpp
   CRect rect(0, 0, 35, 35);
   rect.OffsetRect(230, 230);

   // rect is now (230, 230, 265, 265)
   ASSERT(rect == CRect(230, 230, 265, 265));
```

##  <a name="operator_lpcrect"></a>  CRect::operator LPCRECT konvertiert eine `CRect` auf eine [LPCRECT](../../mfc/reference/data-types-mfc.md).

```
operator LPCRECT() const throw();
```

### <a name="remarks"></a>Hinweise

Wenn Sie diese Funktion verwenden, nicht erforderlich, dem Address-of (**&**) Operator. Dieser Operator wird automatisch verwendet, wenn Sie übergeben eine `CRect` Objekt, das eine Funktion, die erwartet, dass ein `LPCRECT`.

##  <a name="operator_lprect"></a>  CRect::operator LPRECT

Konvertiert eine `CRect` auf eine [LPRECT](../../mfc/reference/data-types-mfc.md).

```
operator LPRECT() throw();
```

### <a name="remarks"></a>Hinweise

Wenn Sie diese Funktion verwenden, nicht erforderlich, dem Address-of (**&**) Operator. Dieser Operator wird automatisch verwendet, wenn Sie übergeben eine `CRect` Objekt, das eine Funktion, die erwartet, dass ein `LPRECT`.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CRect::operator LPCRECT](#operator_lpcrect).

##  <a name="operator_eq"></a>  CRect::operator =

Weist *SrcRect* zu `CRect`.

```
void operator=(const RECT& srcRect) throw();
```

### <a name="parameters"></a>Parameter

*srcRect*<br/>
Bezieht sich auf einem Quellrechteck. Kann eine [RECT](../../mfc/reference/rect-structure.md) oder `CRect`.

### <a name="example"></a>Beispiel

```cpp
   CRect rect(0, 0, 127, 168);
   CRect rect2;

   rect2 = rect;
   ASSERT(rect2 == CRect(0, 0, 127, 168));
```

##  <a name="operator_eq_eq"></a>  CRect::operator ==

Bestimmt, ob `rect` gleich `CRect` durch Vergleichen die Koordinaten der linken, oberen und unteren rechten Ecke.

```
BOOL operator==(const RECT& rect) const throw();
```

### <a name="parameters"></a>Parameter

*Rect*<br/>
Bezieht sich auf einem Quellrechteck. Kann eine [RECT](../../mfc/reference/rect-structure.md) oder `CRect`.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn das Objekt gleich; andernfalls 0.

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Die Rechtecke müssen normalisiert werden, oder dieser Funktion kann fehlschlagen. Rufen Sie [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor Sie diese Funktion aufzurufen.

### <a name="example"></a>Beispiel

```cpp
CRect rect1(35, 150, 10, 25);
CRect rect2(35, 150, 10, 25);
CRect rect3(98, 999, 6, 3);
ASSERT(rect1 == rect2);
// works just fine against RECTs, as well

RECT test;
test.left = 35;
test.top = 150;
test.right = 10;
test.bottom = 25;

ASSERT(rect1 == test);
```

##  <a name="operator_neq"></a>  CRect::operator! =

Bestimmt, ob *Rect* ist nicht gleich `CRect` durch Vergleichen die Koordinaten der linken, oberen und unteren rechten Ecke.

```
BOOL operator!=(const RECT& rect) const throw();
```

### <a name="parameters"></a>Parameter

*Rect*<br/>
Bezieht sich auf einem Quellrechteck. Kann eine [RECT](../../mfc/reference/rect-structure.md) oder `CRect`.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn es nicht übereinstimmt; andernfalls 0.

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Die Rechtecke müssen normalisiert werden, oder dieser Funktion kann fehlschlagen. Rufen Sie [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor Sie diese Funktion aufzurufen.

### <a name="example"></a>Beispiel

```cpp
CRect rect1(35, 150, 10, 25);
CRect rect2(35, 150, 10, 25);
CRect rect3(98, 999,  6,  3);
ASSERT(rect1 != rect3);
// works just fine against RECTs, as well

RECT test;
test.left = 35;
test.top = 150;
test.right = 10;
test.bottom = 25;

ASSERT(rect3 != test);
```

##  <a name="operator_add_eq"></a>  CRect::operator +=

Verschieben Sie die ersten beiden überladen `CRect` durch die angegebenen Offsets.

```
void operator+=(POINT point) throw();
void operator+=(SIZE size) throw();
void operator+=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>Parameter

*Zeigen Sie*<br/>
Ein [Punkt](../../mfc/reference/point-structure.md) Struktur oder [CPoint](cpoint-class.md) Objekt, das die Anzahl der Einheiten, um das Rechteck verschieben angibt.

*size*<br/>
Ein [Größe](https://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder [CSize](csize-class.md) Objekt, das die Anzahl der Einheiten, um das Rechteck verschieben angibt.

*lpRect*<br/>
Verweist auf eine [RECT](../../mfc/reference/rect-structure.md) Struktur oder `CRect` -Objekt, das die Anzahl der Einheiten, um jede Seite der Vergrößerung enthält `CRect`.

### <a name="remarks"></a>Hinweise

Des Parameters des *x* und *y* (oder `cx` und `cy`) Werte hinzugefügt, `CRect`.

Die dritte Überladung vergrößert `CRect` durch die Anzahl der Einheiten, die im jeden Member des-Parameters angegeben.

### <a name="example"></a>Beispiel

```cpp
   CRect   rect1(100, 235, 200, 335);
   CPoint  pt(35, 65);
   CRect   rect2(135, 300, 235, 400);

   rect1 += pt;
   ASSERT(rect1 == rect2);
```

##  <a name="operator_-_eq"></a>  CRect::operator =

Verschieben Sie die ersten beiden überladen `CRect` durch die angegebenen Offsets.

```
void operator-=(POINT point) throw();
void operator-=(SIZE size) throw();
void operator-=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>Parameter

*Zeigen Sie*<br/>
Ein [Punkt](../../mfc/reference/point-structure.md) Struktur oder [CPoint](cpoint-class.md) Objekt, das die Anzahl der Einheiten, um das Rechteck verschieben angibt.

*size*<br/>
Ein [Größe](https://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder [CSize](csize-class.md) Objekt, das die Anzahl der Einheiten, um das Rechteck verschieben angibt.

*lpRect*<br/>
Verweist auf eine [RECT](../../mfc/reference/rect-structure.md) Struktur oder `CRect` -Objekt, das die Anzahl der Einheiten, um jede Seite der deflate enthält `CRect`.

### <a name="remarks"></a>Hinweise

Des Parameters des *x* und *y* (oder `cx` und `cy`) Werten subtrahiert werden `CRect`.

Die dritte Überladung entleert `CRect` durch die Anzahl der Einheiten, die im jeden Member des-Parameters angegeben. Beachten Sie, die diese Überladung wie Funktionen [DeflateRect](#deflaterect).

### <a name="example"></a>Beispiel

```cpp
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);

   rect1 -= pt;
   CRect   rectResult(65, 170, 165, 270);
   ASSERT(rect1 == rectResult);
```

##  <a name="operator_amp_eq"></a>  CRect::operator &amp;=

Legt `CRect` gleich für die Schnittmenge der `CRect` und `rect`.

```
void operator&=(const RECT& rect) throw();
```

### <a name="parameters"></a>Parameter

*Rect*<br/>
Enthält eine [RECT](../../mfc/reference/rect-structure.md) oder `CRect`.

### <a name="remarks"></a>Hinweise

Die Schnittmenge ist das größte Rechteck, das in beiden Rechtecke enthalten ist.

> [!NOTE]
>  Die Rechtecke müssen normalisiert werden, oder dieser Funktion kann fehlschlagen. Rufen Sie [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor Sie diese Funktion aufzurufen.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CRect::IntersectRect](#intersectrect).

##  <a name="operator_or_eq"></a>  CRect::operator &#124;=

Legt `CRect` bezüglich ihrer Gesamtmenge gleich `CRect` und `rect`.

```
void operator|=(const RECT& rect) throw();
```

### <a name="parameters"></a>Parameter

*Rect*<br/>
Enthält eine `CRect` oder [RECT](../../mfc/reference/rect-structure.md).

### <a name="remarks"></a>Hinweise

Die Union ist das kleinste Rechteck befindet, das beide Rechtecke für die Datenquelle enthält.

> [!NOTE]
>  Die Rechtecke müssen normalisiert werden, oder dieser Funktion kann fehlschlagen. Rufen Sie [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor Sie diese Funktion aufzurufen.

### <a name="example"></a>Beispiel

```cpp
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);

   rect1 |= rect2;
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect1);
```

##  <a name="operator_add"></a>  CRect::operator +

Die ersten beiden überladen Zurückgeben einer `CRect` -Objekt, das gleich ist `CRect` verschoben werden, indem die angegebenen Offsets.

```
CRect operator+(POINT point) const throw();
CRect operator+(LPCRECT lpRect) const throw();
CRect operator+(SIZE size) const throw();
```

### <a name="parameters"></a>Parameter

*Zeigen Sie*<br/>
Ein [Punkt](../../mfc/reference/point-structure.md) Struktur oder [CPoint](cpoint-class.md) Objekt, das die Anzahl der Einheiten, verschieben Sie den Rückgabewert angibt.

*size*<br/>
Ein [Größe](https://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder [CSize](csize-class.md) Objekt, das die Anzahl der Einheiten, verschieben Sie den Rückgabewert angibt.

*lpRect*<br/>
Verweist auf eine [RECT](../../mfc/reference/rect-structure.md) Struktur oder `CRect` -Objekt, die Anzahl der Einheiten enthält, um jede Seite des Rückgabewerts vergrößert werden soll.

### <a name="return-value"></a>Rückgabewert

Die `CRect` verschieben bzw. jedoch `CRect` durch die Anzahl der Einheiten, die im Parameter angegeben.

### <a name="remarks"></a>Hinweise

Des Parameters des *x* und *y* (oder `cx` und `cy`) Parameter hinzugefügt werden `CRect`des positionieren.

Die dritte Überladung gibt eine neue `CRect` gleich `CRect` aufgeblasen wird durch die Anzahl der Einheiten, die im jeden Member des-Parameters angegeben.

### <a name="example"></a>Beispiel

```cpp
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);
   CRect   rect2;

   rect2 = rect1 + pt;
   CRect   rectResult(135, 300, 235, 400);
   ASSERT(rectResult == rect2);
```

##  <a name="operator_-"></a>  CRect::operator-

Die ersten beiden überladen Zurückgeben einer `CRect` -Objekt, das gleich ist `CRect` verschoben werden, indem die angegebenen Offsets.

```
CRect operator-(POINT point) const throw();
CRect operator-(SIZE size) const throw();
CRect operator-(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>Parameter

*Zeigen Sie*<br/>
Ein [Punkt](../../mfc/reference/point-structure.md) Struktur oder `CPoint` Objekt, das die Anzahl der Einheiten, verschieben Sie den Rückgabewert angibt.

*size*<br/>
Ein [Größe](https://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder `CSize` Objekt, das die Anzahl der Einheiten, verschieben Sie den Rückgabewert angibt.

*lpRect*<br/>
Verweist auf eine [RECT](../../mfc/reference/rect-structure.md) Struktur oder `CRect` -Objekt, das die Anzahl der Einheiten, um jede Seite des Rückgabewerts deflate enthält.

### <a name="return-value"></a>Rückgabewert

Die `CRect` verschieben bzw. Entleeren `CRect` durch die Anzahl der Einheiten, die im Parameter angegeben.

### <a name="remarks"></a>Hinweise

Des Parameters des *x* und *y* (oder `cx` und `cy`) Parameter subtrahiert werden `CRect`der position.

Die dritte Überladung gibt eine neue `CRect` gleich `CRect` verkleinert werden, um die Anzahl der Einheiten, die im jeden Member des-Parameters angegeben. Beachten Sie, die diese Überladung wie Funktionen [DeflateRect](#deflaterect), nicht [SubtractRect](#subtractrect).

### <a name="example"></a>Beispiel

```cpp
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);
   CRect   rect2;

   rect2 = rect1 - pt;
   CRect   rectResult(65, 170, 165, 270);
   ASSERT(rect2 == rectResult);
```

##  <a name="operator_amp"></a>  CRect::operator &amp;

Gibt eine `CRect` d. h. die Schnittmenge der `CRect` und *rect2*.

```
CRect operator&(const RECT& rect2) const throw();
```

### <a name="parameters"></a>Parameter

*rect2*<br/>
Enthält eine [RECT](../../mfc/reference/rect-structure.md) oder `CRect`.

### <a name="return-value"></a>Rückgabewert

Ein `CRect` d. h. die Schnittmenge der `CRect` und *rect2*.

### <a name="remarks"></a>Hinweise

Die Schnittmenge ist das größte Rechteck, das in beiden Rechtecke enthalten ist.

> [!NOTE]
>  Die Rechtecke müssen normalisiert werden, oder dieser Funktion kann fehlschlagen. Rufen Sie [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor Sie diese Funktion aufzurufen.

### <a name="example"></a>Beispiel

```cpp
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3 = rect1 & rect2;
   CRect   rectResult(100, 100, 200, 200);
   ASSERT(rectResult == rect3);
```

##  <a name="operator_or"></a>  CRect::operator&#124;

Gibt eine `CRect` , die Union der `CRect` und *rect2*.

```
CRect operator|(const RECT&
rect2) const throw();
```

### <a name="parameters"></a>Parameter

*rect2*<br/>
Enthält eine [RECT](../../mfc/reference/rect-structure.md) oder `CRect`.

### <a name="return-value"></a>Rückgabewert

Ein `CRect` , die Union der `CRect` und *rect2*.

### <a name="remarks"></a>Hinweise

Die Union ist das kleinste Rechteck befindet, das beide Rechtecke enthält.

> [!NOTE]
>  Die Rechtecke müssen normalisiert werden, oder dieser Funktion kann fehlschlagen. Rufen Sie [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor Sie diese Funktion aufzurufen.

### <a name="example"></a>Beispiel

```cpp
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3 = rect1 | rect2;
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect3);
```

##  <a name="ptinrect"></a>  CRect::PtInRect

Bestimmt, ob der angegebene Punkt innerhalb liegt `CRect`.

```
BOOL PtInRect(POINT point) const throw();
```

### <a name="parameters"></a>Parameter

*Zeigen Sie*<br/>
Enthält eine [Punkt](../../mfc/reference/point-structure.md) Struktur oder [CPoint](cpoint-class.md) Objekt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Punkt in liegt `CRect`, andernfalls 0.

### <a name="remarks"></a>Hinweise

Ein Punkt ist in `CRect` bei auf der linken oder oberen Seite liegt oder in allen vier Seiten. Ein Punkt auf der rechten oder unteren Seite befindet sich außerhalb `CRect`.

> [!NOTE]
>  Das Rechteck muss normalisiert werden, oder dieser Funktion kann fehlschlagen. Rufen Sie [NormalizeRect](#normalizerect) , das Rechteck zu normalisieren, bevor Sie diese Funktion aufzurufen.

### <a name="example"></a>Beispiel

```cpp
CRect rect(5, 5, 100, 100);
CPoint pt1(35, 50);
CPoint pt2(125, 298);

// this is true, because pt1 is inside the rectangle
ASSERT(rect.PtInRect(pt1));

// this is NOT true, because pt2 is outside the rectangle
ASSERT(!rect.PtInRect(pt2));

// note that the right and the bottom aren't inside
ASSERT(!rect.PtInRect(CPoint(35, 100)));
ASSERT(!rect.PtInRect(CPoint(100, 98)));

// but the top and the left are inside
ASSERT(rect.PtInRect(CPoint(5, 65)));
ASSERT(rect.PtInRect(CPoint(88, 5)));

// and that PtInRect() works against a POINT, too
POINT pt;
pt.x = 35;
pt.y = 50;
ASSERT(rect.PtInRect(pt));
```

##  <a name="setrect"></a>  CRect::SetRect

Gibt die Abmessungen des `CRect` an die angegebenen Koordinaten.

```
void SetRect(int x1, int y1, int x2, int y2) throw();
```

### <a name="parameters"></a>Parameter

*x1*<br/>
Gibt die X-Koordinate der oberen linken Ecke an.

*y1*<br/>
Gibt die y-Koordinate der oberen linken Ecke an.

*x2*<br/>
Gibt die X-Koordinate der unteren rechten Ecke.

*Y2*<br/>
Gibt die y-Koordinate der unteren rechten Ecke.

### <a name="example"></a>Beispiel

```cpp
   CRect rect;
   rect.SetRect(256, 256, 512, 512);
   ASSERT(rect == CRect(256, 256, 512, 512));
```

##  <a name="setrectempty"></a>  CRect::SetRectEmpty

Macht `CRect` ein Rechteck null, indem Sie alle Koordinaten auf 0 (null) festlegen.

```
void SetRectEmpty() throw();
```

### <a name="example"></a>Beispiel

```cpp
CRect rect;
rect.SetRectEmpty();

// rect is now (0, 0, 0, 0)
ASSERT(rect.IsRectEmpty());
```

##  <a name="size"></a>  CRect::SIZE

Die `cx` und `cy` Mitglieder der zurückgegebene Wert enthalten, die Höhe und Breite des `CRect`.

```
CSize Size() const throw();
```

### <a name="return-value"></a>Rückgabewert

Ein [CSize](csize-class.md) Objekt, das die Größe des enthält `CRect`.

### <a name="remarks"></a>Hinweise

Entweder die Höhe oder Breite kann negativ sein.

> [!NOTE]
>  Das Rechteck muss normalisiert werden, oder dieser Funktion kann fehlschlagen. Rufen Sie [NormalizeRect](#normalizerect) , das Rechteck zu normalisieren, bevor Sie diese Funktion aufzurufen.

### <a name="example"></a>Beispiel

```cpp
CRect rect(10, 10, 50, 50);
CSize sz = rect.Size();
ASSERT(sz.cx == 40 && sz.cy == 40);
```

##  <a name="subtractrect"></a>  CRect::SubtractRect

Stellt die Abmessungen des der `CRect` gleich bei die Subtraktion von `lpRectSrc2` aus `lpRectSrc1`.

```
BOOL SubtractRect(LPCRECT lpRectSrc1, LPCRECT lpRectSrc2) throw();
```

### <a name="parameters"></a>Parameter

*lpRectSrc1*<br/>
Verweist auf die [RECT](../../mfc/reference/rect-structure.md) Struktur oder `CRect` Objekt, von dem ein Rechteck subtrahiert werden soll.

*lpRectSrc2*<br/>
Verweist auf die `RECT` Struktur oder `CRect` -Objekt, das auf das Rechteck subtrahiert werden auf die von der *lpRectSrc1* Parameter.

### <a name="return-value"></a>Rückgabewert

Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).

### <a name="remarks"></a>Hinweise

Die Subtraktion ist das kleinste Rechteck, das alle Punkte im enthält *lpRectScr1* , die sich nicht in der Schnittmenge von *lpRectScr1* und *lpRectScr2*.

Anhand des Rechtecks *lpRectSrc1* ist, nicht geändert, wenn das Rechteck angegeben *lpRectSrc2* nicht vollständig anhand des Rechtecks überschneiden *lpRectSrc1*in mindestens einem von der X - oder y-Richtung.

Z. B. wenn *lpRectSrc1* wurden (10,10, 100,100) und *lpRectSrc2* wurden (50,50, 150,150) des Rechtecks zeigt *lpRectSrc1* wäre unverändert sein, wenn die die Funktion zurückgegeben wird. Wenn *lpRectSrc1* wurden (10,10, 100,100) und *lpRectSrc2* wurden (50,10, 150,150), jedoch das Rechteck verweist *lpRectSrc1* enthält die Koordinaten (10,10, Punkt 50,100) Wenn die Funktion zurückgegeben.

`SubtractRect` entspricht nicht der [Operator -](#operator_-) noch [Operator-=](#operator_-_eq). Keines dieser Operatoren jemals ruft `SubtractRect`.

> [!NOTE]
>  Die Rechtecke müssen normalisiert werden, oder dieser Funktion kann fehlschlagen. Rufen Sie [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor Sie diese Funktion aufzurufen.

### <a name="example"></a>Beispiel

```cpp
   RECT   rectOne;
   RECT   rectTwo;

   rectOne.left = 10;
   rectOne.top = 10;
   rectOne.bottom = 100;
   rectOne.right = 100;

   rectTwo.left = 50;
   rectTwo.top = 10;
   rectTwo.bottom = 150;
   rectTwo.right = 150;

   CRect   rectDiff;

   rectDiff.SubtractRect(&rectOne, &rectTwo);
CRect   rectResult(10, 10, 50, 100);

   ASSERT(rectDiff == rectResult);

   // works for CRect, too, since there is
   // implicit CRect -> LPCRECT conversion

   CRect rect1(10, 10, 100, 100);
   CRect rect2(50, 10, 150, 150);
   CRect rectOut;

   rectOut.SubtractRect(rect1, rect2);
   ASSERT(rectResult == rectOut);
```

##  <a name="topleft"></a>  CRect::TopLeft

Die Koordinaten werden zurückgegeben, als Verweis auf eine [CPoint](cpoint-class.md) in enthaltene Objekt `CRect`.

```
CPoint& TopLeft() throw();
const CPoint& TopLeft() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Koordinaten der die linke obere Ecke des Rechtecks.

### <a name="remarks"></a>Hinweise

Sie können diese Funktion verwenden, zum Abrufen oder Festlegen der oberen linken Ecke des Rechtecks. Legen Sie die Ecke mit dieser Funktion auf der linken Seite des Zuweisungsoperators.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CRect::CenterPoint](#centerpoint).

##  <a name="unionrect"></a>  CRect::UnionRect

Stellt die Abmessungen des `CRect` die Union der beiden Rechtecke gleich.

```
BOOL UnionRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>Parameter

*lpRect1*<br/>
Verweist auf eine [RECT](../../mfc/reference/rect-structure.md) oder `CRect` , die einem Quellrechteck enthält.

*lpRect2*<br/>
Verweist auf eine `RECT` oder `CRect` , die einem Quellrechteck enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Union nicht leer ist; 0, wenn die Union leer ist.

### <a name="remarks"></a>Hinweise

Die Union ist das kleinste Rechteck befindet, das beide Rechtecke für die Datenquelle enthält.

Windows ignoriert die Abmessungen des ein leeres Rechteck. d. h. ein Rechteck, das keine Höhe hat oder keine Breite.

> [!NOTE]
>  Die Rechtecke müssen normalisiert werden, oder dieser Funktion kann fehlschlagen. Rufen Sie [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor Sie diese Funktion aufzurufen.

### <a name="example"></a>Beispiel

```cpp
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3.UnionRect(&rect1, &rect2);
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect3);
```

##  <a name="width"></a>  CRect::Width

Berechnet die Breite des `CRect` durch Subtrahieren den linken Wert aus den richtigen Wert.

```
int Width() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Breite des `CRect`.

### <a name="remarks"></a>Hinweise

Die Breite kann negativ sein.

> [!NOTE]
>  Das Rechteck muss normalisiert werden, oder dieser Funktion kann fehlschlagen. Rufen Sie [NormalizeRect](#normalizerect) , das Rechteck zu normalisieren, bevor Sie diese Funktion aufzurufen.

### <a name="example"></a>Beispiel

```cpp
   CRect rect(20, 30, 80, 70);
   int nWid = rect.Width();
   // nWid is now 60
   ASSERT(nWid == 60);
```

## <a name="see-also"></a>Siehe auch

[CPoint-Klasse](cpoint-class.md)<br/>
[CSize-Klasse](csize-class.md)<br/>
[RECT](../../mfc/reference/rect-structure.md)

