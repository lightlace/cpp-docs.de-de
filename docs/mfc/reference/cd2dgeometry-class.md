---
title: CD2DGeometry-Klasse
ms.date: 11/04/2016
f1_keywords:
- CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry::CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry::Attach
- AFXRENDERTARGET/CD2DGeometry::CombineWithGeometry
- AFXRENDERTARGET/CD2DGeometry::CompareWithGeometry
- AFXRENDERTARGET/CD2DGeometry::ComputeArea
- AFXRENDERTARGET/CD2DGeometry::ComputeLength
- AFXRENDERTARGET/CD2DGeometry::ComputePointAtLength
- AFXRENDERTARGET/CD2DGeometry::Destroy
- AFXRENDERTARGET/CD2DGeometry::Detach
- AFXRENDERTARGET/CD2DGeometry::FillContainsPoint
- AFXRENDERTARGET/CD2DGeometry::Get
- AFXRENDERTARGET/CD2DGeometry::GetBounds
- AFXRENDERTARGET/CD2DGeometry::GetWidenedBounds
- AFXRENDERTARGET/CD2DGeometry::IsValid
- AFXRENDERTARGET/CD2DGeometry::Outline
- AFXRENDERTARGET/CD2DGeometry::Simplify
- AFXRENDERTARGET/CD2DGeometry::StrokeContainsPoint
- AFXRENDERTARGET/CD2DGeometry::Tessellate
- AFXRENDERTARGET/CD2DGeometry::Widen
- AFXRENDERTARGET/CD2DGeometry::m_pGeometry
helpviewer_keywords:
- CD2DGeometry [MFC], CD2DGeometry
- CD2DGeometry [MFC], Attach
- CD2DGeometry [MFC], CombineWithGeometry
- CD2DGeometry [MFC], CompareWithGeometry
- CD2DGeometry [MFC], ComputeArea
- CD2DGeometry [MFC], ComputeLength
- CD2DGeometry [MFC], ComputePointAtLength
- CD2DGeometry [MFC], Destroy
- CD2DGeometry [MFC], Detach
- CD2DGeometry [MFC], FillContainsPoint
- CD2DGeometry [MFC], Get
- CD2DGeometry [MFC], GetBounds
- CD2DGeometry [MFC], GetWidenedBounds
- CD2DGeometry [MFC], IsValid
- CD2DGeometry [MFC], Outline
- CD2DGeometry [MFC], Simplify
- CD2DGeometry [MFC], StrokeContainsPoint
- CD2DGeometry [MFC], Tessellate
- CD2DGeometry [MFC], Widen
- CD2DGeometry [MFC], m_pGeometry
ms.assetid: 3f95054b-fdb8-4e87-87f2-9fc3df7279ec
ms.openlocfilehash: 4549b2e7981d5f8493ddf9f24477e75a94ddde8b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57271228"
---
# <a name="cd2dgeometry-class"></a>CD2DGeometry-Klasse

Ein Wrapper für die ID2D1Geometry.

## <a name="syntax"></a>Syntax

