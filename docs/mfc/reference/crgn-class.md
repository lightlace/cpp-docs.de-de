---
title: Crgn-Klasse
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
ms.openlocfilehash: 66721f34a8ac2b6dac6addcfa04a88b46a37ee60
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916830"
---
# <a name="crgn-class"></a>Crgn-Klasse

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
|[CRgn::CombineRgn](#combinergn)|Legt ein `CRgn` -Objekt fest `CRgn` , damit es gleich der Vereinigung zweier angegebener-Objekte ist.|
|[CRgn::CopyRgn](#copyrgn)|Legt ein `CRgn` -Objekt fest, sodass es eine Kopie eines angegebenen `CRgn` -Objekts ist.|
|[CRgn::CreateEllipticRgn](#createellipticrgn)|Initialisiert ein `CRgn` -Objekt mit einem elliptischen Bereich.|
|[CRgn::CreateEllipticRgnIndirect](#createellipticrgnindirect)|Initialisiert ein `CRgn` -Objekt mit einem Ellipsen Bereich, der durch eine [Rect](/windows/desktop/api/windef/ns-windef-tagrect) -Struktur definiert ist.|
|[CRgn::CreateFromData](#createfromdata)|Erstellt einen Bereich aus dem angegebenen Bereich und den Transformations Daten.|
|[CRgn::CreateFromPath](#createfrompath)|Erstellt einen Bereich aus dem Pfad, der im angegebenen Gerätekontext ausgewählt wird.|
|[CRgn::CreatePolygonRgn](#createpolygonrgn)|Initialisiert ein `CRgn` -Objekt mit einem polygonalen Bereich. Das System schließt das Polygon ggf. automatisch, indem eine Linie vom letzten Scheitelpunkt zum ersten gezeichnet wird.|
|[CRgn::CreatePolyPolygonRgn](#createpolypolygonrgn)|Initialisiert ein `CRgn` -Objekt mit einem Bereich, der aus einer Reihe von geschlossenen Polygonen besteht. Die Polygone können zusammen hanglos sein, oder Sie können sich überlappen.|
|[CRgn::CreateRectRgn](#createrectrgn)|Initialisiert ein `CRgn` -Objekt mit einem rechteckigen Bereich.|
|[CRgn::CreateRectRgnIndirect](#createrectrgnindirect)|Initialisiert ein `CRgn` -Objekt mit einem rechteckigen Bereich, der durch eine [Rect](/windows/desktop/api/windef/ns-windef-tagrect) -Struktur definiert ist.|
|[CRgn::CreateRoundRectRgn](#createroundrectrgn)|Initialisiert ein `CRgn` -Objekt mit einem rechteckigen Bereich mit abgerundeten Ecken.|
|[CRgn::EqualRgn](#equalrgn)|Überprüft zwei `CRgn` -Objekte, um zu bestimmen, ob Sie äquivalent sind.|
|[Crgn:: FromHandle](#fromhandle)|Gibt einen Zeiger auf ein `CRgn` -Objekt zurück, wenn ein Handle für einen Windows-Bereich angegeben ist.|
|[CRgn::GetRegionData](#getregiondata)|Füllt den angegebenen Puffer mit Daten, die den angegebenen Bereich beschreiben.|
|[CRgn::GetRgnBox](#getrgnbox)|Ruft die Koordinaten des umgebenden Rechtecks eines `CRgn` -Objekts ab.|
|[CRgn::OffsetRgn](#offsetrgn)|Verschiebt ein `CRgn` -Objekt um die angegebenen Offsets.|
|[CRgn::PtInRegion](#ptinregion)|Bestimmt, ob sich ein angegebener Punkt in der Region befindet.|
|[CRgn::RectInRegion](#rectinregion)|Bestimmt, ob ein beliebiger Teil eines angegebenen Rechtecks innerhalb der Grenzen des Bereichs liegt.|
|[CRgn::SetRectRgn](#setrectrgn)|Legt das `CRgn` -Objekt auf den angegebenen rechteckigen Bereich fest.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[Crgn:: Operator hrgn](#operator_hrgn)|Gibt das Windows-Handle zurück, `CRgn` das im-Objekt enthalten ist.|

## <a name="remarks"></a>Hinweise

Ein Bereich ist ein elliptischer oder polygonaler Bereich innerhalb eines Fensters. Um Bereiche zu verwenden, verwenden Sie die Element Funktionen der `CRgn` -Klasse mit den clippingfunktionen, die `CDC`als Member der-Klasse definiert sind.

Die Element Funktionen von `CRgn` erstellen, ändern und rufen Informationen über das Regions Objekt ab, für das Sie aufgerufen werden.

Weitere Informationen zum Verwenden von `CRgn`finden Sie unter [Graphic Objects](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CRgn`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="combinergn"></a>Crgn:: combinergn

Erstellt einen neuen GDI-Bereich, indem zwei vorhandene Regionen kombiniert werden.

```
int CombineRgn(
    CRgn* pRgn1,
    CRgn* pRgn2,
    int nCombineMode);
```

### <a name="parameters"></a>Parameter

*pRgn1*<br/>
Identifiziert einen vorhandenen Bereich.

*pRgn2*<br/>
Identifiziert einen vorhandenen Bereich.

*nCombineMode*<br/>
Gibt den Vorgang an, der ausgeführt werden soll, wenn die beiden Quellbereiche kombiniert werden. Es kann sich um einen der folgenden Werte handeln:

- RGN_AND verwendet überlappende Bereiche beider Regionen (Schnittmenge).

- RGN_COPY erstellt eine Kopie von Region 1 (identifiziert durch *pRgn1*).

- RGN_DIFF erstellt einen Bereich, der aus den Bereichen von Region 1 (identifiziert durch *pRgn1*) besteht, die nicht Teil von Region 2 sind (identifiziert durch *pRgn2*).

- RGN_OR kombiniert beide Regionen in ihrer Gesamtheit (Union).

- RGN_XOR kombiniert beide Regionen, entfernt jedoch überlappende Bereiche.

### <a name="return-value"></a>Rückgabewert

Gibt den Typ des resultierenden Bereichs an. Dies kann einer der folgenden Werte sein:

- Die neue Region complexregion weist überlappende Rahmen auf.

- Fehler es wurde keine neue Region erstellt.

- NULL Region New Region ist leer.

- Der neue Bereich der simpleregion weist keine überlappenden Rahmen auf.

### <a name="remarks"></a>Hinweise

Die Regionen werden wie von *ncombinemode*angegeben kombiniert.

Die beiden angegebenen Bereiche werden kombiniert, und das resultierende Regions Handle wird im `CRgn` -Objekt gespeichert. Daher wird jede Region, die im `CRgn` -Objekt gespeichert ist, durch den kombinierten Bereich ersetzt.

Die Größe eines Bereichs ist auf 32.767 x 32.767 logische Einheiten oder 64 KB Arbeitsspeicher beschränkt, je nachdem, welcher Wert kleiner ist.

Verwenden Sie [copyrgn](#copyrgn) , um einfach einen Bereich in eine andere Region zu kopieren.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#144](../../mfc/codesnippet/cpp/crgn-class_1.cpp)]

##  <a name="copyrgn"></a>Crgn:: copyrgn

Kopiert den durch *prgnsrc* definierten Bereich in das `CRgn` -Objekt.

```
int CopyRgn(CRgn* pRgnSrc);
```

### <a name="parameters"></a>Parameter

*pRgnSrc*<br/>
Identifiziert einen vorhandenen Bereich.

### <a name="return-value"></a>Rückgabewert

Gibt den Typ des resultierenden Bereichs an. Dies kann einer der folgenden Werte sein:

- Die neue Region complexregion weist überlappende Rahmen auf.

- Fehler es wurde keine neue Region erstellt.

- NULL Region New Region ist leer.

- Der neue Bereich der simpleregion weist keine überlappenden Rahmen auf.

### <a name="remarks"></a>Hinweise

Die neue Region ersetzt den zuvor im `CRgn` -Objekt gespeicherten Bereich. Diese Funktion ist ein Sonderfall der [combinergn](#combinergn) -Member-Funktion.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [crgn:: kreateellipticrgn](#createellipticrgn).

##  <a name="createellipticrgn"></a>Crgn:: kreateellipticrgn

Erstellt einen elliptischen Bereich.

```
BOOL CreateEllipticRgn(
    int x1,
    int y1,
    int x2,
    int y2);
```

### <a name="parameters"></a>Parameter

*x1*<br/>
Gibt die logische x-Koordinate der oberen linken Ecke des Begrenzungs Rechtecks der Ellipse an.

*y1*<br/>
Gibt die logische y-Koordinate der oberen linken Ecke des umgebenden Rechtecks der Ellipse an.

*x2*<br/>
Gibt die logische x-Koordinate der unteren rechten Ecke des umgebenden Rechtecks der Ellipse an.

*y2*<br/>
Gibt die logische y-Koordinate der unteren rechten Ecke des umgebenden Rechtecks der Ellipse an.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Vorgang erfolgreich war. andernfalls 0.

### <a name="remarks"></a>Hinweise

Der Bereich wird durch das umgebende Rechteck definiert, das von *x1*, *Y1*, *x2*und *Y2*angegeben wird. Der Bereich wird im `CRgn` -Objekt gespeichert.

Die Größe eines Bereichs ist auf 32.767 x 32.767 logische Einheiten oder 64 KB Arbeitsspeicher beschränkt, je nachdem, welcher Wert kleiner ist.

Wenn die Verwendung einer mit der `CreateEllipticRgn` -Funktion erstellten Region abgeschlossen ist, sollte eine Anwendung den Bereich aus dem Gerätekontext auswählen und die `DeleteObject` -Funktion verwenden, um Sie zu entfernen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#145](../../mfc/codesnippet/cpp/crgn-class_2.cpp)]

##  <a name="createellipticrgnindirect"></a>Crgn:: kreateellipticrgnindirekte

Erstellt einen elliptischen Bereich.

```
BOOL CreateEllipticRgnIndirect(LPCRECT lpRect);
```

### <a name="parameters"></a>Parameter

*lpRect*<br/>
Verweist auf eine `RECT` -Struktur oder `CRect` ein-Objekt, das die logischen Koordinaten der oberen linken und der unteren rechten Ecke des umgebenden Rechtecks der Ellipse enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Vorgang erfolgreich war. andernfalls 0.

### <a name="remarks"></a>Hinweise

Der Bereich wird durch die Struktur oder das Objekt definiert, auf die von *lprect* verwiesen wird und `CRgn` die im-Objekt gespeichert werden.

Die Größe eines Bereichs ist auf 32.767 x 32.767 logische Einheiten oder 64 KB Arbeitsspeicher beschränkt, je nachdem, welcher Wert kleiner ist.

Wenn die Verwendung einer mit der `CreateEllipticRgnIndirect` -Funktion erstellten Region abgeschlossen ist, sollte eine Anwendung den Bereich aus dem Gerätekontext auswählen und die `DeleteObject` -Funktion verwenden, um Sie zu entfernen.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [crgn:: kreaterectrgnindirekt](#createrectrgnindirect).

##  <a name="createfromdata"></a>Crgn:: kreatefromdata

Erstellt einen Bereich aus dem angegebenen Bereich und den Transformations Daten.

```
BOOL CreateFromData(
    const XFORM* lpXForm,
    int nCount,
    const RGNDATA* pRgnData);
```

### <a name="parameters"></a>Parameter

*lpXForm*<br/>
Verweist auf eine [XForm](/windows/desktop/api/wingdi/ns-wingdi-tagxform) -Datenstruktur, die die Transformation definiert, die für den Bereich ausgeführt werden soll. Wenn dieser Zeiger NULL ist, wird die Identitäts Transformation verwendet.

*nCount*<br/>
Gibt die Anzahl der Bytes an, auf die durch *prgndata*verwiesen wird.

*pRgnData*<br/>
Verweist auf eine [rgnData](/windows/desktop/api/wingdi/ns-wingdi-rgndata) -Datenstruktur, die die Regions Daten enthält.

### <a name="return-value"></a>Rückgabewert

Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).

### <a name="remarks"></a>Hinweise

Eine Anwendung kann Daten für einen Bereich abrufen, indem die `CRgn::GetRegionData` -Funktion aufgerufen wird.

##  <a name="createfrompath"></a>Crgn:: kreatefrompath

Erstellt einen Bereich aus dem Pfad, der im angegebenen Gerätekontext ausgewählt wird.

```
BOOL CreateFromPath(CDC* pDC);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Identifiziert einen Gerätekontext, der einen geschlossenen Pfad enthält.

### <a name="return-value"></a>Rückgabewert

Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).

### <a name="remarks"></a>Hinweise

Der durch den *PDC* -Parameter identifizierte Gerätekontext muss einen geschlossenen Pfad enthalten. Nachdem `CreateFromPath` einen Pfad in einen Bereich konvertiert hat, verwirft Windows den geschlossenen Pfad aus dem Gerätekontext.

##  <a name="createpolygonrgn"></a>Crgn:: kreatepolygonrgn

Erstellt einen polygonalen Bereich.

```
BOOL CreatePolygonRgn(
    LPPOINT lpPoints,
    int nCount,
    int nMode);
```

### <a name="parameters"></a>Parameter

*lpPoints*<br/>
Verweist auf ein Array von `POINT` -Strukturen oder ein Array `CPoint` von-Objekten. Jede-Struktur gibt die x-Koordinate und die y-Koordinate eines Scheitel Punkts des Polygons an. Die `POINT` Struktur weist die folgende Form auf:

```cpp
typedef struct tagPOINT {
    int x;
    int y;
} POINT;
```

*nCount*<br/>
Gibt die Anzahl der `POINT` Strukturen oder `CPoint` Objekte im Array an, auf die von *lppoints*verwiesen wird.

*nMode*<br/>
Gibt den Füll Modus für den Bereich an. Dieser Parameter kann entweder "Alternative" oder "Winding" sein.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Vorgang erfolgreich war. andernfalls 0.

### <a name="remarks"></a>Hinweise

Das System schließt das Polygon ggf. automatisch, indem eine Linie vom letzten Scheitelpunkt zum ersten gezeichnet wird. Der resultierende Bereich wird im `CRgn` -Objekt gespeichert.

Die Größe eines Bereichs ist auf 32.767 x 32.767 logische Einheiten oder 64 KB Arbeitsspeicher beschränkt, je nachdem, welcher Wert kleiner ist.

Wenn der Polygon Füllmodus eine Alternative ist, füllt das System den Bereich zwischen ungeraden und sogar nummerierten Polygon Seiten für jede Scan Zeile aus. Das heißt, das System füllt den Bereich zwischen der ersten und der zweiten Seite, zwischen der dritten und vierten Seite und so weiter.

Wenn sich der Polygon Füllmodus in der Größe befindet, verwendet das System die Richtung, in der eine Figur gezeichnet wurde, um zu bestimmen, ob ein Bereich ausgefüllt werden soll. Jedes Liniensegment in einem Polygon wird entweder im Uhrzeigersinn oder gegen den Uhrzeigersinn gezeichnet. Wenn eine imaginäre Linie, die von einem eingeschlossenen Bereich zum äußeren Rand einer Figur gezeichnet wird, ein Liniensegment im Uhrzeigersinn übergibt, wird eine Anzahl erhöht. Wenn die Linie ein Liniensegment gegen den Uhrzeigersinn übergibt, wird die Anzahl dekrementiert. Der Bereich wird aufgefüllt, wenn die Anzahl nicht 0 (null) ist, wenn die Zeile den äußeren Rand der Abbildung erreicht.

Wenn eine Anwendung die Verwendung eines mit der `CreatePolygonRgn` -Funktion erstellten Bereichs abgeschlossen hat, sollte Sie den Bereich aus dem Gerätekontext auswählen und die `DeleteObject` -Funktion verwenden, um Sie zu entfernen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#146](../../mfc/codesnippet/cpp/crgn-class_3.cpp)]

##  <a name="createpolypolygonrgn"></a>Crgn:: anatepolypolygonrgn

Erstellt einen Bereich, der aus einer Reihe von geschlossenen Polygonen besteht.

```
BOOL CreatePolyPolygonRgn(
    LPPOINT lpPoints,
    LPINT lpPolyCounts,
    int nCount,
    int nPolyFillMode);
```

### <a name="parameters"></a>Parameter

*lpPoints*<br/>
Verweist auf ein Array von `POINT` -Strukturen oder ein Array `CPoint` von-Objekten, das die Scheitel Punkte der Polygone definiert. Jedes Polygon muss explizit geschlossen werden, da das System diese nicht automatisch schließt. Die Polygone werden nacheinander angegeben. Die `POINT` Struktur weist die folgende Form auf:

```cpp
typedef struct tagPOINT {
    int x;
    int y;
} POINT;
```

*lpPolyCounts*<br/>
Verweist auf ein Array aus ganzen Zahlen. Die erste ganze Zahl gibt die Anzahl der Scheitel Punkte im ersten Polygon im *lppoints* -Array an, die zweite Ganzzahl gibt die Anzahl der Scheitel Punkte im zweiten Polygon an usw.

*nCount*<br/>
Gibt die Gesamtzahl ganzer Zahlen im *lppolycounts* -Array an.

*nPolyFillMode*<br/>
Gibt den Polygon Füll Modus an. Bei diesem Wert kann es sich entweder um eine Alternative oder um eine "

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Vorgang erfolgreich war. andernfalls 0.

### <a name="remarks"></a>Hinweise

Der resultierende Bereich wird im `CRgn` -Objekt gespeichert.

Die Polygone können zusammen hanglos sein, oder Sie können sich überlappen.

Die Größe eines Bereichs ist auf 32.767 x 32.767 logische Einheiten oder 64 KB Arbeitsspeicher beschränkt, je nachdem, welcher Wert kleiner ist.

Wenn der Polygon Füllmodus eine Alternative ist, füllt das System den Bereich zwischen ungeraden und sogar nummerierten Polygon Seiten für jede Scan Zeile aus. Das heißt, das System füllt den Bereich zwischen der ersten und der zweiten Seite, zwischen der dritten und vierten Seite und so weiter.

Wenn sich der Polygon Füllmodus in der Größe befindet, verwendet das System die Richtung, in der eine Figur gezeichnet wurde, um zu bestimmen, ob ein Bereich ausgefüllt werden soll. Jedes Liniensegment in einem Polygon wird entweder im Uhrzeigersinn oder gegen den Uhrzeigersinn gezeichnet. Wenn eine imaginäre Linie, die von einem eingeschlossenen Bereich zum äußeren Rand einer Figur gezeichnet wird, ein Liniensegment im Uhrzeigersinn übergibt, wird eine Anzahl erhöht. Wenn die Linie ein Liniensegment gegen den Uhrzeigersinn übergibt, wird die Anzahl dekrementiert. Der Bereich wird aufgefüllt, wenn die Anzahl nicht 0 (null) ist, wenn die Zeile den äußeren Rand der Abbildung erreicht.

Wenn eine Anwendung die Verwendung eines mit der `CreatePolyPolygonRgn` -Funktion erstellten Bereichs abgeschlossen hat, sollte Sie den Bereich aus dem Gerätekontext auswählen und die Member-Funktion [CGdiObject::D eleteobject](../../mfc/reference/cgdiobject-class.md#deleteobject) verwenden, um Sie zu entfernen.

##  <a name="createrectrgn"></a>Crgn:: "kreaterectrgn"

Erstellt einen rechteckigen Bereich, der `CRgn` im-Objekt gespeichert ist.

```
BOOL CreateRectRgn(
    int x1,
    int y1,
    int x2,
    int y2);
```

### <a name="parameters"></a>Parameter

*x1*<br/>
Gibt die logische x-Koordinate der oberen linken Ecke des Bereichs an.

*y1*<br/>
Gibt die logische y-Koordinate der oberen linken Ecke des Bereichs an.

*x2*<br/>
Gibt die logische x-Koordinate der unteren rechten Ecke des Bereichs an.

*y2*<br/>
Gibt die logische y-Koordinate der unteren rechten Ecke des Bereichs an.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Vorgang erfolgreich war. andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Größe eines Bereichs ist auf 32.767 x 32.767 logische Einheiten oder 64 KB Arbeitsspeicher beschränkt, je nachdem, welcher Wert kleiner ist.

Wenn die Verwendung eines von `CreateRectRgn`erstellten Bereichs abgeschlossen ist, sollte eine Anwendung die [CGdiObject::D eleteobject](../../mfc/reference/cgdiobject-class.md#deleteobject) -Member-Funktion verwenden, um den Bereich zu entfernen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#147](../../mfc/codesnippet/cpp/crgn-class_4.cpp)]

Ein weiteres Beispiel finden Sie unter [crgn:: combinergn](#combinergn).

##  <a name="createrectrgnindirect"></a>Crgn:: "kreaterectrgnindirekte"

Erstellt einen rechteckigen Bereich, der `CRgn` im-Objekt gespeichert ist.

```
BOOL CreateRectRgnIndirect(LPCRECT lpRect);
```

### <a name="parameters"></a>Parameter

*lpRect*<br/>
Verweist auf eine `RECT` Struktur oder `CRect` ein Objekt, das die logischen Koordinaten der oberen linken und der unteren rechten Ecke des Bereichs enthält. Die `RECT` Struktur weist die folgende Form auf:

```cpp
typedef struct tagRECT {
    int left;
    int top;
    int right;
    int bottom;
} RECT;
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Vorgang erfolgreich war. andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Größe eines Bereichs ist auf 32.767 x 32.767 logische Einheiten oder 64 KB Arbeitsspeicher beschränkt, je nachdem, welcher Wert kleiner ist.

Wenn die Verwendung eines von `CreateRectRgnIndirect`erstellten Bereichs abgeschlossen ist, sollte eine Anwendung die [CGdiObject::D eleteobject](../../mfc/reference/cgdiobject-class.md#deleteobject) -Member-Funktion verwenden, um den Bereich zu entfernen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#148](../../mfc/codesnippet/cpp/crgn-class_5.cpp)]

##  <a name="createroundrectrgn"></a>Crgn:: "kreateroundrectrgn"

Erstellt einen rechteckigen Bereich mit abgerundeten Ecken, der `CRgn` im-Objekt gespeichert ist.

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
Gibt die logische x-Koordinate der oberen linken Ecke des Bereichs an.

*y1*<br/>
Gibt die logische y-Koordinate der oberen linken Ecke des Bereichs an.

*x2*<br/>
Gibt die logische x-Koordinate der unteren rechten Ecke des Bereichs an.

*y2*<br/>
Gibt die logische y-Koordinate der unteren rechten Ecke des Bereichs an.

*x3*<br/>
Gibt die Breite der Ellipse an, mit der die abgerundeten Ecken erstellt werden.

*y3*<br/>
Gibt die Höhe der Ellipse an, mit der die abgerundeten Ecken erstellt werden.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Vorgang erfolgreich war. andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Größe eines Bereichs ist auf 32.767 x 32.767 logische Einheiten oder 64 KB Arbeitsspeicher beschränkt, je nachdem, welcher Wert kleiner ist.

Wenn eine Anwendung die Verwendung eines mit der `CreateRoundRectRgn` -Funktion erstellten Bereichs abgeschlossen hat, sollte Sie den Bereich aus dem Gerätekontext auswählen und die Member-Funktion [CGdiObject::D eleteobject](../../mfc/reference/cgdiobject-class.md#deleteobject) verwenden, um Sie zu entfernen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#149](../../mfc/codesnippet/cpp/crgn-class_6.cpp)]

##  <a name="crgn"></a>Crgn:: crgn

Erstellt ein `CRgn`-Objekt.

```
CRgn();
```

### <a name="remarks"></a>Hinweise

Der `m_hObject` Datenmember enthält keinen gültigen Windows-GDI-Bereich, bis das Objekt mit einer oder mehreren der anderen `CRgn` Element Funktionen initialisiert wird.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [crgn:: kreateroundrectrgn](#createroundrectrgn).

##  <a name="equalrgn"></a>Crgn:: equalrgn

Bestimmt, ob der angegebene Bereich der im `CRgn` -Objekt gespeicherten Region entspricht.

```
BOOL EqualRgn(CRgn* pRgn) const;
```

### <a name="parameters"></a>Parameter

*pRgn*<br/>
Identifiziert einen Bereich.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die beiden Bereiche gleichwertig sind. andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#150](../../mfc/codesnippet/cpp/crgn-class_7.cpp)]

##  <a name="fromhandle"></a>Crgn:: FromHandle

Gibt einen Zeiger auf ein `CRgn` -Objekt zurück, wenn ein Handle für einen Windows-Bereich angegeben ist.

```
static CRgn* PASCAL FromHandle(HRGN hRgn);
```

### <a name="parameters"></a>Parameter

*hRgn*<br/>
Gibt ein Handle für einen Windows-Bereich an.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein `CRgn` -Objekt. Wenn die Funktion nicht erfolgreich war, ist der Rückgabewert NULL.

### <a name="remarks"></a>Hinweise

Wenn ein `CRgn` -Objekt noch nicht an das Handle angefügt ist, `CRgn` wird ein temporäres Objekt erstellt und angefügt. Dieses temporäre `CRgn` Objekt ist nur gültig, bis das nächste Mal die Leerlaufzeit der Anwendung in der Ereignisschleife liegt. zu diesem Zeitpunkt werden alle temporären Grafik Objekte gelöscht. Eine andere Möglichkeit, dies zu sagen, besteht darin, dass das temporäre Objekt nur während der Verarbeitung einer Fenster Nachricht gültig ist.

##  <a name="getregiondata"></a>Crgn:: GetRegionData

Füllt den angegebenen Puffer mit Daten, die den Bereich beschreiben.

```
int GetRegionData(
    LPRGNDATA lpRgnData,
    int nCount) const;
```

### <a name="parameters"></a>Parameter

*lpRgnData*<br/>
Verweist auf eine [rgnData](/windows/desktop/api/wingdi/ns-wingdi-rgndata) -Datenstruktur, die die Informationen empfängt. Wenn dieser Parameter NULL ist, enthält der Rückgabewert die Anzahl der Bytes, die für die Regions Daten benötigt werden.

*nCount*<br/>
Gibt die Größe des *lprgndata* -Puffers in Bytes an.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ausgeführt wird und *nCount* eine angemessene Anzahl von Bytes angibt, ist der Rückgabewert immer *nCount*. Wenn die Funktion fehlschlägt oder wenn *nCount* weniger als eine angemessene Anzahl von Bytes angibt, ist der Rückgabewert 0 (Fehler).

### <a name="remarks"></a>Hinweise

Diese Daten umfassen die Dimensionen der Rechtecke, die den Bereich bilden. Diese Funktion wird in Verbindung mit der `CRgn::CreateFromData` -Funktion verwendet.

##  <a name="getrgnbox"></a>Crgn:: getrgnbox

Ruft die Koordinaten des umgebenden Rechtecks des `CRgn` -Objekts ab.

```
int GetRgnBox(LPRECT lpRect) const;
```

### <a name="parameters"></a>Parameter

*lpRect*<br/>
Verweist auf eine `RECT` Struktur oder `CRect` ein Objekt, um die Koordinaten des umgebenden Rechtecks zu erhalten. Die `RECT` Struktur weist die folgende Form auf:

`typedef struct tagRECT {`

`int left;`

`int top;`

`int right;`

`int bottom;`

`} RECT;`

### <a name="return-value"></a>Rückgabewert

Gibt den Typ des Bereichs an. Dabei kann es sich um einen der folgenden Werte handeln:

- Der complexregion-Bereich hat überlappende Rahmen.

- Der NULLREGION-Bereich ist leer.

- Das `CRgn` Error-Objekt gibt keinen gültigen Bereich an.

- Der simpleregion-Bereich weist keine überlappenden Rahmen auf.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [crgn:: kreatepolygonrgn](#createpolygonrgn).

##  <a name="offsetrgn"></a>Crgn:: offort TRGN

Verschiebt den Bereich, der im `CRgn` -Objekt gespeichert ist, um die angegebenen Offsets.

```
int OffsetRgn(
    int x,
    int y);

int OffsetRgn(POINT point);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Gibt die Anzahl der Einheiten an, nach links oder rechts verschoben werden soll.

*y*<br/>
Gibt die Anzahl der Einheiten an, die nach oben oder unten verschoben werden.

*point*<br/>
Die x-Koordinate des *Punkts* gibt die Anzahl der Einheiten an, die nach links oder rechts verschoben werden. Die y-Koordinate des *Punkts* gibt die Anzahl der Einheiten an, die nach oben oder unten verschoben werden. Der *Punkt* Parameter kann entweder eine `POINT` Struktur oder ein `CPoint` -Objekt sein.

### <a name="return-value"></a>Rückgabewert

Der Typ der neuen Region. Es kann sich um einen der folgenden Werte handeln:

- Der complexregion-Bereich hat überlappende Rahmen.

- Das Handle des Fehler Bereichs ist ungültig.

- Der NULLREGION-Bereich ist leer.

- Der simpleregion-Bereich weist keine überlappenden Rahmen auf.

### <a name="remarks"></a>Hinweise

Die-Funktion verschiebt die Einheiten *x* -Einheiten entlang der x-Achse und *y* -Einheiten entlang der y-Achse.

Die Koordinaten Werte eines Bereichs müssen kleiner oder gleich 32.767 und größer oder gleich-32.768 sein. Der *x* -und der *y* -Parameter müssen sorgfältig ausgewählt werden, um ungültige Regions Koordinaten zu verhindern.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [crgn:: kreateellipticrgn](#createellipticrgn).

##  <a name="operator_hrgn"></a>Crgn:: Operator hrgn

Verwenden Sie diesen Operator, um das angefügte Windows-GDI `CRgn` -Handle des-Objekts zu erhalten.

```
operator HRGN() const;
```

### <a name="return-value"></a>Rückgabewert

Bei Erfolg ein Handle für das von dem `CRgn` -Objekt dargestellte Windows-GDI-Objekt, andernfalls NULL.

### <a name="remarks"></a>Hinweise

Dieser Operator ist ein Typumwandlungs Operator, der die direkte Verwendung eines hrgn-Objekts unterstützt.

Weitere Informationen zum Verwenden von Grafikobjekten finden Sie im Artikel [Graphic Objects](/windows/desktop/gdi/graphic-objects) in the Windows SDK.

##  <a name="ptinregion"></a>Crgn::P tinregion

Überprüft, ob sich der von *x* und *y* angegebene Punkt in der im- `CRgn` Objekt gespeicherten Region befindet.

```
BOOL PtInRegion(
    int x,
    int y) const;

BOOL PtInRegion(POINT point) const;
```

### <a name="parameters"></a>Parameter

*w*<br/>
Gibt die logische x-Koordinate des Punkts an, der getestet werden soll.

*y*<br/>
Gibt die logische y-Koordinate des Punkts an, der getestet werden soll.

*point*<br/>
Mit den x-und y-Koordinaten des *Punkts* werden die x-und y-Koordinaten des Punkts angegeben, dessen Wert getestet werden soll. Der *Punkt* Parameter kann entweder eine `POINT` Struktur oder ein `CPoint` -Objekt sein.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn sich der Punkt in der Region befindet. andernfalls 0.

##  <a name="rectinregion"></a>Crgn:: rectinregion

Bestimmt, ob ein beliebiger Teil des Rechtecks, der von *lprect* angegeben wird, innerhalb der `CRgn` Grenzen des im-Objekt gespeicherten Bereichs liegt.

```
BOOL RectInRegion(LPCRECT lpRect) const;
```

### <a name="parameters"></a>Parameter

*lpRect*<br/>
Verweist auf eine `RECT` Struktur oder `CRect` ein Objekt. Die `RECT` Struktur weist die folgende Form auf:

```cpp
typedef struct tagRECT {
    int left;
    int top;
    int right;
    int bottom;
} RECT;
```

### <a name="return-value"></a>Rückgabewert

Ein Wert ungleich 0 (null), wenn ein Teil des angegebenen Rechtecks innerhalb der Grenzen des Bereichs liegt. andernfalls 0.

##  <a name="setrectrgn"></a>Crgn:: setrectrgn

Erstellt einen rechteckigen Bereich.

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
Gibt die x-Koordinate der linken oberen Ecke des rechteckigen Bereichs an.

*y1*<br/>
Gibt die y-Koordinate der oberen linken Ecke des rechteckigen Bereichs an.

*x2*<br/>
Gibt die x-Koordinate der unteren rechten Ecke des rechteckigen Bereichs an.

*y2*<br/>
Gibt die y-Koordinate der unteren rechten Ecke des rechteckigen Bereichs an.

*lpRect*<br/>
Gibt den rechteckigen Bereich an. Kann entweder ein Zeiger auf eine `RECT` -Struktur oder ein `CRect` -Objekt sein.

### <a name="remarks"></a>Hinweise

Anders als bei [CreateRectRgn](#createrectrgn) belegt sie keinen zusätzlichen Speicherplatz aus dem lokalen Windows-Anwendungsheap. Stattdessen wird der für die Region zugeordnete Speicherplatz verwendet, der `CRgn` im-Objekt gespeichert ist. Dies bedeutet, dass `CRgn` das Objekt bereits mit einem gültigen Windows-Bereich initialisiert worden sein muss `SetRectRgn`, bevor aufgerufen wird. Die von *x1*, *Y1*, *x2*und *Y2* angegebenen Punkte geben die minimale Größe des zugewiesenen Speicherplatzes an.

Verwenden Sie diese Funktion anstelle der `CreateRectRgn` Member-Funktion, um Aufrufe an den lokalen Speicher-Manager zu vermeiden.

## <a name="see-also"></a>Siehe auch

[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
