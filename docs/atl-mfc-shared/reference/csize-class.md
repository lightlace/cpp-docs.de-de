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
ms.openlocfilehash: 5e19ab9b9339f3e6f61abf7731a40ed3832b50c9
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58767361"
---
# <a name="csize-class"></a>CSize-Klasse

Ähnelt der Windows-Struktur [SIZE](/windows/desktop/api/windef/ns-windef-tagsize) , bei der eine relative Koordinate oder Position implementiert wird

## <a name="syntax"></a>Syntax

```
class CSize : public tagSIZE
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSize::CSize](#csize)|Erstellt ein `CSize`-Objekt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CSize::operator-](#operator_-)|Subtrahiert zwei Größen an.|
|[CSize::operator! =](#operator_neq)|Prüft auf Ungleichheit zwischen `CSize` und einer Größe.|
|[CSize::operator +](#operator_add)|Fügt zwei Größen hinzu.|
|[CSize::operator +=](#operator_add_eq)|Fügt eine Größe, auf `CSize`.|
|[CSize::operator =](#operator_-_eq)|Subtrahiert eine Größe von `CSize`.|
|[CSize::operator ==](#operator_eq_eq)|Überprüft die Gleichheit zwischen `CSize` und einer Größe.|

## <a name="remarks"></a>Hinweise

Diese Klasse ist abgeleitet von der `SIZE` Struktur. Dies bedeutet, Sie können übergeben eine `CSize` in einem Parameter, der für eine `SIZE` und Datenmember der der `SIZE` Struktur werden die zugänglichen Datenmember `CSize`.

Die `cx` und `cy` Mitglied `SIZE` (und `CSize`) sind öffentlich. Darüber hinaus `CSize` implementiert Memberfunktionen zum Bearbeiten der `SIZE` Struktur.

> [!NOTE]
> Weitere Informationen zu freigegebenen hilfsprogrammklassen (z. B. `CSize`), finden Sie unter [gemeinsam genutzten Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`tagSIZE`

`CSize`

## <a name="requirements"></a>Anforderungen

**Header:** atltypes.h

##  <a name="csize"></a>  CSize::CSize

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
Legt die `cx` Member für die `CSize`.

*initCY*<br/>
Legt die `cy` Member für die `CSize`.

*initSize*<br/>
[Größe](/windows/desktop/api/windef/ns-windef-tagsize) Struktur oder `CSize` verwendet, um initialisieren-Objekt `CSize`.

*initPt*<br/>
[Punkt](/windows/desktop/api/windef/ns-windef-tagpoint) Struktur oder `CPoint` verwendet, um initialisieren-Objekt `CSize`.

*dwSize*<br/>
DWORD, das zum Initialisieren verwendet `CSize`. Ist das niederwertige Wort der `cx` angehört und das höherwertige Wort der `cy` Member.

### <a name="remarks"></a>Hinweise

Wenn keine Argumente angegeben werden, `cx` und `cy` auf 0 (null) initialisiert werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#97](../../atl-mfc-shared/codesnippet/cpp/csize-class_1.cpp)]

##  <a name="operator_eq_eq"></a>  CSize::operator ==

Prüft auf Gleichheit zwischen zwei Größen.

```
BOOL operator==(SIZE size) const throw();
```

### <a name="remarks"></a>Hinweise

Gibt, die ungleich NULL, wenn die Größen gleich sind, Otherwize 0 zurückgegeben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#98](../../atl-mfc-shared/codesnippet/cpp/csize-class_2.cpp)]

##  <a name="operator_neq"></a>  CSize::operator! =

Prüft auf Ungleichheit zwischen zwei Größen.

```
BOOL operator!=(SIZE size) const throw();
```

### <a name="remarks"></a>Hinweise

Ungleich NULL, wenn die Größen nicht gleich sind. gibt andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#99](../../atl-mfc-shared/codesnippet/cpp/csize-class_3.cpp)]

##  <a name="operator_add_eq"></a>  CSize::operator +=

Fügt eine Größe dieser `CSize`.

```
void operator+=(SIZE size) throw();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#100](../../atl-mfc-shared/codesnippet/cpp/csize-class_4.cpp)]

##  <a name="operator_-_eq"></a>  CSize::operator =

Eine Größe von dieser subtrahiert `CSize`.

