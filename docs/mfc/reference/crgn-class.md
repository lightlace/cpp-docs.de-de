---
title: CRgn-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b569efb201f95ade8987aaa89bb6cea1bc0c15c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
|[CRgn::CombineRgn](#combinergn)|Legt eine `CRgn` Objekt, sodass sie der Union von zwei angegebenen entspricht `CRgn` Objekte.|  
|[CRgn::CopyRgn](#copyrgn)|Legt eine `CRgn` Objekt, sodass er eine Kopie einer angegebenen ist `CRgn` Objekt.|  
|[CRgn::CreateEllipticRgn](#createellipticrgn)|Initialisiert ein `CRgn` Objekt mit einem elliptischen Bereich.|  
|[CRgn::CreateEllipticRgnIndirect](#createellipticrgnindirect)|Initialisiert eine `CRgn` Objekt mit einem elliptischen Bereich definiert durch eine [RECT](../../mfc/reference/rect-structure1.md) Struktur.|  
|[CRgn::CreateFromData](#createfromdata)|Erstellt einen Bereich aus der angegebenen Region und die Transformation Daten an.|  
|[CRgn::CreateFromPath](#createfrompath)|Erstellt einen Bereich aus dem Pfad, der den angegebenen Gerätekontext ausgewählt ist.|  
|[CRgn::CreatePolygonRgn](#createpolygonrgn)|Initialisiert ein `CRgn` Objekt mit einem Polygonbereich. Das System das Polygon wird automatisch geschlossen, ggf. durch eine Linie zwischen dem letzten Scheitelpunkt mit dem ersten.|  
|[CRgn::CreatePolyPolygonRgn](#createpolypolygonrgn)|Initialisiert ein `CRgn` Objekt mit einer Region eine Reihe von geschlossenen Polygonen besteht. Die Polygone zusammenhanglosen werden, oder sie überlappen.|  
|[CRgn::CreateRectRgn](#createrectrgn)|Initialisiert ein `CRgn` Objekt mit einem rechteckigen Bereich liegt.|  
|[CRgn::CreateRectRgnIndirect](#createrectrgnindirect)|Initialisiert eine `CRgn` Objekt mit einem rechteckigen Bereichs, durch eine [RECT](../../mfc/reference/rect-structure1.md) Struktur.|  
|[CRgn::CreateRoundRectRgn](#createroundrectrgn)|Initialisiert ein `CRgn` Objekt mit einem rechteckigen Bereich mit abgerundeten Ecken.|  
|[CRgn::EqualRgn](#equalrgn)|Überprüft zwei `CRgn` Objekte bestimmen, ob sie gleich sind.|  
|[CRgn::FromHandle](#fromhandle)|Gibt einen Zeiger auf ein `CRgn` Objekt, wenn ein Handle zu einer Windows-Region vorhanden.|  
|[CRgn::GetRegionData](#getregiondata)|Füllt den angegebenen Puffer mit Daten, die den angegebenen Bereich beschreibt.|  
|[CRgn::GetRgnBox](#getrgnbox)|Ruft die Koordinaten des umschließenden Rechtecks von einem `CRgn` Objekt.|  
|[CRgn::OffsetRgn](#offsetrgn)|Verschiebt ein `CRgn` Objekt, indem die angegebenen Offsets.|  
|[CRgn::PtInRegion](#ptinregion)|Bestimmt, ob ein angegebener Punkt in der Region.|  
|[CRgn::RectInRegion](#rectinregion)|Bestimmt, ob alle einem angegebenen Rechteck innerhalb der Grenzen der Region gehört.|  
|[CRgn::SetRectRgn](#setrectrgn)|Legt die `CRgn` Objekt in den angegebenen rechteckigen Bereich.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRgn::operator HRGN](#operator_hrgn)|Gibt das Windows-Handle, das innerhalb der `CRgn` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Bereich ist ein elliptischen oder polygonalen Bereich innerhalb eines Fensters. Um Bereiche verwenden zu können, verwenden Sie die Memberfunktionen der Klasse `CRgn` mit Clipping-Funktionen, die als Mitglieder der Klasse definiert `CDC`.  
  
 Die Memberfunktionen von `CRgn` erstellen, ändern und Abrufen von Informationen über das Region-Objekt, das für die sie aufgerufen werden.  
  
 Weitere Informationen zur Verwendung von `CRgn`, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CRgn`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="combinergn"></a>  CRgn::CombineRgn  
 Erstellt eine neue GDI-Region durch Kombinieren von zwei vorhandenen Regionen an.  
  
```  
int CombineRgn(
    CRgn* pRgn1,  
    CRgn* pRgn2,  
    int nCombineMode);
```  
  
### <a name="parameters"></a>Parameter  
 `pRgn1`  
 Identifiziert eine vorhandene Region an.  
  
 `pRgn2`  
 Identifiziert eine vorhandene Region an.  
  
 `nCombineMode`  
 Gibt den Vorgang ausgeführt werden, wenn die beiden Regionen kombiniert. Eine der folgenden Werte sind möglich:  
  
- **RGN_AND** überlappenden Bereiche von beiden Regionen (Schnittmenge) verwendet.  
  
- **RGN_COPY** erstellt eine Kopie des Bereichs von 1 (identifiziert durch `pRgn1`).  
  
- **RGN_DIFF** erstellt einen Bereich, bestehend aus den Bereichen des Bereichs von 1 (identifiziert durch `pRgn1`), sind nicht Teil von Region 2 (identifizierte `pRgn2`).  
  
- **RGN_OR** beide Regionen in ihrer Gesamtheit (Vereinigung) kombiniert.  
  
- **RGN_XOR** entfernt überlappenden Bereiche jedoch beide Regionen kombiniert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Typ der resultierenden Region. Die folgenden Werte sind möglich:  
  
- **COMPLEXREGION** neues Region weist überlappende Rahmen.  
  
- **Fehler** keine neue Region erstellt.  
  
- **NULLREGION** neues Region ist leer.  
  
- **SIMPLEREGION** neues Region besitzt keine überlappenden Rahmen.  
  
### <a name="remarks"></a>Hinweise  
 Die Regionen kombiniert werden nach den Angaben von `nCombineMode`.  
  
 Die beiden angegebenen Regionen kombiniert sind, und die resultierende Bereiches befindet sich in der `CRgn` Objekt. Folglich beliebige Region gespeichert ist, in der `CRgn` Objekt wird durch die kombinierten Region ersetzt.  
  
 Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB an Arbeitsspeicher begrenzt, welcher Wert kleiner ist.  
  
 Verwendung [CopyRgn](#copyrgn) einer Region in einer anderen Region zu kopieren.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#144](../../mfc/codesnippet/cpp/crgn-class_1.cpp)]  
  
##  <a name="copyrgn"></a>  CRgn::CopyRgn  
 Kopiert den Bereich durch definierten `pRgnSrc` in die `CRgn` Objekt.  
  
```  
int CopyRgn(CRgn* pRgnSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `pRgnSrc`  
 Identifiziert eine vorhandene Region an.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Typ der resultierenden Region. Die folgenden Werte sind möglich:  
  
- **COMPLEXREGION** neues Region weist überlappende Rahmen.  
  
- **Fehler** keine neue Region erstellt.  
  
- **NULLREGION** neues Region ist leer.  
  
- **SIMPLEREGION** neues Region besitzt keine überlappenden Rahmen.  
  
### <a name="remarks"></a>Hinweise  
 Die neue Region ersetzt die Region, die früher gespeichert, der `CRgn` Objekt. Diese Funktion ist ein Sonderfall, der die [CombineRgn](#combinergn) Memberfunktion.  
  
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
 `x1`  
 Gibt die logische X-Koordinate der oberen linken Ecke des umschließenden Rechtecks der Ellipse.  
  
 `y1`  
 Gibt die logische y-Koordinate der oberen linken Ecke des umschließenden Rechtecks der Ellipse.  
  
 `x2`  
 Gibt die logische X-Koordinate der unteren rechten Ecke des umschließenden Rechtecks der Ellipse.  
  
 `y2`  
 Gibt die logische y-Koordinate der unteren rechten Ecke des umschließenden Rechtecks der Ellipse.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Region wird durch das umschließende Rechteck von definiert `x1`, `y1`, `x2`, und `y2`. Der Bereich befindet sich in der `CRgn` Objekt.  
  
 Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB an Arbeitsspeicher begrenzt, welcher Wert kleiner ist.  
  
 Wenn es nicht mehr verwendet eine Region erstellt, mit der `CreateEllipticRgn` -Funktion, eine Anwendung sollte wählen Sie die Region, des Gerätekontext und verwenden Sie die `DeleteObject` Funktion zu entfernen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#145](../../mfc/codesnippet/cpp/crgn-class_2.cpp)]  
  
##  <a name="createellipticrgnindirect"></a>  CRgn::CreateEllipticRgnIndirect  
 Erstellt einen elliptischen Bereich an.  
  
```  
BOOL CreateEllipticRgnIndirect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf eine `RECT` Struktur oder ein `CRect` Objekt, das die logischen Koordinaten linken, oberen und unteren rechten Ecke des umschließenden Rechtecks der Ellipse enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Region wird durch die Struktur oder das Objekt definiert `lpRect` und befindet sich in der `CRgn` Objekt.  
  
 Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB an Arbeitsspeicher begrenzt, welcher Wert kleiner ist.  
  
 Wenn es nicht mehr verwendet eine Region erstellt, mit der `CreateEllipticRgnIndirect` -Funktion, eine Anwendung sollte wählen Sie die Region, des Gerätekontext und verwenden Sie die `DeleteObject` Funktion zu entfernen.  
  
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
 *lpXForm*  
 Verweist auf ein [XFORM](../../mfc/reference/xform-structure.md) Datenstruktur, die die Transformation definiert, die für die Region ausgeführt werden. Wenn dieser Zeiger ist **NULL**, die Identitätstransformation verwendet wird.  
  
 `nCount`  
 Gibt die Anzahl der Bytes, die durch `pRgnData`.  
  
 `pRgnData`  
 Verweist auf eine [RGNDATA](../../mfc/reference/rgndata-structure.md) Datenstruktur, die Daten für die Region enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Eine Anwendung kann Daten für eine Region abrufen, durch Aufrufen der `CRgn::GetRegionData` Funktion.  
  
##  <a name="createfrompath"></a>  CRgn::CreateFromPath  
 Erstellt einen Bereich aus dem Pfad, der den angegebenen Gerätekontext ausgewählt ist.  
  
```  
BOOL CreateFromPath(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Bezeichnet einen Gerätekontext, der einen geschlossenen Pfad enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Der Gerätekontext identifizierte der `pDC` Parameter muss einen geschlossenen Pfad enthalten. Nach dem `CreateFromPath` konvertiert einen Pfad in einer Region, Windows, verwirft den geschlossenen Pfad aus dem Gerätekontext.  
  
##  <a name="createpolygonrgn"></a>  CRgn::CreatePolygonRgn  
 Erstellt einen Polygonbereich an.  
  
```  
BOOL CreatePolygonRgn(
    LPPOINT lpPoints,  
    int nCount,  
    int nMode);
```  
  
### <a name="parameters"></a>Parameter  
 `lpPoints`  
 Verweist auf ein Array von **Punkt** Strukturen oder ein Array von `CPoint` Objekte. Jede Struktur gibt die X-Koordinate und y-Koordinate eines scheitels des Polygons. Die **Punkt** Struktur weist folgende Form:  
  
 `typedef struct tagPOINT {`  
  
 `int x;`  
  
 `int y;`  
  
 `} POINT;`  
  
 `nCount`  
 Gibt die Anzahl der **Punkt** Strukturen oder `CPoint` Objekte im Array verweist `lpPoints`.  
  
 `nMode`  
 Gibt den Modus "ausfüllen" für die Region. Dieser Parameter kann entweder sein **ALTERNATIVEN** oder **WINDING**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Das System das Polygon wird automatisch geschlossen, ggf. durch eine Linie zwischen dem letzten Scheitelpunkt mit dem ersten. Der resultierende Bereich befindet sich in der `CRgn` Objekt.  
  
 Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB an Arbeitsspeicher begrenzt, welcher Wert kleiner ist.  
  
 Wenn der Polygon füllenden Modus ist **ALTERNATIVEN**, das System füllt den Bereich zwischen ungerader und gerader Polygonseiten für jede Scanzeile. Das System füllt, also den Bereich zwischen der ersten und zweiten Seite, zwischen dem dritten und vierten Seite und So weiter.  
  
 Wenn der Polygon füllenden Modus ist **WINDING**, verwendet das System die Richtung, in der Abbildung gezeichnet wurde, um zu ermitteln, ob eine Fläche auszufüllen. Jedes Liniensegment in einem Polygon wird im Uhrzeigersinn oder gegen den Uhrzeigersinn gezeichnet. Wenn gegen den Uhrzeigersinn Liniensegment eine imaginäre Linie gezeichnet aus einem eingeschlossenen Bereich außerhalb der Abbildung durchläuft, wird eine Anzahl erhöht. Wenn die Zeile gegen den Uhrzeigersinn Liniensegment durchläuft, wird die Anzahl verringert. Der Bereich wird ausgefüllt, wenn der Wert ungleich NULL ist, wenn die Zeile außerhalb der in der Abbildung erreicht.  
  
 Wenn eine Anwendung nicht mehr verwendet eine Region erstellt, mit der `CreatePolygonRgn` -Funktion, sie sollten wählen Sie die Region, des Gerätekontext und verwenden Sie die `DeleteObject` Funktion zu entfernen.  
  
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
 `lpPoints`  
 Verweist auf ein Array von **Punkt** Strukturen oder ein Array von `CPoint` -Objekten, die die Eckpunkte des der Polygone definiert. Jedes Polygon muss explizit geschlossen werden, da das System nicht sie automatisch geschlossen wird. Die Polygone werden fortlaufend angegeben. Die **Punkt** Struktur weist folgende Form:  
  
 `typedef struct tagPOINT {`  
  
 `int x;`  
  
 `int y;`  
  
 `} POINT;`  
  
 `lpPolyCounts`  
 Verweist auf ein Array von ganzen Zahlen. Die erste ganze Zahl gibt die Anzahl der Scheitelpunkte im ersten Polygons in die `lpPoints` Array, die zweite ganze Zahl gibt die Anzahl der Scheitelpunkte in der zweiten Polygon und So weiter.  
  
 `nCount`  
 Gibt die Gesamtanzahl von ganzen Zahlen in der `lpPolyCounts` Array.  
  
 `nPolyFillMode`  
 Gibt den Modus für die Polygon-füllen. Dieser Wert möglicherweise entweder **ALTERNATIVEN** oder **WINDING**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Der resultierende Bereich befindet sich in der `CRgn` Objekt.  
  
 Die Polygone zusammenhanglosen werden, oder sie überlappen.  
  
 Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB an Arbeitsspeicher begrenzt, welcher Wert kleiner ist.  
  
 Wenn der Polygon füllenden Modus ist **ALTERNATIVEN**, das System füllt den Bereich zwischen ungerader und gerader Polygonseiten für jede Scanzeile. Das System füllt, also den Bereich zwischen der ersten und zweiten Seite, zwischen dem dritten und vierten Seite und So weiter.  
  
 Wenn der Polygon füllenden Modus ist **WINDING**, verwendet das System die Richtung, in der Abbildung gezeichnet wurde, um zu ermitteln, ob eine Fläche auszufüllen. Jedes Liniensegment in einem Polygon wird im Uhrzeigersinn oder gegen den Uhrzeigersinn gezeichnet. Wenn gegen den Uhrzeigersinn Liniensegment eine imaginäre Linie gezeichnet aus einem eingeschlossenen Bereich außerhalb der Abbildung durchläuft, wird eine Anzahl erhöht. Wenn die Zeile gegen den Uhrzeigersinn Liniensegment durchläuft, wird die Anzahl verringert. Der Bereich wird ausgefüllt, wenn der Wert ungleich NULL ist, wenn die Zeile außerhalb der in der Abbildung erreicht.  
  
 Wenn eine Anwendung nicht mehr verwendet eine Region erstellt, mit der `CreatePolyPolygonRgn` -Funktion, sie sollten wählen Sie die Region, des Gerätekontext und verwenden Sie die [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) Member-Funktion, um ihn zu entfernen.  
  
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
 `x1`  
 Gibt die logische X-Koordinate der oberen linken Ecke des Bereichs an.  
  
 `y1`  
 Gibt die logische y-Koordinate der oberen linken Ecke des Bereichs an.  
  
 `x2`  
 Gibt die logische X-Koordinate der unteren rechten Ecke des Bereichs an.  
  
 `y2`  
 Gibt die logische y-Koordinate der unteren rechten Ecke des Bereichs an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB an Arbeitsspeicher begrenzt, welcher Wert kleiner ist.  
  
 Wenn es nicht mehr verwendet eine Region erstellt, indem `CreateRectRgn`, eine Anwendung verwenden, sollten die [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) Memberfunktion versucht, den Bereich zu entfernen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#147](../../mfc/codesnippet/cpp/crgn-class_4.cpp)]  
  
 Ein weiteres Beispiel finden Sie unter [CRgn::CombineRgn](#combinergn).  
  
##  <a name="createrectrgnindirect"></a>  CRgn::CreateRectRgnIndirect  
 Erstellt einen rechteckigen Bereich, die in gespeichert ist die `CRgn` Objekt.  
  
```  
BOOL CreateRectRgnIndirect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf eine `RECT` Struktur oder `CRect` Objekt, das die logischen Koordinaten linken, oberen und unteren rechten Ecke des Bereichs enthält. Die `RECT` Struktur weist folgende Form:  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB an Arbeitsspeicher begrenzt, welcher Wert kleiner ist.  
  
 Wenn es nicht mehr verwendet eine Region erstellt, indem `CreateRectRgnIndirect`, eine Anwendung verwenden, sollten die [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) Memberfunktion versucht, den Bereich zu entfernen.  
  
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
 `x1`  
 Gibt die logische X-Koordinate der oberen linken Ecke des Bereichs an.  
  
 `y1`  
 Gibt die logische y-Koordinate der oberen linken Ecke des Bereichs an.  
  
 `x2`  
 Gibt die logische X-Koordinate der unteren rechten Ecke des Bereichs an.  
  
 `y2`  
 Gibt die logische y-Koordinate der unteren rechten Ecke des Bereichs an.  
  
 *x3*  
 Gibt die Breite der Ellipse verwendet, um die abgerundeten Ecken zu erstellen.  
  
 `y3`  
 Gibt die Höhe der Ellipse verwendet, um die abgerundeten Ecken zu erstellen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB an Arbeitsspeicher begrenzt, welcher Wert kleiner ist.  
  
 Wenn eine Anwendung nicht mehr verwendet eine Region erstellt, mit der `CreateRoundRectRgn` -Funktion, sie sollten wählen Sie die Region, des Gerätekontext und verwenden Sie die [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) Member-Funktion, um ihn zu entfernen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#149](../../mfc/codesnippet/cpp/crgn-class_6.cpp)]  
  
##  <a name="crgn"></a>  CRgn::CRgn  
 Erstellt ein `CRgn`-Objekt.  
  
```  
CRgn();
```  
  
### <a name="remarks"></a>Hinweise  
 Die `m_hObject` -Datenmember enthält keine gültigen Windows-GDI-Region aus, bis das Objekt mit einem oder mehreren der anderen initialisiert wird `CRgn` Memberfunktionen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRgn::CreateRoundRectRgn](#createroundrectrgn).  
  
##  <a name="equalrgn"></a>  CRgn::EqualRgn  
 Bestimmt, ob der jeweiligen Region der Region in gespeicherten entspricht der `CRgn` Objekt.  
  
```  
BOOL EqualRgn(CRgn* pRgn) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pRgn`  
 Identifiziert den Bereich an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die beiden Bereiche gleichwertig sind; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#150](../../mfc/codesnippet/cpp/crgn-class_7.cpp)]  
  
##  <a name="fromhandle"></a>  CRgn::FromHandle  
 Gibt einen Zeiger auf ein `CRgn` Objekt, wenn ein Handle zu einer Windows-Region vorhanden.  
  
```  
static CRgn* PASCAL FromHandle(HRGN hRgn);
```  
  
### <a name="parameters"></a>Parameter  
 `hRgn`  
 Gibt ein Handle für ein Windows-Region an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CRgn` Objekt. Wenn die Funktion nicht erfolgreich war, ist der Rückgabewert **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine `CRgn` Objekt ist nicht bereits angefügt an das Handle, das einen temporären `CRgn` Objekt erstellt und angefügt. Dieser temporäre `CRgn` Objekt ist nur dann gültig, bis das nächste Mal die Anwendung Leerlaufzeit in seiner-Ereignisschleife aufweist, zu dem alle temporären Grafik Zeit Objekte gelöscht werden. Anders ausgedrückt: Dies ist, dass der Zugriff auf das temporäre Objekt während der Verarbeitung der Nachricht von einem Fenster nur gültig ist.  
  
##  <a name="getregiondata"></a>  CRgn::GetRegionData  
 Füllt den angegebenen Puffer mit Daten, die den Bereich beschreibt.  
  
```  
int GetRegionData(
    LPRGNDATA lpRgnData,  
    int nCount) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpRgnData`  
 Verweist auf eine [RGNDATA](../../mfc/reference/rgndata-structure.md) Datenstruktur, die die Informationen erhält. Wenn dieser Parameter ist **NULL**, den Rückgabewert enthält die Anzahl der Bytes, die für die Region Daten erforderlich sind.  
  
 `nCount`  
 Gibt die Größe in Bytes, der die `lpRgnData` Puffer.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ausgeführt wird und `nCount` gibt eine ausreichende Anzahl von Bytes, der Rückgabewert ist immer `nCount`. Wenn die Funktion fehlerhaft ist oder wenn `nCount` gibt kleiner als angemessene Anzahl von Bytes, der Rückgabewert ist 0 (Fehler).  
  
### <a name="remarks"></a>Hinweise  
 Diese Daten umfassen die Dimensionen der Rechtecke, aus denen der Bereich besteht. Diese Funktion dient in Verbindung mit der `CRgn::CreateFromData` Funktion.  
  
##  <a name="getrgnbox"></a>  CRgn::GetRgnBox  
 Ruft die Koordinaten des umschließenden Rechtecks des ab der `CRgn` Objekt.  
  
```  
int GetRgnBox(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf eine `RECT` Struktur oder `CRect` Objekt, das die Koordinaten des umschließenden Rechtecks empfangen. Die `RECT` Struktur weist folgende Form:  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Region-Typs. Die folgenden Werte sind möglich:  
  
- **COMPLEXREGION** Region wurde überlappende Rahmen.  
  
- **NULLREGION** Region ist leer.  
  
- **Fehler beim** `CRgn` Objekts gibt kein gültigen Bereichs.  
  
- **SIMPLEREGION** Region besitzt keine überlappenden Rahmen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRgn::CreatePolygonRgn](#createpolygonrgn).  
  
##  <a name="offsetrgn"></a>  CRgn::OffsetRgn  
 Verschiebt die Region gespeichert, der `CRgn` Objekt durch den angegebenen Offsets.  
  
```  
int OffsetRgn(
    int x,  
    int y);  
  
int OffsetRgn(POINT point);
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 Gibt die Anzahl der Einheiten, die zum Verschieben von links oder rechts an.  
  
 *y*  
 Gibt die Anzahl der Einheiten, um nach oben oder unten zu verschieben.  
  
 `point`  
 Die X-Koordinate der `point` gibt die Anzahl der Einheiten, die zum Verschieben von links oder rechts. Die y-Koordinate der `point` gibt die Anzahl der Einheiten, um nach oben oder unten zu verschieben. Die `point` Parameter möglicherweise entweder eine **Punkt** Struktur oder ein `CPoint` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die neue Region-Typs. Eine der folgenden Werte sind möglich:  
  
- **COMPLEXREGION** Region wurde überlappende Rahmen.  
  
- **Fehler** Bereichshandle ist ungültig.  
  
- **NULLREGION** Region ist leer.  
  
- **SIMPLEREGION** Region besitzt keine überlappenden Rahmen.  
  
### <a name="remarks"></a>Hinweise  
 Die-Funktion verschiebt die Region *x* Einheiten entlang der x-Achse und *y* Einheiten entlang der y-Achse.  
  
 Die Koordinatenwerte eines Datenbereichs müssen kleiner als oder gleich 32.767 und größer als oder gleich -32.768 sein. Die *x* und *y* Parameter müssen sorgfältig gewählt werden, um zu verhindern, dass ungültige Region Koordinaten.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRgn::CreateEllipticRgn](#createellipticrgn).  
  
##  <a name="operator_hrgn"></a>  CRgn::operator HRGN  
 Verwenden Sie diesen Operator, um das angefügte Windows-GDI-Handle Abrufen der `CRgn` Objekt.  
  
```  
operator HRGN() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, ein Handle für das Windows-GDI-Objekt durch dargestellt die `CRgn` Objekt; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator wird ein Typumwandlungsoperator, die direkte Verwendung von unterstützt eine **HRGN** Objekt.  
  
 Weitere Informationen zum Verwenden von Grafikobjekten, finden Sie im Artikel [Grafik Objekte](http://msdn.microsoft.com/library/windows/desktop/dd144962) im Windows SDK.  
  
##  <a name="ptinregion"></a>  CRgn::PtInRegion  
 Überprüft, ob der Punkt, der durch *x* und *y* befindet sich in der Region gespeichert, der `CRgn` Objekt.  
  
```  
BOOL PtInRegion(
    int x,  
    int y) const;  
  
BOOL PtInRegion(POINT point) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 Gibt die logische X-Koordinate des Punkts zu testen.  
  
 *y*  
 Gibt die logische y-Koordinate des Punkts zu testen.  
  
 `point`  
 Die x- und y-Koordinaten der `point` Geben Sie die x- und y-Koordinaten des Punkts, der den Wert testen. Die `point` Parameter kann entweder ein **Punkt** Struktur oder ein `CPoint` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Punkt in der Region ist; andernfalls 0.  
  
##  <a name="rectinregion"></a>  CRgn::RectInRegion  
 Bestimmt, ob durch einen beliebigen Teil des Rechtecks angegebene `lpRect` innerhalb der Grenzen der Region gespeichert, der `CRgn` Objekt.  
  
```  
BOOL RectInRegion(LPCRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf eine `RECT` Struktur oder `CRect` Objekt. Die `RECT` Struktur weist folgende Form:  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn Sie einen beliebigen Teil des angegebenen Rechtecks innerhalb der Grenzen des Bereichs liegt; andernfalls 0.  
  
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
 `x1`  
 Gibt die X-Koordinate von der linken oberen Ecke des rechteckigen Bereichs an.  
  
 `y1`  
 Gibt die y-Koordinate von der linken oberen Ecke des rechteckigen Bereichs an.  
  
 `x2`  
 Gibt die X-Koordinate der unteren rechten Ecke des rechteckigen Bereichs an.  
  
 `y2`  
 Gibt die y-Koordinate der unteren rechten Ecke des rechteckigen Bereichs an.  
  
 `lpRect`  
 Gibt den rechteckigen Bereich liegt. Kann entweder ein Zeiger auf eine `RECT` Struktur oder ein `CRect` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Im Gegensatz zu [CreateRectRgn](#createrectrgn), jedoch ist es keine zusätzlichen Speicher zuweisen, aus dem Heap der lokalen Windows-Anwendung. Stattdessen wird den Speicherplatz für die Region gespeichert die `CRgn` Objekt. Dies bedeutet, dass die `CRgn` Objekt bereits initialisiert worden sein, mit einem gültigen Windows-Bereich vor dem Aufruf `SetRectRgn`. Die Punkte, die vom `x1`, `y1`, `x2`, und `y2` Geben Sie die minimale Größe des belegten Speicherplatzes.  
  
 Verwenden Sie diese Funktion statt der `CreateRectRgn` Member-Funktion, um Aufrufe an den lokalen Speicher-Manager zu vermeiden.  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



