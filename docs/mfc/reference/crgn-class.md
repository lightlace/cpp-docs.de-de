---
title: CRgn-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRgn
dev_langs:
- C++
helpviewer_keywords:
- HRGN
- CRgn class
- regions, MFC
ms.assetid: d904da84-76aa-481e-8780-b09485f49e64
caps.latest.revision: 23
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
ms.openlocfilehash: 9ec2634a2495d301e09b483d60db8838be0b14ab
ms.lasthandoff: 02/24/2017

---
# <a name="crgn-class"></a>CRgn-Klasse
Kapselt einen Bereich der Windows GDI (Graphics Device Interface).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CRgn : public CGdiObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRgn::CRgn](#crgn)|Erstellt ein `CRgn`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRgn::CombineRgn](#combinergn)|Legt eine `CRgn` Objekt, sodass sie die Vereinigung von zwei angegebenen entspricht `CRgn` Objekte.|  
|[CRgn::CopyRgn](#copyrgn)|Legt eine `CRgn` Objekt, sodass es sich um eine Kopie einer angegebenen ist `CRgn` Objekt.|  
|[CRgn::CreateEllipticRgn](#createellipticrgn)|Initialisiert ein `CRgn` Objekt mit einem elliptischen Bereich.|  
|[CRgn::CreateEllipticRgnIndirect](#createellipticrgnindirect)|Initialisiert eine `CRgn` Objekt mit einem elliptischen Bereich definiert ein [RECT](../../mfc/reference/rect-structure1.md) Struktur.|  
|[CRgn::CreateFromData](#createfromdata)|Erstellt einen Bereich aus der angegebenen Region und die Transformation Daten.|  
|[CRgn::CreateFromPath](#createfrompath)|Erstellt einen Bereich aus dem Pfad, der den angegebenen Gerätekontext ausgewählt ist.|  
|[CRgn::CreatePolygonRgn](#createpolygonrgn)|Initialisiert ein `CRgn` Objekt mit einem polygonalen Bereich. Das System schließt das Polygon automatisch, ggf. durch Zeichnen einer Linie zwischen dem letzten Scheitelpunkt zum ersten.|  
|[CRgn::CreatePolyPolygonRgn](#createpolypolygonrgn)|Initialisiert ein `CRgn` Objekt mit einem Bereich mit einer Reihe von geschlossenen Polygonen. Die Polygone können sein, oder möglicherweise überlappen.|  
|[CRgn::CreateRectRgn](#createrectrgn)|Initialisiert ein `CRgn` -Objekt mit einem rechteckigen Bereich.|  
|[CRgn::CreateRectRgnIndirect](#createrectrgnindirect)|Initialisiert eine `CRgn` -Objekt mit einem rechteckigen Bereichs, durch eine [RECT](../../mfc/reference/rect-structure1.md) Struktur.|  
|[CRgn::CreateRoundRectRgn](#createroundrectrgn)|Initialisiert ein `CRgn` -Objekt mit einem rechteckigen Bereich mit abgerundeten Ecken.|  
|[CRgn::EqualRgn](#equalrgn)|Überprüft zwei `CRgn` Objekte bestimmen, ob diese gleich sind.|  
|[CRgn::FromHandle](#fromhandle)|Gibt einen Zeiger auf ein `CRgn` Objekt, wenn ein Handle auf einen Windows-Bereich angegeben.|  
|[CRgn::GetRegionData](#getregiondata)|Füllt den angegebenen Puffer mit Daten, die den angegebenen Bereich beschreibt.|  
|[CRgn::GetRgnBox](#getrgnbox)|Ruft die Koordinaten des umschließenden Rechtecks von einem `CRgn` Objekt.|  
|[CRgn::OffsetRgn](#offsetrgn)|Verschiebt ein `CRgn` -Objekt mit den angegebenen Offsets.|  
|[CRgn::PtInRegion](#ptinregion)|Bestimmt, ob es sich bei ein angegebenen Punkt in der Region befindet.|  
|[CRgn::RectInRegion](#rectinregion)|Bestimmt, ob ein Teil einem angegebenen Rechteck innerhalb der Grenzen des Bereichs ist.|  
|[CRgn::SetRectRgn](#setrectrgn)|Legt die `CRgn` Objekt in den angegebenen rechteckige Bereich.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRgn::operator HRGN](#operator_hrgn)|Gibt das Windows-Handle, das Bestandteil der `CRgn` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Bereich ist ein elliptischen oder polygonalen Bereich innerhalb eines Fensters. Um Bereiche zu verwenden, verwenden Sie die Memberfunktionen der Klasse `CRgn` mit die Clipping definierten Funktionen als Member der Klasse `CDC`.  
  
 Die Memberfunktionen von `CRgn` erstellen, ändern und Abrufen von Informationen über das Region-Objekt, für das sie aufgerufen werden.  
  
 Weitere Informationen zur Verwendung von `CRgn`, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CRgn`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="a-namecombinergna--crgncombinergn"></a><a name="combinergn"></a>CRgn::CombineRgn  
 Erstellt eine neue GDI-Region durch Kombinieren von zwei vorhandenen Bereichen.  
  
```  
int CombineRgn(
    CRgn* pRgn1,  
    CRgn* pRgn2,  
    int nCombineMode);
```  
  
### <a name="parameters"></a>Parameter  
 `pRgn1`  
 Identifiziert einen vorhandenen Bereich.  
  
 `pRgn2`  
 Identifiziert einen vorhandenen Bereich.  
  
 `nCombineMode`  
 Gibt den Vorgang ausgeführt werden, wenn die beiden Bereiche kombiniert. Einer der folgenden Werte sind möglich:  
  
- **RGN_AND** überlappenden Bereiche der beiden Regionen (Schnittmenge) verwendet.  
  
- **RGN_COPY** erstellt eine Kopie der Region 1 (identifiziert durch `pRgn1`).  
  
- **RGN_DIFF** erstellt einen Bereich, bestehend aus den Bereichen der Region 1 (identifiziert durch `pRgn1`), sind nicht Teil von Region 2 (identifizierten `pRgn2`).  
  
- **RGN_OR** beide Regionen in ihrer Gesamtheit (Vereinigung) kombiniert.  
  
- **RGN_XOR** entfernt überlappenden Bereiche jedoch beide Regionen kombiniert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Typ der resultierenden Region. Die folgenden Werte sind möglich:  
  
- **COMPLEXREGION** neue Region hat Ränder überlappen.  
  
- **Fehler beim** keine neue Region erstellt.  
  
- **NULLREGION** neue Region ist leer.  
  
- **SIMPLEREGION** neue Region besitzt keine überlappenden Rahmen.  
  
### <a name="remarks"></a>Hinweise  
 Die Bereiche werden kombiniert gemäß `nCombineMode`.  
  
 Die beiden angegebenen Bereiche werden kombiniert, und die resultierende Bereichshandle befindet sich in der `CRgn` Objekt. Daher unabhängig Region gespeichert ist, in der `CRgn` Objekt wird durch den kombinierten Bereich ersetzt.  
  
 Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB begrenzt, welcher Wert kleiner ist.  
  
 Verwendung [CopyRgn](#copyrgn) einfach eine Region in einer anderen Region kopieren.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#144;](../../mfc/codesnippet/cpp/crgn-class_1.cpp)]  
  
##  <a name="a-namecopyrgna--crgncopyrgn"></a><a name="copyrgn"></a>CRgn::CopyRgn  
 Kopiert den Bereich definiert `pRgnSrc` in den `CRgn` Objekt.  
  
```  
int CopyRgn(CRgn* pRgnSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `pRgnSrc`  
 Identifiziert einen vorhandenen Bereich.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Typ der resultierenden Region. Die folgenden Werte sind möglich:  
  
- **COMPLEXREGION** neue Region hat Ränder überlappen.  
  
- **Fehler beim** keine neue Region erstellt.  
  
- **NULLREGION** neue Region ist leer.  
  
- **SIMPLEREGION** neue Region besitzt keine überlappenden Rahmen.  
  
### <a name="remarks"></a>Hinweise  
 Die neue Region die Region, die früher in gespeicherten ersetzt die `CRgn` Objekt. Diese Funktion ist eine besondere Variante der [CombineRgn](#combinergn) Member-Funktion.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRgn::CreateEllipticRgn](#createellipticrgn).  
  
##  <a name="a-namecreateellipticrgna--crgncreateellipticrgn"></a><a name="createellipticrgn"></a>CRgn::CreateEllipticRgn  
 Erstellt einen elliptischen Bereich.  
  
```  
BOOL CreateEllipticRgn(
    int x1,  
    int y1,  
    int x2,  
    int y2);
```  
  
### <a name="parameters"></a>Parameter  
 `x1`  
 Gibt die logische X-Koordinate der oberen linken Ecke des umschließenden Rechtecks der Ellipse an.  
  
 `y1`  
 Gibt die logische y-Koordinate der oberen linken Ecke des umschließenden Rechtecks der Ellipse an.  
  
 `x2`  
 Gibt die logische X-Koordinate der unteren rechten Ecke des umschließenden Rechtecks der Ellipse an.  
  
 `y2`  
 Gibt die logische y-Koordinate der unteren rechten Ecke des umschließenden Rechtecks der Ellipse an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Der Bereich wird definiert, indem das umschließende Rechteck von `x1`, `y1`, `x2`, und `y2`. Der Bereich befindet sich in der `CRgn` Objekt.  
  
 Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB begrenzt, welcher Wert kleiner ist.  
  
 Wenn er abgeschlossen hat, verwenden eine Region erstellt, mit der `CreateEllipticRgn` -Funktion, eine Anwendung sollte auswählen des Bereichs, der den Gerätekontext und die Verwendung der `DeleteObject` Funktion zu entfernen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#145;](../../mfc/codesnippet/cpp/crgn-class_2.cpp)]  
  
##  <a name="a-namecreateellipticrgnindirecta--crgncreateellipticrgnindirect"></a><a name="createellipticrgnindirect"></a>CRgn::CreateEllipticRgnIndirect  
 Erstellt einen elliptischen Bereich.  
  
```  
BOOL CreateEllipticRgnIndirect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf eine `RECT` Struktur oder ein `CRect` -Objekt, das die logischen Koordinaten der oberen linken und der unteren rechten Ecke das umschließende Rechteck der Ellipse enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Der Bereich wird definiert, indem die Struktur oder das Objekt, auf `lpRect` und befindet sich in der `CRgn` Objekt.  
  
 Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB begrenzt, welcher Wert kleiner ist.  
  
 Wenn er abgeschlossen hat, verwenden eine Region erstellt, mit der `CreateEllipticRgnIndirect` -Funktion, eine Anwendung sollte auswählen des Bereichs, der den Gerätekontext und die Verwendung der `DeleteObject` Funktion zu entfernen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRgn::CreateRectRgnIndirect](#createrectrgnindirect).  
  
##  <a name="a-namecreatefromdataa--crgncreatefromdata"></a><a name="createfromdata"></a>CRgn::CreateFromData  
 Erstellt einen Bereich aus der angegebenen Region und die Transformation Daten.  
  
```  
BOOL CreateFromData(
    const XFORM* lpXForm,  
    int nCount,  
    const RGNDATA* pRgnData);
```  
  
### <a name="parameters"></a>Parameter  
 *lpXForm*  
 Verweist auf ein [XFORM](../../mfc/reference/xform-structure.md) -Datenstruktur, die die Transformation definiert, die für die Region ausgeführt werden. Wenn dieser Zeiger ist **NULL**, die Identitätstransformation wird verwendet.  
  
 `nCount`  
 Gibt die Anzahl der Bytes, die auf den `pRgnData`.  
  
 `pRgnData`  
 Verweist auf eine [RGNDATA](../../mfc/reference/rgndata-structure.md) -Datenstruktur, die Daten für die Region enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Eine Anwendung kann Daten für eine Region abrufen, durch Aufrufen der `CRgn::GetRegionData` Funktion.  
  
##  <a name="a-namecreatefrompatha--crgncreatefrompath"></a><a name="createfrompath"></a>CRgn::CreateFromPath  
 Erstellt einen Bereich aus dem Pfad, der den angegebenen Gerätekontext ausgewählt ist.  
  
```  
BOOL CreateFromPath(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Gibt einen Gerätekontext, der einen geschlossenen Pfad enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Der Gerätekontext, der durch identifiziert die `pDC` Parameter muss einen geschlossenen Pfad enthalten. Nach dem `CreateFromPath` konvertiert einen Pfad in einen Bereich, Windows verwirft den geschlossenen Pfad aus dem Gerätekontext.  
  
##  <a name="a-namecreatepolygonrgna--crgncreatepolygonrgn"></a><a name="createpolygonrgn"></a>CRgn::CreatePolygonRgn  
 Erstellt einen polygonalen Bereich.  
  
```  
BOOL CreatePolygonRgn(
    LPPOINT lpPoints,  
    int nCount,  
    int nMode);
```  
  
### <a name="parameters"></a>Parameter  
 `lpPoints`  
 Verweist auf ein Array von **Punkt** Strukturen oder ein Array von `CPoint` Objekte. Jede Struktur gibt die X-Koordinate und y-Koordinate des Scheitelpunkts des Polygons. Die **Punkt** -Struktur hat folgende Form:  
  
 `typedef struct tagPOINT {`  
  
 `int x;`  
  
 `int y;`  
  
 `} POINT;`  
  
 `nCount`  
 Gibt die Anzahl der **Punkt** Strukturen oder `CPoint` Objekte im Array auf die `lpPoints`.  
  
 `nMode`  
 Gibt den Füllmodus für die Region an. Dieser Parameter kann entweder sein **ALTERNATIVEN** oder **WICKLUNGSREIHENFOLGEN**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Das System schließt das Polygon automatisch, ggf. durch Zeichnen einer Linie zwischen dem letzten Scheitelpunkt zum ersten. Der resultierende Bereich befindet sich in der `CRgn` Objekt.  
  
 Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB begrenzt, welcher Wert kleiner ist.  
  
 Wenn die Polygon-Füllmodus ist **ALTERNATIVEN**, das System füllt den Bereich zwischen ungerade und gerade Polygonseiten in jeder Scanzeile ein. Das System füllt, also den Bereich zwischen der ersten und zweiten Seite, zwischen dem dritten und vierten Seite usw..  
  
 Wenn die Polygon-Füllmodus ist **WICKLUNGSREIHENFOLGEN**, verwendet das System die Richtung, in der Abbildung, um festzustellen, ob das Ausfüllen eines Bereichs gezeichnet wurde. Jedes Liniensegment in einem Polygon wird im Uhrzeigersinn oder gegen den Uhrzeigersinn gezeichnet. Wenn eine imaginäre Linie gezeichnet aus einem eingeschlossenen Bereich außerhalb einer Abbildung im Uhrzeigersinn Liniensegment durchläuft, wird die Anzahl erhöht. Wenn die Zeile gegen den Uhrzeigersinn Liniensegment durchläuft, wird der Zähler verringert. Der Bereich wird ausgefüllt, wenn der Wert ungleich NULL ist, wenn die Zeile außerhalb der Abbildung erreicht.  
  
 Wenn eine Anwendung nicht mehr verwendet eine Region erstellt, mit der `CreatePolygonRgn` -Funktion sollten sie die Region, der den Gerätekontext und die Verwendung auswählen die `DeleteObject` Funktion zu entfernen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#146;](../../mfc/codesnippet/cpp/crgn-class_3.cpp)]  
  
##  <a name="a-namecreatepolypolygonrgna--crgncreatepolypolygonrgn"></a><a name="createpolypolygonrgn"></a>CRgn::CreatePolyPolygonRgn  
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
 Verweist auf ein Array von **Punkt** Strukturen oder ein Array von `CPoint` -Objekten, die die Eckpunkte der Polygone definiert. Jedes Polygon muss explizit geschlossen werden, da das System nicht diese automatisch geschlossen wird. Die Polygone werden nacheinander festgelegt. Die **Punkt** -Struktur hat folgende Form:  
  
 `typedef struct tagPOINT {`  
  
 `int x;`  
  
 `int y;`  
  
 `} POINT;`  
  
 `lpPolyCounts`  
 Zeigt auf ein Array von ganzen Zahlen. Die erste ganze Zahl gibt die Anzahl der Scheitelpunkte im ersten Polygons in die `lpPoints` Array, die zweite ganze Zahl gibt die Anzahl der Scheitelpunkte in der zweiten Polygon und So weiter.  
  
 `nCount`  
 Gibt die Gesamtanzahl von ganzen Zahlen in der `lpPolyCounts` Array.  
  
 `nPolyFillMode`  
 Gibt den Modus Polygon füllen. Dieser Wert kann entweder sein **ALTERNATIVEN** oder **WICKLUNGSREIHENFOLGEN**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Der resultierende Bereich befindet sich in der `CRgn` Objekt.  
  
 Die Polygone können sein, oder möglicherweise überlappen.  
  
 Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB begrenzt, welcher Wert kleiner ist.  
  
 Wenn die Polygon-Füllmodus ist **ALTERNATIVEN**, das System füllt den Bereich zwischen ungerade und gerade Polygonseiten in jeder Scanzeile ein. Das System füllt, also den Bereich zwischen der ersten und zweiten Seite, zwischen dem dritten und vierten Seite usw..  
  
 Wenn die Polygon-Füllmodus ist **WICKLUNGSREIHENFOLGEN**, verwendet das System die Richtung, in der Abbildung, um festzustellen, ob das Ausfüllen eines Bereichs gezeichnet wurde. Jedes Liniensegment in einem Polygon wird im Uhrzeigersinn oder gegen den Uhrzeigersinn gezeichnet. Wenn eine imaginäre Linie gezeichnet aus einem eingeschlossenen Bereich außerhalb einer Abbildung im Uhrzeigersinn Liniensegment durchläuft, wird die Anzahl erhöht. Wenn die Zeile gegen den Uhrzeigersinn Liniensegment durchläuft, wird der Zähler verringert. Der Bereich wird ausgefüllt, wenn der Wert ungleich NULL ist, wenn die Zeile außerhalb der Abbildung erreicht.  
  
 Wenn eine Anwendung nicht mehr verwendet eine Region erstellt, mit der `CreatePolyPolygonRgn` -Funktion sollten sie die Region, der den Gerätekontext und die Verwendung auswählen die [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) Member-Funktion, um ihn zu entfernen.  
  
##  <a name="a-namecreaterectrgna--crgncreaterectrgn"></a><a name="createrectrgn"></a>CRgn::CreateRectRgn  
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
 Gibt die logische X-Koordinate der oberen linken Ecke des Bereichs.  
  
 `y1`  
 Gibt die logische y-Koordinate der oberen linken Ecke des Bereichs.  
  
 `x2`  
 Gibt die logische X-Koordinate der unteren rechten Ecke des Bereichs.  
  
 `y2`  
 Gibt die logische y-Koordinate der unteren rechten Ecke des Bereichs.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB begrenzt, welcher Wert kleiner ist.  
  
 Wenn er abgeschlossen wurde, mit einer Region erstellt, indem `CreateRectRgn`, eine Anwendung verwenden, sollten die [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) Member-Funktion, um den Bereich zu entfernen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#147;](../../mfc/codesnippet/cpp/crgn-class_4.cpp)]  
  
 Ein zusätzliches Beispiel finden Sie unter [CRgn::CombineRgn](#combinergn).  
  
##  <a name="a-namecreaterectrgnindirecta--crgncreaterectrgnindirect"></a><a name="createrectrgnindirect"></a>CRgn::CreateRectRgnIndirect  
 Erstellt einen rechteckigen Bereich, die in gespeichert ist die `CRgn` Objekt.  
  
```  
BOOL CreateRectRgnIndirect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf eine `RECT` Struktur oder `CRect` -Objekt, das die logischen Koordinaten der linken, oberen und unteren rechten Ecke des Bereichs enthält. Die `RECT` -Struktur hat folgende Form:  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB begrenzt, welcher Wert kleiner ist.  
  
 Wenn er abgeschlossen wurde, mit einer Region erstellt, indem `CreateRectRgnIndirect`, eine Anwendung verwenden, sollten die [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) Member-Funktion, um den Bereich zu entfernen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#148;](../../mfc/codesnippet/cpp/crgn-class_5.cpp)]  
  
##  <a name="a-namecreateroundrectrgna--crgncreateroundrectrgn"></a><a name="createroundrectrgn"></a>CRgn::CreateRoundRectRgn  
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
 Gibt die logische X-Koordinate der oberen linken Ecke des Bereichs.  
  
 `y1`  
 Gibt die logische y-Koordinate der oberen linken Ecke des Bereichs.  
  
 `x2`  
 Gibt die logische X-Koordinate der unteren rechten Ecke des Bereichs.  
  
 `y2`  
 Gibt die logische y-Koordinate der unteren rechten Ecke des Bereichs.  
  
 *x3*  
 Gibt die Breite der Ellipse, die verwendet werden, um die abgerundeten Ecken zu erstellen.  
  
 `y3`  
 Gibt die Höhe der Ellipse, die verwendet werden, um die abgerundeten Ecken zu erstellen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Größe eines Bereichs ist auf 32.767 von 32.767 logische Einheiten oder 64 KB begrenzt, welcher Wert kleiner ist.  
  
 Wenn eine Anwendung nicht mehr verwendet eine Region erstellt, mit der `CreateRoundRectRgn` -Funktion sollten sie die Region, der den Gerätekontext und die Verwendung auswählen die [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) Member-Funktion, um ihn zu entfernen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#149;](../../mfc/codesnippet/cpp/crgn-class_6.cpp)]  
  
##  <a name="a-namecrgna--crgncrgn"></a><a name="crgn"></a>CRgn::CRgn  
 Erstellt ein `CRgn`-Objekt.  
  
```  
CRgn();
```  
  
### <a name="remarks"></a>Hinweise  
 Die `m_hObject` -Datenmember enthält keine gültige Windows-GDI-Region, bis das Objekt, mit einem oder mehreren der anderen initialisiert wurde `CRgn` Memberfunktionen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRgn::CreateRoundRectRgn](#createroundrectrgn).  
  
##  <a name="a-nameequalrgna--crgnequalrgn"></a><a name="equalrgn"></a>CRgn::EqualRgn  
 Bestimmt, ob die angegebene Region in der Region in gespeicherten entspricht der `CRgn` Objekt.  
  
```  
BOOL EqualRgn(CRgn* pRgn) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pRgn`  
 Identifiziert den Bereich.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die beiden Bereiche gleichwertig sind; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#150;](../../mfc/codesnippet/cpp/crgn-class_7.cpp)]  
  
##  <a name="a-namefromhandlea--crgnfromhandle"></a><a name="fromhandle"></a>CRgn::FromHandle  
 Gibt einen Zeiger auf ein `CRgn` Objekt, wenn ein Handle auf einen Windows-Bereich angegeben.  
  
```  
static CRgn* PASCAL FromHandle(HRGN hRgn);
```  
  
### <a name="parameters"></a>Parameter  
 `hRgn`  
 Gibt ein Handle für ein Windows-Bereich.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein `CRgn` Objekt. Wenn die Funktion nicht erfolgreich war, ist der Rückgabewert **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein `CRgn` Objekt noch nicht angefügt, das Handle zu einem temporären `CRgn` Objekt erstellt und angefügt wird. Dieser temporäre `CRgn` Objekt ist nur dann gültig, bis das nächste Mal die Anwendung Leerlaufzeit in seiner Ereignisschleife aufweist, zu der Zeit, dass alle temporären Grafik Objekte gelöscht werden. Anders ausgedrückt: Dies ist, dass das temporäre Objekt nur während der Verarbeitung der Nachricht ein Fenster gültig ist.  
  
##  <a name="a-namegetregiondataa--crgngetregiondata"></a><a name="getregiondata"></a>CRgn::GetRegionData  
 Füllt den angegebenen Puffer mit Daten, die den Bereich beschreibt.  
  
```  
int GetRegionData(
    LPRGNDATA lpRgnData,  
    int nCount) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpRgnData`  
 Verweist auf eine [RGNDATA](../../mfc/reference/rgndata-structure.md) -Datenstruktur, die die Informationen erhält. Wenn dieser Parameter **NULL**, der Rückgabewert enthält die Anzahl der Bytes, die für die Region-Daten erforderlich sind.  
  
 `nCount`  
 Gibt die Größe in Bytes, der die `lpRgnData` Puffer.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ist und `nCount` gibt eine ausreichende Anzahl von Bytes, der Rückgabewert ist immer `nCount`. Wenn die Funktion fehlschlägt oder `nCount` gibt kleiner als ausreichende Anzahl von Bytes, ist der Rückgabewert 0 (Fehler).  
  
### <a name="remarks"></a>Hinweise  
 Diese Daten umfassen die Dimensionen der Rechtecke, die den Bereich bilden. Diese Funktion dient in Verbindung mit der `CRgn::CreateFromData` Funktion.  
  
##  <a name="a-namegetrgnboxa--crgngetrgnbox"></a><a name="getrgnbox"></a>CRgn::GetRgnBox  
 Ruft die Koordinaten des umschließenden Rechtecks der ab dem `CRgn` Objekt.  
  
```  
int GetRgnBox(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf eine `RECT` Struktur oder `CRect` -Objekt, das die Koordinaten des umschließenden Rechtecks zu erhalten. Die `RECT` -Struktur hat folgende Form:  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Region. Die folgenden Werte sind möglich:  
  
- **COMPLEXREGION** Bereich hat Ränder überlappen.  
  
- **NULLREGION** Region ist leer.  
  
- **Fehler beim** `CRgn` Objekts gibt kein gültigen Bereichs.  
  
- **SIMPLEREGION** Region besitzt keine überlappenden Rahmen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRgn::CreatePolygonRgn](#createpolygonrgn).  
  
##  <a name="a-nameoffsetrgna--crgnoffsetrgn"></a><a name="offsetrgn"></a>CRgn::OffsetRgn  
 Verschiebt die Region, die in gespeicherten der `CRgn` -Objekt mit den angegebenen Offsets.  
  
```  
int OffsetRgn(
    int x,  
    int y);  
  
int OffsetRgn(POINT point);
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die Anzahl der Einheiten, die zum Verschieben von links oder rechts.  
  
 *y*  
 Gibt die Anzahl der Einheiten nach oben oder unten zu verschieben.  
  
 `point`  
 Die X-Koordinate des `point` gibt die Anzahl der Einheiten, die zum Verschieben von links oder rechts. Die y-Koordinate des `point` gibt die Anzahl der Einheiten nach oben oder unten zu verschieben. Die `point` Parameter befinden sich entweder eine **Punkt** Struktur oder ein `CPoint` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der neue Bereich Typ. Einer der folgenden Werte sind möglich:  
  
- **COMPLEXREGION** Bereich hat Ränder überlappen.  
  
- **Fehler** Bereichshandle ist ungültig.  
  
- **NULLREGION** Region ist leer.  
  
- **SIMPLEREGION** Region besitzt keine überlappenden Rahmen.  
  
### <a name="remarks"></a>Hinweise  
 Die-Funktion verschiebt die Region *x* Einheiten entlang der x-Achse und *y* Einheiten entlang der y-Achse.  
  
 Die Koordinatenwerte eines Bereichs müssen kleiner oder gleich 32.767 und größer als oder gleich – 32.768 sein. Die *x* und *y* Parameter müssen sorgfältig ausgewählt werden, um zu verhindern, dass ungültige Region Koordinaten.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRgn::CreateEllipticRgn](#createellipticrgn).  
  
##  <a name="a-nameoperatorhrgna--crgnoperator-hrgn"></a><a name="operator_hrgn"></a>CRgn::operator HRGN  
 Verwenden Sie diesen Operator zum Abrufen der angefügten Windows GDI-Handle für die `CRgn` Objekt.  
  
```  
operator HRGN() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, ein Handle für das Windows-GDI-Objekt durch dargestellt die `CRgn` Objekt; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator ist ein Typumwandlungsoperator verwendet, die direkte Verwendung von unterstützt ein **HRGN** Objekt.  
  
 Weitere Informationen zur Verwendung von Grafikobjekten, finden Sie im Artikel [Grafik Objekte](http://msdn.microsoft.com/library/windows/desktop/dd144962) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameptinregiona--crgnptinregion"></a><a name="ptinregion"></a>CRgn::PtInRegion  
 Überprüft, ob der Punkt, der durch *x* und *y* in der Region in gespeichert ist die `CRgn` Objekt.  
  
```  
BOOL PtInRegion(
    int x,  
    int y) const;  
  
BOOL PtInRegion(POINT point) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die logische X-Koordinate des Punktes, der überprüft.  
  
 *y*  
 Gibt die logische y-Koordinate des Punktes, der überprüft.  
  
 `point`  
 Die x- und y-Koordinaten der `point` geben die x- und y-Koordinaten des Punkts, der den Wert testen. Die `point` Parameter kann entweder ein **Punkt** Struktur oder ein `CPoint` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Punkt in der Region ist; andernfalls 0.  
  
##  <a name="a-namerectinregiona--crgnrectinregion"></a><a name="rectinregion"></a>CRgn::RectInRegion  
 Bestimmt, ob alle Teile des Rechtecks durch angegebene `lpRect` innerhalb der Grenzen des Bereichs gespeichert, der `CRgn` Objekt.  
  
```  
BOOL RectInRegion(LPCRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf eine `RECT` Struktur oder `CRect` Objekt. Die `RECT` -Struktur hat folgende Form:  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn alle Teil des angegebenen Rechtecks liegt innerhalb der Grenzen des Bereichs; andernfalls 0.  
  
##  <a name="a-namesetrectrgna--crgnsetrectrgn"></a><a name="setrectrgn"></a>CRgn::SetRectRgn  
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
 `x1`  
 Gibt die X-Koordinate der oberen linken Ecke des rechteckigen Bereichs.  
  
 `y1`  
 Gibt die y-Koordinate der oberen linken Ecke des rechteckigen Bereichs.  
  
 `x2`  
 Gibt die X-Koordinate der unteren rechten Ecke des rechteckigen Bereichs.  
  
 `y2`  
 Gibt die y-Koordinate der unteren rechten Ecke des rechteckigen Bereichs.  
  
 `lpRect`  
 Gibt den rechteckigen Bereich an. Kann entweder ein Zeiger auf eine `RECT` Struktur oder ein `CRect` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Im Gegensatz zu [CreateRectRgn](#createrectrgn), es werden keine zusätzlichen Speicher reserviert, vom lokalen Heap der Windows-Anwendung. Stattdessen wird den Speicherplatz für die Region in gespeicherte der `CRgn` Objekt. Dies bedeutet, dass die `CRgn` Objekt bereits initialisiert worden sein, mit einem gültigen Windows-Bereich vor dem Aufruf von `SetRectRgn`. Die Punkte, die vom `x1`, `y1`, `x2`, und `y2` Geben Sie die minimale Größe des belegten Speicherplatzes.  
  
 Verwenden Sie diese Funktion statt der `CreateRectRgn` Member-Funktion zu vermeiden, dass der lokale Speicher-Manager aufgerufen.  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