```
class CD2DGeometry : public CD2DResource;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DGeometry::CD2DGeometry](#cd2dgeometry)|Erstellt ein CD2DGeometry-Objekt.|
|[CD2DGeometry::~CD2DGeometry](#_dtorcd2dgeometry)|Der Destruktor. Wird aufgerufen, wenn ein D2D-Geometry-Objekt zerstört wird.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CD2DGeometry::Attach](#attach)|Hängt die vorhandene Ressourcenschnittstelle für das Objekt|
|[CD2DGeometry::CombineWithGeometry](#combinewithgeometry)|Kombiniert diese Geometrie mit der angegebenen Geometrie und speichert das Ergebnis in eine ID2D1SimplifiedGeometrySink.|
|[CD2DGeometry::CompareWithGeometry](#comparewithgeometry)|Beschreibt die Schnittmenge dieser Geometrie und der angegebenen Geometrie. Der Vergleich erfolgt mit der angegebenen flattening Toleranz.|
|[CD2DGeometry::ComputeArea](#computearea)|Der Bereich der Geometrie berechnet, nachdem sie wurde von der angegebenen Matrix transformiert und mit der angegebenen Toleranz vereinfacht.|
|[CD2DGeometry::ComputeLength](#computelength)|Berechnet die Länge der Geometry-Instanz, als ob jedes Segment in eine Zeile nicht entrollten wäre.|
|[CD2DGeometry::ComputePointAtLength](#computepointatlength)|Den Vektor und Tangentenendpunkte im angegebenen Abstand entlang der Geometrie berechnet, nachdem sie wurde von der angegebenen Matrix transformiert und mit der angegebenen Toleranz vereinfacht.|
|[CD2DGeometry::Destroy](#destroy)|Zerstört ein CD2DGeometry-Objekt. (Überschreibt [CD2DResource:: Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DGeometry::Detach](#detach)|Resource-Schnittstelle aus dem Objekt getrennt|
|[CD2DGeometry::FillContainsPoint](#fillcontainspoint)|Gibt an, ob der Bereich gefüllt, die durch die Geometrie einen angegebenen Punkt, die angegebene flattening Toleranz enthält.|
|[CD2DGeometry::Get](#get)|Gibt die ID2D1Geometry-Schnittstelle|
|[CD2DGeometry::GetBounds](#getbounds)||
|[CD2DGeometry::GetWidenedBounds](#getwidenedbounds)|Ruft die Begrenzungen der Geometry-Instanz ab, nachdem er erweitert, indem die angegebenen Strichbreite und den Stil und mit der angegebenen Matrix transformiert wurde.|
|[CD2DGeometry::IsValid](#isvalid)|Überprüft die Gültigkeit der Ressource (überschreibt [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DGeometry::Outline](#outline)|Berechnet die Kontur der Geometrie und schreibt das Ergebnis in eine ID2D1SimplifiedGeometrySink.|
|[CD2DGeometry::Simplify](#simplify)|Erstellt eine vereinfachte Version der Geometry-Instanz, die nur die Zeilen und (optional) kubische Bezier-Kurven enthält und schreibt das Ergebnis in eine ID2D1SimplifiedGeometrySink.|
|[CD2DGeometry::StrokeContainsPoint](#strokecontainspoint)|Bestimmt, ob der Strich der Geometrie den angegebenen Punkt, der anhand der angegebenen Strichstärke, Stil und Transformation enthält.|
|[CD2DGeometry::Tessellate](#tessellate)|Erstellt einen Satz von Uhrzeigerrichtung, die die Geometrie abdecken, nachdem sie mit der angegebenen Matrix transformiert wurde, und mit der angegebenen Toleranz vereinfacht.|
|[CD2DGeometry::Widen](#widen)|Erweitert die Geometrie, indem der angegebene Strich und schreibt Sie das Ergebnis in eine ID2D1SimplifiedGeometrySink, nachdem sie wurde von der angegebenen Matrix transformiert und mit der angegebenen Toleranz vereinfacht.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DGeometry::Operator ID2D1Geometry *](#operator_id2d1geometry_star)|Gibt die ID2D1Geometry-Schnittstelle|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CD2DGeometry::m_pGeometry](#m_pgeometry)|Ein Zeiger auf ein ID2D1Geometry.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DGeometry`

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget.h

##  <a name="_dtorcd2dgeometry"></a>  CD2DGeometry:: ~ CD2DGeometry

Der Destruktor. Wird aufgerufen, wenn ein D2D-Geometry-Objekt zerstört wird.

```
virtual ~CD2DGeometry();
```

##  <a name="attach"></a>  CD2DGeometry::Attach

Hängt die vorhandene Ressourcenschnittstelle für das Objekt

```
void Attach(ID2D1Geometry* pResource);
```

### <a name="parameters"></a>Parameter

*pResource*<br/>
Vorhandene Ressourcenschnittstelle. NULL darf nicht sein

