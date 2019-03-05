---
title: CRgn-Klasse
ms.date: 11/04/2016
f1_keywords:
- CRgn
- AFXWIN/CRgn
- AFXWIN/CRgn::CRgn
- AFXWIN/CRgn::CombineRgn
- AFXWIN/CRgn::CopyRgn
- AFXWIN/CRgn::CreateEllipticRgn
- AFXWIN/CRgn::CreateEllipticRgnIndirect
- AFXWIN/CRgn::CreateFromData
- AFXWIN/CRgn::CreateFromPath
- AFXWIN/CRgn::CreatePolygonRgn
- AFXWIN/CRgn::CreatePolyPolygonRgn
- AFXWIN/CRgn::CreateRectRgn
- AFXWIN/CRgn::CreateRectRgnIndirect
- AFXWIN/CRgn::CreateRoundRectRgn
- AFXWIN/CRgn::EqualRgn
- AFXWIN/CRgn::FromHandle
- AFXWIN/CRgn::GetRegionData
- AFXWIN/CRgn::GetRgnBox
- AFXWIN/CRgn::OffsetRgn
- AFXWIN/CRgn::PtInRegion
- AFXWIN/CRgn::RectInRegion
- AFXWIN/CRgn::SetRectRgn
helpviewer_keywords:
- CRgn [MFC], CRgn
- CRgn [MFC], CombineRgn
- CRgn [MFC], CopyRgn
- CRgn [MFC], CreateEllipticRgn
- CRgn [MFC], CreateEllipticRgnIndirect
- CRgn [MFC], CreateFromData
- CRgn [MFC], CreateFromPath
- CRgn [MFC], CreatePolygonRgn
- CRgn [MFC], CreatePolyPolygonRgn
- CRgn [MFC], CreateRectRgn
- CRgn [MFC], CreateRectRgnIndirect
- CRgn [MFC], CreateRoundRectRgn
- CRgn [MFC], EqualRgn
- CRgn [MFC], FromHandle
- CRgn [MFC], GetRegionData
- CRgn [MFC], GetRgnBox
- CRgn [MFC], OffsetRgn
- CRgn [MFC], PtInRegion
- CRgn [MFC], RectInRegion
- CRgn [MFC], SetRectRgn
ms.assetid: d904da84-76aa-481e-8780-b09485f49e64
ms.openlocfilehash: 54018c3d59fe3d7e3d7a5062cda9b40da4f5d586
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57279363"
---
# <a name="crgn-class"></a>CRgn-Klasse

Kapselt einen Bereich der Windows GDI (Graphics Device Interface).

## <a name="syntax"></a>Syntax

