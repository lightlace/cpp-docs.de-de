---
title: CD2DGeometrySink-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink::CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink::AddArc
- AFXRENDERTARGET/CD2DGeometrySink::AddBezier
- AFXRENDERTARGET/CD2DGeometrySink::AddBeziers
- AFXRENDERTARGET/CD2DGeometrySink::AddLine
- AFXRENDERTARGET/CD2DGeometrySink::AddLines
- AFXRENDERTARGET/CD2DGeometrySink::AddQuadraticBezier
- AFXRENDERTARGET/CD2DGeometrySink::AddQuadraticBeziers
- AFXRENDERTARGET/CD2DGeometrySink::BeginFigure
- AFXRENDERTARGET/CD2DGeometrySink::Close
- AFXRENDERTARGET/CD2DGeometrySink::EndFigure
- AFXRENDERTARGET/CD2DGeometrySink::Get
- AFXRENDERTARGET/CD2DGeometrySink::IsValid
- AFXRENDERTARGET/CD2DGeometrySink::SetFillMode
- AFXRENDERTARGET/CD2DGeometrySink::SetSegmentFlags
- AFXRENDERTARGET/CD2DGeometrySink::m_pSink
dev_langs:
- C++
helpviewer_keywords:
- CD2DGeometrySink [MFC], CD2DGeometrySink
- CD2DGeometrySink [MFC], AddArc
- CD2DGeometrySink [MFC], AddBezier
- CD2DGeometrySink [MFC], AddBeziers
- CD2DGeometrySink [MFC], AddLine
- CD2DGeometrySink [MFC], AddLines
- CD2DGeometrySink [MFC], AddQuadraticBezier
- CD2DGeometrySink [MFC], AddQuadraticBeziers
- CD2DGeometrySink [MFC], BeginFigure
- CD2DGeometrySink [MFC], Close
- CD2DGeometrySink [MFC], EndFigure
- CD2DGeometrySink [MFC], Get
- CD2DGeometrySink [MFC], IsValid
- CD2DGeometrySink [MFC], SetFillMode
- CD2DGeometrySink [MFC], SetSegmentFlags
- CD2DGeometrySink [MFC], m_pSink
ms.assetid: e5e07f41-0343-4ab1-9d6b-8c62ed33c04a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b97bccbf9615c90292976839f841e4b2ffe6af9d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383806"
---
# <a name="cd2dgeometrysink-class"></a>CD2DGeometrySink-Klasse

Ein Wrapper für ID2D1GeometrySink.

## <a name="syntax"></a>Syntax

```
class CD2DGeometrySink;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DGeometrySink::CD2DGeometrySink](#cd2dgeometrysink)|Erstellt ein Objekt CD2DGeometrySink CD2DPathGeometry-Objekts.|
|[CD2DGeometrySink:: ~ CD2DGeometrySink](#_dtorcd2dgeometrysink)|Der Destruktor. Wird aufgerufen, wenn Senke D2D Geometry-Objekt zerstört wird.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CD2DGeometrySink::AddArc](#addarc)|Fügt einem einzelnen Bogen der Pfadgeometrie hinzu|
|[CD2DGeometrySink::AddBezier](#addbezier)|Erstellt eine kubische Bézierkurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt.|
|[CD2DGeometrySink::AddBeziers](#addbeziers)|Erstellt eine Sequenz von kubische Bezier-Kurven und fügt diese an die Geometriesenke.|
|[CD2DGeometrySink::AddLine](#addline)|Erstellt ein Liniensegment zwischen dem aktuellen Punkt und dem angegebenen Endpunkt und fügt es auf die Geometriesenke.|
|[CD2DGeometrySink::AddLines](#addlines)|Erstellt eine Sequenz von Zeilen, die mit den angegebenen Punkten und die Geometriesenke hinzugefügt.|
|[CD2DGeometrySink::AddQuadraticBezier](#addquadraticbezier)|Erstellt eine quadratische Bezierkurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt.|
|[CD2DGeometrySink::AddQuadraticBeziers](#addquadraticbeziers)|Fügt eine Sequenz von quadratischen Bezier-Segmente als ein Array, in einem einzigen Aufruf hinzu.|
|[CD2DGeometrySink::BeginFigure](#beginfigure)|Startet eine neue Figur am angegebenen Punkt.|
|[CD2DGeometrySink::Close](#close)|Schließt die Geometriesenke|
|[CD2DGeometrySink::EndFigure](#endfigure)|Beendet die aktuelle Figur an; optional, wird geschlossen.|
|[CD2DGeometrySink::Get](#get)|Gibt die ID2D1GeometrySink-Schnittstelle|
|[CD2DGeometrySink::IsValid](#isvalid)|Überprüft die Gültigkeit der Geometrie-Senke|
|[CD2DGeometrySink::SetFillMode](#setfillmode)|Gibt die Methode verwendet, um zu bestimmen, welche Punkte innerhalb der Geometrie, die von dieser Geometriesenke beschrieben und außerhalb.|
|[CD2DGeometrySink::SetSegmentFlags](#setsegmentflags)|Gibt an, Strich und Join-Optionen auf neuen Segmenten, die die Geometriesenke hinzugefügt angewendet werden.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DGeometrySink::Operator ID2D1GeometrySink *](#operator_id2d1geometrysink_star)|Gibt die ID2D1GeometrySink-Schnittstelle|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CD2DGeometrySink::m_pSink](#m_psink)|Ein Zeiger auf ein ID2D1GeometrySink.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CD2DGeometrySink`

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget.h