```
void operator-=(SIZE size) throw();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#101](../../atl-mfc-shared/codesnippet/cpp/csize-class_5.cpp)]

##  <a name="operator_add"></a>  CSize::operator +

Diese Operatoren fügen `CSize` Wert, der den Wert des Parameters.

```
CSize operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="remarks"></a>Hinweise

Finden Sie unter den folgenden Beschreibungen der einzelnen Operatoren:

- **Operator + (** *Größe* **)**

  Dieser Vorgang fügt zwei `CSize` Werte.

- **Operator + (** *zeigen* **)**

  Dieser Vorgang versetzt (verschiebt) ein [Punkt](/previous-versions/dd162805\(v=vs.85\)) (oder [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)) Wert von diesem `CSize` Wert. Die `cx` und `cy` Member dieser `CSize` Wert hinzugefügt werden die `x` und `y` Datenmember der `POINT` Wert. Es ist analog zu der Version von [CPoint::operator +](../../atl-mfc-shared/reference/cpoint-class.md#operator_add) , akzeptiert eine [Größe](/windows/desktop/api/windef/ns-windef-tagsize) Parameter.

- **operator +(** *lpRect* **)**

   Dieser Vorgang versetzt (verschiebt) ein [RECT](/previous-versions/dd162897\(v=vs.85\)) (oder [CRect](../../atl-mfc-shared/reference/crect-class.md)) Wert von diesem `CSize` Wert. Die `cx` und `cy` Member dieser `CSize` Wert hinzugefügt werden die `left`, `top`, `right`, und `bottom` Datenmember der `RECT` Wert. Es ist analog zu der Version von [CRect::operator +](../../atl-mfc-shared/reference/crect-class.md#operator_add) , akzeptiert eine [Größe](/windows/desktop/api/windef/ns-windef-tagsize) Parameter.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#102](../../atl-mfc-shared/codesnippet/cpp/csize-class_6.cpp)]

##  <a name="operator_-"></a>  CSize::operator-

Die ersten drei dieser Operatoren subtrahieren dieser `CSize` Wert, der den Wert des Parameters.

```
CSize operator-(SIZE size) const throw();
CPoint operator-(POINT point) const throw();
CRect operator-(const RECT* lpRect) const throw();
CSize operator-() const throw();
```

### <a name="remarks"></a>Hinweise

Der vierte Operator, der unäres minus, ändert das Vorzeichen der `CSize` Wert. Finden Sie unter den folgenden Beschreibungen der einzelnen Operatoren:

- **Operator-(** *Größe* **)**

  Dieser Vorgang subtrahiert zwei `CSize` Werte.

- **Operator-(** *zeigen* **)**

  Dieser Vorgang versetzt (verschiebt) ein [Punkt](/previous-versions/dd162805\(v=vs.85\)) oder [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Wert durch die Additive Inverse dieser `CSize` Wert. Die `cx` und `cy` dieses `CSize` Wert subtrahiert werden die `x` und `y` Datenmember der `POINT` Wert. Es ist analog zu der Version von [CPoint::operator -](../../atl-mfc-shared/reference/cpoint-class.md#operator_-) , akzeptiert eine [Größe](/windows/desktop/api/windef/ns-windef-tagsize) Parameter.

- **operator -(** *lpRect* **)**

  Dieser Vorgang versetzt (verschiebt) ein [RECT](/previous-versions/dd162897\(v=vs.85\)) oder [CRect](../../atl-mfc-shared/reference/crect-class.md) Wert durch die Additive Inverse dieser `CSize` Wert. Die `cx` und `cy` Member dieser `CSize` Wert subtrahiert werden die `left`, `top`, `right`, und `bottom` Datenmember der `RECT` Wert. Es ist analog zu der Version von [CRect::operator -](../../atl-mfc-shared/reference/crect-class.md#operator_-) , akzeptiert eine [Größe](/windows/desktop/api/windef/ns-windef-tagsize) Parameter.

- **operator -()**

  Dieser Vorgang gibt die Additive Inverse dieser `CSize` Wert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATLMFC_Utilities#103](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]

## <a name="see-also"></a>Siehe auch

[MDI MFC-Beispiel](../../overview/visual-cpp-samples.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CRect-Klasse](../../atl-mfc-shared/reference/crect-class.md)<br/>
[CPoint-Klasse](../../atl-mfc-shared/reference/cpoint-class.md)
