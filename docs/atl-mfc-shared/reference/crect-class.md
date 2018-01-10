---
title: CRect Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRect
- ATLTYPES/ATL::CRect
- ATLTYPES/ATL::CRect::CRect
- ATLTYPES/ATL::CRect::BottomRight
- ATLTYPES/ATL::CRect::CenterPoint
- ATLTYPES/ATL::CRect::CopyRect
- ATLTYPES/ATL::CRect::DeflateRect
- ATLTYPES/ATL::CRect::EqualRect
- ATLTYPES/ATL::CRect::Height
- ATLTYPES/ATL::CRect::InflateRect
- ATLTYPES/ATL::CRect::IntersectRect
- ATLTYPES/ATL::CRect::IsRectEmpty
- ATLTYPES/ATL::CRect::IsRectNull
- ATLTYPES/ATL::CRect::MoveToX
- ATLTYPES/ATL::CRect::MoveToXY
- ATLTYPES/ATL::CRect::MoveToY
- ATLTYPES/ATL::CRect::NormalizeRect
- ATLTYPES/ATL::CRect::OffsetRect
- ATLTYPES/ATL::CRect::PtInRect
- ATLTYPES/ATL::CRect::SetRect
- ATLTYPES/ATL::CRect::SetRectEmpty
- ATLTYPES/ATL::CRect::Size
- ATLTYPES/ATL::CRect::SubtractRect
- ATLTYPES/ATL::CRect::TopLeft
- ATLTYPES/ATL::CRect::UnionRect
- ATLTYPES/ATL::CRect::Width
dev_langs: C++
helpviewer_keywords:
- LPCRECT data type
- CRect class
- LPRECT operator
- RECT structure
ms.assetid: dee4e752-15d6-4db4-b68f-1ad65b2ed6ca
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 067f683b5322b11a4ca33f015d64850c8113ce18
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="crect-class"></a>CRect-Klasse
Ähnelt der Windows [RECT](../../mfc/reference/rect-structure1.md) Struktur.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CRect : public tagRECT  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRect::CRect](#crect)|Erstellt ein `CRect`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRect::BottomRight](#bottomright)|Gibt die zum Zeitpunkt der unteren rechten Ecke des `CRect`.|  
|[CRect::CenterPoint](#centerpoint)|Gibt den Mittelpunkt des `CRect`.|  
|[CRect::CopyRect](#copyrect)|Kopiert die Dimensionen der einem Quellrechteck auf `CRect`.|  
|[CRect::DeflateRect](#deflaterect)|Verringert die Breite und Höhe des `CRect`.|  
|[CRect::EqualRect](#equalrect)|Bestimmt, ob `CRect` gleich einem angegebenen Rechteck.|  
|[CRect::Height](#height)|Berechnet die Höhe des `CRect`.|  
|[CRect::InflateRect](#inflaterect)|Vergrößert die Breite und Höhe des `CRect`.|  
|[CRect::IntersectRect](#intersectrect)|Legt `CRect` die Schnittmenge zweier Rechtecke gleich.|  
|[CRect::IsRectEmpty](#isrectempty)|Bestimmt, ob `CRect` ist leer. `CRect`ist leer, wenn die Breite bzw. Höhe 0 sind.|  
|[CRect::IsRectNull](#isrectnull)|Bestimmt, ob die **oben**, **unteren**, **linken**, und **rechten** Membervariablen sind alle gleich 0.|  
|[CRect::MoveToX](#movetox)|Verschiebt `CRect` zur angegebenen X-Koordinate.|  
|[CRect::MoveToXY](#movetoxy)|Verschiebt `CRect` auf den angegebenen x- und y-Koordinaten.|  
|[CRect::MoveToY](#movetoy)|Verschiebt `CRect` zur angegebenen y-Koordinate.|  
|[CRect:: NormalizeRect](#normalizerect)|Die Höhe und Breite der standardisiert `CRect`.|  
|[CRect::OffsetRect](#offsetrect)|Verschiebt `CRect` durch den angegebenen Offsets.|  
|[CRect::PtInRect](#ptinrect)|Bestimmt, ob der angegebene Punkt innerhalb liegt `CRect`.|  
|[CRect::SetRect](#setrect)|Gibt die Abmessungen des `CRect`.|  
|[CRect::SetRectEmpty](#setrectempty)|Legt `CRect` auf ein leeres Rechteck (alle Koordinaten ungleich 0).|  
|[CRect::Size](#size)|Berechnet die Größe des `CRect`.|  
|[CRect::SubtractRect](#subtractrect)|Subtrahiert ein Rechteck von einem anderen.|  
|[CRect::TopLeft](#topleft)|Gibt die linke obere Punkt `CRect`.|  
|[CRect::UnionRect](#unionrect)|Legt `CRect` die Vereinigung zweier Rechtecke gleich.|  
|[CRect::Width](#width)|Berechnet die Breite der `CRect`.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren    
|Name|Beschreibung|  
|----------|-----------------|  
|[CRect::operator-](#operator_-)|Subtrahiert den angegebenen Offsets von `CRect` oder entfernt `CRect` und gibt das resultierende `CRect`.|  
|[CRect::operator LPCRECT](#operator_lpcrect)|Konvertiert eine `CRect` auf eine **LPCRECT**.|  
|[CRect::operator LPRECT](#operator_lprect)|Konvertiert eine `CRect` auf eine `LPRECT`.|  
|[CRect::operator! =](#operator_neq)|Bestimmt, ob `CRect` stimmt nicht mit einem Rechteck.|  
|[CRect::operator&amp;](#operator_amp)|Erstellt die Schnittmenge der `CRect` und ein Rechteck und gibt das resultierende `CRect`.|  
|[CRect::operator&amp;=](#operator_amp_eq)|Legt `CRect` gleich bei der Schnittmenge der `CRect` und ein Rechteck.|  
|[CRect::operator |](#operator_or)|Erstellt die Vereinigung der `CRect` und ein Rechteck und gibt das resultierende `CRect`.|  
|[CRect::operator |=](#operator_or_eq)|Legt `CRect` entspricht die Kombination `CRect` und ein Rechteck.|  
|[CRect::operator +](#operator_add)|Fügt die angegebenen Offsets `CRect` oder vergrößert `CRect` und gibt das resultierende `CRect`.|  
|[CRect::operator +=](#operator_add_eq)|Fügt die angegebenen Offsets `CRect` oder vergrößert `CRect`.|  
|[CRect::operator =](#operator_eq)|Kopiert die Dimensionen eines Rechtecks, das `CRect`.|  
|[CRect::operator =](#operator_-_eq)|Subtrahiert den angegebenen Offsets von `CRect` oder entfernt `CRect`.|  
|[CRect::operator ==](#operator_eq_eq)|Bestimmt, ob `CRect` entspricht einem Rechteck.|  
  
## <a name="remarks"></a>Hinweise  
 `CRect`enthält auch Memberfunktionen zum Bearbeiten von `CRect` Objekte und Windows `RECT` Strukturen.  
  
 Ein `CRect` Objekt übergeben werden, als Funktionsparameter immer ein `RECT` Struktur **LPCRECT**, oder `LPRECT` übergeben werden kann.  
  
> [!NOTE]
>  Diese Klasse ist abgeleitet von der **TagRECT** Struktur. (Der Name **TagRECT** weniger häufig verwendete Name ist für die `RECT` Struktur.) Dies bedeutet, dass das Datenmember (**linken**, **oben**, **rechten**, und **unteren**) von der `RECT` Struktur werden die Daten zugegriffen werden kann Mitglieder der `CRect`.  
  
 Ein `CRect` Membervariablen, die definieren, die Punkte oberen linken und unteren rechten Ecke eines Rechtecks enthält.  
  
 Beim Angeben einer `CRect`, achten Sie es erstellen, damit er normalisiert ist – also so, dass der Wert der die linke Koordinate kleiner als der rechten Seite und dem oberen ist kleiner als die unteren. Z. B. eine oben links (10,10) unten rechts auf der (20,20) definiert ein normalisierte Rechteck jedoch eine oben links (20,20) und unten rechts auf der (10,10) definiert ein nicht normalisierter Rechteck. Wenn das Rechteck wird nicht normalisiert, viele `CRect` Memberfunktionen möglicherweise falsche Ergebnisse zurückgegeben. (Siehe [CRect:: NormalizeRect](#normalizerect) eine Liste dieser Funktionen.) Vor dem Aufrufen einer funktionsrückgabewerts, die normalisierte Rechtecke erfordert, können Sie nicht normalisierte Rechtecke normalisieren, durch Aufrufen der `NormalizeRect` Funktion.  
  
 Seien Sie vorsichtig beim Bearbeiten einer `CRect` mit der [CDC::DPtoLP](../../mfc/reference/cdc-class.md#dptolp) und [CDC::LPtoDP](../../mfc/reference/cdc-class.md#lptodp) Memberfunktionen. Wenn der Zuordnungsmodus eines Kontexts Anzeige ist die y-Block negativ ist, wie in `MM_LOENGLISH`, klicken Sie dann `CDC::DPtoLP` Transformation wird die `CRect` , damit die oben im unteren Bereich größer ist. Funktionen wie **Höhe** und **Größe** negative Werte für die Höhe des transformierten dann zurück `CRect`, und das Rechteck wird nicht normalisiert werden.  

  
 Wenn mithilfe von überladenen `CRect` Operatoren wird der erste Operand muss ein `CRect`; das zweite kann es sich um eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder ein `CRect` Objekt.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `tagRECT`  
  
 `CRect`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atltypes.h  
  
##  <a name="bottomright"></a>CRect::BottomRight  
 Die Koordinaten werden zurückgegeben, als Verweis auf eine [CPoint](cpoint-class.md) in enthaltene Objekt `CRect`.  
  
```  
CPoint& BottomRight() throw();
const CPoint& BottomRight() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Koordinaten der der unteren rechten Ecke des Rechtecks.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Funktion verwenden, zum Abrufen oder Festlegen der unteren rechten Ecke des Rechtecks. Legen Sie mithilfe dieser Funktion auf der linken Seite des Zuweisungsoperators der Ecke.  
  
### <a name="example"></a>Beispiel  
```cpp  
 // use BottomRight() to retrieve the bottom
 // right POINT 
 CRect rect(210, 150, 350, 900);
 CPoint ptDown;

 ptDown = rect.BottomRight();

 // ptDown is now set to (350, 900)
 ASSERT(ptDown == CPoint(350, 900));

 // or, use BottomRight() to set the bottom
 // right POINT 
 CRect rect2(10, 10, 350, 350);
 CPoint ptLow(180, 180);

   CRect rect2(10, 10, 350, 350);
   CPoint ptLow(180, 180);
rect2.BottomRight() = ptLow;

   // rect2 is now (10, 10, 180, 180)
   ASSERT(rect2 == CRect(10, 10, 180, 180));   
```
  
##  <a name="centerpoint"></a>CRect::CenterPoint 
 Berechnet den Mittelpunkt der `CRect` durch die linken und rechten Werte addiert und geteilt durch zwei, und die oberen und unteren Werte addiert und geteilt durch zwei.  
  
```  
CPoint CenterPoint() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CPoint` Objekt, das den Mittelpunkt der `CRect`.  
  
### <a name="example"></a>Beispiel  
```cpp  
// Code from this OnPaint() implementation can be pasted into your own application
// to draw lines that would look like a letter "Y" within your dialog. 
void CMyDlg::OnPaint()
{
    CPaintDC dc(this);


    // device context for painting

    // get the size and position of the client area of 
    // your window

    CRect rect;
    GetClientRect(&rect);

    // Move the current pen to the top left of the window. We call the
    // TopLeft() member of CRect here and it returns a CPoint object we
    // pass to the override of CDC::MoveTo() that accepts a CPoint.

    dc.MoveTo(rect.TopLeft());

    // Draw a line from the top left to the center of the window.
    // CenterPoint() gives us the middle point of the window as a
    // CPoint, and since CDC::LineTo() has an override that accepts a
    // CPoint, we can just pass it along.

    dc.LineTo(rect.CenterPoint());

    // Now, draw a line to the top right of the window. There's no
    // CRect member which returns a CPoint for the top right of the
    // window, so we'll reference the CPoint members directly and call
    // the CDC::LineTo() override which takes two integers.

    dc.LineTo(rect.right, rect.top);

    // The top part of the "Y" is drawn. Now, we'll draw the stem. We
    // start from the center point.

    dc.MoveTo(rect.CenterPoint());

    // and then draw to the middle of the bottom edge of the window.
    // We'll get the x-coordinate from the x member of the CPOINT 
  // returned by CenterPoint(), and the y value comes directly from
    // the rect.

    dc.LineTo(rect.CenterPoint().x, rect.bottom);
}
```
  
##  <a name="copyrect"></a>CRect::CopyRect  
 Kopiert die `lpSrcRect` Rechteck in `CRect`.  
  
```  
void CopyRect(LPCRECT lpSrcRect) throw(); 
```  
  
### <a name="parameters"></a>Parameter  
 `lpSrcRect`  
 Verweist auf die [RECT](../../mfc/reference/rect-structure1.md) Struktur oder `CRect` -Objekt, das kopiert werden soll.  
  
### <a name="example"></a>Beispiel  
```cpp  
 CRect rectSource(35, 10, 125, 10);
 CRect rectDest;

 rectDest.CopyRect(&rectSource);

 // rectDest is now set to (35, 10, 125, 10)

 RECT rectSource2;
 rectSource2.left = 0;
 rectSource2.top = 0;
 rectSource2.bottom = 480;
 rectSource2.right = 640;

 rectDest.CopyRect(&rectSource2);

 // works against RECT structures, too!
 // rectDest is now set to (0, 0, 640, 480)   
```

  
##  <a name="crect"></a>CRect::CRect  
 Erstellt ein `CRect`-Objekt.  
  
```  
CRect() throw();
CRect(int l, int t, int r, int b) throw();
CRect(const RECT& srcRect) throw();
CRect(LPCRECT lpSrcRect) throw();
CRect(POINT point, SIZE size) throw();
CRect(POINT topLeft, POINT bottomRight) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 *l*  
 Gibt die linke Position der `CRect`.  
  
 *t*  
 Gibt den Anfang `CRect`.  
  
 *r*  
 Gibt die Rechte Position der `CRect`.  
  
 *b*  
 Gibt den unteren Rand `CRect`.  
  
 *srcRect*  
 Bezieht sich auf die [RECT](../../mfc/reference/rect-structure1.md) Struktur mit den Koordinaten für `CRect`.  
  
 `lpSrcRect`  
 Verweist auf die `RECT` Struktur mit den Koordinaten für `CRect`.  
  
 `point`  
 Gibt den Ausgangspunkt für das Rechteck erstellt werden soll. Entspricht der linken oberen Ecke.  
  
 `size`  
 Gibt die Verschiebung von der linken oberen Ecke der unteren rechten Ecke des Rechtecks erstellt werden soll.  
  
 *topLeft*  
 Gibt die linke obere Position der `CRect`.  
  
 *bottomRight*  
 Gibt die Position der unteren rechten Ecke der `CRect`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn keine Argumente angegeben werden, **linken**, **oben**, **rechten**, und **unteren** Member nicht initialisiert werden.  
  
 Die `CRect`(**const RECT &**) und `CRect`(**LPCRECT**) Konstruktoren führen eine [CopyRect](#copyrect). Die anderen Konstruktoren initialisieren die Membervariablen des Objekts direkt auf.  
  
### <a name="example"></a>Beispiel  
```cpp  
 // default constructor doesn't initialize!
 CRect rectUnknown;

 // four-integers are left, top, right, and bottom
 CRect rect(0, 0, 100, 50);
 ASSERT(rect.Width() == 100);
 ASSERT(rect.Height() == 50);

 // Initialize from RECT stucture
 RECT sdkRect;
 sdkRect.left = 0;
 sdkRect.top = 0;
 sdkRect.right = 100;
 sdkRect.bottom = 50;

 CRect rect2(sdkRect);
 // by reference
 CRect rect3(&sdkRect);


 // by address
 ASSERT(rect2 == rect);
 ASSERT(rect3 == rect);

 // from a point and a size
 CPoint pt(0, 0);
 CSize sz(100, 50);
 CRect rect4(pt, sz);
 ASSERT(rect4 == rect2);

 // from two points
 CPoint ptBottomRight(100, 50);
 CRect rect5(pt, ptBottomRight);
 ASSERT(rect5 == rect4);  
```
  
##  <a name="deflaterect"></a>CRect::DeflateRect  
 `DeflateRect`entfernt `CRect` durch seine Seiten an dessen Mitte verschieben.  
  
```  
void DeflateRect(int x, int y) throw();
void DeflateRect(SIZE size) throw();
void DeflateRect(LPCRECT lpRect) throw();
void DeflateRect(int l, int t, int r, int b) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 Gibt die Anzahl der Einheiten, um die deflate links und rechts vom `CRect`.  
  
 *y*  
 Gibt die Anzahl der Einheiten, um den oberen bzw. unteren Rand deflate `CRect`.  
  
 `size`  
 Ein [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) oder [CSize](csize-class.md) , die angibt, dass der Anzahl der Einheiten, um die deflate `CRect`. Die `cx` Wert gibt die Anzahl der Einheiten, um die linken und rechten Seite Deflate ausführen und die `cy` Wert gibt die Anzahl der Einheiten, um die am oberen bzw. unteren Deflate ausführen.  
  
 `lpRect`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder `CRect` , die die Anzahl der Einheiten, um jede Seite deflate angibt.  
  
 *l*  
 Gibt die Anzahl der Einheiten auf der linken Seite des deflate `CRect`.  
  
 *t*  
 Gibt die Anzahl der Einheiten, um am Anfang deflate `CRect`.  
  
 *r*  
 Gibt die Anzahl der Einheiten auf der rechten Seite des deflate `CRect`.  
  
 *b*  
 Gibt die Anzahl der Einheiten, um das Ende deflate `CRect`.  
  
### <a name="remarks"></a>Hinweise  
 Hierzu `DeflateRect` linken und oberen Einheiten hinzugefügt und Einheiten aus dem rechten und unteren subtrahiert. Die Parameter der `DeflateRect` signiert werden Werte: positive Werte deflate `CRect` und negative Werte vergrößern sie.  
  
 Die ersten beiden Überladungen deflate beide Paare von gegenüberliegenden Seiten des `CRect` , damit die Gesamtbreite um zweimal verringert *x* (oder `cx`) und die gesamte Höhe wird zweimal verringert *y* () oder `cy`). Die anderen beiden Überladungen deflate jede Seite der `CRect` unabhängig von den anderen.  
  
### <a name="example"></a>Beispiel  
```cpp  
   CRect rect(10, 10, 50, 50);
   rect.DeflateRect(1, 2);
   ASSERT(rect.left == 11 && rect.right == 49);
   ASSERT(rect.top == 12 && rect.bottom == 48);
   
   CRect rect2(10, 10, 50, 50);
   CRect rectDeflate(1, 2, 3, 4);
   rect2.DeflateRect(&rectDeflate);
   ASSERT(rect2.left == 11 && rect2.right == 47);
   ASSERT(rect2.top == 12 && rect2.bottom == 46);   
```
  
##  <a name="equalrect"></a>CRect::EqualRect  
 Bestimmt, ob `CRect` gleich einem angegebenen Rechteck.  
  
```  
BOOL EqualRect(LPCRECT lpRect) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder `CRect` Objekt, das die Koordinaten der oberen linken und unteren rechten Ecke eines Rechtecks enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die zwei Rechtecken, die gleichen oben, links, unteren und rechten Werte haben; andernfalls 0.  
  
> [!NOTE]
>  Müssen sowohl der Rechtecke normalisiert werden, oder diese Funktion kann fehlschlagen. Sie können Aufrufen [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor Sie diese Funktion aufrufen.  
  
### <a name="example"></a>Beispiel  
```cpp  
   CRect rect1(35, 150, 10, 25);
   CRect rect2(35, 150, 10, 25);
   CRect rect3(98, 999, 6, 3);
ASSERT(rect1.EqualRect(rect2));
   ASSERT(!rect1.EqualRect(rect3));
 // works just fine against RECTs, as well

 RECT test;
 test.left = 35;
 test.top = 150;
 test.right = 10;
 test.bottom = 25;

 ASSERT(rect1.EqualRect(&test));  
```

##  <a name="height"></a>CRect::Height  
 Berechnet die Höhe des `CRect` durch Subtrahieren den obersten Wert aus dem unteren Wert.  
  
```  
int Height() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe des `CRect`.  
  
### <a name="remarks"></a>Hinweise  
 Der Ergebniswert kann negativ sein.  
  
> [!NOTE]
>  Das Rechteck muss normalisiert werden, oder diese Funktion möglicherweise ein Fehler. Sie können Aufrufen [NormalizeRect](#normalizerect) , das Rechteck zu normalisieren, bevor Sie diese Funktion aufrufen.  
  
### <a name="example"></a>Beispiel  
```cpp  
 CRect rect(20, 30, 80, 70);
 int nHt = rect.Height();

```cpp  
   CRect rect(20, 30, 80, 70);
int nHt = rect.Height();

   // nHt is now 40
   ASSERT(nHt == 40);   
```

  
##  <a name="inflaterect"></a>CRect::InflateRect  
 `InflateRect`Vergrößert dieses `CRect` durch seine Seiten Weg von der Mitte verschieben.  
  
```  
void InflateRect(int x, int y) throw();
void InflateRect(SIZE size) throw();
void InflateRect(LPCRECT lpRect) throw();
void InflateRect(int l, int t, int r,  int b) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 Gibt die Anzahl der Einheiten, um Links vergrößert werden soll und rechten Seite des Anwendungsfensters `CRect`.  
  
 *y*  
 Gibt die Anzahl der Einheiten, um die am oberen bzw. unteren Rand vergrößern `CRect`.  
  
 `size`  
 Ein [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) oder [CSize](csize-class.md) , die gibt der Anzahl der Einheiten vergrößern `CRect`. Die `cx` Wert gibt die Anzahl der Einheiten, um die Links und rechts zu vergrößern und den `cy` Wert gibt die Anzahl der Einheiten, um die am oberen bzw. unteren vergrößert werden soll.  
  
 `lpRect`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder `CRect` , der angibt, dass der Anzahl der Einheiten, um jede Seite vergrößert werden soll.  
  
 *l*  
 Gibt die Anzahl der Einheiten auf der linken Seite des vergrößern `CRect`.  
  
 *t*  
 Gibt die Anzahl der Einheiten, um am Anfang vergrößern `CRect`.  
  
 *r*  
 Gibt die Anzahl der Einheiten vergrößern rechts neben `CRect`.  
  
 *b*  
 Gibt die Anzahl der Einheiten, um das Ende vergrößert werden soll `CRect`.  
  
### <a name="remarks"></a>Hinweise  
 Hierzu `InflateRect` subtrahiert Einheiten vom linken und oberen und den rechten und unteren Einheiten hinzugefügt. Die Parameter der `InflateRect` signiert werden positive Werte vergrößern Werte `CRect` und negative Werte deflate es.  
  
 Die ersten beiden Überladungen vergrößert werden soll, beide Paare von gegenüberliegenden Seiten des `CRect` , damit die Gesamtbreite zweimal gestiegen ist *x* (oder `cx`) und die gesamte Höhe ist zweimal gestiegen *y* () oder `cy`). Die anderen beiden Überladungen vergrößert werden soll, jede Seite der `CRect` unabhängig von den anderen.  
  
### <a name="example"></a>Beispiel  
```cpp  
 CRect rect(0, 0, 300, 300);
 rect.InflateRect(50, 200);

 // rect is now (-50, -200, 350, 500)
 ASSERT(rect == CRect(-50, -200, 350, 500));  
```
  
##  <a name="intersectrect"></a>CRect::IntersectRect  
 Stellt eine `CRect` gleich der Schnittmenge von zwei vorhandenen Rechtecken.  
  
```  
BOOL IntersectRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect1`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder `CRect` Objekt, das einem Quellrechteck enthält.  
  
 `lpRect2`  
 Verweist auf eine `RECT` Struktur oder `CRect` Objekt, das einem Quellrechteck enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Schnittmenge nicht leer ist; 0, wenn die Schnittmenge leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Schnittmenge ist das größte Rechteck, das in beiden vorhandenen Rechtecke enthalten sind.  
  
> [!NOTE]
>  Müssen sowohl der Rechtecke normalisiert werden, oder diese Funktion kann fehlschlagen. Sie können Aufrufen [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor Sie diese Funktion aufrufen.  
  
### <a name="example"></a>Beispiel  
```cpp  
 CRect rectOne(125, 0, 150, 200);
 CRect rectTwo(0, 75, 350,  95);
 CRect rectInter;

```cpp  
   CRect rectOne(125,  0, 150, 200);
   CRect rectTwo(0, 75, 350, 95);
   CRect rectInter;

   rectInter.IntersectRect(rectOne, rectTwo);
 ASSERT(rectInter == CRect(125, 75, 150, 95));
 // operator &= can do the same task:

 CRect rectInter2 = rectOne;
 rectInter2 &= rectTwo;
 ASSERT(rectInter2 == CRect(125, 75, 150, 95));  
```
  
##  <a name="isrectempty"></a>CRect::IsRectEmpty  
 Bestimmt, ob `CRect` ist leer.  
  
```  
BOOL IsRectEmpty() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich NULL `CRect` leer ist; 0 Wenn `CRect` ist nicht leer.  
  
### <a name="remarks"></a>Hinweise  
 Ein Rechteck ist leer, wenn die Breite bzw. Höhe 0 sind oder negativ sein. Unterscheidet sich von `IsRectNull`, der bestimmt, ob alle Koordinaten des Rechtecks 0 (null) sind.  
  
> [!NOTE]
>  Das Rechteck muss normalisiert werden, oder diese Funktion möglicherweise ein Fehler. Sie können Aufrufen [NormalizeRect](#normalizerect) , das Rechteck zu normalisieren, bevor Sie diese Funktion aufrufen.  
  
### <a name="example"></a>Beispiel  
```cpp  
 CRect rectNone(0, 0, 0, 0);
 CRect rectSome(35, 50, 135, 150);

```cpp  
   CRect rectNone(0, 0, 0, 0);
   CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectEmpty());
   ASSERT(!rectSome.IsRectEmpty());
CRect rectEmpty(35, 35, 35, 35);
   ASSERT(rectEmpty.IsRectEmpty());   
```

  
##  <a name="isrectnull"></a>CRect::IsRectNull  
 Bestimmt, ob der oberen linken unten, und mit der rechten Maustaste Werte `CRect` sind alle gleich 0.  
  
```  
BOOL IsRectNull() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich NULL `CRect`des oben, links, unteren und rechten Werte sind alle gleich 0, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Unterscheidet sich von `IsRectEmpty`, der bestimmt, ob das Rechteck leer ist.  
  
### <a name="example"></a>Beispiel  
```cpp  
 CRect rectNone(0, 0, 0, 0);
 CRect rectSome(35, 50, 135, 150);

```cpp  
   CRect rectNone(0, 0, 0, 0);
   CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectNull());
   ASSERT(!rectSome.IsRectNull());
 // note that null means _all_ zeros

 CRect rectNotNull(0, 0, 35, 50);
 ASSERT(!rectNotNull.IsRectNull());  
```
  
##  <a name="movetox"></a>CRect::MoveToX  
 Mit dieser Funktion können Sie das Rechteck verschieben, um die absolute X-Koordinate angegeben *x*.  
  
```  
void MoveToX(int x) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 Die absolute X-Koordinate für die linke obere Ecke des Rechtecks.  
  
### <a name="example"></a>Beispiel  
```cpp  
 CRect rect(0, 0, 100, 100);
 rect.MoveToX(10);

```cpp  
   CRect rect(0, 0, 100, 100);
rect.MoveToX(10);

   // rect is now (10, 0, 110, 100);
   ASSERT(rect == CRect(10, 0, 110, 100));   
```
  
##  <a name="movetoxy"></a>CRect::MoveToXY  
 Mit dieser Funktion können verschieben Sie das Rechteck auf die absolute X - und y-Koordinaten angegeben.  
  
```  
void MoveToXY(int x, int y) throw();
void MoveToXY(POINT point) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 Die absolute X-Koordinate für die linke obere Ecke des Rechtecks.  
  
 *y*  
 Die absolute y-Koordinate für die linke obere Ecke des Rechtecks.  
  
 `point`  
 Ein **Punkt** Struktur, die die absolute linke obere Ecke des Rechtecks angibt.  
  
### <a name="example"></a>Beispiel  
```cpp  
 CRect rect(0, 0, 100, 100);
 rect.MoveToXY(10, 10);

```cpp  
   CRect rect(0, 0, 100, 100);
   rect.MoveToXY(10, 10);
// rect is now (10, 10, 110, 110);
   ASSERT(rect == CRect(10, 10, 110, 110));   
```

  
##  <a name="movetoy"></a>CRect::MoveToY  
 Mit dieser Funktion können Sie das Rechteck verschieben, um die absolute y-Koordinate angegeben *y*.  
  
```  
void MoveToY(int y) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 *y*  
 Die absolute y-Koordinate für die linke obere Ecke des Rechtecks.  
  
### <a name="example"></a>Beispiel  
```cpp  
 CRect rect(0, 0, 100, 100);
 rect.MoveToY(10);

```cpp  
   CRect rect(0, 0, 100, 100);
   rect.MoveToY(10);
// rect is now (0, 10, 100, 110);
   ASSERT(rect == CRect(0, 10, 100, 110));   
```

  
##  <a name="normalizerect"></a>CRect:: NormalizeRect  
 Normalisiert `CRect` , damit die Höhe und Breite nicht sicher sind.  
  
```  
void NormalizeRect() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Rechteck ist für die vierte Quadranten Positionierung, normalisiert die Verwendung von Windows in der Regel für die Koordinaten. `NormalizeRect`Vergleicht die oberen und unteren Werten und vertauscht diese, wenn im oberen Bereich im unteren Bereich größer ist. Auf ähnliche Weise vertauscht den linken und rechten Werte, wenn der linken Seite größer als der rechten Seite ist. Diese Funktion ist hilfreich beim Umgang mit verschiedenen Zuordnungsmodi und Rechtecke umgekehrt.  
  
> [!NOTE]
>  Die folgenden `CRect` Memberfunktionen normalisierte Rechtecke erfordern, damit Sie ordnungsgemäß funktioniert: [Höhe](#height), [Breite](#width), [Größe](#size), [ IsRectEmpty](#isrectempty), [PtInRect](#ptinrect), [EqualRect](#equalrect), [UnionRect](#unionrect), [IntersectRect](#intersectrect), [ SubtractRect](#subtractrect), [Operator ==](#operator_eq_eq), [Operator! =](#operator_neq), [Operator &#124;](#operator_or), [Operator &#124;=](#operator_or_eq), [Operator &](#operator_amp), und [Operator & =](#operator_amp_eq).  
  
### <a name="example"></a>Beispiel  
```cpp  
 CRect rect1(110, 100, 250, 310);
 CRect rect2(250, 310, 110, 100);

```cpp  
   CRect rect1(110, 100, 250, 310);
   CRect rect2(250, 310, 110, 100);
rect1.NormalizeRect();
   rect2.NormalizeRect();
 ASSERT(rect1 == rect2);  
```
  
##  <a name="offsetrect"></a>CRect::OffsetRect  
 Verschiebt `CRect` durch den angegebenen Offsets.  
  
```  
void OffsetRect(int x, int y) throw();
void OffsetRect(POINT point) throw();
void OffsetRect(SIZE size) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 Gibt die Menge, die zum Verschieben von links oder rechts. Sie müssen nach links verschieben negativ sein.  
  
 *y*  
 Gibt den Umfang nach oben oder unten zu verschieben. Es muss auf nach oben verschieben negativ sein.  
  
 `point`  
 Enthält eine [Punkt](../../mfc/reference/point-structure1.md) Struktur oder [CPoint](cpoint-class.md) Objekt, das beide Dimensionen nach dem Verschieben angibt.  
  
 `size`  
 Enthält eine [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder [CSize](csize-class.md) Objekt, das beide Dimensionen nach dem Verschieben angibt.  
  
### <a name="remarks"></a>Hinweise  
 Verschiebt `CRect` *x* Einheiten entlang der x-Achse und *y* Einheiten entlang der y-Achse. Die *x* und *y* Parameter sind Werte mit Vorzeichen, sodass `CRect` können verschoben werden, links oder rechts oben oder unten.  
  
### <a name="example"></a>Beispiel  
```cpp  
 CRect rect(0, 0, 35, 35);
 rect.OffsetRect(230, 230);

```cpp  
   CRect rect(0, 0, 35, 35);
   rect.OffsetRect(230, 230);

   // rect is now (230, 230, 265, 265)
   ASSERT(rect == CRect(230, 230, 265, 265));   
```

  
##  <a name="operator_lpcrect"></a>CRect::operator LPCRECT konvertiert eine `CRect` auf eine [LPCRECT](../../mfc/reference/data-types-mfc.md).  

  
```  
operator LPCRECT() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie diese Funktion verwenden, Sie brauchen nicht die Adresse des (**&**) Operator. Dieser Operator wird automatisch verwendet, wenn Sie übergeben ein `CRect` -Objekt an eine Funktion, die erwartet ein **LPCRECT**.  
  

##  <a name="operator_lprect"></a>CRect::operator LPRECT  
 Konvertiert eine `CRect` auf eine [LPRECT](../../mfc/reference/data-types-mfc.md).  

  
```
operator LPRECT() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie diese Funktion verwenden, Sie brauchen nicht die Adresse des (**&**) Operator. Dieser Operator wird automatisch verwendet, wenn Sie übergeben ein `CRect` -Objekt an eine Funktion, die erwartet ein `LPRECT`.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CRect::operator LPCRECT](#operator_lpcrect).  
  
##  <a name="operator_eq"></a>CRect::operator =  
 Weist *SrcRect* auf `CRect`.  
  
```  
void operator=(const RECT& srcRect) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *srcRect*  
 Bezieht sich auf einem Quellrechteck. Kann eine [RECT](../../mfc/reference/rect-structure1.md) oder `CRect`.  
  
### <a name="example"></a>Beispiel  
```cpp  
 CRect rect(0, 0, 127, 168);
 CRect rect2;

```cpp  
   CRect rect(0, 0, 127, 168);
   CRect rect2;

   rect2 = rect;
   ASSERT(rect2 == CRect(0, 0, 127, 168));   
```

  
##  <a name="operator_eq_eq"></a>CRect::operator ==  
 Bestimmt, ob `rect` gleich `CRect` durch Vergleichen die Koordinaten der oberen linken und unteren rechten Ecke.  
  
```  
BOOL operator==(const RECT& rect) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Bezieht sich auf einem Quellrechteck. Kann eine [RECT](../../mfc/reference/rect-structure1.md) oder `CRect`.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn es übereinstimmt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Müssen sowohl der Rechtecke normalisiert werden, oder diese Funktion kann fehlschlagen. Sie können Aufrufen [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor Sie diese Funktion aufrufen.  
  
### <a name="example"></a>Beispiel  
```cpp  
 CRect rect1(35, 150, 10, 25);
 CRect rect2(35, 150, 10, 25);
 CRect rect3(98, 999,  6,  3);

```cpp  
   CRect rect1(35, 150, 10, 25);
   CRect rect2(35, 150, 10, 25);
   CRect rect3(98, 999, 6, 3);
ASSERT(rect1 == rect2);
 // works just fine against RECTs, as well

 RECT test;
 test.left = 35;
 test.top = 150;
 test.right = 10;
 test.bottom = 25;

 ASSERT(rect1 == test);  
```

  
##  <a name="operator_neq"></a>CRect::operator! =  
 Bestimmt, ob `rect` stimmt nicht mit `CRect` durch Vergleichen die Koordinaten der oberen linken und unteren rechten Ecke.  
  
```  
BOOL operator!=(const RECT& rect) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Bezieht sich auf einem Quellrechteck. Kann eine [RECT](../../mfc/reference/rect-structure1.md) oder `CRect`.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn nicht gleich sind; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Müssen sowohl der Rechtecke normalisiert werden, oder diese Funktion kann fehlschlagen. Sie können Aufrufen [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor Sie diese Funktion aufrufen.  
  
### <a name="example"></a>Beispiel  
```cpp  
 CRect rect1(35, 150, 10, 25);
 CRect rect2(35, 150, 10, 25);
 CRect rect3(98, 999,  6,  3);

```cpp  
   CRect rect1(35, 150, 10, 25);
   CRect rect2(35, 150, 10, 25);
   CRect rect3(98, 999, 6, 3);
ASSERT(rect1 != rect3);
 // works just fine against RECTs, as well

 RECT test;
 test.left = 35;
 test.top = 150;
 test.right = 10;
 test.bottom = 25;

 ASSERT(rect3 != test);  
```
  
##  <a name="operator_add_eq"></a>CRect::operator +=  
 Verschieben Sie die ersten beiden Überladungen `CRect` durch den angegebenen Offsets.  
  
```  
void operator+=(POINT point) throw();
void operator+=(SIZE size) throw();
void operator+=(LPCRECT lpRect) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `point`  
 Ein [Punkt](../../mfc/reference/point-structure1.md) Struktur oder [CPoint](cpoint-class.md) Objekt, das die Anzahl der Einheiten, um das Rechteck verschieben angibt.  
  
 `size`  
 Ein [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder [CSize](csize-class.md) Objekt, das die Anzahl der Einheiten, um das Rechteck verschieben angibt.  
  
 `lpRect`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder `CRect` -Objekt, das die Anzahl der Einheiten, um die beiden Seiten des vergrößern enthält `CRect`.  
  
### <a name="remarks"></a>Hinweise  
 Des Parameters *x* und *y* (oder `cx` und `cy`) werden hinzugefügt, um `CRect`.  
  
 Die dritte Überladung vergrößert `CRect` durch die Anzahl der Einheiten, die in jedes Element des Parameters angegeben.  
  
### <a name="example"></a>Beispiel  
```cpp  
 CRect rect1(100, 235, 200, 335);
 CPoint pt(35, 65);
 CRect rect2(135, 300, 235, 400);

```cpp  
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);
   CRect   rect2(135, 300, 235, 400);

   rect1 += pt;
   ASSERT(rect1 == rect2);   
```
  
##  <a name="operator_-_eq"></a>CRect::operator =  
 Verschieben Sie die ersten beiden Überladungen `CRect` durch den angegebenen Offsets.  
  
```  
void operator-=(POINT point) throw();
void operator-=(SIZE size) throw();
void operator-=(LPCRECT lpRect) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `point`  
 Ein [Punkt](../../mfc/reference/point-structure1.md) Struktur oder [CPoint](cpoint-class.md) Objekt, das die Anzahl der Einheiten, um das Rechteck verschieben angibt.  
  
 `size`  
 Ein [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder [CSize](csize-class.md) Objekt, das die Anzahl der Einheiten, um das Rechteck verschieben angibt.  
  
 `lpRect`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder `CRect` -Objekt, das die Anzahl der Einheiten, um die beiden Seiten des deflate enthält `CRect`.  
  
### <a name="remarks"></a>Hinweise  
 Des Parameters *x* und *y* (oder `cx` und `cy`) Werte subtrahiert `CRect`.  
  
 Die dritte Überladung entfernt `CRect` durch die Anzahl der Einheiten, die in jedes Element des Parameters angegeben. Beachten Sie, die diese Überladung wie funktioniert [DeflateRect](#deflaterect).  
  
### <a name="example"></a>Beispiel  
```cpp  
 CRect rect1(100, 235, 200, 335);
 CPoint pt(35, 65);
 rect1 -= pt;

```cpp  
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);

   rect1 -= pt;
   CRect   rectResult(65, 170, 165, 270);
   ASSERT(rect1 == rectResult);   
```
  
##  <a name="operator_amp_eq"></a>CRect::operator&amp;=  
 Legt `CRect` gleich bei der Schnittmenge der `CRect` und `rect`.  
  
```  
void operator&=(const RECT& rect) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Enthält eine [RECT](../../mfc/reference/rect-structure1.md) oder `CRect`.  
  
### <a name="remarks"></a>Hinweise  
 Die Schnittmenge ist das größte Rechteck, das in beiden Rechtecke enthalten ist.  
  
> [!NOTE]
>  Müssen sowohl der Rechtecke normalisiert werden, oder diese Funktion kann fehlschlagen. Sie können Aufrufen [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor Sie diese Funktion aufrufen.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CRect::IntersectRect](#intersectrect).  
  
##  <a name="operator_or_eq"></a>CRect::operator &#124; =  
 Legt `CRect` entspricht die Kombination `CRect` und `rect`.  
  
```  
void operator|=(const RECT& rect) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Enthält eine `CRect` oder [RECT](../../mfc/reference/rect-structure1.md).  
  
### <a name="remarks"></a>Hinweise  
 Die Union ist das kleinste Rechteck befindet, das sowohl Quelle Rechtecke enthält.  
  
> [!NOTE]
>  Müssen sowohl der Rechtecke normalisiert werden, oder diese Funktion kann fehlschlagen. Sie können Aufrufen [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor Sie diese Funktion aufrufen.  
  
### <a name="example"></a>Beispiel  
```cpp  
 CRect rect1(100,   0, 200, 300);
 CRect rect2( 0, 100, 300, 200);
 rect1 |= rect2;

```cpp  
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);

   rect1 |= rect2;
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect1);   
```

  
##  <a name="operator_add"></a>CRect::operator +  
 Die ersten beiden Überladungen Zurückgeben einer `CRect` -Objekt, das gleich `CRect` ersetzt durch den angegebenen Offsets.  
  
```  
CRect operator+(POINT point) const throw();
CRect operator+(LPCRECT lpRect) const throw();
CRect operator+(SIZE size) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `point`  
 Ein [Punkt](../../mfc/reference/point-structure1.md) Struktur oder [CPoint](cpoint-class.md) Objekt, das die Anzahl der Einheiten, um das Verschieben des Rückgabewerts angibt.  
  
 `size`  
 Ein [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder [CSize](csize-class.md) Objekt, das die Anzahl der Einheiten, um das Verschieben des Rückgabewerts angibt.  
  
 `lpRect`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder `CRect` -Objekt, das die Anzahl der Einheiten, um jede Seite des Rückgabewerts vergrößert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Die `CRect` entstandene verschieben oder überhöhte `CRect` durch die Anzahl der Einheiten, die im Parameter angegeben.  
  
### <a name="remarks"></a>Hinweise  
 Des Parameters *x* und *y* (oder `cx` und `cy`) Parameter hinzugefügt werden `CRect`des positionieren.  
  
 Die dritte Überladung gibt eine neue `CRect` , die gleich `CRect` vergrößert, um die Anzahl der Einheiten, die in jedes Element des Parameters angegeben.  
  
### <a name="example"></a>Beispiel  
```cpp  
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);
   CRect   rect2;

   rect2 = rect1 + pt;
   CRect   rectResult(135, 300, 235, 400);
   ASSERT(rectResult == rect2);   
```

  
##  <a name="operator_-"></a>CRect::operator-  
 Die ersten beiden Überladungen Zurückgeben einer `CRect` -Objekt, das gleich `CRect` ersetzt durch den angegebenen Offsets.  
  
```  
CRect operator-(POINT point) const throw();
CRect operator-(SIZE size) const throw();
CRect operator-(LPCRECT lpRect) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `point`  
 Ein [Punkt](../../mfc/reference/point-structure1.md) Struktur oder `CPoint` Objekt, das die Anzahl der Einheiten, um das Verschieben des Rückgabewerts angibt.  
  
 `size`  
 Ein [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder `CSize` Objekt, das die Anzahl der Einheiten, um das Verschieben des Rückgabewerts angibt.  
  
 `lpRect`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder `CRect` -Objekt, das die Anzahl von Einheiten auf jeder Seite des Rückgabewerts deflate enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Die `CRect` entstandene verschieben oder Entleeren `CRect` durch die Anzahl der Einheiten, die im Parameter angegeben.  
  
### <a name="remarks"></a>Hinweise  
 Des Parameters *x* und *y* (oder `cx` und `cy`) Parameter subtrahiert `CRect`des positionieren.  
  
 Die dritte Überladung gibt eine neue `CRect` , die gleich `CRect` verkleinert werden, um die Anzahl der Einheiten, die in jedes Element des Parameters angegeben. Beachten Sie, die diese Überladung wie funktioniert [DeflateRect](#deflaterect), nicht [SubtractRect](#subtractrect).  
  
### <a name="example"></a>Beispiel  
```cpp  
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);
   CRect   rect2;

   rect2 = rect1 - pt;
   CRect   rectResult(65, 170, 165, 270);
   ASSERT(rect2 == rectResult);   
```

  
##  <a name="operator_amp"></a>CRect::operator&amp;  
 Gibt eine `CRect` also die Schnittmenge der `CRect` und *rect2*.  
  
```  
CRect operator&(const RECT& rect2) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 *rect2*  
 Enthält eine [RECT](../../mfc/reference/rect-structure1.md) oder `CRect`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CRect` also die Schnittmenge der `CRect` und *rect2*.  
  
### <a name="remarks"></a>Hinweise  
 Die Schnittmenge ist das größte Rechteck, das in beiden Rechtecke enthalten ist.  
  
> [!NOTE]
>  Müssen sowohl der Rechtecke normalisiert werden, oder diese Funktion kann fehlschlagen. Sie können Aufrufen [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor Sie diese Funktion aufrufen.  
  
### <a name="example"></a>Beispiel  
```cpp  
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3 = rect1 & rect2;
   CRect   rectResult(100, 100, 200, 200);
   ASSERT(rectResult == rect3);   
```

  
##  <a name="operator_or"></a>CRect::operator &#124;  
 Gibt eine `CRect` die Kombination `CRect` und *rect2*.  
  
```   
CRect operator|(const RECT& 
rect2) const throw(); 
```  
  
### <a name="parameters"></a>Parameter  
 *rect2*  
 Enthält eine [RECT](../../mfc/reference/rect-structure1.md) oder `CRect`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CRect` die Kombination `CRect` und *rect2*.  
  
### <a name="remarks"></a>Hinweise  
 Die Union ist das kleinste Rechteck befindet, das beide Rechtecke enthält.  
  
> [!NOTE]
>  Müssen sowohl der Rechtecke normalisiert werden, oder diese Funktion kann fehlschlagen. Sie können Aufrufen [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor Sie diese Funktion aufrufen.  
  
### <a name="example"></a>Beispiel  
```cpp  
 CRect rect1(100,   0, 200, 300);
 CRect rect2( 0, 100, 300, 200);
 CRect rect3;

```cpp  
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3 = rect1 | rect2;
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect3);   
```

  
##  <a name="ptinrect"></a>CRect::PtInRect  
 Bestimmt, ob der angegebene Punkt innerhalb liegt `CRect`.  
  
```   
BOOL PtInRect(POINT point) const throw(); 
```  
  
### <a name="parameters"></a>Parameter  
 `point`  
 Enthält eine [Punkt](../../mfc/reference/point-structure1.md) Struktur oder [CPoint](cpoint-class.md) Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Punkt innerhalb liegt `CRect`, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein Punkt ist in `CRect` liegt auf der linken oder oberen Seite oder in allen vier Seiten. Ein Punkt auf der rechten oder unteren Seite liegt außerhalb `CRect`.  
  
> [!NOTE]
>  Das Rechteck muss normalisiert werden, oder diese Funktion möglicherweise ein Fehler. Sie können Aufrufen [NormalizeRect](#normalizerect) , das Rechteck zu normalisieren, bevor Sie diese Funktion aufrufen.  
  
### <a name="example"></a>Beispiel  
```cpp  
 CRect rect(5, 5, 100, 100);
 CPoint pt1(35, 50);
 CPoint pt2(125, 298);

 // this is true, because pt1 is inside the rectangle
 ASSERT(rect.PtInRect(pt1));

 // this is NOT true, because pt2 is outside the rectangle
 ASSERT(!rect.PtInRect(pt2));

 // note that the right and the bottom aren't inside
 ASSERT(!rect.PtInRect(CPoint(35, 100)));
 ASSERT(!rect.PtInRect(CPoint(100, 98)));

 // but the top and the left are inside
 ASSERT(rect.PtInRect(CPoint(5, 65)));
 ASSERT(rect.PtInRect(CPoint(88, 5)));

 // and that PtInRect() works against a POINT, too
 POINT pt;
 pt.x = 35;
 pt.y = 50;
 ASSERT(rect.PtInRect(pt));  
```
  
##  <a name="setrect"></a>CRect::SetRect  
 Gibt die Abmessungen des `CRect` an die angegebenen Koordinaten.  
  
```   
void SetRect(int x1, int y1, int x2, int y2) throw(); 
```  
  
### <a name="parameters"></a>Parameter  
 `x1`  
 Gibt die X-Koordinate der oberen linken Ecke.  
  
 `y1`  
 Gibt die y-Koordinate der oberen linken Ecke.  
  
 `x2`  
 Gibt die X-Koordinate der unteren rechten Ecke.  
  
 `y2`  
 Gibt die y-Koordinate der unteren rechten Ecke.  
  
### <a name="example"></a>Beispiel  
```cpp  
 CRect rect;
 rect.SetRect(256, 256, 512, 512);

```cpp  
   CRect rect;
   rect.SetRect(256, 256, 512, 512);
   ASSERT(rect == CRect(256, 256, 512, 512));   
```

  
##  <a name="setrectempty"></a>CRect::SetRectEmpty  
 Macht `CRect` ein Rechteck null, indem Sie alle Koordinaten auf 0 (null) festlegen.  
  
```  
void SetRectEmpty() throw();
```  
  
### <a name="example"></a>Beispiel  
```cpp  
CRect rect;
rect.SetRectEmpty();

// rect is now (0, 0, 0, 0)
ASSERT(rect.IsRectEmpty());  
```
  
##  <a name="size"></a>CRect::SIZE 
 Die `cx` und `cy` Mitglieder der zurückgegebene Wert enthalten, die Höhe und Breite des `CRect`.  
  
```  
CSize Size() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CSize](csize-class.md) -Objekt, das die Größe des enthält `CRect`.  
  
### <a name="remarks"></a>Hinweise  
 Höhe oder Breite kann negativ sein.  
  
> [!NOTE]
>  Das Rechteck muss normalisiert werden, oder diese Funktion möglicherweise ein Fehler. Sie können Aufrufen [NormalizeRect](#normalizerect) , das Rechteck zu normalisieren, bevor Sie diese Funktion aufrufen.  
  
### <a name="example"></a>Beispiel  
```cpp  
 CRect rect(10, 10, 50, 50);
 CSize sz = rect.Size();
 ASSERT(sz.cx == 40 && sz.cy == 40);  
```

##  <a name="subtractrect"></a>CRect::SubtractRect  
 Macht die Dimensionen der **CRect** gleich der Subtraktion von `lpRectSrc2` aus `lpRectSrc1`.  
  
```  
BOOL SubtractRect(LPCRECT lpRectSrc1, LPCRECT lpRectSrc2) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpRectSrc1`  
 Verweist auf die [RECT](../../mfc/reference/rect-structure1.md) Struktur oder `CRect` Objekt, von dem ein Rechteck subtrahiert werden soll.  
  
 `lpRectSrc2`  
 Verweist auf die `RECT` Struktur oder `CRect` Objekt, von dem Rechteck abgezogen werden verweist die `lpRectSrc1` Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Subtraktion ist das kleinste Rechteck befindet, die alle Punkte enthält `lpRectScr1` , die sich nicht in der Schnittmenge der `lpRectScr1` und *lpRectScr2*.  
  
 Das Rechteck, angegeben durch `lpRectSrc1` werden unverändert, wenn das Rechteck nach angegeben `lpRectSrc2` nicht vollständig durch angegebenen Rechtecks überschneiden *lpRectSrc1* in mindestens einer der x oder y-Richtung.  
  
 Z. B. wenn `lpRectSrc1` wurden (10,10, 100,100) und `lpRectSrc2` wurden (50,50, 150,150), das Rechteck verweist `lpRectSrc1` würde unverändert sein, wenn die Funktion zurückgegeben. Wenn `lpRectSrc1` wurden (10,10, 100,100) und `lpRectSrc2` wurden (50,10, 150,150), jedoch das Rechteck verweist `lpRectSrc1` enthält die Koordinaten (10,10, Punkt 50,100) bei die Funktion zurückgegeben.  
  
 `SubtractRect`entspricht nicht dem als [Operator -](#operator_-) noch [Operator-=](#operator_-_eq). Keines dieser Operatoren jemals ruft `SubtractRect`.  
  
> [!NOTE]
>  Müssen sowohl der Rechtecke normalisiert werden, oder diese Funktion kann fehlschlagen. Sie können Aufrufen [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor Sie diese Funktion aufrufen.  
  
### <a name="example"></a>Beispiel  
```cpp  
   RECT   rectOne;
   RECT   rectTwo;

   rectOne.left = 10;
   rectOne.top = 10;
   rectOne.bottom = 100;
   rectOne.right = 100;

   rectTwo.left = 50;
   rectTwo.top = 10;
   rectTwo.bottom = 150;
   rectTwo.right = 150;

   CRect   rectDiff;

   rectDiff.SubtractRect(&rectOne, &rectTwo);
CRect   rectResult(10, 10, 50, 100);

   ASSERT(rectDiff == rectResult);

   // works for CRect, too, since there is
   // implicit CRect -> LPCRECT conversion

   CRect rect1(10, 10, 100, 100);
   CRect rect2(50, 10, 150, 150);
   CRect rectOut;

   rectOut.SubtractRect(rect1, rect2);
   ASSERT(rectResult == rectOut);   
```
  
##  <a name="topleft"></a>CRect::TopLeft  
 Die Koordinaten werden zurückgegeben, als Verweis auf eine [CPoint](cpoint-class.md) in enthaltene Objekt `CRect`.  
  
```  
CPoint& TopLeft() throw();
const CPoint& TopLeft() const throw(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Koordinaten von der oberen linken Ecke des Rechtecks.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Funktion verwenden, zum Abrufen oder Festlegen der oberen linken Ecke des Rechtecks. Legen Sie mithilfe dieser Funktion auf der linken Seite des Zuweisungsoperators der Ecke.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CRect::CenterPoint](#centerpoint).  
  
##  <a name="unionrect"></a>CRect::UnionRect  
 Macht die Dimensionen der `CRect` der Union der beiden Rechtecke gleich.  
  
```  
BOOL UnionRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect1`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) oder `CRect` , einem Quellrechteck enthält.  
  
 `lpRect2`  
 Verweist auf eine `RECT` oder `CRect` , einem Quellrechteck enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Union nicht leer ist; 0, wenn die Union leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Union ist das kleinste Rechteck befindet, das sowohl Quelle Rechtecke enthält.  
  
 Die Dimensionen der ein leeres Rechteck, ignoriert Windows; d. h. ein Rechteck, das keine Höhe hat oder keine Breite.  
  
> [!NOTE]
>  Müssen sowohl der Rechtecke normalisiert werden, oder diese Funktion kann fehlschlagen. Sie können Aufrufen [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor Sie diese Funktion aufrufen.  
  
### <a name="example"></a>Beispiel  
```cpp  
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3.UnionRect(&rect1, &rect2);
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect3);   
```
 
##  <a name="width"></a>CRect::Width  
 Berechnet die Breite der `CRect` durch den linken Wert aus den richtigen Wert subtrahiert.  
  
```  
int Width() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite des `CRect`.  
  
### <a name="remarks"></a>Hinweise  
 Die Breite kann negativ sein.  
  
> [!NOTE]
>  Das Rechteck muss normalisiert werden, oder diese Funktion möglicherweise ein Fehler. Sie können Aufrufen [NormalizeRect](#normalizerect) , das Rechteck zu normalisieren, bevor Sie diese Funktion aufrufen.  
  
### <a name="example"></a>Beispiel  

```cpp  
   CRect rect(20, 30, 80, 70);
int nWid = rect.Width();
   // nWid is now 60
   ASSERT(nWid == 60);   
```
## <a name="see-also"></a>Siehe auch  
 [CPoint-Klasse](cpoint-class.md)   
 [CSize-Klasse](csize-class.md)   
 [RECT](../../mfc/reference/rect-structure1.md)