##  <a name="_dtorcd2dgeometrysink"></a>  CD2DGeometrySink:: ~ CD2DGeometrySink

Der Destruktor. Wird aufgerufen, wenn Senke D2D Geometry-Objekt zerstört wird.

```
virtual ~CD2DGeometrySink();
```

##  <a name="addarc"></a>  CD2DGeometrySink::AddArc

Fügt einem einzelnen Bogen der Pfadgeometrie hinzu

```
void AddArc(const D2D1_ARC_SEGMENT& arc);
```

### <a name="parameters"></a>Parameter

*Einen Bogen konvertiert.*<br/>
Das Bogensegment in der Abbildung hinzu

##  <a name="addbezier"></a>  CD2DGeometrySink::AddBezier

Erstellt eine kubische Bézierkurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt.

```
void AddBezier(const D2D1_BEZIER_SEGMENT& bezier);
```

### <a name="parameters"></a>Parameter

*Bezier*<br/>
Eine Struktur, die beschreibt, die Control-Punkte und Endpunkt der Bezier-Kurve hinzufügen.

##  <a name="addbeziers"></a>  CD2DGeometrySink::AddBeziers

Erstellt eine Sequenz von kubische Bezier-Kurven und fügt diese an die Geometriesenke.

```
void AddBeziers(
    const CArray<D2D1_BEZIER_SEGMENT,
    D2D1_BEZIER_SEGMENT>& beziers);
```

### <a name="parameters"></a>Parameter

*Beziers*<br/>
Ein Array von Bezier-Segmente, die beschreibt, die Bezier-Kurven zu erstellen. Eine Kurve gezeichnet wird an den Endpunkt, der das erste Bezier-Segment in das Array vom aktuellen Punkt von der Geometriesenke (der Endpunkt das letzte Segment gezeichnet oder den Speicherort, der durch BeginFigure angegeben). Wenn das Array zusätzliche Bezier-Segmente enthält, verwendet jedes nachfolgende Bezier-Segment der Endpunkt des vorherigen Segments Bezier als Anfangspunkt.

##  <a name="addline"></a>  CD2DGeometrySink::AddLine

Erstellt ein Liniensegment zwischen dem aktuellen Punkt und dem angegebenen Endpunkt und fügt es auf die Geometriesenke.

```
void AddLine(CD2DPointF point);
```

### <a name="parameters"></a>Parameter

*Zeigen Sie*<br/>
Der Endpunkt der Linie zu zeichnen.

##  <a name="addlines"></a>  CD2DGeometrySink::AddLines

Erstellt eine Sequenz von Zeilen, die mit den angegebenen Punkten und die Geometriesenke hinzugefügt.

```
void AddLines(
    const CArray<CD2DPointF,
    CD2DPointF>& points);
```

### <a name="parameters"></a>Parameter

*Punkte*<br/>
Ein Array von einem oder mehreren Punkten, die beschreiben, die Zeilen, die gezeichnet werden soll. Eine Zeile wird dem ersten Punkt im Array vom aktuellen Punkt von der Geometriesenke (der Endpunkt das letzte Segment gezeichnet oder den Speicherort, der anhand des BeginFigure) gezeichnet. Wenn das Array zusätzliche Punkte enthält, wird eine Linie zwischen dem ersten zum zweiten Punkt im Array, aus der zweiten, zeigen Sie auf der dritten Punkt usw. gezeichnet. Ein Array aus einer Folge von den Endpunkten der Linien zu zeichnen.

##  <a name="addquadraticbezier"></a>  CD2DGeometrySink::AddQuadraticBezier