##  <a name="cd2dgeometry"></a>  CD2DGeometry::CD2DGeometry

Erstellt ein CD2DGeometry-Objekt.

```
CD2DGeometry(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parameter

*pParentTarget*<br/>
Ein Zeiger auf das Renderziel.

*bAutoDestroy*<br/>
Gibt an, dass vom Besitzer (pParentTarget) das Objekt zerstört wird.

##  <a name="combinewithgeometry"></a>  CD2DGeometry::CombineWithGeometry

Kombiniert diese Geometrie mit der angegebenen Geometrie und speichert das Ergebnis in eine ID2D1SimplifiedGeometrySink.

```
BOOL CombineWithGeometry(
    CD2DGeometry& inputGeometry,
    D2D1_COMBINE_MODE combineMode,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parameter

*inputGeometry*<br/>
Die Geometrie, die mit dieser Instanz.

*combineMode*<br/>
Der Typ des auszuführenden kombinieren-Vorgangs.

*inputGeometryTransform*<br/>
Die Transformation auf InputGeometry vor dem vereinen angewendet.

*geometrySink*<br/>
Das Ergebnis des Vorgangs kombinieren.

*flatteningTolerance*<br/>
Die maximalen Grenzen für die Entfernung zwischen Punkten in der polygonalen Approximation der Geometrien. Kleinere Werte liefern genauere Ergebnisse jedoch dazu führen, dass Ausführung verlangsamt.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird "true" zurückgegeben. Andernfalls wird FALSE zurückgegeben.

##  <a name="comparewithgeometry"></a>  CD2DGeometry::CompareWithGeometry

Beschreibt die Schnittmenge dieser Geometrie und der angegebenen Geometrie. Der Vergleich erfolgt mit der angegebenen flattening Toleranz.

```
D2D1_GEOMETRY_RELATION CompareWithGeometry(
    CD2DGeometry& inputGeometry,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parameter

*inputGeometry*<br/>
Die Geometrie um zu testen.

*inputGeometryTransform*<br/>
Die Transformation auf InputGeometry angewendet.

*flatteningTolerance*<br/>
Die maximalen Grenzen für die Entfernung zwischen Punkten in der polygonalen Approximation der Geometrien. Kleinere Werte liefern genauere Ergebnisse jedoch dazu führen, dass Ausführung verlangsamt.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird "true" zurückgegeben. Andernfalls wird FALSE zurückgegeben.

##  <a name="computearea"></a>  CD2DGeometry::ComputeArea

Der Bereich der Geometrie berechnet, nachdem sie wurde von der angegebenen Matrix transformiert und mit der angegebenen Toleranz vereinfacht.

```
BOOL ComputeArea(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& area,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parameter

*worldTransform*<br/>
Die Transformation, die auf dieser Geometrie anwenden, bevor seine Fläche berechnen.

*area*<br/>
Bei der Rückgabe dieser Methode enthält einen Zeiger auf den Bereich der transformierten, vereinfachte Version dieser Geometrie. Sie müssen diesen Parameter Speicher zuweisen.

*flatteningTolerance*<br/>
Die maximalen Grenzen für die Entfernung zwischen Punkten in der polygonalen Approximation der Geometrie. Kleinere Werte liefern genauere Ergebnisse jedoch dazu führen, dass Ausführung verlangsamt.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird "true" zurückgegeben. Andernfalls wird FALSE zurückgegeben.

##  <a name="computelength"></a>  CD2DGeometry::ComputeLength

Berechnet die Länge der Geometry-Instanz, als ob jedes Segment in eine Zeile nicht entrollten wäre.

```
BOOL ComputeLength(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& length,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parameter

*worldTransform*<br/>
Die Transformation auf die Geometrie angewendet werden soll, vor der Berechnung seine Länge.

*length*<br/>
Bei der Rückgabe dieser Methode enthält einen Zeiger auf die Länge der Geometry-Instanz. Für geschlossene Geometrien enthält die Länge ein Segments implizite schließen. Sie müssen diesen Parameter Speicher zuweisen.

*flatteningTolerance*<br/>
Die maximalen Grenzen für die Entfernung zwischen Punkten in der polygonalen Approximation der Geometrie. Kleinere Werte liefern genauere Ergebnisse jedoch dazu führen, dass Ausführung verlangsamt.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird "true" zurückgegeben. Andernfalls wird FALSE zurückgegeben.

##  <a name="computepointatlength"></a>  CD2DGeometry::ComputePointAtLength

Den Vektor und Tangentenendpunkte im angegebenen Abstand entlang der Geometrie berechnet, nachdem sie wurde von der angegebenen Matrix transformiert und mit der angegebenen Toleranz vereinfacht.

```
BOOL ComputePointAtLength(
    FLOAT length,
    const D2D1_MATRIX_3X2_F& worldTransform,
    CD2DPointF& point,
    CD2DPointF& unitTangentVector,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parameter

*length*<br/>
Die Entfernung entlang der Geometrie der Punkt und Tangens gefunden. Wenn dieser Abstand kleiner 0 ist, wird diese Methode den ersten Punkt in der Geometrie berechnet. Wenn dieser Abstand größer als die Länge der Geometry-Instanz ist, wird diese Methode den letzten Punkt in der Geometrie berechnet.

*worldTransform*<br/>
Die Transformation, vor dem Berechnen des angegebenen Punkt und der Tangens auf die Geometrie angewendet werden soll.

*point*<br/>
Die Position, an der angegebenen Entfernung entlang der Geometrie werden soll. Wenn die Geometrie leer ist, enthält dieser Punkt NaN als x und y Werte.

*unitTangentVector*<br/>
Bei der Rückgabe dieser Methode enthält einen Zeiger auf den Tangentenvektor im angegebenen Abstand entlang der Geometrie. Wenn die Geometrie leer ist, enthält dieses Vektors NaN als seine x- und y Werte. Sie müssen diesen Parameter Speicher zuweisen.

*flatteningTolerance*<br/>
Die maximalen Grenzen für die Entfernung zwischen Punkten in der polygonalen Approximation der Geometrie. Kleinere Werte liefern genauere Ergebnisse jedoch dazu führen, dass Ausführung verlangsamt.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird "true" zurückgegeben. Andernfalls wird FALSE zurückgegeben.

##  <a name="destroy"></a>  CD2DGeometry:: Destroy

Zerstört ein CD2DGeometry-Objekt.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DGeometry::Detach

Resource-Schnittstelle aus dem Objekt getrennt

```
ID2D1Geometry* Detach();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf getrennten Resource-Schnittstelle.

##  <a name="fillcontainspoint"></a>  CD2DGeometry::FillContainsPoint

Gibt an, ob der Bereich gefüllt, die durch die Geometrie einen angegebenen Punkt, die angegebene flattening Toleranz enthält.

```
BOOL FillContainsPoint(
    CD2DPointF point,
    const D2D1_MATRIX_3X2_F& worldTransform,
    BOOL* contains,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parameter

*point*<br/>
Der Punkt, um zu testen.

*worldTransform*<br/>
Die Transformation angewendet auf die Geometrie vor dem Testen, für die Kapselung.

*contains*<br/>
Bei der Rückgabe dieser Methode enthält einen booleschen Wert, der TRUE ist, wenn die von der Geometrie ausgefüllte Bereich Punkt enthält; andernfalls "false". Sie müssen diesen Parameter Speicher zuweisen.

*flatteningTolerance*<br/>
Die numerische Genauigkeit, mit denen der genaue geometrischen Pfad und der Pfadschnittmenge wird berechnet. Fehlt die Füllung von weniger als die Toleranz Punkte gelten weiterhin in. Kleinere Werte liefern genauere Ergebnisse jedoch dazu führen, dass Ausführung verlangsamt.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird "true" zurückgegeben. Andernfalls wird FALSE zurückgegeben.

##  <a name="get"></a>  CD2DGeometry::Get

Gibt die ID2D1Geometry-Schnittstelle

```
ID2D1Geometry* Get();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf ein ID2D1Geometry-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

##  <a name="getbounds"></a>  CD2DGeometry::GetBounds

```
BOOL GetBounds(
const D2D1_MATRIX_3X2_F& worldTransform,
CD2DRectF& bounds) const;
```

### <a name="parameters"></a>Parameter

*worldTransform*<br/>
*bounds*

### <a name="return-value"></a>Rückgabewert

##  <a name="getwidenedbounds"></a>  CD2DGeometry::GetWidenedBounds

Ruft die Begrenzungen der Geometry-Instanz ab, nachdem er erweitert, indem die angegebenen Strichbreite und den Stil und mit der angegebenen Matrix transformiert wurde.

```
BOOL GetWidenedBounds(
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    CD2DRectF& bounds,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parameter

*strokeWidth*<br/>
Der Betrag, um die Kontur zuweisen seine Kontur die Geometrie verbreitern.

*strokeStyle*<br/>
Der Stil der Kontur, die die Geometrie erweitert werden kann.

*worldTransform*<br/>
Eine Transformation auf die Geometrie angewendet werden soll, nachdem die Geometrie transformiert und die Geometrie-Element gezeichnet worden ist.

*bounds*<br/>
Bei der Rückgabe dieser Methode enthält die Begrenzungen des erweiterten Geometrie. Sie müssen diesen Parameter Speicher zuweisen.

*flatteningTolerance*<br/>
Die maximalen Grenzen für die Entfernung zwischen Punkten in der polygonalen Approximation der Geometrien. Kleinere Werte liefern genauere Ergebnisse jedoch dazu führen, dass Ausführung verlangsamt.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird "true" zurückgegeben. Andernfalls wird FALSE zurückgegeben.

##  <a name="isvalid"></a>  CD2DGeometry::IsValid

Die Gültigkeit der Überprüfungen-Ressource

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn die Ressource gültig ist. andernfalls "false".

##  <a name="m_pgeometry"></a>  CD2DGeometry::m_pGeometry

Ein Zeiger auf ein ID2D1Geometry.

```
ID2D1Geometry* m_pGeometry;
```

##  <a name="operator_id2d1geometry_star"></a>  CD2DGeometry::Operator ID2D1Geometry *

Gibt die ID2D1Geometry-Schnittstelle

```
operator ID2D1Geometry*();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf ein ID2D1Geometry-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

##  <a name="outline"></a>  CD2DGeometry::Outline

Berechnet die Kontur der Geometrie und schreibt das Ergebnis in eine ID2D1SimplifiedGeometrySink.

```
BOOL Outline(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parameter

*worldTransform*<br/>
Die Transformation, um die Kontur der Geometrie angewendet werden soll.

*geometrySink*<br/>
Die ID2D1SimplifiedGeometrySink, der die transformierten Geometrie-Gliederung angefügt wird.

*flatteningTolerance*<br/>
Die maximalen Grenzen für die Entfernung zwischen Punkten in der polygonalen Approximation der Geometrie. Kleinere Werte liefern genauere Ergebnisse jedoch dazu führen, dass Ausführung verlangsamt.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird "true" zurückgegeben. Andernfalls wird FALSE zurückgegeben.

##  <a name="simplify"></a>  CD2DGeometry::Simplify

Erstellt eine vereinfachte Version der Geometry-Instanz, die nur die Zeilen und (optional) kubische Bezier-Kurven enthält und schreibt das Ergebnis in eine ID2D1SimplifiedGeometrySink.

```
BOOL Simplify(
    D2D1_GEOMETRY_SIMPLIFICATION_OPTION simplificationOption,
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parameter

*simplificationOption*<br/>
Ein Wert, der angibt, ob die vereinfachte Geometrie Kurven enthalten soll.

*worldTransform*<br/>
Die Transformation, um die vereinfachte Geometrie angewendet werden soll.

*geometrySink*<br/>
Die ID2D1SimplifiedGeometrySink, die die vereinfachte Geometrie angefügt wird.

*flatteningTolerance*<br/>
Die maximalen Grenzen für die Entfernung zwischen Punkten in der polygonalen Approximation der Geometrie. Kleinere Werte liefern genauere Ergebnisse jedoch dazu führen, dass Ausführung verlangsamt.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird "true" zurückgegeben. Andernfalls wird FALSE zurückgegeben.

##  <a name="strokecontainspoint"></a>  CD2DGeometry::StrokeContainsPoint

Bestimmt, ob der Strich der Geometrie den angegebenen Punkt, der anhand der angegebenen Strichstärke, Stil und Transformation enthält.

```
BOOL StrokeContainsPoint(
    CD2DPointF point,
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    BOOL* contains,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parameter

*point*<br/>
Der zu überprüfende Punkt.

*strokeWidth*<br/>
Die Stärke des Strichs angewendet werden soll.

*strokeStyle*<br/>
Der Stil des Strichs angewendet werden soll.

*worldTransform*<br/>
Die Transformation auf die Geometrie gestrichelt angewendet.

*contains*<br/>
Bei der Rückgabe dieser Methode enthält einen booleschen Wert, der auf "true" festgelegt wird, wenn der Strich der Geometrie den angegebenen Punkt enthält. andernfalls "false". Sie müssen diesen Parameter Speicher zuweisen.

*flatteningTolerance*<br/>
Die numerische Genauigkeit, mit denen der genaue geometrischen Pfad und der Pfadschnittmenge wird berechnet. Zeigt den Strich von weniger als die Toleranz fehlt gelten weiterhin in. Kleinere Werte liefern genauere Ergebnisse jedoch dazu führen, dass Ausführung verlangsamt.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird "true" zurückgegeben. Andernfalls wird FALSE zurückgegeben.

##  <a name="tessellate"></a>  CD2DGeometry::Tessellate

Erstellt einen Satz von Uhrzeigerrichtung, die die Geometrie abdecken, nachdem sie mit der angegebenen Matrix transformiert wurde, und mit der angegebenen Toleranz vereinfacht.

```
BOOL Tessellate(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1TessellationSink* tessellationSink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parameter

*worldTransform*<br/>
Die Transformation angewendet auf dieser Geometrie oder NULL.

*tessellationSink*<br/>
Die ID2D1TessellationSink, zu dem der Mosaikprozess angefügt wird.

*flatteningTolerance*<br/>
Die maximalen Grenzen für die Entfernung zwischen Punkten in der polygonalen Approximation der Geometrie. Kleinere Werte liefern genauere Ergebnisse jedoch dazu führen, dass Ausführung verlangsamt.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird "true" zurückgegeben. Andernfalls wird FALSE zurückgegeben.

##  <a name="widen"></a>  CD2DGeometry::Widen

Erweitert die Geometrie, indem der angegebene Strich und schreibt Sie das Ergebnis in eine ID2D1SimplifiedGeometrySink, nachdem sie wurde von der angegebenen Matrix transformiert und mit der angegebenen Toleranz vereinfacht.

```
BOOL Widen(
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parameter

*strokeWidth*<br/>
Der Betrag, um die Geometrie zu erweitern.

*strokeStyle*<br/>
Der Stil des Strichs der Geometrie oder NULL zuweisen.

*worldTransform*<br/>
Die Transformation auf die Geometrie angewendet werden, nach dem erweitern.

*geometrySink*<br/>
Die ID2D1SimplifiedGeometrySink, die die vergrößerte Geometrie angefügt wird.

*flatteningTolerance*<br/>
Die maximalen Grenzen für die Entfernung zwischen Punkten in der polygonalen Approximation der Geometrie. Kleinere Werte liefern genauere Ergebnisse jedoch dazu führen, dass Ausführung verlangsamt.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird "true" zurückgegeben. Andernfalls wird FALSE zurückgegeben.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
