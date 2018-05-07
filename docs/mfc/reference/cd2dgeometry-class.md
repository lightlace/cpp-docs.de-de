---
title: CD2DGeometry-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 05bfd912d3c4b6ee8b462775f6919c5fe81cc936
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cd2dgeometry-class"></a>CD2DGeometry-Klasse
Ein Wrapper für ID2D1Geometry.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DGeometry : public CD2DResource;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DGeometry::CD2DGeometry](#cd2dgeometry)|Erstellt ein CD2DGeometry-Objekt.|  
|[CD2DGeometry:: ~ CD2DGeometry](#_dtorcd2dgeometry)|Der Destruktor. Wird aufgerufen, wenn ein D2D-Geometry-Objekt zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DGeometry::Attach](#attach)|Hängt die vorhandene Ressourcenschnittstelle, um das Objekt|  
|[CD2DGeometry::CombineWithGeometry](#combinewithgeometry)|Diese Geometrie mit dem angegebenen Geometry kombiniert und speichert das Ergebnis in eine ID2D1SimplifiedGeometrySink.|  
|[CD2DGeometry::CompareWithGeometry](#comparewithgeometry)|Beschreibt die Schnittmenge dieser Geometry-Datentyp und die angegebene Geometrie. Der Vergleich erfolgt mithilfe der angegebenen flattening Toleranz.|  
|[CD2DGeometry::ComputeArea](#computearea)|Berechnet den Bereich der Geometry-Instanz, nachdem sie wurde mit der angegebenen Matrix transformiert und mit der angebenen Toleranz vereinfacht.|  
|[CD2DGeometry::ComputeLength](#computelength)|Berechnet die Länge der Geometrie, als wäre jedes Segment in eine Linie unrolled.|  
|[CD2DGeometry::ComputePointAtLength](#computepointatlength)|Den Vektor und Tangentenendpunkte im angegebenen Abstand entlang der Geometrie berechnet, nachdem sie wurde mit der angegebenen Matrix transformiert und mit der angebenen Toleranz vereinfacht.|  
|[CD2DGeometry:: Destroy](#destroy)|Zerstört ein CD2DGeometry-Objekt. (Überschreibt [CD2DResource:: Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DGeometry::Detach](#detach)|Trennt Ressourcenschnittstelle aus dem Objekt|  
|[CD2DGeometry::FillContainsPoint](#fillcontainspoint)|Gibt an, ob die Fläche ausgefüllt, die durch die Geometrie einen angegebenen Punkt, die angegebene flattening Toleranz enthalten würde.|  
|[CD2DGeometry::Get](#get)|Gibt die ID2D1Geometry-Schnittstelle|  
|[CD2DGeometry::GetBounds](#getbounds)||  
|[CD2DGeometry::GetWidenedBounds](#getwidenedbounds)|Ruft die Grenzen der Geometrie ab, nachdem er erweitert, indem die angegebenen Strichbreite und den Stil und mit der angegebenen Matrix transformiert wurde.|  
|[CD2DGeometry::IsValid](#isvalid)|Überprüft die Gültigkeit der Ressource (Außerkraftsetzungen [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
|[CD2DGeometry::Outline](#outline)|Berechnet die Kontur der Geometrie und schreibt das Ergebnis in eine ID2D1SimplifiedGeometrySink.|  
|[CD2DGeometry::Simplify](#simplify)|Erstellt eine vereinfachte Version der Geometry-Instanz, die nur Linien und (optional) kubische Bézier-Kurven enthält und schreibt das Ergebnis in eine ID2D1SimplifiedGeometrySink.|  
|[CD2DGeometry::StrokeContainsPoint](#strokecontainspoint)|Bestimmt, ob die Geometrie Strich einen angegebenen Punkt, den angegebenen Schriftstärke,-Stil und -Transformation enthält.|  
|[CD2DGeometry::Tessellate](#tessellate)|Erstellt einen Satz von Uhrzeigerrichtung, die die Geometrie abdecken, nachdem er mit der angegebenen Matrix transformiert wurde, und mit der angebenen Toleranz vereinfacht.|  
|[CD2DGeometry::Widen](#widen)|Erweitert die Geometrie der angegebenen Striche und das Ergebnis in eine ID2D1SimplifiedGeometrySink schreibt, nachdem sie wurde mit der angegebenen Matrix transformiert und mit der angebenen Toleranz vereinfacht.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DGeometry::Operator ID2D1Geometry *](#operator_id2d1geometry_star)|Gibt die ID2D1Geometry-Schnittstelle|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CD2DGeometry::m_pGeometry](#m_pgeometry)|Ein Zeiger auf eine ID2D1Geometry.|  
  
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
 Hängt die vorhandene Ressourcenschnittstelle, um das Objekt  
  
```  
void Attach(ID2D1Geometry* pResource);
```  
  
### <a name="parameters"></a>Parameter  
 `pResource`  
 Vorhandene Ressourcenschnittstelle. NULL darf nicht sein  
  
##  <a name="cd2dgeometry"></a>  CD2DGeometry::CD2DGeometry  
 Erstellt ein CD2DGeometry-Objekt.  
  
```  
CD2DGeometry(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentTarget`  
 Ein Zeiger auf das Renderziel.  
  
 `bAutoDestroy`  
 Gibt an, dass das Objekt vom Besitzer (pParentTarget) zerstört wird.  
  
##  <a name="combinewithgeometry"></a>  CD2DGeometry::CombineWithGeometry  
 Diese Geometrie mit dem angegebenen Geometry kombiniert und speichert das Ergebnis in eine ID2D1SimplifiedGeometrySink.  
  
```  
BOOL CombineWithGeometry(
    CD2DGeometry& inputGeometry,  
    D2D1_COMBINE_MODE combineMode,  
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `inputGeometry`  
 Die Geometrie, die mit dieser Instanz.  
  
 `combineMode`  
 Der Typ des auszuführenden kombinieren-Vorgangs.  
  
 `inputGeometryTransform`  
 Die Transformation auf InputGeometry vor dem vereinen angewendet werden soll.  
  
 `geometrySink`  
 Das Ergebnis des Vorgangs kombinieren.  
  
 `flatteningTolerance`  
 Die maximale Grenzen für die Entfernung zwischen Punkten in die polygonale Näherung der Geometrien. Bei kleineren Werten genauere Ergebnisse erzeugen jedoch dazu führen, dass Ausführung verlangsamt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird "Wahr" zurückgegeben. Andernfalls wird "false" zurückgegeben.  
  
##  <a name="comparewithgeometry"></a>  CD2DGeometry::CompareWithGeometry  
 Beschreibt die Schnittmenge dieser Geometry-Datentyp und die angegebene Geometrie. Der Vergleich erfolgt mithilfe der angegebenen flattening Toleranz.  
  
```  
D2D1_GEOMETRY_RELATION CompareWithGeometry(
    CD2DGeometry& inputGeometry,  
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `inputGeometry`  
 Die Geometrie zu testen.  
  
 `inputGeometryTransform`  
 Die Transformation auf InputGeometry angewendet werden soll.  
  
 `flatteningTolerance`  
 Die maximale Grenzen für die Entfernung zwischen Punkten in die polygonale Näherung der Geometrien. Bei kleineren Werten genauere Ergebnisse erzeugen jedoch dazu führen, dass Ausführung verlangsamt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird "Wahr" zurückgegeben. Andernfalls wird "false" zurückgegeben.  
  
##  <a name="computearea"></a>  CD2DGeometry::ComputeArea  
 Berechnet den Bereich der Geometry-Instanz, nachdem sie wurde mit der angegebenen Matrix transformiert und mit der angebenen Toleranz vereinfacht.  
  
```  
BOOL ComputeArea(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    FLOAT& area,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `worldTransform`  
 Die Transformation, die auf diese Geometrie anwenden, bevor das Berechnen der Fläche.  
  
 `area`  
 Bei der Rückgabe dieser Methode enthält einen Zeiger auf den Bereich der transformierten, vereinfachte Version dieser Geometry-Instanz. Sie müssen das Zuweisen von Speicher für diesen Parameter.  
  
 `flatteningTolerance`  
 Die maximale Grenzen für die Entfernung zwischen Punkten in die polygonale Näherung der Geometry-Instanz. Bei kleineren Werten genauere Ergebnisse erzeugen jedoch dazu führen, dass Ausführung verlangsamt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird "Wahr" zurückgegeben. Andernfalls wird "false" zurückgegeben.  
  
##  <a name="computelength"></a>  CD2DGeometry::ComputeLength  
 Berechnet die Länge der Geometrie, als wäre jedes Segment in eine Linie unrolled.  
  
```  
BOOL ComputeLength(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    FLOAT& length,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `worldTransform`  
 Die Transformation auf die Geometrie anwenden, bevor seine Länge berechnet werden soll.  
  
 `length`  
 Bei der Rückgabe dieser Methode enthält einen Zeiger auf die Länge der Geometry-Instanz. Für geschlossene Geometrien schließt die Länge ein impliziten schließende-Segments. Sie müssen das Zuweisen von Speicher für diesen Parameter.  
  
 `flatteningTolerance`  
 Die maximale Grenzen für die Entfernung zwischen Punkten in die polygonale Näherung der Geometry-Instanz. Bei kleineren Werten genauere Ergebnisse erzeugen jedoch dazu führen, dass Ausführung verlangsamt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird "Wahr" zurückgegeben. Andernfalls wird "false" zurückgegeben.  
  
##  <a name="computepointatlength"></a>  CD2DGeometry::ComputePointAtLength  
 Den Vektor und Tangentenendpunkte im angegebenen Abstand entlang der Geometrie berechnet, nachdem sie wurde mit der angegebenen Matrix transformiert und mit der angebenen Toleranz vereinfacht.  
  
```  
BOOL ComputePointAtLength(
    FLOAT length,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    CD2DPointF& point,  
    CD2DPointF& unitTangentVector,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `length`  
 Die Entfernung entlang der Geometrie des Punkt und Tangens gefunden. Wenn dieser Wert kleiner 0 ist, wird diese Methode den ersten Punkt in der Geometrie berechnet. Wenn dieser Abstand größer als die Länge der Geometry-Instanz ist, wird diese Methode den letzten Punkt in der Geometrie berechnet.  
  
 `worldTransform`  
 Die Transformation vor dem Berechnen des angegebenen Punkt und Tangens auf die Geometrie angewendet werden soll.  
  
 `point`  
 Die Position, an der angegebenen Entfernung entlang der Geometrie werden soll. Wenn die Geometrie leer ist, enthält dieser Punkt "NaN" als x und y Werte.  
  
 `unitTangentVector`  
 Bei der Rückgabe dieser Methode enthält einen Zeiger auf den Tangens Vektor im angegebenen Abstand entlang der Geometrie. Wenn die Geometrie leer ist, enthält dieser Vektor "NaN" als x und y Werte. Sie müssen das Zuweisen von Speicher für diesen Parameter.  
  
 `flatteningTolerance`  
 Die maximale Grenzen für die Entfernung zwischen Punkten in die polygonale Näherung der Geometry-Instanz. Bei kleineren Werten genauere Ergebnisse erzeugen jedoch dazu führen, dass Ausführung verlangsamt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird "Wahr" zurückgegeben. Andernfalls wird "false" zurückgegeben.  
  
##  <a name="destroy"></a>  CD2DGeometry:: Destroy  
 Zerstört ein CD2DGeometry-Objekt.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>  CD2DGeometry::Detach  
 Trennt Ressourcenschnittstelle aus dem Objekt  
  
```  
ID2D1Geometry* Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf getrennten Ressourcenschnittstelle.  
  
##  <a name="fillcontainspoint"></a>  CD2DGeometry::FillContainsPoint  
 Gibt an, ob die Fläche ausgefüllt, die durch die Geometrie einen angegebenen Punkt, die angegebene flattening Toleranz enthalten würde.  
  
```  
BOOL FillContainsPoint(
    CD2DPointF point,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    BOOL* contains,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `point`  
 Der Punkt zu testen.  
  
 `worldTransform`  
 Die Transformation auf die Geometrie vor für die Kapselung testen anwenden.  
  
 `contains`  
 Rückkehr dieser Methode enthält einen Bool-Wert, der TRUE ist, wenn die Fläche, die durch die Geometrie ausgefüllt Punkt enthält. andernfalls "false". Sie müssen das Zuweisen von Speicher für diesen Parameter.  
  
 `flatteningTolerance`  
 Die numerische Genauigkeit, mit denen die präzise geometrische Pfad und den Pfadschnittmenge berechnet wird. Fehlende Füllung kleiner als die Anzahl der Punkte gelten weiterhin in. Bei kleineren Werten genauere Ergebnisse erzeugen jedoch dazu führen, dass Ausführung verlangsamt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird "Wahr" zurückgegeben. Andernfalls wird "false" zurückgegeben.  
  
##  <a name="get"></a>  CD2DGeometry::Get  
 Gibt die ID2D1Geometry-Schnittstelle  
  
```  
ID2D1Geometry* Get();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine ID2D1Geometry-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="getbounds"></a>  CD2DGeometry::GetBounds  
  
```   
BOOL GetBounds(
const D2D1_MATRIX_3X2_F& worldTransform,  
CD2DRectF& bounds) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `worldTransform`  
 `bounds`  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="getwidenedbounds"></a>  CD2DGeometry::GetWidenedBounds  
 Ruft die Grenzen der Geometrie ab, nachdem er erweitert, indem die angegebenen Strichbreite und den Stil und mit der angegebenen Matrix transformiert wurde.  
  
```  
BOOL GetWidenedBounds(
    FLOAT strokeWidth,  
    ID2D1StrokeStyle* strokeStyle,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    CD2DRectF& bounds,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `strokeWidth`  
 Der Betrag, um die Geometrie, die durch seine Kontur Verlauf erweitert werden.  
  
 `strokeStyle`  
 Der Stil der Kontur, die die Geometrie erweitert wird.  
  
 `worldTransform`  
 Eine Transformation, die auf die Geometrie angewendet werden soll, nachdem die Geometrie transformiert und die Geometrie gezeichnet wurde.  
  
 `bounds`  
 Wenn diese Methode zurückgibt, enthält die Grenzen der erweiterten Geometrie. Sie müssen das Zuweisen von Speicher für diesen Parameter.  
  
 `flatteningTolerance`  
 Die maximale Grenzen für die Entfernung zwischen Punkten in die polygonale Näherung der Geometrien. Bei kleineren Werten genauere Ergebnisse erzeugen jedoch dazu führen, dass Ausführung verlangsamt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird "Wahr" zurückgegeben. Andernfalls wird "false" zurückgegeben.  
  
##  <a name="isvalid"></a>  CD2DGeometry::IsValid  
 Die Ressource Gültigkeit überprüft  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Ressource gültig ist. andernfalls "false".  
  
##  <a name="m_pgeometry"></a>  CD2DGeometry::m_pGeometry  
 Ein Zeiger auf eine ID2D1Geometry.  
  
```  
ID2D1Geometry* m_pGeometry;  
```  
  
##  <a name="operator_id2d1geometry_star"></a>  CD2DGeometry::Operator ID2D1Geometry *  
 Gibt die ID2D1Geometry-Schnittstelle  
  
```  
operator ID2D1Geometry*();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine ID2D1Geometry-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="outline"></a>  CD2DGeometry::Outline  
 Berechnet die Kontur der Geometrie und schreibt das Ergebnis in eine ID2D1SimplifiedGeometrySink.  
  
```  
BOOL Outline(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `worldTransform`  
 Die Transformation für die Geometrie Gliederung gelten.  
  
 `geometrySink`  
 Die ID2D1SimplifiedGeometrySink, an das die transformierten Geometry-Gliederung angefügt wird.  
  
 `flatteningTolerance`  
 Die maximale Grenzen für die Entfernung zwischen Punkten in die polygonale Näherung der Geometry-Instanz. Bei kleineren Werten genauere Ergebnisse erzeugen jedoch dazu führen, dass Ausführung verlangsamt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird "Wahr" zurückgegeben. Andernfalls wird "false" zurückgegeben.  
  
##  <a name="simplify"></a>  CD2DGeometry::Simplify  
 Erstellt eine vereinfachte Version der Geometry-Instanz, die nur Linien und (optional) kubische Bézier-Kurven enthält und schreibt das Ergebnis in eine ID2D1SimplifiedGeometrySink.  
  
```  
BOOL Simplify(
    D2D1_GEOMETRY_SIMPLIFICATION_OPTION simplificationOption,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `simplificationOption`  
 Ein Wert, der angibt, ob die vereinfachte Geometrie Kurven enthalten soll.  
  
 `worldTransform`  
 Die Transformation an, auf die vereinfachte Geometrie angewendet werden soll.  
  
 `geometrySink`  
 Die ID2D1SimplifiedGeometrySink, an das die vereinfachte Geometrie angefügt wird.  
  
 `flatteningTolerance`  
 Die maximale Grenzen für die Entfernung zwischen Punkten in die polygonale Näherung der Geometry-Instanz. Bei kleineren Werten genauere Ergebnisse erzeugen jedoch dazu führen, dass Ausführung verlangsamt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird "Wahr" zurückgegeben. Andernfalls wird "false" zurückgegeben.  
  
##  <a name="strokecontainspoint"></a>  CD2DGeometry::StrokeContainsPoint  
 Bestimmt, ob die Geometrie Strich einen angegebenen Punkt, den angegebenen Schriftstärke,-Stil und -Transformation enthält.  
  
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
 `point`  
 Der zu überprüfende Punkt.  
  
 `strokeWidth`  
 Die Stärke des Strichs angewendet werden soll.  
  
 `strokeStyle`  
 Der Stil der Kontur anwenden.  
  
 `worldTransform`  
 Die Transformation an, auf die gestrichelte Geometrie angewendet werden soll.  
  
 `contains`  
 Bei der Rückgabe dieser Methode enthält einen booleschen Wert auf "true" festgelegt werden, wenn die Geometrie Strich angegebenen Punkt enthält. andernfalls "false". Sie müssen das Zuweisen von Speicher für diesen Parameter.  
  
 `flatteningTolerance`  
 Die numerische Genauigkeit, mit denen die präzise geometrische Pfad und den Pfadschnittmenge berechnet wird. Fehlende Strichs kleiner als die Anzahl der Punkte gelten weiterhin in. Bei kleineren Werten genauere Ergebnisse erzeugen jedoch dazu führen, dass Ausführung verlangsamt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird "Wahr" zurückgegeben. Andernfalls wird "false" zurückgegeben.  
  
##  <a name="tessellate"></a>  CD2DGeometry::Tessellate  
 Erstellt einen Satz von Uhrzeigerrichtung, die die Geometrie abdecken, nachdem er mit der angegebenen Matrix transformiert wurde, und mit der angebenen Toleranz vereinfacht.  
  
```  
BOOL Tessellate(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1TessellationSink* tessellationSink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `worldTransform`  
 Die Transformation für dieses Geometry, oder NULL.  
  
 `tessellationSink`  
 Die ID2D1TessellationSink an das der Mosaikprozess angefügt wird.  
  
 `flatteningTolerance`  
 Die maximale Grenzen für die Entfernung zwischen Punkten in die polygonale Näherung der Geometry-Instanz. Bei kleineren Werten genauere Ergebnisse erzeugen jedoch dazu führen, dass Ausführung verlangsamt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird "Wahr" zurückgegeben. Andernfalls wird "false" zurückgegeben.  
  
##  <a name="widen"></a>  CD2DGeometry::Widen  
 Erweitert die Geometrie der angegebenen Striche und das Ergebnis in eine ID2D1SimplifiedGeometrySink schreibt, nachdem sie wurde mit der angegebenen Matrix transformiert und mit der angebenen Toleranz vereinfacht.  
  
```  
BOOL Widen(
    FLOAT strokeWidth,  
    ID2D1StrokeStyle* strokeStyle,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `strokeWidth`  
 Der Betrag, um die Geometrie erweitert werden.  
  
 `strokeStyle`  
 Der Stil der Kontur für die Geometrie, oder NULL.  
  
 `worldTransform`  
 Die Transformation für die Geometrie gelten, nach dem erweitern.  
  
 `geometrySink`  
 Die ID2D1SimplifiedGeometrySink an das vergrößerte Geometrie angefügt wird.  
  
 `flatteningTolerance`  
 Die maximale Grenzen für die Entfernung zwischen Punkten in die polygonale Näherung der Geometry-Instanz. Bei kleineren Werten genauere Ergebnisse erzeugen jedoch dazu führen, dass Ausführung verlangsamt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird "Wahr" zurückgegeben. Andernfalls wird "false" zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