Erstellt eine quadratische Bezierkurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt.

```
void AddQuadraticBezier(const D2D1_QUADRATIC_BEZIER_SEGMENT& bezier);
```

### <a name="parameters"></a>Parameter

*Bezier*<br/>
Eine Struktur, die beschreibt, der Kontrollpunkt und dem Endpunkt der quadratischen Bezier-Kurve hinzufügen.

##  <a name="addquadraticbeziers"></a>  CD2DGeometrySink::AddQuadraticBeziers

Fügt eine Sequenz von quadratischen Bezier-Segmente als ein Array, in einem einzigen Aufruf hinzu.

```
void AddQuadraticBeziers(
    const CArray<D2D1_QUADRATIC_BEZIER_SEGMENT,
    D2D1_QUADRATIC_BEZIER_SEGMENT>& beziers);
```

### <a name="parameters"></a>Parameter

*Beziers*<br/>
Ein Array aus einer Folge von quadratischen Bezier-Segmente.

##  <a name="beginfigure"></a>  CD2DGeometrySink::BeginFigure

Startet eine neue Figur am angegebenen Punkt.

```
void BeginFigure(
    CD2DPointF startPoint,
    D2D1_FIGURE_BEGIN figureBegin);
```

### <a name="parameters"></a>Parameter

*startPoint*<br/>
Der Punkt, an dem die neue Abbildung beginnt.

*figureBegin*<br/>
Gibt an, ob die neue Abbildung gefüllt oder sein sollte.

##  <a name="cd2dgeometrysink"></a>  CD2DGeometrySink::CD2DGeometrySink

Erstellt ein Objekt CD2DGeometrySink CD2DPathGeometry-Objekts.

```
CD2DGeometrySink(CD2DPathGeometry& pathGeometry);
```

### <a name="parameters"></a>Parameter

*pathGeometry*<br/>
Ein vorhandenes CD2DPathGeometry-Objekt.

##  <a name="close"></a>  CD2DGeometrySink::Close

Schließt die Geometriesenke

```
BOOL Close();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL Wenn erfolgreich; andernfalls "false".

##  <a name="endfigure"></a>  CD2DGeometrySink::EndFigure

Beendet die aktuelle Figur an; optional, wird geschlossen.

```
void EndFigure(D2D1_FIGURE_END figureEnd);
```

### <a name="parameters"></a>Parameter

*figureEnd*<br/>
Ein Wert, der angibt, ob die aktuelle Figur geschlossen ist. Wenn die Abbildung geschlossen ist, wird eine Linie zwischen dem aktuellen Punkt und den Startpunkt mit BeginFigure angegebenen gezeichnet.

##  <a name="get"></a>  CD2DGeometrySink::Get

Gibt die ID2D1GeometrySink-Schnittstelle

```
ID2D1GeometrySink* Get();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine ID2D1GeometrySink-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

##  <a name="isvalid"></a>  CD2DGeometrySink::IsValid

Überprüft die Gültigkeit der Geometrie-Senke

```
BOOL IsValid() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn die Geometriesenke gültig ist. andernfalls "false".

##  <a name="m_psink"></a>  CD2DGeometrySink::m_pSink

Ein Zeiger auf ein ID2D1GeometrySink.

```
ID2D1GeometrySink* m_pSink;
```

##  <a name="operator_id2d1geometrysink_star"></a>  CD2DGeometrySink::Operator ID2D1GeometrySink *

Gibt die ID2D1GeometrySink-Schnittstelle

```
operator ID2D1GeometrySink*();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine ID2D1GeometrySink-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

##  <a name="setfillmode"></a>  CD2DGeometrySink::SetFillMode

Gibt die Methode verwendet, um zu bestimmen, welche Punkte innerhalb der Geometrie, die von dieser Geometriesenke beschrieben und außerhalb.

```
void SetFillMode(D2D1_FILL_MODE fillMode);
```

### <a name="parameters"></a>Parameter

*fillMode*<br/>
Die Methode verwendet, um zu bestimmen, ob ein bestimmter Punkt Teil der Geometrie ist.

##  <a name="setsegmentflags"></a>  CD2DGeometrySink::SetSegmentFlags

Gibt an, Strich und Join-Optionen auf neuen Segmenten, die die Geometriesenke hinzugefügt angewendet werden.

```
void SetSegmentFlags(D2D1_PATH_SEGMENT vertexFlags);
```

### <a name="parameters"></a>Parameter

*vertexFlags*<br/>
Optionen für Strich und Join auf neuen Segmenten, die die Geometriesenke hinzugefügt angewendet werden.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
