---
title: CD2DGeometry-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CD2DGeometry class
ms.assetid: 3f95054b-fdb8-4e87-87f2-9fc3df7279ec
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 948b2e2154259557e3a52c2045586cffce2a16f8
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dgeometry-class"></a>CD2DGeometry-Klasse
Ein Wrapper für die ID2D1Geometry.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DGeometry : public CD2DResource;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DGeometry::CD2DGeometry](#cd2dgeometry)|Erstellt ein CD2DGeometry-Objekt.|  
|[CD2DGeometry:: ~ CD2DGeometry](#_dtorcd2dgeometry)|Der Destruktor. Wird aufgerufen, wenn ein D2D-Geometrieobjekt zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DGeometry::Attach](#attach)|Hängt die vorhandene Ressourcenschnittstelle für das Objekt|  
|[CD2DGeometry::CombineWithGeometry](#combinewithgeometry)|Kombiniert diese Geometrie mit der angegebenen Geometrie und speichert das Ergebnis in eine ID2D1SimplifiedGeometrySink.|  
|[CD2DGeometry::CompareWithGeometry](#comparewithgeometry)|Beschreibt die Schnittmenge zwischen dieser Geometrie und der angegebenen Geometrie. Der Vergleich erfolgt mit der angegebenen Toleranz reduzieren.|  
|[CD2DGeometry::ComputeArea](#computearea)|Der Bereich der Geometrie berechnet, nachdem er wurde von der angegebenen Matrix transformiert und mit der angegebenen Toleranz vereinfacht.|  
|[CD2DGeometry::ComputeLength](#computelength)|Berechnet die Länge der Geometrie, als wäre jedes Segment in eine Linie entrollt.|  
|[CD2DGeometry::ComputePointAtLength](#computepointatlength)|Den Vektor und Tangentenendpunkte mit der angegebenen Entfernung entlang der Geometrie berechnet, nachdem er wurde von der angegebenen Matrix transformiert und mit der angegebenen Toleranz vereinfacht.|  
|[CD2DGeometry:: Destroy](#destroy)|Zerstört ein CD2DGeometry-Objekt. (Überschreibt [CD2DResource:: Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DGeometry::Detach](#detach)|Ressourcenschnittstelle aus dem Objekt getrennt|  
|[CD2DGeometry::FillContainsPoint](#fillcontainspoint)|Gibt an, ob der Bereich, der von der Geometrie ausgefüllte Berücksichtigung der angegebene Toleranz reduzieren den angegebenen Punkt enthält.|  
|[CD2DGeometry::Get](#get)|Gibt die ID2D1Geometry-Schnittstelle|  
|[CD2DGeometry::GetBounds](#getbounds)||  
|[CD2DGeometry::GetWidenedBounds](#getwidenedbounds)|Ruft die Grenzen der Geometrie ab, nachdem sie von der angegebenen Strichbreite und Style erweitert und mit der angegebenen Matrix transformiert wurde.|  
|[CD2DGeometry::IsValid](#isvalid)|Überprüft die Gültigkeit der Ressource (überschreibt [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
|[CD2DGeometry::Outline](#outline)|Berechnet die Konturen der Geometrie und schreibt das Ergebnis in eine ID2D1SimplifiedGeometrySink.|  
|[CD2DGeometry::Simplify](#simplify)|Erstellt eine vereinfachte Version der Geometrie, die nur Linien und (optional) kubische Bezier-Kurven enthält, und schreibt das Ergebnis in eine ID2D1SimplifiedGeometrySink.|  
|[CD2DGeometry::StrokeContainsPoint](#strokecontainspoint)|Bestimmt, ob der Strich der Geometrie den angegebenen Punkt angegebenen angegebener Strichstärke, Format und Transformation enthält.|  
|[CD2DGeometry::Tessellate](#tessellate)|Erstellt einen Satz von Uhrzeigerrichtung, die die Geometrie abdecken, nachdem diese mit der angegebenen Matrix transformiert wurde, und mit der angegebenen Toleranz vereinfacht.|  
|[CD2DGeometry::Widen](#widen)|Erweitert die Geometrie um den angegebenen Strich und schreibt Sie das Ergebnis in eine ID2D1SimplifiedGeometrySink, nachdem er wurde von der angegebenen Matrix transformiert und mit der angegebenen Toleranz vereinfacht.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DGeometry::Operator ID2D1Geometry *](#operator_id2d1geometry_star)|Gibt die ID2D1Geometry-Schnittstelle|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DGeometry::m_pGeometry](#m_pgeometry)|Ein Zeiger auf eine ID2D1Geometry.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DGeometry`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="_dtorcd2dgeometry"></a>CD2DGeometry:: ~ CD2DGeometry  
 Der Destruktor. Wird aufgerufen, wenn ein D2D-Geometrieobjekt zerstört wird.  
  
```  
virtual ~CD2DGeometry();
```  
  
##  <a name="attach"></a>CD2DGeometry::Attach  
 Hängt die vorhandene Ressourcenschnittstelle für das Objekt  
  
```  
void Attach(ID2D1Geometry* pResource);
```  
  
### <a name="parameters"></a>Parameter  
 `pResource`  
 Vorhandene Ressourcenschnittstelle. NULL darf nicht sein  
  
##  <a name="cd2dgeometry"></a>CD2DGeometry::CD2DGeometry  
 Erstellt ein CD2DGeometry-Objekt.  
  
```  
CD2DGeometry(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentTarget`  
 Ein Zeiger auf das Renderingziel.  
  
 `bAutoDestroy`  
 Gibt an, dass das Objekt vom Besitzer (pParentTarget) zerstört wird.  
  
##  <a name="combinewithgeometry"></a>CD2DGeometry::CombineWithGeometry  
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
 `inputGeometry`  
 Die Geometrie, die mit dieser Instanz.  
  
 `combineMode`  
 Der Typ des auszuführenden kombinieren.  
  
 `inputGeometryTransform`  
 Die Transformation, die auf InputGeometry vor dem vereinen angewendet.  
  
 `geometrySink`  
 Das Ergebnis der Operation kombinieren.  
  
 `flatteningTolerance`  
 Die maximalen Grenzen für die Entfernung zwischen Punkten in der polygonalen Näherung der Geometrien. Kleinere Werte liefern genauere Ergebnisse jedoch, dass die Ausführung langsameren.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird TRUE zurückgegeben. Andernfalls wird FALSE zurückgegeben.  
  
##  <a name="comparewithgeometry"></a>CD2DGeometry::CompareWithGeometry  
 Beschreibt die Schnittmenge zwischen dieser Geometrie und der angegebenen Geometrie. Der Vergleich erfolgt mit der angegebenen Toleranz reduzieren.  
  
```  
D2D1_GEOMETRY_RELATION CompareWithGeometry(
    CD2DGeometry& inputGeometry,  
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `inputGeometry`  
 Die zu testende Geometrie.  
  
 `inputGeometryTransform`  
 Die Transformation, die auf InputGeometry angewendet werden soll.  
  
 `flatteningTolerance`  
 Die maximalen Grenzen für die Entfernung zwischen Punkten in der polygonalen Näherung der Geometrien. Kleinere Werte liefern genauere Ergebnisse jedoch, dass die Ausführung langsameren.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird TRUE zurückgegeben. Andernfalls wird FALSE zurückgegeben.  
  
##  <a name="computearea"></a>CD2DGeometry::ComputeArea  
 Der Bereich der Geometrie berechnet, nachdem er wurde von der angegebenen Matrix transformiert und mit der angegebenen Toleranz vereinfacht.  
  
```  
BOOL ComputeArea(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    FLOAT& area,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `worldTransform`  
 Die Transformation, die vor dem berechnen seines Bereichs auf diese Geometrie angewendet werden soll.  
  
 `area`  
 Bei der Rückgabe dieser Methode enthält einen Zeiger auf den Bereich der transformierten, vereinfachten Version dieser Geometrie. Sie müssen Speicher für diesen Parameter reservieren.  
  
 `flatteningTolerance`  
 Die maximalen Grenzen für die Entfernung zwischen Punkten in der polygonalen Näherung der Geometrie. Kleinere Werte liefern genauere Ergebnisse jedoch, dass die Ausführung langsameren.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird TRUE zurückgegeben. Andernfalls wird FALSE zurückgegeben.  
  
##  <a name="computelength"></a>CD2DGeometry::ComputeLength  
 Berechnet die Länge der Geometrie, als wäre jedes Segment in eine Linie entrollt.  
  
```  
BOOL ComputeLength(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    FLOAT& length,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `worldTransform`  
 Die Transformation auf die Geometrie angewendet, bevor seine Länge berechnet werden soll.  
  
 `length`  
 Enthält nach dem Beenden dieser Methode einen Zeiger auf die Länge der Geometrie. Für geschlossene Geometrien schließt die Länge ein Segments implizite schließen. Sie müssen Speicher für diesen Parameter reservieren.  
  
 `flatteningTolerance`  
 Die maximalen Grenzen für die Entfernung zwischen Punkten in der polygonalen Näherung der Geometrie. Kleinere Werte liefern genauere Ergebnisse jedoch, dass die Ausführung langsameren.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird TRUE zurückgegeben. Andernfalls wird FALSE zurückgegeben.  
  
##  <a name="computepointatlength"></a>CD2DGeometry::ComputePointAtLength  
 Den Vektor und Tangentenendpunkte mit der angegebenen Entfernung entlang der Geometrie berechnet, nachdem er wurde von der angegebenen Matrix transformiert und mit der angegebenen Toleranz vereinfacht.  
  
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
 Die Entfernung entlang der Geometrie zeigen und zu suchen. Wenn diese Entfernung kleiner 0 ist, berechnet diese Methode den ersten Punkt in der Geometrie. Ist dieser Wert größer als die Länge der Geometrie, berechnet diese Methode den letzten Punkt in der Geometrie.  
  
 `worldTransform`  
 Die Transformation, die vor dem Berechnen des angegebenen Punkt und Tangens auf die Geometrie angewendet werden soll.  
  
 `point`  
 Die Position, an der angegebenen Entfernung entlang der Geometrie werden soll. Wenn die Geometrie leer ist, enthält dieser Punkt NaN als x- und y Werte.  
  
 `unitTangentVector`  
 Bei der Rückgabe dieser Methode enthält einen Zeiger auf den Tangensvektor mit der angegebenen Entfernung entlang der Geometrie. Wenn die Geometrie leer ist, enthält dieser Vektor NaN als x- und y Werte. Sie müssen Speicher für diesen Parameter reservieren.  
  
 `flatteningTolerance`  
 Die maximalen Grenzen für die Entfernung zwischen Punkten in der polygonalen Näherung der Geometrie. Kleinere Werte liefern genauere Ergebnisse jedoch, dass die Ausführung langsameren.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird TRUE zurückgegeben. Andernfalls wird FALSE zurückgegeben.  
  
##  <a name="destroy"></a>CD2DGeometry:: Destroy  
 Zerstört ein CD2DGeometry-Objekt.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DGeometry::Detach  
 Ressourcenschnittstelle aus dem Objekt getrennt  
  
```  
ID2D1Geometry* Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf getrennte Ressourcenschnittstelle.  
  
##  <a name="fillcontainspoint"></a>CD2DGeometry::FillContainsPoint  
 Gibt an, ob der Bereich, der von der Geometrie ausgefüllte Berücksichtigung der angegebene Toleranz reduzieren den angegebenen Punkt enthält.  
  
```  
BOOL FillContainsPoint(
    CD2DPointF point,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    BOOL* contains,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `point`  
 Der zu überprüfende Punkt.  
  
 `worldTransform`  
 Die Transformation, die auf die Geometrie vor dem Testen auf Einschluss angewendet.  
  
 `contains`  
 Diese Methode zurückgibt, enthält einen Bool-Wert, der TRUE ist, wenn der Bereich, der von der Geometrie ausgefüllte Punkt enthält. andernfalls "false". Sie müssen Speicher für diesen Parameter reservieren.  
  
 `flatteningTolerance`  
 Die numerische Genauigkeit, mit der der präzise geometrische Pfad und den Pfadschnittmenge berechnet wird. Punkte außerhalb des Füllbereichs um weniger als die Toleranz werden immer noch als innerhalb betrachtet. Kleinere Werte liefern genauere Ergebnisse jedoch, dass die Ausführung langsameren.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird TRUE zurückgegeben. Andernfalls wird FALSE zurückgegeben.  
  
##  <a name="get"></a>CD2DGeometry::Get  
 Gibt die ID2D1Geometry-Schnittstelle  
  
```  
ID2D1Geometry* Get();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine ID2D1Geometry-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="getbounds"></a>CD2DGeometry::GetBounds  
  
```   
BOOL GetBounds(
const D2D1_MATRIX_3X2_F& worldTransform,  
CD2DRectF& bounds) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `worldTransform`  
 `bounds`  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="getwidenedbounds"></a>CD2DGeometry::GetWidenedBounds  
 Ruft die Grenzen der Geometrie ab, nachdem sie von der angegebenen Strichbreite und Style erweitert und mit der angegebenen Matrix transformiert wurde.  
  
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
 Der Betrag, um die Geometrie, die durch die Kontur Verlauf erweitert werden.  
  
 `strokeStyle`  
 Der Stil der Kontur, die die Geometrie erweitert werden kann.  
  
 `worldTransform`  
 Eine Transformation, die auf die Geometrie angewendet werden soll, nachdem die Geometrie transformiert und die Geometrie gezeichnet wurde.  
  
 `bounds`  
 Enthält nach dem Beenden dieser Methode die Grenzen der erweiterten Geometrie. Sie müssen Speicher für diesen Parameter reservieren.  
  
 `flatteningTolerance`  
 Die maximalen Grenzen für die Entfernung zwischen Punkten in der polygonalen Näherung der Geometrien. Kleinere Werte liefern genauere Ergebnisse jedoch, dass die Ausführung langsameren.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird TRUE zurückgegeben. Andernfalls wird FALSE zurückgegeben.  
  
##  <a name="isvalid"></a>CD2DGeometry::IsValid  
 Die Ressource Gültigkeit überprüft  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Ressource gültig ist. andernfalls FALSE.  
  
##  <a name="m_pgeometry"></a>CD2DGeometry::m_pGeometry  
 Ein Zeiger auf eine ID2D1Geometry.  
  
```  
ID2D1Geometry* m_pGeometry;  
```  
  
##  <a name="operator_id2d1geometry_star"></a>CD2DGeometry::Operator ID2D1Geometry *  
 Gibt die ID2D1Geometry-Schnittstelle  
  
```  
operator ID2D1Geometry*();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine ID2D1Geometry-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="outline"></a>CD2DGeometry::Outline  
 Berechnet die Konturen der Geometrie und schreibt das Ergebnis in eine ID2D1SimplifiedGeometrySink.  
  
```  
BOOL Outline(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `worldTransform`  
 Die Transformation für die Gliederung des Geometry gelten.  
  
 `geometrySink`  
 Die ID2D1SimplifiedGeometrySink, an die die Geometrie transformierten Konturen angefügt wird.  
  
 `flatteningTolerance`  
 Die maximalen Grenzen für die Entfernung zwischen Punkten in der polygonalen Näherung der Geometrie. Kleinere Werte liefern genauere Ergebnisse jedoch, dass die Ausführung langsameren.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird TRUE zurückgegeben. Andernfalls wird FALSE zurückgegeben.  
  
##  <a name="simplify"></a>CD2DGeometry::Simplify  
 Erstellt eine vereinfachte Version der Geometrie, die nur Linien und (optional) kubische Bezier-Kurven enthält, und schreibt das Ergebnis in eine ID2D1SimplifiedGeometrySink.  
  
```  
BOOL Simplify(
    D2D1_GEOMETRY_SIMPLIFICATION_OPTION simplificationOption,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `simplificationOption`  
 Ein Wert, der angibt, ob die vereinfachte Geometrie Kurven enthalten sollte.  
  
 `worldTransform`  
 Die Transformation auf die vereinfachte Geometrie angewendet werden soll.  
  
 `geometrySink`  
 Die ID2D1SimplifiedGeometrySink, an die die vereinfachte Geometrie angefügt wird.  
  
 `flatteningTolerance`  
 Die maximalen Grenzen für die Entfernung zwischen Punkten in der polygonalen Näherung der Geometrie. Kleinere Werte liefern genauere Ergebnisse jedoch, dass die Ausführung langsameren.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird TRUE zurückgegeben. Andernfalls wird FALSE zurückgegeben.  
  
##  <a name="strokecontainspoint"></a>CD2DGeometry::StrokeContainsPoint  
 Bestimmt, ob der Strich der Geometrie den angegebenen Punkt angegebenen angegebener Strichstärke, Format und Transformation enthält.  
  
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
 Die Stärke des Strichs anwenden.  
  
 `strokeStyle`  
 Der Stil der Kontur anwenden.  
  
 `worldTransform`  
 Die Transformation, die auf die gestrichelte Geometrie angewendet werden soll.  
  
 `contains`  
 Bei der Rückgabe dieser Methode enthält einen booleschen Wert auf TRUE festgelegt, wenn der Strich der Geometrie den angegebenen Punkt enthält. andernfalls "false". Sie müssen Speicher für diesen Parameter reservieren.  
  
 `flatteningTolerance`  
 Die numerische Genauigkeit, mit der der präzise geometrische Pfad und den Pfadschnittmenge berechnet wird. Punkte, die weniger als die Toleranz des Strichs fehlende gelten weiterhin in. Kleinere Werte liefern genauere Ergebnisse jedoch, dass die Ausführung langsameren.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird TRUE zurückgegeben. Andernfalls wird FALSE zurückgegeben.  
  
##  <a name="tessellate"></a>CD2DGeometry::Tessellate  
 Erstellt einen Satz von Uhrzeigerrichtung, die die Geometrie abdecken, nachdem diese mit der angegebenen Matrix transformiert wurde, und mit der angegebenen Toleranz vereinfacht.  
  
```  
BOOL Tessellate(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1TessellationSink* tessellationSink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `worldTransform`  
 Die Transformation, die für diese Geometrie zutreffen.  
  
 `tessellationSink`  
 Die ID2D1TessellationSink, an die der Mosaikprozess angefügt wird.  
  
 `flatteningTolerance`  
 Die maximalen Grenzen für die Entfernung zwischen Punkten in der polygonalen Näherung der Geometrie. Kleinere Werte liefern genauere Ergebnisse jedoch, dass die Ausführung langsameren.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird TRUE zurückgegeben. Andernfalls wird FALSE zurückgegeben.  
  
##  <a name="widen"></a>CD2DGeometry::Widen  
 Erweitert die Geometrie um den angegebenen Strich und schreibt Sie das Ergebnis in eine ID2D1SimplifiedGeometrySink, nachdem er wurde von der angegebenen Matrix transformiert und mit der angegebenen Toleranz vereinfacht.  
  
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
 Das Format des Strichs, das auf die Geometrie oder NULL angewendet.  
  
 `worldTransform`  
 Die Transformation auf die Geometrie anwenden, nach dem erweitern.  
  
 `geometrySink`  
 Die ID2D1SimplifiedGeometrySink, an die die vergrößerte Geometrie angefügt wird.  
  
 `flatteningTolerance`  
 Die maximalen Grenzen für die Entfernung zwischen Punkten in der polygonalen Näherung der Geometrie. Kleinere Werte liefern genauere Ergebnisse jedoch, dass die Ausführung langsameren.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird TRUE zurückgegeben. Andernfalls wird FALSE zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

