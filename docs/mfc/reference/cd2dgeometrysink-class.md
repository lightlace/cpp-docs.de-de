---
title: CD2DGeometrySink-Klasse | Microsoft Docs
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
ms.openlocfilehash: b67aa3345f8739714cb6758f8363c3d2054dd4e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
|[CD2DGeometrySink::CD2DGeometrySink](#cd2dgeometrysink)|Erstellt ein CD2DGeometrySink-Objekt aus CD2DPathGeometry-Objekt.|  
|[CD2DGeometrySink:: ~ CD2DGeometrySink](#_dtorcd2dgeometrysink)|Der Destruktor. Wird aufgerufen, wenn ein D2D-Geometry-Sink-Objekt zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DGeometrySink::AddArc](#addarc)|Fügt einem einzelnen Bogen der Pfadgeometrie hinzu|  
|[CD2DGeometrySink::AddBezier](#addbezier)|Erstellt eine kubische Bézierkurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt.|  
|[CD2DGeometrySink::AddBeziers](#addbeziers)|Erstellt eine Sequenz von kubische Bézier-Kurven aus, und die Geometriesenke hinzugefügt.|  
|[CD2DGeometrySink::AddLine](#addline)|Erstellt ein Liniensegment zwischen den aktuellen Stand und den angegebenen Endpunkt und die Geometriesenke hinzugefügt.|  
|[CD2DGeometrySink::AddLines](#addlines)|Erstellt eine Sequenz von Zeilen, die mit den angegebenen Punkten und die Geometriesenke hinzugefügt.|  
|[CD2DGeometrySink::AddQuadraticBezier](#addquadraticbezier)|Erstellt eine quadratische Bézier-Kurve zwischen den aktuellen Stand und den angegebenen Endpunkt.|  
|[CD2DGeometrySink::AddQuadraticBeziers](#addquadraticbeziers)|Fügt eine Sequenz von quadratische Bézier Segmente als ein Array, in einem einzigen Aufruf hinzu.|  
|[CD2DGeometrySink::BeginFigure](#beginfigure)|Startet eine neue Abbildung an der angegebenen Position.|  
|[CD2DGeometrySink::Close](#close)|Schließt die Geometriesenke|  
|[CD2DGeometrySink::EndFigure](#endfigure)|Beendet die aktuelle Abbildung; optional, wird geschlossen.|  
|[CD2DGeometrySink::Get](#get)|Gibt die ID2D1GeometrySink-Schnittstelle|  
|[CD2DGeometrySink::IsValid](#isvalid)|Überprüft die Senke Gültigkeit Geometrie|  
|[CD2DGeometrySink::SetFillMode](#setfillmode)|Gibt die Methode verwendet, um zu bestimmen, welche Punkte innerhalb der Geometrie, die von dieser Geometriesenke beschrieben und die Punkte sind außerhalb.|  
|[CD2DGeometrySink::SetSegmentFlags](#setsegmentflags)|Gibt an, Strich und Join-Optionen auf neue hinzugefügte Geometriesenke Segmente angewendet werden soll.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DGeometrySink::Operator ID2D1GeometrySink *](#operator_id2d1geometrysink_star)|Gibt die ID2D1GeometrySink-Schnittstelle|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CD2DGeometrySink::m_pSink](#m_psink)|Ein Zeiger auf eine ID2D1GeometrySink.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CD2DGeometrySink`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="_dtorcd2dgeometrysink"></a>  CD2DGeometrySink:: ~ CD2DGeometrySink  
 Der Destruktor. Wird aufgerufen, wenn ein D2D-Geometry-Sink-Objekt zerstört wird.  
  
```  
virtual ~CD2DGeometrySink();
```  
  
##  <a name="addarc"></a>  CD2DGeometrySink::AddArc  
 Fügt einem einzelnen Bogen der Pfadgeometrie hinzu  
  
```  
void AddArc(const D2D1_ARC_SEGMENT& arc);
```  
  
### <a name="parameters"></a>Parameter  
 `arc`  
 Das Bogensegment Abbildung hinzu  
  
##  <a name="addbezier"></a>  CD2DGeometrySink::AddBezier  
 Erstellt eine kubische Bézierkurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt.  
  
```  
void AddBezier(const D2D1_BEZIER_SEGMENT& bezier);
```  
  
### <a name="parameters"></a>Parameter  
 `bezier`  
 Eine Struktur, die die Steuerpunkte und Endpunkt der Bézier-Kurve hinzuzufügende beschreiben.  
  
##  <a name="addbeziers"></a>  CD2DGeometrySink::AddBeziers  
 Erstellt eine Sequenz von kubische Bézier-Kurven aus, und die Geometriesenke hinzugefügt.  
  
```  
void AddBeziers(
    const CArray<D2D1_BEZIER_SEGMENT,  
    D2D1_BEZIER_SEGMENT>& beziers);
```  
  
### <a name="parameters"></a>Parameter  
 `beziers`  
 Ein Array von Bézier Segmente, die zum Erstellen der Bézier-Kurven beschreibt. Eine Kurve wird aus der Geometriesenke aktuellen Zeitpunkt (dem Endpunkt des letzten Segments gezeichnet oder durch BeginFigure angegebenen Speicherort) den Endpunkt des ersten Bézier-Segments im Array dargestellt. Wenn das Array zusätzliche Bézier Segmente enthält, verwendet jedes nachfolgende Bézier-Segment der Endpunkt der vorhergehenden Bézier-Segment als Anfangspunkt.  
  
##  <a name="addline"></a>  CD2DGeometrySink::AddLine  
 Erstellt ein Liniensegment zwischen den aktuellen Stand und den angegebenen Endpunkt und die Geometriesenke hinzugefügt.  
  
```  
void AddLine(CD2DPointF point);
```  
  
### <a name="parameters"></a>Parameter  
 `point`  
 Der Endpunkt der Linie gezeichnet werden soll.  
  
##  <a name="addlines"></a>  CD2DGeometrySink::AddLines  
 Erstellt eine Sequenz von Zeilen, die mit den angegebenen Punkten und die Geometriesenke hinzugefügt.  
  
```  
void AddLines(
    const CArray<CD2DPointF,  
    CD2DPointF>& points);
```  
  
### <a name="parameters"></a>Parameter  
 `points`  
 Ein Array von einem oder mehreren Punkten, die beschreiben, die Linien gezeichnet werden soll. Eine Zeile wird aus der Geometriesenke aktuellen Zeitpunkt (dem Endpunkt des letzten Segments gezeichnet oder durch BeginFigure angegebenen Speicherort) der erste Punkt im Array dargestellt. Wenn das Array zusätzliche Punkte enthält, wird eine Zeile aus dem ersten Punkt der zweite Punkt im Array, aus der zweiten, zeigen Sie auf der dritten Punkt usw. dargestellt. Ein Array aus einer Folge von den Endpunkten der Linien gezeichnet werden soll.  
  
##  <a name="addquadraticbezier"></a>  CD2DGeometrySink::AddQuadraticBezier  
 Erstellt eine quadratische Bézier-Kurve zwischen den aktuellen Stand und den angegebenen Endpunkt.  
  
```  
void AddQuadraticBezier(const D2D1_QUADRATIC_BEZIER_SEGMENT& bezier);
```  
  
### <a name="parameters"></a>Parameter  
 `bezier`  
 Eine Struktur, die den Kontrollpunkt und den Endpunkt der quadratische Bézier-Kurve hinzuzufügende beschreibt.  
  
##  <a name="addquadraticbeziers"></a>  CD2DGeometrySink::AddQuadraticBeziers  
 Fügt eine Sequenz von quadratische Bézier Segmente als ein Array, in einem einzigen Aufruf hinzu.  
  
```  
void AddQuadraticBeziers(
    const CArray<D2D1_QUADRATIC_BEZIER_SEGMENT,  
    D2D1_QUADRATIC_BEZIER_SEGMENT>& beziers);
```  
  
### <a name="parameters"></a>Parameter  
 `beziers`  
 Ein Array aus einer Folge von quadratische Bézier Segmente.  
  
##  <a name="beginfigure"></a>  CD2DGeometrySink::BeginFigure  
 Startet eine neue Abbildung an der angegebenen Position.  
  
```  
void BeginFigure(
    CD2DPointF startPoint,  
    D2D1_FIGURE_BEGIN figureBegin);
```  
  
### <a name="parameters"></a>Parameter  
 `startPoint`  
 Der Punkt, an dem die neue Abbildung beginnt.  
  
 `figureBegin`  
 Gibt an, ob die neue Abbildung gefüllt oder sein sollten.  
  
##  <a name="cd2dgeometrysink"></a>  CD2DGeometrySink::CD2DGeometrySink  
 Erstellt ein CD2DGeometrySink-Objekt aus CD2DPathGeometry-Objekt.  
  
```  
CD2DGeometrySink(CD2DPathGeometry& pathGeometry);
```  
  
### <a name="parameters"></a>Parameter  
 `pathGeometry`  
 Ein vorhandenes CD2DPathGeometry-Objekt.  
  
##  <a name="close"></a>  CD2DGeometrySink::Close  
 Schließt die Geometriesenke  
  
```  
BOOL Close();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; andernfalls "false".  
  
##  <a name="endfigure"></a>  CD2DGeometrySink::EndFigure  
 Beendet die aktuelle Abbildung; optional, wird geschlossen.  
  
```  
void EndFigure(D2D1_FIGURE_END figureEnd);
```  
  
### <a name="parameters"></a>Parameter  
 `figureEnd`  
 Ein Wert, der angibt, ob die aktuelle Abbildung geschlossen wird. Wenn in der Abbildung geschlossen ist, wird eine Linie zwischen den aktuellen Stand und den Ausgangspunkt BeginFigure gemäß gezeichnet.  
  
##  <a name="get"></a>  CD2DGeometrySink::Get  
 Gibt die ID2D1GeometrySink-Schnittstelle  
  
```  
ID2D1GeometrySink* Get();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine ID2D1GeometrySink-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="isvalid"></a>  CD2DGeometrySink::IsValid  
 Überprüft die Senke Gültigkeit Geometrie  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Geometriesenke gültig ist. andernfalls "false".  
  
##  <a name="m_psink"></a>  CD2DGeometrySink::m_pSink  
 Ein Zeiger auf eine ID2D1GeometrySink.  
  
```  
ID2D1GeometrySink* m_pSink;  
```  
  
##  <a name="operator_id2d1geometrysink_star"></a>  CD2DGeometrySink::Operator ID2D1GeometrySink *  
 Gibt die ID2D1GeometrySink-Schnittstelle  
  
```  
operator ID2D1GeometrySink*();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine ID2D1GeometrySink-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="setfillmode"></a>  CD2DGeometrySink::SetFillMode  
 Gibt die Methode verwendet, um zu bestimmen, welche Punkte innerhalb der Geometrie, die von dieser Geometriesenke beschrieben und die Punkte sind außerhalb.  
  
```  
void SetFillMode(D2D1_FILL_MODE fillMode);
```  
  
### <a name="parameters"></a>Parameter  
 `fillMode`  
 Die Methode verwendet, um zu bestimmen, ob ein bestimmter Punkt Teil der Geometrie ist.  
  
##  <a name="setsegmentflags"></a>  CD2DGeometrySink::SetSegmentFlags  
 Gibt an, Strich und Join-Optionen auf neue hinzugefügte Geometriesenke Segmente angewendet werden soll.  
  
```  
void SetSegmentFlags(D2D1_PATH_SEGMENT vertexFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `vertexFlags`  
 Optionen für Strich und Join auf neue hinzugefügte Geometriesenke Segmente angewendet werden soll.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
