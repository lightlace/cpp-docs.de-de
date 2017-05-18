---
title: CD2DGeometrySink-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CD2DGeometrySink class
ms.assetid: e5e07f41-0343-4ab1-9d6b-8c62ed33c04a
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 8a51d9475437ae460340d419a88bc46effa81f5f
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dgeometrysink-class"></a>CD2DGeometrySink-Klasse
Ein Wrapper für ID2D1GeometrySink.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DGeometrySink;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DGeometrySink::CD2DGeometrySink](#cd2dgeometrysink)|Erstellt ein CD2DGeometrySink-Objekt aus CD2DPathGeometry-Objekt.|  
|[CD2DGeometrySink:: ~ CD2DGeometrySink](#_dtorcd2dgeometrysink)|Der Destruktor. Wird aufgerufen, wenn ein D2D-Geometrieobjekt Senke zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DGeometrySink::AddArc](#addarc)|Fügt der Pfadgeometrie einen einzelnen Bogen hinzu|  
|[CD2DGeometrySink::AddBezier](#addbezier)|Erstellt eine kubische Bézierkurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt.|  
|[CD2DGeometrySink::AddBeziers](#addbeziers)|Erstellt eine Sequenz von kubische Bezier-Kurven und die Geometriesenke hinzugefügt.|  
|[CD2DGeometrySink::AddLine](#addline)|Erstellt ein Liniensegment zwischen dem aktuellen Punkt und dem angegebenen Endpunkt und die Geometriesenke hinzugefügt.|  
|[CD2DGeometrySink::AddLines](#addlines)|Erstellt eine Sequenz von Zeilen, die mit den angegebenen Punkten und die Geometriesenke hinzugefügt.|  
|[CD2DGeometrySink::AddQuadraticBezier](#addquadraticbezier)|Erstellt eine quadratische Bézier-Kurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt.|  
|[CD2DGeometrySink::AddQuadraticBeziers](#addquadraticbeziers)|Eine Sequenz von quadratische Bézier-Segmenten hinzugefügt als ein Array in einem einzigen Aufruf.|  
|[CD2DGeometrySink::BeginFigure](#beginfigure)|Beginnt eine neue am angegebenen Punkt.|  
|[CD2DGeometrySink::Close](#close)|Schließt die Geometriesenke|  
|[CD2DGeometrySink::EndFigure](#endfigure)|Beendet die aktuelle Abbildung; Schließt sie optional.|  
|[CD2DGeometrySink::Get](#get)|Gibt die ID2D1GeometrySink-Schnittstelle|  
|[CD2DGeometrySink::IsValid](#isvalid)|Überprüft die Senke Gültigkeit Geometrie|  
|[CD2DGeometrySink::SetFillMode](#setfillmode)|Gibt die Methode verwendet, um zu bestimmen, welche Punkte innerhalb der Geometrie, die durch diese Geometriesenke beschrieben und außerhalb.|  
|[CD2DGeometrySink::SetSegmentFlags](#setsegmentflags)|Gibt Strich- und Joinoptionen Optionen auf neue Geometriesenke hinzugefügte Segmente angewendet werden.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DGeometrySink::Operator ID2D1GeometrySink *](#operator_id2d1geometrysink_star)|Gibt die ID2D1GeometrySink-Schnittstelle|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DGeometrySink::m_pSink](#m_psink)|Ein Zeiger auf eine ID2D1GeometrySink.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CD2DGeometrySink`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="_dtorcd2dgeometrysink"></a>CD2DGeometrySink:: ~ CD2DGeometrySink  
 Der Destruktor. Wird aufgerufen, wenn ein D2D-Geometrieobjekt Senke zerstört wird.  
  
```  
virtual ~CD2DGeometrySink();
```  
  
##  <a name="addarc"></a>CD2DGeometrySink::AddArc  
 Fügt der Pfadgeometrie einen einzelnen Bogen hinzu  
  
```  
void AddArc(const D2D1_ARC_SEGMENT& arc);
```  
  
### <a name="parameters"></a>Parameter  
 `arc`  
 Das Bogensegment der Abbildung hinzugefügt  
  
##  <a name="addbezier"></a>CD2DGeometrySink::AddBezier  
 Erstellt eine kubische Bézierkurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt.  
  
```  
void AddBezier(const D2D1_BEZIER_SEGMENT& bezier);
```  
  
### <a name="parameters"></a>Parameter  
 `bezier`  
 Eine Struktur, die beschreibt, die Kontrollpunkte und den Endpunkt der Bézier-Kurve hinzu.  
  
##  <a name="addbeziers"></a>CD2DGeometrySink::AddBeziers  
 Erstellt eine Sequenz von kubische Bezier-Kurven und die Geometriesenke hinzugefügt.  
  
```  
void AddBeziers(
    const CArray<D2D1_BEZIER_SEGMENT,  
    D2D1_BEZIER_SEGMENT>& beziers);
```  
  
### <a name="parameters"></a>Parameter  
 `beziers`  
 Ein Array von Bézier-Segmenten, die beschreibt, die Bézier-Kurven zu erstellen. Eine Kurve wird von der Geometriesenke aktuellen Punkt (dem Endpunkt des letzten gezeichneten Segments oder der mit BeginFigure angegebenen) und dem Endpunkt des ersten Bézier-Segments im Array gezeichnet. Wenn das Array zusätzliche Bézier-Segmente enthält, verwendet jede nachfolgende Bézier-Segment den Endpunkt des vorherigen Segments Bézier als Anfangspunkt.  
  
##  <a name="addline"></a>CD2DGeometrySink::AddLine  
 Erstellt ein Liniensegment zwischen dem aktuellen Punkt und dem angegebenen Endpunkt und die Geometriesenke hinzugefügt.  
  
```  
void AddLine(CD2DPointF point);
```  
  
### <a name="parameters"></a>Parameter  
 `point`  
 Der Endpunkt der Linie zu zeichnen.  
  
##  <a name="addlines"></a>CD2DGeometrySink::AddLines  
 Erstellt eine Sequenz von Zeilen, die mit den angegebenen Punkten und die Geometriesenke hinzugefügt.  
  
```  
void AddLines(
    const CArray<CD2DPointF,  
    CD2DPointF>& points);
```  
  
### <a name="parameters"></a>Parameter  
 `points`  
 Ein Array von einem oder mehreren Punkten, die die zu zeichnenden Linien beschreiben. Eine Linie wird von der Geometriesenke aktuellen Punkt (dem Endpunkt des letzten gezeichneten Segments oder der mit BeginFigure angegebenen) und dem ersten Punkt im Array gezeichnet. Wenn das Array zusätzliche Punkte enthält, wird eine Linie vom ersten Punkt zum zweiten Punkt im Array, vom zweiten Punkt zum dritten Punkt usw. gezeichnet. Ein Array einer Sequenz der Endpunkte der Linien, die gezeichnet werden soll.  
  
##  <a name="addquadraticbezier"></a>CD2DGeometrySink::AddQuadraticBezier  
 Erstellt eine quadratische Bézier-Kurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt.  
  
```  
void AddQuadraticBezier(const D2D1_QUADRATIC_BEZIER_SEGMENT& bezier);
```  
  
### <a name="parameters"></a>Parameter  
 `bezier`  
 Eine Struktur, die den Kontrollpunkt und den Endpunkt der quadratische Bézier-Kurve hinzufügen beschreibt.  
  
##  <a name="addquadraticbeziers"></a>CD2DGeometrySink::AddQuadraticBeziers  
 Eine Sequenz von quadratische Bézier-Segmenten hinzugefügt als ein Array in einem einzigen Aufruf.  
  
```  
void AddQuadraticBeziers(
    const CArray<D2D1_QUADRATIC_BEZIER_SEGMENT,  
    D2D1_QUADRATIC_BEZIER_SEGMENT>& beziers);
```  
  
### <a name="parameters"></a>Parameter  
 `beziers`  
 Ein Array aus einer Folge von quadratische Bézier-Segmenten.  
  
##  <a name="beginfigure"></a>CD2DGeometrySink::BeginFigure  
 Beginnt eine neue am angegebenen Punkt.  
  
```  
void BeginFigure(
    CD2DPointF startPoint,  
    D2D1_FIGURE_BEGIN figureBegin);
```  
  
### <a name="parameters"></a>Parameter  
 `startPoint`  
 Der Punkt, an dem die neue Abbildung beginnt.  
  
 `figureBegin`  
 Gibt an, ob die neue Abbildung hohl oder ausgefüllt werden soll.  
  
##  <a name="cd2dgeometrysink"></a>CD2DGeometrySink::CD2DGeometrySink  
 Erstellt ein CD2DGeometrySink-Objekt aus CD2DPathGeometry-Objekt.  
  
```  
CD2DGeometrySink(CD2DPathGeometry& pathGeometry);
```  
  
### <a name="parameters"></a>Parameter  
 `pathGeometry`  
 Ein vorhandenes CD2DPathGeometry-Objekt.  
  
##  <a name="close"></a>CD2DGeometrySink::Close  
 Schließt die Geometriesenke  
  
```  
BOOL Close();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; andernfalls FALSE.  
  
##  <a name="endfigure"></a>CD2DGeometrySink::EndFigure  
 Beendet die aktuelle Abbildung; Schließt sie optional.  
  
```  
void EndFigure(D2D1_FIGURE_END figureEnd);
```  
  
### <a name="parameters"></a>Parameter  
 `figureEnd`  
 Ein Wert, der angibt, ob die aktuelle Abbildung geschlossen wird. Wenn die Figur geschlossen ist, wird eine Linie zwischen dem aktuellen und den Startpunkt mit BeginFigure angegebenen gezeichnet.  
  
##  <a name="get"></a>CD2DGeometrySink::Get  
 Gibt die ID2D1GeometrySink-Schnittstelle  
  
```  
ID2D1GeometrySink* Get();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine ID2D1GeometrySink-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="isvalid"></a>CD2DGeometrySink::IsValid  
 Überprüft die Senke Gültigkeit Geometrie  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Geometriesenke gültig ist. andernfalls FALSE.  
  
##  <a name="m_psink"></a>CD2DGeometrySink::m_pSink  
 Ein Zeiger auf eine ID2D1GeometrySink.  
  
```  
ID2D1GeometrySink* m_pSink;  
```  
  
##  <a name="operator_id2d1geometrysink_star"></a>CD2DGeometrySink::Operator ID2D1GeometrySink *  
 Gibt die ID2D1GeometrySink-Schnittstelle  
  
```  
operator ID2D1GeometrySink*();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine ID2D1GeometrySink-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="setfillmode"></a>CD2DGeometrySink::SetFillMode  
 Gibt die Methode verwendet, um zu bestimmen, welche Punkte innerhalb der Geometrie, die durch diese Geometriesenke beschrieben und außerhalb.  
  
```  
void SetFillMode(D2D1_FILL_MODE fillMode);
```  
  
### <a name="parameters"></a>Parameter  
 `fillMode`  
 Die Methode verwendet, um zu bestimmen, ob ein bestimmter Punkt Teil der Geometrie ist.  
  
##  <a name="setsegmentflags"></a>CD2DGeometrySink::SetSegmentFlags  
 Gibt Strich- und Joinoptionen Optionen auf neue Geometriesenke hinzugefügte Segmente angewendet werden.  
  
```  
void SetSegmentFlags(D2D1_PATH_SEGMENT vertexFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `vertexFlags`  
 Optionen für Strich und Join auf neue Geometriesenke hinzugefügte Segmente angewendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

