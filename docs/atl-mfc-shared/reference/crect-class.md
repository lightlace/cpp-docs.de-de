---
title: CRect Class | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- LPCRECT data type
- CRect class
- LPRECT operator
- RECT structure
ms.assetid: dee4e752-15d6-4db4-b68f-1ad65b2ed6ca
caps.latest.revision: 24
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: fa528d300c546bfdeaab55ff88735efcaf8533a5
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="crect-class"></a>CRect-Klasse
Ähnlich wie ein Windows [RECT](../../mfc/reference/rect-structure1.md) Struktur.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CRect : public tagRECT  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRect::CRect](#crect)|Erstellt ein `CRect`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRect::BottomRight](#bottomright)|Gibt den Punkt unteren rechten Ecke des `CRect`.|  
|[CRect::CenterPoint](#centerpoint)|Gibt den Mittelpunkt des `CRect`.|  
|[CRect::CopyRect](#copyrect)|Kopiert die Dimensionen eines Rechtecks Quelle an `CRect`.|  
|[CRect::DeflateRect](#deflaterect)|Verringert die Breite und Höhe des `CRect`.|  
|[CRect::EqualRect](#equalrect)|Bestimmt, ob `CRect` angegebenen Rechteck entspricht.|  
|[CRect::Height](#height)|Berechnet die Höhe der `CRect`.|  
|[CRect::InflateRect](#inflaterect)|Erhöht die Breite und Höhe des `CRect`.|  
|[CRect::IntersectRect](#intersectrect)|Legt `CRect` auf die Schnittmenge zweier Rechtecke gleich.|  
|[CRect::IsRectEmpty](#isrectempty)|Bestimmt, ob `CRect` ist leer. `CRect`ist leer, wenn die Breite bzw. Höhe 0 sind.|  
|[CRect::IsRectNull](#isrectnull)|Bestimmt, ob die **oben**, **unten**, **linken**, und **rechten** Membervariablen sind alle gleich 0.|  
|[CRect::MoveToX](#movetox)|Verschiebt `CRect` an der angegebenen X-Koordinate.|  
|[CRect::MoveToXY](#movetoxy)|Verschiebt `CRect` an den angegebenen x- und y-Koordinaten.|  
|[CRect::MoveToY](#movetoy)|Verschiebt `CRect` zur angegebenen y-Koordinate.|  
|[CRect:: NormalizeRect](#normalizerect)|Standardisiert die Höhe und Breite des `CRect`.|  
|[CRect::OffsetRect](#offsetrect)|Verschiebt `CRect` durch den angegebenen Offsets.|  
|[CRect::PtInRect](#ptinrect)|Bestimmt, ob der angegebene Punkt innerhalb liegt `CRect`.|  
|[CRect::SetRect](#setrect)|Legt die Maße des `CRect`.|  
|[CRect::SetRectEmpty](#setrectempty)|Legt `CRect` auf ein leeres Rechteck (alle Koordinaten gleich 0).|  
|[CRect::Size](#size)|Berechnet die Größe des `CRect`.|  
|[CRect::SubtractRect](#subtractrect)|Subtrahiert ein Rechteck von einem anderen.|  
|[CRect::TopLeft](#topleft)|Gibt die linke obere Punkt `CRect`.|  
|[CRect::UnionRect](#unionrect)|Legt `CRect` für die Union zweier Rechtecke gleich.|  
|[CRect::Width](#width)|Berechnet die Breite der `CRect`.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren    
|Name|Beschreibung|  
|----------|-----------------|  
|[CRect::operator-](#operator_-)|Subtrahiert den angegebenen Offsets von `CRect` oder verkleinert `CRect` und gibt das resultierende `CRect`.|  
|[CRect::operator LPCRECT](#operator_lpcrect)|Konvertiert eine `CRect` zu einer **LPCRECT**.|  
|[CRect::operator LPRECT](#operator_lprect)|Konvertiert eine `CRect` zu einer `LPRECT`.|  
|[CRect::operator! =](#operator_neq)|Bestimmt, ob `CRect` stimmt nicht mit einem Rechteck.|  
|[CRect::operator&amp;](#operator_amp)|Erstellt die Schnittmenge der `CRect` und ein Rechteck und gibt das resultierende `CRect`.|  
|[CRect::operator&amp;=](#operator_amp_eq)|Legt `CRect` gleich auf die Schnittmenge des `CRect` und ein Rechteck.|  
|[CRect::operator |](#operator_or)|Erstellt die Gesamtmenge der `CRect` und ein Rechteck und gibt das resultierende `CRect`.|  
|[CRect::operator |=](#operator_or_eq)|Legt `CRect` gleich der Vereinigung von `CRect` und ein Rechteck.|  
|[CRect::operator +](#operator_add)|Fügt die angegebenen Offsets `CRect` oder vergrößert `CRect` und gibt das resultierende `CRect`.|  
|[CRect::operator +=](#operator_add_eq)|Fügt die angegebenen Offsets `CRect` oder vergrößert `CRect`.|  
|[CRect::operator =](#operator_eq)|Kopiert die Dimensionen eines Rechtecks an `CRect`.|  
|[CRect::operator =](#operator_-_eq)|Subtrahiert den angegebenen Offsets von `CRect` oder verkleinert `CRect`.|  
|[CRect::operator ==](#operator_eq_eq)|Bestimmt, ob `CRect` entspricht einem Rechteck.|  
  
## <a name="remarks"></a>Hinweise  
 `CRect`enthält auch Memberfunktionen zum Bearbeiten von `CRect` Objekte und Windows `RECT` Strukturen.  
  
 Ein `CRect` Objekt kann als Funktionsparameter übergeben werden immer ein `RECT` Struktur **LPCRECT**, oder `LPRECT` übergeben werden kann.  
  
> [!NOTE]
>  Diese Klasse ist abgeleitet von der **TagRECT** Struktur. (Der Name **TagRECT** weniger häufig verwendete Name ist für die `RECT` Struktur.) Dies bedeutet, dass die Datenelemente (**linken**, **oben**, **Rechte**, und **unten**) von der `RECT` Struktur sind zugänglich Datenmember der `CRect`.  
  
 Ein `CRect` enthält Membervariablen, die die oberen linken und unteren rechten Ecke eines Rechtecks definieren.  
  
 Bei der Angabe einer `CRect`, achten Sie es erstellen, damit er normalisiert ist – also, dass der Wert, der die linke Koordinate der rechten Seite und dem oberen unterschreitet ist kleiner als unten. Z. B. oben links (10,10) unten rechts (20,20) ein normalisiertes Rechtecks definiert jedoch oben links (20,20) und unten rechts (10,10) definiert eine nicht normalisierte Rechteck. Wenn das Rechteck wird nicht normalisiert, viele `CRect` Memberfunktionen möglicherweise falsche Ergebnisse zurück. (Siehe [CRect:: NormalizeRect](#normalizerect) eine Liste dieser Funktionen.) Bevor Sie eine Funktion, die normalisierte Rechtecke erfordert aufrufen, können Sie nicht normalisierte Rechtecke normalisieren, durch Aufrufen der `NormalizeRect` Funktion.  
  
 Seien Sie vorsichtig beim Bearbeiten einer `CRect` mit der [CDC::DPtoLP](../../mfc/reference/cdc-class.md#dptolp) und [CDC::LPtoDP](../../mfc/reference/cdc-class.md#lptodp) Memberfunktionen. Wenn der Zuordnungsmodus eines Kontexts für die Anzeige ist der y-Block negativ ist, wie in `MM_LOENGLISH`, dann `CDC::DPtoLP` werden Transformieren der `CRect` , damit die oben im unteren Bereich größer ist. Funktionen wie **Höhe** und **Größe** gibt negative Werte für die Höhe des transformierten zurück `CRect`, und das Rechteck wird nicht normalisiert werden.  

  
 Wenn mithilfe von überladenen `CRect` Operatoren der erste Operand muss ein `CRect`; das zweite kann entweder ein [RECT](../../mfc/reference/rect-structure1.md) Struktur oder ein `CRect` Objekt.  
  
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
 Die Koordinate der unteren rechten Ecke des Rechtecks.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Funktion verwenden, um entweder abrufen oder Festlegen der unteren rechten Ecke des Rechtecks. Legen Sie die Ecke mit dieser Funktion auf der linken Seite des Zuweisungsoperators.  
  
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
 Berechnet den Mittelpunkt des `CRect` durch die linken und rechten Werte addiert und geteilt durch zwei, und die oberen und unteren Werte addiert und geteilt durch zwei.  
  
```  
CPoint CenterPoint() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CPoint` Objekt, das den Mittelpunkt des `CRect`.  
  
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
 Gibt die Verschiebung von der oberen linken Ecke der unteren rechten Ecke des Rechtecks erstellt werden soll.  
  
 *topLeft*  
 Gibt die obere linke Position der `CRect`.  
  
 *bottomRight*  
 Gibt die Position der unteren rechten Ecke des `CRect`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn keine Argumente angegeben werden, **linken**, **oben**, **Rechte**, und **unten** Member werden nicht initialisiert.  
  
 Die `CRect`(**const RECT &**) und `CRect`(**LPCRECT**) Konstruktoren führen eine [CopyRect](#copyrect). Die anderen Konstruktoren initialisieren die Membervariablen des Objekts direkt.  
  
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
 `DeflateRect`entfernt `CRect` durch Verschieben der Seiten in der Mitte.  
  
```  
void DeflateRect(int x, int y) throw();
void DeflateRect(SIZE size) throw();
void DeflateRect(LPCRECT lpRect) throw();
void DeflateRect(int l, int t, int r, int b) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die Anzahl der Einheiten zum Verkleinern nach links und rechts vom `CRect`.  
  
 *y*  
 Gibt die Anzahl der Einheiten, um die oberen und unteren Rand deflate `CRect`.  
  
 `size`  
 Ein [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) oder [CSize](csize-class.md) , angibt, dass die Anzahl der Einheiten, deflate `CRect`. Die `cx` Wert gibt die Anzahl der Einheiten, um die linken und rechten Seite deflate und `cy` Wert gibt die Anzahl der Einheiten, um nach oben und unten verkleinern.  
  
 `lpRect`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder `CRect` , die die Anzahl der Einheiten auf jeder Seite deflate angibt.  
  
 *l*  
 Gibt die Anzahl der Einheiten auf der linken Seite des deflate `CRect`.  
  
 *t*  
 Gibt die Anzahl der Einheiten, um am Anfang deflate `CRect`.  
  
 *r*  
 Gibt die Anzahl der Einheiten auf der rechten Seite des deflate `CRect`.  
  
 *b*  
 Gibt die Anzahl der Einheiten, um am Ende deflate `CRect`.  
  
### <a name="remarks"></a>Hinweise  
 Hierzu `DeflateRect` linken und oberen Einheiten hinzugefügt und Einheiten am rechten und unteren subtrahiert. Die Parameter des `DeflateRect` signiert werden Werte: positive Werte deflate `CRect` und negative Werte vergrößern sie.  
  
 Die ersten beiden Überladungen deflate Paare von gegenüberliegenden Seiten des `CRect` , damit die Gesamtbreite um zweimal verringert *x* (oder `cx`) und die Gesamthöhe zweimal gesunken ist *y* (oder `cy`). Die beiden anderen Überladungen deflate jeder Seite des `CRect` unabhängig von den anderen.  
  
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
 Bestimmt, ob `CRect` angegebenen Rechteck entspricht.  
  
```  
BOOL EqualRect(LPCRECT lpRect) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder `CRect` -Objekt, das die Koordinaten der oberen linken und der unteren rechten Ecke eines Rechtecks enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die zwei Rechtecke der gleichen oben, links, unten und rechts Werte verfügen; andernfalls 0.  
  
> [!NOTE]
>  Sowohl der Rechtecke normalisiert werden müssen, oder diese Funktion schlagen fehl. Rufen Sie [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor diese Funktion aufzurufen.  
  
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
 Berechnet die Höhe der `CRect` den obersten Wert aus dem unteren Wert subtrahiert.  
  
```  
int Height() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe des `CRect`.  
  
### <a name="remarks"></a>Hinweise  
 Der resultierende Wert kann negativ sein.  
  
> [!NOTE]
>  Das Rechteck muss normalisiert werden, oder diese Funktion kann fehlschlagen. Rufen Sie [NormalizeRect](#normalizerect) , das Rechteck zu normalisieren, bevor diese Funktion aufzurufen.  
  
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
 `InflateRect`Vergrößert dieses `CRect` durch die Seiten von der Mitte verschieben.  
  
```  
void InflateRect(int x, int y) throw();
void InflateRect(SIZE size) throw();
void InflateRect(LPCRECT lpRect) throw();
void InflateRect(int l, int t, int r,  int b) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Gibt die Anzahl der Einheiten auf der linken Seite vergrößert werden soll und die rechte Seite des `CRect`.  
  
 *y*  
 Gibt die Anzahl der Einheiten, um die oberen und unteren Rand vergrößert werden soll `CRect`.  
  
 `size`  
 Ein [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) oder [CSize](csize-class.md) , angibt, dass die Anzahl der Einheiten vergrößern `CRect`. Die `cx` Wert gibt die Anzahl der Einheiten, um die linken und rechten Seite vergrößert werden soll und die `cy` Wert gibt die Anzahl der Einheiten, um die oberen und unteren vergrößert werden soll.  
  
 `lpRect`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder `CRect` , die angibt, dass der Anzahl der Einheiten, um jede Seite vergrößert werden soll.  
  
 *l*  
 Gibt die Anzahl der Einheiten auf der linken Seite des vergrößern `CRect`.  
  
 *t*  
 Gibt die Anzahl der Einheiten, um am Anfang vergrößert werden soll `CRect`.  
  
 *r*  
 Gibt die Anzahl der Einheiten nach rechts vergrößern `CRect`.  
  
 *b*  
 Gibt die Anzahl der Einheiten vergrößern unten `CRect`.  
  
### <a name="remarks"></a>Hinweise  
 Hierzu `InflateRect` Einheiten vom linken und oberen subtrahiert, und am rechten und unteren Einheiten hinzugefügt. Die Parameter des `InflateRect` signiert werden positive Werte vergrößern Werte `CRect` und negative Werte deflate es.  
  
 Die ersten beiden Überladungen vergrößern sowohl Paare von gegenüberliegenden Seiten des `CRect` , damit die gesamte Breite um zwei Mal erhöht wird, *x* (oder `cx`) und die gesamte Höhe wird erhöht, zwei Mal *y* (oder `cy`). Die beiden anderen Überladungen vergrößert werden soll jede Seite der `CRect` unabhängig von den anderen.  
  
### <a name="example"></a>Beispiel  
```cpp  
 CRect rect(0, 0, 300, 300);
 rect.InflateRect(50, 200);

 // rect is now (-50, -200, 350, 500)
 ASSERT(rect == CRect(-50, -200, 350, 500));  
```
  
##  <a name="intersectrect"></a>CRect::IntersectRect  
 Stellt eine `CRect` gleich auf die Schnittmenge von zwei vorhandenen Rechtecken.  
  
```  
BOOL IntersectRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect1`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder `CRect` -Objekt, das ein Rechteck enthält.  
  
 `lpRect2`  
 Verweist auf eine `RECT` Struktur oder `CRect` -Objekt, das ein Rechteck enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Schnittmenge nicht leer ist; 0, wenn die Schnittmenge leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Schnittmenge ist das größte Rechteck in beide vorhandenen Rechtecke enthalten sind.  
  
> [!NOTE]
>  Sowohl der Rechtecke normalisiert werden müssen, oder diese Funktion schlagen fehl. Rufen Sie [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor diese Funktion aufzurufen.  
  
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
 Einen Wert ungleich NULL `CRect` leer ist; 0 Wenn `CRect` nicht leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Ein Rechteck ist leer, wenn die Breite bzw. Höhe 0 sind oder negativ sein. Unterscheidet sich von `IsRectNull`, die bestimmt, ob alle Koordinaten des Rechtecks&0; (null) sind.  
  
> [!NOTE]
>  Das Rechteck muss normalisiert werden, oder diese Funktion kann fehlschlagen. Rufen Sie [NormalizeRect](#normalizerect) , das Rechteck zu normalisieren, bevor diese Funktion aufzurufen.  
  
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
 Bestimmt, ob oben, links, unten und rechts Werte `CRect` sind alle gleich 0.  
  
```  
BOOL IsRectNull() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich NULL `CRect`des oberen, linken, unteren und rechten Werte sind alle gleich 0 ist, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Unterscheidet sich von `IsRectEmpty`, die bestimmt, ob das Rechteck leer ist.  
  
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
 Mit dieser Funktion können Sie das Rechteck verschieben, um die absolute angegebenen X-Koordinate *x*.  
  
```  
void MoveToX(int x) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
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
 Rufen Sie diese Funktion, um das Rechteck verschieben, um die absolute X - und y-Koordinaten angegeben.  
  
```  
void MoveToXY(int x, int y) throw();
void MoveToXY(POINT point) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Die absolute X-Koordinate für die linke obere Ecke des Rechtecks.  
  
 *y*  
 Die absolute y-Koordinate für die linke obere Ecke des Rechtecks.  
  
 `point`  
 Ein **Punkt** -Struktur, die absolute linke obere Ecke des Rechtecks angibt.  
  
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
 Mit dieser Funktion können Sie das Rechteck verschieben, um die absolute angegebenen y-Koordinate *y*.  
  
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
 Normalisiert `CRect` , damit die Höhe und Breite positiv sind.  
  
```  
void NormalizeRect() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Rechteck wird für die vierte Quadranten Positionierung, normalisiert die Windows in der Regel für die Koordinaten verwendet. `NormalizeRect`Vergleicht die oberen und unteren Werte und vertauscht diese, wenn oben im unteren Bereich überschreitet. Auf ähnliche Weise vertauscht die Werte links und rechts, ist der linken Seite größer als der Rechte. Diese Funktion ist nützlich beim Umgang mit verschiedenen Zuordnungsmodi und Rechtecke umgekehrt.  
  
> [!NOTE]
>  Die folgenden `CRect` Memberfunktionen erfordern normalisierte Rechtecke, damit Sie einwandfrei funktionieren: [Höhe](#height), [Breite](#width), [Größe](#size), [IsRectEmpty](#isrectempty), [PtInRect](#ptinrect), [EqualRect](#equalrect), [UnionRect](#unionrect), [IntersectRect](#intersectrect), [SubtractRect](#subtractrect), [Operator ==](#operator_eq_eq), [Operator! =](#operator_neq), [Operator |](#operator_or), [Operator | =](#operator_or_eq), [Operator &](#operator_amp), und [Operator & =](#operator_amp_eq).  
  
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
 *x*  
 Gibt die Menge verschieben nach links oder rechts. Es muss nach links verschieben negativ sein.  
  
 *y*  
 Gibt die Menge nach oben oder unten zu verschieben. Es muss nach oben verschoben negativ sein.  
  
 `point`  
 Enthält eine [Punkt](../../mfc/reference/point-structure1.md) Struktur oder [CPoint](cpoint-class.md) -Objekt, mit beiden Dimensionen, um die verschoben.  
  
 `size`  
 Enthält eine [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder [CSize](csize-class.md) -Objekt, mit beiden Dimensionen, um die verschoben.  
  
### <a name="remarks"></a>Hinweise  
 Verschiebt `CRect` *x* Einheiten entlang der x-Achse und *y* Einheiten entlang der y-Achse. Die *x* und *y* Parameter sind Werte mit Vorzeichen, sodass `CRect` nach links verschoben werden oder direkt nach oben oder unten.  
  
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

  
##  <a name="operator_lpcrect"></a>CRect::operator LPCRECT konvertiert eine `CRect` zu einer [LPCRECT](../../mfc/reference/data-types-mfc.md).  

  
```  
operator LPCRECT() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie diese Funktion verwenden, Sie brauchen nicht die Adresse des (**&**) Operator. Dieser Operator wird automatisch verwendet, wenn Sie übergeben ein `CRect` -Objekt, eine Funktion, erwartet ein **LPCRECT**.  
  

##  <a name="operator_lprect"></a>CRect::operator LPRECT  
 Konvertiert eine `CRect` zu einer [LPRECT](../../mfc/reference/data-types-mfc.md).  

  
```
operator LPRECT() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie diese Funktion verwenden, Sie brauchen nicht die Adresse des (**&**) Operator. Dieser Operator wird automatisch verwendet, wenn Sie übergeben ein `CRect` -Objekt, eine Funktion, erwartet ein `LPRECT`.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CRect::operator LPCRECT](#operator_lpcrect).  
  
##  <a name="operator_eq"></a>CRect::operator =  
 Weist *SrcRect* auf `CRect`.  
  
```  
void operator=(const RECT& srcRect) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *srcRect*  
 Bezieht sich auf ein Rechteck. Can be a [RECT](../../mfc/reference/rect-structure1.md) or `CRect`.  
  
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
 Bestimmt, ob `rect` gleich `CRect` durch Vergleichen die Koordinaten der oberen linken und der unteren rechten Ecke.  
  
```  
BOOL operator==(const RECT& rect) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Bezieht sich auf ein Rechteck. Can be a [RECT](../../mfc/reference/rect-structure1.md) or `CRect`.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn gleich; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Sowohl der Rechtecke normalisiert werden müssen, oder diese Funktion schlagen fehl. Rufen Sie [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor diese Funktion aufzurufen.  
  
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
 Bestimmt, ob `rect` stimmt nicht mit `CRect` durch Vergleichen die Koordinaten der oberen linken und der unteren rechten Ecke.  
  
```  
BOOL operator!=(const RECT& rect) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Bezieht sich auf ein Rechteck. Can be a [RECT](../../mfc/reference/rect-structure1.md) or `CRect`.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn nicht gleich; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Sowohl der Rechtecke normalisiert werden müssen, oder diese Funktion schlagen fehl. Rufen Sie [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor diese Funktion aufzurufen.  
  
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
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder `CRect` -Objekt, das die Anzahl von Einheiten auf jeder Seite des vergrößern enthält `CRect`.  
  
### <a name="remarks"></a>Hinweise  
 Des Parameters *x* und *y* (oder `cx` und `cy`) Werte hinzugefügt, `CRect`.  
  
 Die dritte Überladung vergrößert `CRect` durch die Anzahl der Einheiten, die in jeder Member des Parameters angegeben.  
  
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
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder `CRect` -Objekt, das die Anzahl von Einheiten auf jeder Seite des deflate enthält `CRect`.  
  
### <a name="remarks"></a>Hinweise  
 Des Parameters *x* und *y* (oder `cx` und `cy`) Werte subtrahiert `CRect`.  
  
 Die dritte Überladung entfernt `CRect` durch die Anzahl der Einheiten, die in jeder Member des Parameters angegeben. Beachten Sie, die diese Überladung wie funktioniert [DeflateRect](#deflaterect).  
  
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
 Legt `CRect` gleich auf die Schnittmenge des `CRect` und `rect`.  
  
```  
void operator&=(const RECT& rect) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Enthält eine [RECT](../../mfc/reference/rect-structure1.md) oder `CRect`.  
  
### <a name="remarks"></a>Hinweise  
 Die Schnittmenge ist das größte Rechteck, das in beiden Rechtecke enthalten ist.  
  
> [!NOTE]
>  Sowohl der Rechtecke normalisiert werden müssen, oder diese Funktion schlagen fehl. Rufen Sie [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor diese Funktion aufzurufen.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CRect::IntersectRect](#intersectrect).  
  
##  <a name="operator_or_eq"></a>CRect::operator | =  
 Legt `CRect` gleich der Vereinigung von `CRect` und `rect`.  
  
```  
void operator|=(const RECT& rect) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Enthält eine `CRect` oder [RECT](../../mfc/reference/rect-structure1.md).  
  
### <a name="remarks"></a>Hinweise  
 Die Union ist das kleinste Rechteck, das beide Rechtecke Quelle enthält.  
  
> [!NOTE]
>  Sowohl der Rechtecke normalisiert werden müssen, oder diese Funktion schlagen fehl. Rufen Sie [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor diese Funktion aufzurufen.  
  
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
 Ein [Punkt](../../mfc/reference/point-structure1.md) Struktur oder [CPoint](cpoint-class.md) Objekt, das die Anzahl der Einheiten, die zum Verschieben des Rückgabewerts angibt.  
  
 `size`  
 Ein [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder [CSize](csize-class.md) Objekt, das die Anzahl der Einheiten, die zum Verschieben des Rückgabewerts angibt.  
  
 `lpRect`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder `CRect` -Objekt, das die Anzahl der Einheiten, um jede Seite des Rückgabewerts vergrößert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Die `CRect` verschieben bzw. überhöhte `CRect` durch die Anzahl der Einheiten, die im Parameter angegeben.  
  
### <a name="remarks"></a>Hinweise  
 Des Parameters *x* und *y* (oder `cx` und `cy`) Parameter hinzugefügt werden `CRect`die position.  
  
 Die dritte Überladung gibt eine neue `CRect` gleich `CRect` aufgeblasen wird durch die Anzahl der Einheiten, die in jeder Member des Parameters angegeben.  
  
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
 Ein [Punkt](../../mfc/reference/point-structure1.md) Struktur oder `CPoint` Objekt, das die Anzahl der Einheiten, die zum Verschieben des Rückgabewerts angibt.  
  
 `size`  
 Ein [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder `CSize` Objekt, das die Anzahl der Einheiten, die zum Verschieben des Rückgabewerts angibt.  
  
 `lpRect`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder `CRect` -Objekt, das die Anzahl von Einheiten auf jeder Seite des Rückgabewerts deflate enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Die `CRect` verschieben bzw. Entleeren `CRect` durch die Anzahl der Einheiten, die im Parameter angegeben.  
  
### <a name="remarks"></a>Hinweise  
 Des Parameters *x* und *y* (oder `cx` und `cy`) Parameter subtrahiert `CRect`die position.  
  
 Die dritte Überladung gibt eine neue `CRect` gleich `CRect` verkleinert werden, um die Anzahl der Einheiten, die in jeder Member des Parameters angegeben. Beachten Sie, die diese Überladung wie funktioniert [DeflateRect](#deflaterect), nicht [SubtractRect](#subtractrect).  
  
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
 Gibt eine `CRect` , um die Schnittmenge der `CRect` und *rect2*.  
  
```  
CRect operator&(const RECT& rect2) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 *rect2*  
 Enthält eine [RECT](../../mfc/reference/rect-structure1.md) oder `CRect`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CRect` , um die Schnittmenge der `CRect` und *rect2*.  
  
### <a name="remarks"></a>Hinweise  
 Die Schnittmenge ist das größte Rechteck, das in beiden Rechtecke enthalten ist.  
  
> [!NOTE]
>  Sowohl der Rechtecke normalisiert werden müssen, oder diese Funktion schlagen fehl. Rufen Sie [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor diese Funktion aufzurufen.  
  
### <a name="example"></a>Beispiel  
```cpp  
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3 = rect1 & rect2;
   CRect   rectResult(100, 100, 200, 200);
   ASSERT(rectResult == rect3);   
```

  
##  <a name="operator_or"></a>CRect::operator |  
 Gibt eine `CRect` , die Gesamtmenge der `CRect` und *rect2*.  
  
```   
CRect operator|(const RECT& 
rect2) const throw(); 
```  
  
### <a name="parameters"></a>Parameter  
 *rect2*  
 Enthält eine [RECT](../../mfc/reference/rect-structure1.md) oder `CRect`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CRect` , die Gesamtmenge der `CRect` und *rect2*.  
  
### <a name="remarks"></a>Hinweise  
 Die Union ist das kleinste Rechteck, das beide Rechtecke enthält.  
  
> [!NOTE]
>  Sowohl der Rechtecke normalisiert werden müssen, oder diese Funktion schlagen fehl. Rufen Sie [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor diese Funktion aufzurufen.  
  
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
 Ungleich NULL, wenn der Punkt liegt `CRect`; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein Punkt ist in `CRect` liegt auf der linken oder oberen Seite oder in allen vier Seiten wird. Ein Punkt auf der rechten oder unteren Seite liegt außerhalb des `CRect`.  
  
> [!NOTE]
>  Das Rechteck muss normalisiert werden, oder diese Funktion kann fehlschlagen. Rufen Sie [NormalizeRect](#normalizerect) , das Rechteck zu normalisieren, bevor diese Funktion aufzurufen.  
  
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
 Legt die Dimensionen des `CRect` an die angegebenen Koordinaten.  
  
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
 Macht `CRect` null Rechtecks durch alle Koordinaten auf Null festlegen.  
  
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
 Die `cx` und `cy` Mitglieder des Rückgabewerts enthalten, die Höhe und Breite des `CRect`.  
  
```  
CSize Size() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CSize](csize-class.md) -Objekt, das die Größe des `CRect`.  
  
### <a name="remarks"></a>Hinweise  
 Höhe oder Breite kann negativ sein.  
  
> [!NOTE]
>  Das Rechteck muss normalisiert werden, oder diese Funktion kann fehlschlagen. Rufen Sie [NormalizeRect](#normalizerect) , das Rechteck zu normalisieren, bevor diese Funktion aufzurufen.  
  
### <a name="example"></a>Beispiel  
```cpp  
 CRect rect(10, 10, 50, 50);
 CSize sz = rect.Size();
 ASSERT(sz.cx == 40 && sz.cy == 40);  
```

##  <a name="subtractrect"></a>CRect::SubtractRect  
 Macht die Dimensionen der **CRect** gleich der Subtraktion von `lpRectSrc2` von `lpRectSrc1`.  
  
```  
BOOL SubtractRect(LPCRECT lpRectSrc1, LPCRECT lpRectSrc2) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpRectSrc1`  
 Verweist auf die [RECT](../../mfc/reference/rect-structure1.md) Struktur oder `CRect` Objekt, von dem ein Rechteck subtrahiert werden soll.  
  
 `lpRectSrc2`  
 Verweist auf die `RECT` Struktur oder `CRect` Objekt, aus dem Rechteck subtrahiert werden soll auf die von der `lpRectSrc1` Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Subtraktion ist das kleinste Rechteck, das alle Punkte enthält `lpRectScr1` , die sich nicht in der Schnittmenge des `lpRectScr1` und *lpRectScr2*.  
  
 Die durch angegebene Rechteck `lpRectSrc1` wird, unverändert, wenn das Rechteck angegeben `lpRectSrc2` nicht vollständig angegebenen Rechtecks überschneiden *lpRectSrc1* in mindestens einer der x oder y-Richtung.  
  
 Z. B. wenn `lpRectSrc1` wurden (10,10, 100,100) und `lpRectSrc2` wurden (50,50, 150,150), das Rechteck auf den `lpRectSrc1` ist, nicht geändert, wenn die Funktion zurückgegeben. Wenn `lpRectSrc1` wurden (10,10, 100,100) und `lpRectSrc2` wurden (50,10, 150,150), jedoch das Rechteck auf die `lpRectSrc1` enthält die Koordinaten (10,10, Punkt 50,100) bei die Funktion zurückgegeben.  
  
 `SubtractRect`entspricht nicht dem [Operator -](#operator_-) noch [Operator-=](#operator_-_eq). Keines dieser Operatoren jemals ruft `SubtractRect`.  
  
> [!NOTE]
>  Sowohl der Rechtecke normalisiert werden müssen, oder diese Funktion schlagen fehl. Rufen Sie [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor diese Funktion aufzurufen.  
  
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
 Die Koordinate der oberen linken Ecke des Rechtecks.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Funktion verwenden, um entweder abrufen oder Festlegen der oberen linken Ecke des Rechtecks. Legen Sie die Ecke mit dieser Funktion auf der linken Seite des Zuweisungsoperators.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CRect::CenterPoint](#centerpoint).  
  
##  <a name="unionrect"></a>CRect::UnionRect  
 Macht die Dimensionen der `CRect` der Union der beiden Rechtecke gleich.  
  
```  
BOOL UnionRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect1`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) oder `CRect` , die ein Rechteck enthält.  
  
 `lpRect2`  
 Verweist auf eine `RECT` oder `CRect` , die ein Rechteck enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Union nicht leer ist; 0, wenn die Union leer ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Union ist das kleinste Rechteck, das beide Rechtecke Quelle enthält.  
  
 Windows ignoriert die Dimensionen des ein leeres Rechteck. d. h. ein Rechteck, das keine Höhe hat oder keine Breite.  
  
> [!NOTE]
>  Sowohl der Rechtecke normalisiert werden müssen, oder diese Funktion schlagen fehl. Rufen Sie [NormalizeRect](#normalizerect) , Rechtecke zu normalisieren, bevor diese Funktion aufzurufen.  
  
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
>  Das Rechteck muss normalisiert werden, oder diese Funktion kann fehlschlagen. Rufen Sie [NormalizeRect](#normalizerect) , das Rechteck zu normalisieren, bevor diese Funktion aufzurufen.  
  
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