```
class CRgn : public CGdiObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CRgn::CRgn](#crgn)|Erstellt ein `CRgn`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CRgn::CombineRgn](#combinergn)|Legt eine `CRgn` Objekts, sodass es die Union von zwei angegebenen entspricht `CRgn` Objekte.|
|[CRgn::CopyRgn](#copyrgn)|Legt eine `CRgn` Objekts, sodass es sich um eine Kopie einer angegebenen ist `CRgn` Objekt.|
|[CRgn::CreateEllipticRgn](#createellipticrgn)|Initialisiert eine `CRgn` Objekt mit einer elliptischen Region.|
|[CRgn::CreateEllipticRgnIndirect](#createellipticrgnindirect)|Initialisiert eine `CRgn` Objekt mit einer elliptischen Bereichs, der durch eine [RECT](/windows/desktop/api/windef/ns-windef-tagrect) Struktur.|
|[CRgn::CreateFromData](#createfromdata)|Erstellt einen Bereich aus der angegebenen Region und die Transformation Daten an.|
|[CRgn::CreateFromPath](#createfrompath)|Erstellt einen Bereich aus dem Pfad, der für den angegebenen Gerätekontext ausgewählt ist.|
|[CRgn::CreatePolygonRgn](#createpolygonrgn)|Initialisiert eine `CRgn` Objekt mit einer polygonalen Region. Das System des Polygons wird automatisch geschlossen, falls erforderlich, durch eine Linie zwischen dem letzten Scheitelpunkt mit dem ersten.|
|[CRgn::CreatePolyPolygonRgn](#createpolypolygonrgn)|Initialisiert eine `CRgn` Objekt mit einer Region mit einer Reihe von geschlossenen Polygonen. Die Polygone zusammenhanglosen werden, oder sie möglicherweise überlappen.|
|[CRgn::CreateRectRgn](#createrectrgn)|Initialisiert eine `CRgn` Objekt mit einem rechteckigen Bereich.|
|[CRgn::CreateRectRgnIndirect](#createrectrgnindirect)|Initialisiert eine `CRgn` Objekt mit einer rechteckigen Bereichs, der durch eine [RECT](/windows/desktop/api/windef/ns-windef-tagrect) Struktur.|
|[CRgn::CreateRoundRectRgn](#createroundrectrgn)|Initialisiert eine `CRgn` Objekt mit einem rechteckigen Bereich mit abgerundeten Ecken.|
|[CRgn::EqualRgn](#equalrgn)|Überprüft zwei `CRgn` Objekte zu bestimmen, ob sie gleich sind.|
|[CRgn::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CRgn` Objekt, wenn ein Handle zu einer Windows-Region zu erhalten.|
|[CRgn::GetRegionData](#getregiondata)|Füllt den angegebenen Puffer mit Daten, das den angegebenen Bereich beschreibt.|
|[CRgn::GetRgnBox](#getrgnbox)|Ruft die Koordinaten des umgebenden Rechtecks des ab einem `CRgn` Objekt.|
|[CRgn::OffsetRgn](#offsetrgn)|Verschiebt eine `CRgn` Objekt, indem die angegebenen Offsets.|
|[CRgn::PtInRegion](#ptinregion)|Bestimmt, ob ein angegebene Punkt befindet sich in der Region.|
|[CRgn::RectInRegion](#rectinregion)|Bestimmt, ob ein Teil einem angegebenen Rechteck innerhalb der Grenzen des Bereichs.|
|[CRgn::SetRectRgn](#setrectrgn)|Legt die `CRgn` Objekt in den angegebenen rechteckige Bereich.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CRgn::operator HRGN](#operator_hrgn)|Gibt zurück, das Windows-Handle, das innerhalb der `CRgn` Objekt.|

## <a name="remarks"></a>Hinweise

Ein Bereich ist ein elliptischen oder polygonalen Bereich innerhalb eines Fensters. Um Bereiche zu verwenden, verwenden Sie die Memberfunktionen der Klasse `CRgn` mit den Clipping-Funktionen, die als Member der Klasse definiert `CDC`.

Die Memberfunktionen der `CRgn` erstellen, ändern und Abrufen von Informationen über das Region-Objekt, das für die sie aufgerufen werden.

Weitere Informationen zur Verwendung von `CRgn`, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CRgn`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="combinergn"></a>  CRgn::CombineRgn

Erstellt eine neue GDI-Region durch die Kombination von zwei vorhandener Regions an.

```
int CombineRgn(
    CRgn* pRgn1,
    CRgn* pRgn2,
    int nCombineMode);
```

### <a name="parameters"></a>Parameter

*pRgn1*<br/>
Identifiziert eine vorhandene Region an.

*pRgn2*<br/>
Identifiziert eine vorhandene Region an.

*nCombineMode*<br/>
Gibt den Vorgang ausgeführt werden, wenn die beiden Regionen kombiniert. Eine der folgenden Werte sind möglich:

- RGN_AND verwendet überlappende Bereiche der beiden Regionen (Schnittmenge).

- RGN_COPY erstellt eine Kopie des Region-1 (identifizierte *pRgn1*).

- RGN_DIFF erstellt einen Bereich, der aus den Bereichen des Bereichs von 1 (identifizierte *pRgn1*), sind nicht Teil von Region-2 (identifizierte *pRgn2*).

- RGN_OR kombiniert die beiden Regionen in ihrer Gesamtheit (Union).

- RGN_XOR entfernt von überlappenden Bereiche jedoch beide Regionen kombiniert.

### <a name="return-value"></a>Rückgabewert

Gibt den Typ der resultierenden Region. Es kann eine der folgenden Werte sein:

- Neue COMPLEXREGION Region hat überlappende Grenzen.

- Fehler, die keine neue Region erstellt werden.

- Neue NULLREGION Region ist leer.

- Neue SIMPLEREGION Region verfügt über keine überlappenden Rahmen.

### <a name="remarks"></a>Hinweise

Die Bereiche kombiniert werden nach den Angaben von *nCombineMode*.

Die beiden angegebenen Bereiche werden kombiniert, und das resultierende Handle für die Region befindet sich in der `CRgn` Objekt. Daher alle Region gespeichert ist, in der `CRgn` Objekt wird durch den kombinierten Bereich ersetzt.

Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB an Arbeitsspeicher begrenzt, welcher Wert kleiner ist.

Verwendung [CopyRgn](#copyrgn) , eine Region in einer anderen Region zu kopieren.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#144](../../mfc/codesnippet/cpp/crgn-class_1.cpp)]

##  <a name="copyrgn"></a>  CRgn::CopyRgn

Kopiert von definierten Bereichs *pRgnSrc* in die `CRgn` Objekt.

```
int CopyRgn(CRgn* pRgnSrc);
```

### <a name="parameters"></a>Parameter

*pRgnSrc*<br/>
Identifiziert eine vorhandene Region an.

### <a name="return-value"></a>Rückgabewert

Gibt den Typ der resultierenden Region. Es kann eine der folgenden Werte sein:

- Neue COMPLEXREGION Region hat überlappende Grenzen.

- Fehler, die keine neue Region erstellt werden.

- Neue NULLREGION Region ist leer.

- Neue SIMPLEREGION Region verfügt über keine überlappenden Rahmen.

### <a name="remarks"></a>Hinweise

Die neue Region ersetzt die Region, die früher gespeichert, der `CRgn` Objekt. Diese Funktion ist ein Sonderfall der [CombineRgn](#combinergn) Member-Funktion.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CRgn::CreateEllipticRgn](#createellipticrgn).

##  <a name="createellipticrgn"></a>  CRgn::CreateEllipticRgn

Erstellt einen elliptischen Bereich an.

```
BOOL CreateEllipticRgn(
    int x1,
    int y1,
    int x2,
    int y2);
```

### <a name="parameters"></a>Parameter

*x1*<br/>
Gibt die logische X-Koordinate der oberen linken Ecke des umschließenden Rechtecks der Ellipse an.

*y1*<br/>
Gibt die logische y-Koordinate der oberen linken Ecke des umschließenden Rechtecks der Ellipse an.

*x2*<br/>
Gibt die logische X-Koordinate der unteren rechten Ecke des umschließenden Rechtecks der Ellipse an.

*y2*<br/>
Gibt die logische y-Koordinate der unteren rechten Ecke des umschließenden Rechtecks der Ellipse an.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Region wird definiert, indem das umschließende Rechteck gemäß *X1*, *y1*, *X2*, und *y2*. Die Region befindet sich in der `CRgn` Objekt.

Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB an Arbeitsspeicher begrenzt, welcher Wert kleiner ist.

Wenn er abgeschlossen wurde, mit einer Region erstellt, mit der `CreateEllipticRgn` -Funktion, eine Anwendung sollte wählen Sie die Region, den Gerätekontext und die Verwendung der `DeleteObject` Funktion, um ihn zu entfernen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#145](../../mfc/codesnippet/cpp/crgn-class_2.cpp)]

##  <a name="createellipticrgnindirect"></a>  CRgn::CreateEllipticRgnIndirect

Erstellt einen elliptischen Bereich an.

```
BOOL CreateEllipticRgnIndirect(LPCRECT lpRect);
```

### <a name="parameters"></a>Parameter

*lpRect*<br/>
Verweist auf eine `RECT` Struktur oder ein `CRect` Objekt, das die logischen Koordinaten der oberen linken und rechten unteren Ecke des umschließenden Rechtecks der Ellipse enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Region wird durch die Struktur oder das Objekt definiert *LpRect* und befindet sich in der `CRgn` Objekt.

Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB an Arbeitsspeicher begrenzt, welcher Wert kleiner ist.

Wenn er abgeschlossen wurde, mit einer Region erstellt, mit der `CreateEllipticRgnIndirect` -Funktion, eine Anwendung sollte wählen Sie die Region, den Gerätekontext und die Verwendung der `DeleteObject` Funktion, um ihn zu entfernen.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CRgn::CreateRectRgnIndirect](#createrectrgnindirect).

##  <a name="createfromdata"></a>  CRgn::CreateFromData

Erstellt einen Bereich aus der angegebenen Region und die Transformation Daten an.

```
BOOL CreateFromData(
    const XFORM* lpXForm,
    int nCount,
    const RGNDATA* pRgnData);
```

### <a name="parameters"></a>Parameter

*lpXForm*<br/>
Verweist auf eine [XFORM](/windows/desktop/api/wingdi/ns-wingdi-tagxform) -Datenstruktur, die die Transformation definiert, in der Region ausgeführt werden soll. Wenn dieser Zeiger NULL ist, wird die Identitätstransformation verwendet.

*nCount*<br/>
Gibt die Anzahl der Bytes, die auf den von *pRgnData*.

*pRgnData*<br/>
Verweist auf eine [RGNDATA](/windows/desktop/api/wingdi/ns-wingdi-_rgndata) -Datenstruktur, die Daten für die Region enthält.

### <a name="return-value"></a>Rückgabewert

Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).

### <a name="remarks"></a>Hinweise

Eine Anwendung kann Daten für einen Bereich abrufen, durch den Aufruf der `CRgn::GetRegionData` Funktion.

##  <a name="createfrompath"></a>  CRgn::CreateFromPath

Erstellt einen Bereich aus dem Pfad, der für den angegebenen Gerätekontext ausgewählt ist.

```
BOOL CreateFromPath(CDC* pDC);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Gibt einen Gerätekontext, der einen geschlossenen Pfad enthält.

### <a name="return-value"></a>Rückgabewert

Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).

### <a name="remarks"></a>Hinweise

Der Gerätekontext, die durch identifiziert die *pDC* Parameter muss einen geschlossenen Pfad enthalten. Nach dem `CreateFromPath` konvertiert einen Pfad in einer Region, Windows, verwirft den geschlossenen Pfad aus dem Gerätekontext.

##  <a name="createpolygonrgn"></a>  CRgn::CreatePolygonRgn

Erstellt eine polygonale Region an.

```
BOOL CreatePolygonRgn(
    LPPOINT lpPoints,
    int nCount,
    int nMode);
```

### <a name="parameters"></a>Parameter

*lpPoints*<br/>
Verweist auf ein Array von `POINT` Strukturen oder ein Array von `CPoint` Objekte. Jede Struktur gibt an, die X-Koordinate und y-Koordinate eines scheitels des Polygons. Die `POINT` Struktur weist folgende Form:

```cpp
typedef struct tagPOINT {
    int x;
    int y;
} POINT;
```

*nCount*<br/>
Gibt die Anzahl der `POINT` Strukturen oder `CPoint` Objekte im Array zeigt *LpPoints*.

*nMode*<br/>
Gibt den Füllmodus für die Region an. Dieser Parameter kann entweder alternative oder WICKELN sein.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Das System des Polygons wird automatisch geschlossen, falls erforderlich, durch eine Linie zwischen dem letzten Scheitelpunkt mit dem ersten. Der resultierende Bereich befindet sich in der `CRgn` Objekt.

Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB an Arbeitsspeicher begrenzt, welcher Wert kleiner ist.

Wenn der Modus für die Polygon-füllen-Alternative ist, füllt das System den Bereich zwischen ungerade und geradzahlige Polygonseiten für jede Scanzeile an. Das System füllt, also den Bereich zwischen der ersten und zweiten Seite, zwischen der dritte und vierte Seite, und So weiter.

Wenn der Modus für die Polygon-füllen WICKLUNG ist, verwendet das System die Richtung, in der eine Abbildung gezeichnet wurde, um festzustellen, ob das Ausfüllen eines Bereichs, an. Jedes Liniensegment in einem Polygon, die in einen im Uhrzeigersinn oder gegen den Uhrzeigersinn gezeichnet wird. Wenn Sie eine gedachte Linie, die von eine eingeschlossene Bereich gezeichnet wird, an die Außenwelt einer Abbildung im Uhrzeigersinn Liniensegment durchläuft, wird eine Anzahl erhöht. Wenn die Zeile ein gegen den Uhrzeigersinn Liniensegment durchläuft, wird die Anzahl die verringert. Der Bereich wird ausgefüllt, wenn die Anzahl die ungleich NULL ist, wenn die Zeile außerhalb der in der Abbildung erreicht.

Wenn eine Anwendung wurde mit einer Region erstellt, mit der `CreatePolygonRgn` -Funktion, es sollte wählen Sie die Region, den Gerätekontext und die Verwendung der `DeleteObject` Funktion, um ihn zu entfernen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#146](../../mfc/codesnippet/cpp/crgn-class_3.cpp)]

##  <a name="createpolypolygonrgn"></a>  CRgn::CreatePolyPolygonRgn

Erstellt einen Bereich mit einer Reihe von geschlossenen Polygonen.

```
BOOL CreatePolyPolygonRgn(
    LPPOINT lpPoints,
    LPINT lpPolyCounts,
    int nCount,
    int nPolyFillMode);
```

### <a name="parameters"></a>Parameter

*lpPoints*<br/>
Verweist auf ein Array von `POINT` Strukturen oder ein Array von `CPoint` Objekte, die den Vertices für die Polygone definiert. Jedes Polygon muss explizit geschlossen werden, da das System nicht diese automatisch geschlossen wird. Die Polygone werden nacheinander angegeben werden. Die `POINT` Struktur weist folgende Form:

```cpp
typedef struct tagPOINT {
    int x;
    int y;
} POINT;
```

*lpPolyCounts*<br/>
Zeigt auf ein Array von ganzen Zahlen. Die erste ganze Zahl gibt die Anzahl der Scheitelpunkte im ersten Polygons in die *LpPoints* Array ist, die zweite ganze Zahl gibt die Anzahl der Scheitelpunkte in der zweiten Polygon- und So weiter.

*nCount*<br/>
Gibt die Gesamtanzahl von ganzen Zahlen in der *LpPolyCounts* Array.

*nPolyFillMode*<br/>
Gibt den Modus für die Polygon-füllen. Dieser Wert kann entweder alternative oder WICKELN sein.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Der resultierende Bereich befindet sich in der `CRgn` Objekt.

Die Polygone zusammenhanglosen werden, oder sie möglicherweise überlappen.

Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB an Arbeitsspeicher begrenzt, welcher Wert kleiner ist.

Wenn der Modus für die Polygon-füllen-Alternative ist, füllt das System den Bereich zwischen ungerade und geradzahlige Polygonseiten für jede Scanzeile an. Das System füllt, also den Bereich zwischen der ersten und zweiten Seite, zwischen der dritte und vierte Seite, und So weiter.

Wenn der Modus für die Polygon-füllen WICKLUNG ist, verwendet das System die Richtung, in der eine Abbildung gezeichnet wurde, um festzustellen, ob das Ausfüllen eines Bereichs, an. Jedes Liniensegment in einem Polygon, die in einen im Uhrzeigersinn oder gegen den Uhrzeigersinn gezeichnet wird. Wenn Sie eine gedachte Linie, die von eine eingeschlossene Bereich gezeichnet wird, an die Außenwelt einer Abbildung im Uhrzeigersinn Liniensegment durchläuft, wird eine Anzahl erhöht. Wenn die Zeile ein gegen den Uhrzeigersinn Liniensegment durchläuft, wird die Anzahl die verringert. Der Bereich wird ausgefüllt, wenn die Anzahl die ungleich NULL ist, wenn die Zeile außerhalb der in der Abbildung erreicht.

Wenn eine Anwendung wurde mit einer Region erstellt, mit der `CreatePolyPolygonRgn` -Funktion, es sollte wählen Sie die Region, den Gerätekontext und die Verwendung der [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) Member-Funktion, um ihn zu entfernen.

##  <a name="createrectrgn"></a>  CRgn::CreateRectRgn

Erstellt einen rechteckigen Bereich, die in gespeichert ist die `CRgn` Objekt.

```
BOOL CreateRectRgn(
    int x1,
    int y1,
    int x2,
    int y2);
```

### <a name="parameters"></a>Parameter

*x1*<br/>
Gibt die logische X-Koordinate der oberen linken Ecke des Bereichs an.

*y1*<br/>
Gibt die logische y-Koordinate der oberen linken Ecke des Bereichs an.

*x2*<br/>
Gibt die logische X-Koordinate der unteren rechten Ecke des Bereichs an.

*y2*<br/>
Gibt die logische y-Koordinate der unteren rechten Ecke des Bereichs an.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB an Arbeitsspeicher begrenzt, welcher Wert kleiner ist.

Wenn er abgeschlossen wurde, mit einer Region erstellt `CreateRectRgn`, eine Anwendung verwenden, sollten die [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) Memberfunktion, um den Bereich zu entfernen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#147](../../mfc/codesnippet/cpp/crgn-class_4.cpp)]

Ein zusätzliches Beispiel finden Sie unter [CRgn::CombineRgn](#combinergn).

##  <a name="createrectrgnindirect"></a>  CRgn::CreateRectRgnIndirect

Erstellt einen rechteckigen Bereich, die in gespeichert ist die `CRgn` Objekt.

```
BOOL CreateRectRgnIndirect(LPCRECT lpRect);
```

### <a name="parameters"></a>Parameter

*lpRect*<br/>
Verweist auf eine `RECT` Struktur oder `CRect` Objekt, das die logischen Koordinaten der oberen linken und rechten unteren Ecke des Bereichs enthält. Die `RECT` Struktur weist folgende Form:

```cpp
typedef struct tagRECT {
    int left;
    int top;
    int right;
    int bottom;
} RECT;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB an Arbeitsspeicher begrenzt, welcher Wert kleiner ist.

Wenn er abgeschlossen wurde, mit einer Region erstellt `CreateRectRgnIndirect`, eine Anwendung verwenden, sollten die [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) Memberfunktion, um den Bereich zu entfernen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#148](../../mfc/codesnippet/cpp/crgn-class_5.cpp)]

##  <a name="createroundrectrgn"></a>  CRgn::CreateRoundRectRgn

Erstellt einen rechteckigen Bereich mit abgerundeten Ecken, die in gespeichert ist die `CRgn` Objekt.

```
BOOL CreateRoundRectRgn(
    int x1,
    int y1,
    int x2,
    int y2,
    int x3,
    int y3);
```

### <a name="parameters"></a>Parameter

*x1*<br/>
Gibt die logische X-Koordinate der oberen linken Ecke des Bereichs an.

*y1*<br/>
Gibt die logische y-Koordinate der oberen linken Ecke des Bereichs an.

*x2*<br/>
Gibt die logische X-Koordinate der unteren rechten Ecke des Bereichs an.

*y2*<br/>
Gibt die logische y-Koordinate der unteren rechten Ecke des Bereichs an.

*x3*<br/>
Gibt die Breite der Ellipse verwendet, um die abgerundeten Ecken zu erstellen.

*y3*<br/>
Gibt die Höhe der Ellipse verwendet, um die abgerundeten Ecken zu erstellen.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB an Arbeitsspeicher begrenzt, welcher Wert kleiner ist.

Wenn eine Anwendung wurde mit einer Region erstellt, mit der `CreateRoundRectRgn` -Funktion, es sollte wählen Sie die Region, den Gerätekontext und die Verwendung der [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) Member-Funktion, um ihn zu entfernen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#149](../../mfc/codesnippet/cpp/crgn-class_6.cpp)]

##  <a name="crgn"></a>  CRgn::CRgn

Erstellt ein `CRgn`-Objekt.

```
CRgn();
```

### <a name="remarks"></a>Hinweise

Die `m_hObject` -Datenmember enthält keine gültige Windows-GDI-Region aus, bis das Objekt, mit einem oder mehreren der anderen initialisiert wird `CRgn` Memberfunktionen.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CRgn::CreateRoundRectRgn](#createroundrectrgn).

##  <a name="equalrgn"></a>  CRgn::EqualRgn

Bestimmt, ob es sich bei der angegebene Region entspricht, in der Region gespeichert, der `CRgn` Objekt.

```
BOOL EqualRgn(CRgn* pRgn) const;
```

### <a name="parameters"></a>Parameter

*pRgn*<br/>
Identifiziert den Bereich an.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die beiden Bereiche gleichwertig sind; andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#150](../../mfc/codesnippet/cpp/crgn-class_7.cpp)]

##  <a name="fromhandle"></a>  CRgn::FromHandle

Gibt einen Zeiger auf eine `CRgn` Objekt, wenn ein Handle zu einer Windows-Region zu erhalten.

```
static CRgn* PASCAL FromHandle(HRGN hRgn);
```

### <a name="parameters"></a>Parameter

*hRgn*<br/>
Gibt ein Handle für eine Windows-Region an.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein `CRgn` -Objekt. Wenn die Funktion nicht erfolgreich war, ist der Rückgabewert NULL.

### <a name="remarks"></a>Hinweise

Wenn eine `CRgn` Objekt ist noch nicht auf das Handle, eine temporäre angefügt `CRgn` Objekt erstellt und angefügt. Diese temporären `CRgn` Objekt ist nur dann gültig, bis das nächste Mal die Anwendung Zeit im Leerlauf in seiner Ereignisschleife verfügt, an der Zeit, dass alle temporären Grafik Objekte gelöscht werden. Anders ausgedrückt: Dies ist, dass der Zugriff auf das temporäre Objekt während der Verarbeitung der Nachricht von einem Fenster nur gültig ist.

##  <a name="getregiondata"></a>  CRgn::GetRegionData

Füllt den angegebenen Puffer mit Daten, das den Bereich beschreibt.

```
int GetRegionData(
    LPRGNDATA lpRgnData,
    int nCount) const;
```

### <a name="parameters"></a>Parameter

*lpRgnData*<br/>
Verweist auf eine [RGNDATA](/windows/desktop/api/wingdi/ns-wingdi-_rgndata) -Datenstruktur, die die Informationen erhält. Wenn dieser Parameter NULL ist, enthält der Rückgabewert die Anzahl der Bytes, die für die Region-Daten erforderlich sind.

*nCount*<br/>
Gibt die Größe in Bytes, der die *LpRgnData* Puffer.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist und *nCount* gibt an, eine angemessene Anzahl von Bytes, der Rückgabewert ist immer *nCount*. Wenn die Funktion fehlerhaft ist oder wenn *nCount* gibt kleiner als angemessene Anzahl von Bytes, der Rückgabewert ist 0 (Fehler).

### <a name="remarks"></a>Hinweise

Diese Daten umfassen die Dimensionen der Rechtecke, aus denen die Region besteht. Diese Funktion dient in Verbindung mit der `CRgn::CreateFromData` Funktion.

##  <a name="getrgnbox"></a>  CRgn::GetRgnBox

Ruft die Koordinaten des umgebenden Rechtecks des ab der `CRgn` Objekt.

```
int GetRgnBox(LPRECT lpRect) const;
```

### <a name="parameters"></a>Parameter

*lpRect*<br/>
Verweist auf eine `RECT` Struktur oder `CRect` Objekt, das die Koordinaten des umgebenden Rechtecks zu erhalten. Die `RECT` Struktur weist folgende Form:

`typedef struct tagRECT {`

`int left;`

`int top;`

`int right;`

`int bottom;`

`} RECT;`

### <a name="return-value"></a>Rückgabewert

Gibt des Bereichs. Eines der folgenden Werte sind möglich:

- Region, COMPLEXREGION wird überlappende Grenzen.

- NULLREGION Region ist leer.

- Fehler `CRgn` Objekts gibt kein gültigen Bereichs.

- SIMPLEREGION Region verfügt über keine überlappenden Rahmen.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CRgn::CreatePolygonRgn](#createpolygonrgn).

##  <a name="offsetrgn"></a>  CRgn::OffsetRgn

Verschiebt die Region gespeichert, der `CRgn` Objekt, indem die angegebenen Offsets.

```
int OffsetRgn(
    int x,
    int y);

int OffsetRgn(POINT point);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Gibt die Anzahl der Einheiten, die zum Verschieben von links oder rechts an.

*y*<br/>
Gibt die Anzahl der Einheiten nach oben oder unten zu verschieben.

*point*<br/>
Die X-Koordinate der *zeigen* gibt die Anzahl der Einheiten, die zum Verschieben von links oder rechts. Die y-Koordinate der *zeigen* gibt die Anzahl der Einheiten nach oben oder unten zu verschieben. Die *zeigen* Parameter möglicherweise entweder eine `POINT` Struktur oder ein `CPoint` Objekt.

### <a name="return-value"></a>Rückgabewert

Die neue Region-Typ. Eine der folgenden Werte sind möglich:

- Region, COMPLEXREGION wird überlappende Grenzen.

- Fehler von Bereichshandle ist ungültig.

- NULLREGION Region ist leer.

- SIMPLEREGION Region verfügt über keine überlappenden Rahmen.

### <a name="remarks"></a>Hinweise

Die Funktion wird die Region verschoben *x* Einheiten entlang der x-Achse und *y* Einheiten entlang der y-Achse.

Die Koordinatenwerte eines Bereichs müssen kleiner als oder gleich 32.767 und größer als oder gleich -32.768 sein. Die *x* und *y* Parameter müssen sorgfältig ausgewählt werden, um zu verhindern, dass ungültige Region Koordinaten.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CRgn::CreateEllipticRgn](#createellipticrgn).

##  <a name="operator_hrgn"></a>  CRgn::operator HRGN

Verwenden Sie diesen Operator, um das angefügte Windows-GDI-Handle des erhalten die `CRgn` Objekt.

```
operator HRGN() const;
```

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, ein Handle für das Windows-GDI-Objekt durch dargestellt die `CRgn` Objekt; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Dieser Operator ist ein Umwandlungsoperator, die direkte Verwendung eines Objekts HRGN unterstützt.

Weitere Informationen zur Verwendung von Grafikobjekten finden Sie im Artikel [Grafik Objekte](/windows/desktop/gdi/graphic-objects) im Windows SDK.

##  <a name="ptinregion"></a>  CRgn::PtInRegion

Überprüft, ob der Punkt, der von *x* und *y* ist in der Region gespeichert, der `CRgn` Objekt.

```
BOOL PtInRegion(
    int x,
    int y) const;

BOOL PtInRegion(POINT point) const;
```

### <a name="parameters"></a>Parameter

*w*<br/>
Gibt die logische X-Koordinate des Punktes, der überprüft.

*y*<br/>
Gibt die logische y-Koordinate des Punktes, der überprüft.

*point*<br/>
Die x- und y-Koordinaten der *zeigen* geben die x- und y-Koordinaten des Punkts, der den Wert testen. Die *zeigen* Parameter kann entweder sein. eine `POINT` Struktur oder ein `CPoint` Objekt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn der Punkt in der Region ist; andernfalls 0.

##  <a name="rectinregion"></a>  CRgn::RectInRegion

Bestimmt, ob durch einen beliebigen Teil des Rechtecks angegeben *LpRect* innerhalb der Grenzen der Region gespeichert, der `CRgn` Objekt.

```
BOOL RectInRegion(LPCRECT lpRect) const;
```

### <a name="parameters"></a>Parameter

*lpRect*<br/>
Verweist auf eine `RECT` Struktur oder `CRect` Objekt. Die `RECT` Struktur weist folgende Form:

```cpp
typedef struct tagRECT {
    int left;
    int top;
    int right;
    int bottom;
} RECT;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn alle Teil des angegebenen Rechtecks liegt innerhalb der Grenzen des Bereichs; andernfalls 0.

##  <a name="setrectrgn"></a>  CRgn::SetRectRgn

Erstellt einen rechteckigen Bereich an.

```
void SetRectRgn(
    int x1,
    int y1,
    int x2,
    int y2);

void SetRectRgn(LPCRECT lpRect);
```

### <a name="parameters"></a>Parameter

*x1*<br/>
Gibt die X-Koordinate von der linken oberen Ecke des rechteckigen Bereichs.

*y1*<br/>
Gibt die y-Koordinate von der linken oberen Ecke des rechteckigen Bereichs.

*x2*<br/>
Gibt die X-Koordinate von der unteren rechten Ecke des rechteckigen Bereichs.

*y2*<br/>
Gibt die y-Koordinate von der unteren rechten Ecke des rechteckigen Bereichs.

*lpRect*<br/>
Gibt an, der rechteckige Bereich. Kann entweder ein Zeiger auf eine `RECT` Struktur oder ein `CRect` Objekt.

### <a name="remarks"></a>Hinweise

Im Gegensatz zu [CreateRectRgn](#createrectrgn), allerdings ist es keinen zusätzlichen Speicher belegen, aus dem lokalen Windows-Anwendung-Heap. Stattdessen wird der Speicherplatz für die Region als gespeichert der `CRgn` Objekt. Dies bedeutet, dass die `CRgn` Objekt bereits initialisiert worden sein, mit einem gültigen Windows-Bereich vor dem Aufruf `SetRectRgn`. Die Punkte, die vom *X1*, *y1*, *X2*, und *y2* geben die minimale Größe des belegten Speicherplatzes.

Verwenden Sie diese Funktion statt der `CreateRectRgn` Member-Funktion, um Aufrufe an den lokalen Speicher-Manager zu vermeiden.

## <a name="see-also"></a>Siehe auch

[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
