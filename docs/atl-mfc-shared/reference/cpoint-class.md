---
title: CPoint Class | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPoint
- ATLTYPES/ATL::CPoint
- ATLTYPES/ATL::CPoint::CPoint
- ATLTYPES/ATL::CPoint::Offset
dev_langs:
- C++
helpviewer_keywords:
- LPPOINT structure
- POINT structure
- CPoint class
ms.assetid: a6d4db93-35cc-444d-9221-c3e160f6edaa
caps.latest.revision: 22
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 6b1afeea5a1d55fb3317b432871f2ed15dd5d19e
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cpoint-class"></a>CPoint-Klasse
Ähnlich der Windows-Struktur `POINT` .  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPoint : public tagPOINT 
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPoint::CPoint](#cpoint)|Erstellt ein Objekt vom Typ `CPoint`.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPoint::Offset](#offset)|Fügt Werte für die **x** und **y** Mitglieder der `CPoint`.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPoint::operator-](#operator_-)|Gibt die Differenz zwischen einer `CPoint` und eine Größe oder die Negation von einem Punkt oder den Größenunterschied zwischen zwei Punkten oder eine negative Größe der Offset der.|  
|[CPoint::operator! =](#operator_neq)|Prüft auf Ungleichheit zwischen zwei Punkten.|  
|[CPoint::operator +](#operator_add)|Gibt die Summe der ein `CPoint` und eine Größe oder ein Punkt oder ein `CRect` offset durch eine Größe.|  
|[CPoint::operator +=](#operator_add_eq)|Offsets `CPoint` einen Größe oder einen Punkt hinzufügen.|  
|[CPoint::operator =](#operator_-_eq)|Offsets `CPoint` durch Subtrahieren eines Größe bzw..|  
|[CPoint::operator ==](#operator_eq_eq)|Überprüft die Gleichheit zwischen zwei Punkten.|  
  
## <a name="remarks"></a>Hinweise  
 Es enthält auch Memberfunktionen zum Bearbeiten von `CPoint` und [Punkt](../../mfc/reference/point-structure1.md) Strukturen.  
  
 Ein `CPoint` Objekt kann überall verwendet eine `POINT` Struktur verwendet wird. Die Operatoren dieser Klasse, die Interaktion mit einem "Size" akzeptieren Sie entweder [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekte oder [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Datenstrukturen, da die beiden austauschbar sind.  
  
> [!NOTE]
>  Diese Klasse ist abgeleitet von der `tagPOINT` Struktur. (Der Name `tagPOINT` weniger häufig verwendeter Name ist für die `POINT` Struktur.) Dies bedeutet, dass der Datenmember der `POINT` Struktur `x` und `y`, sind Mitglieder der verfügbaren Daten `CPoint`.  
  
> [!NOTE]
>  Weitere Informationen zu freigegebenen Dienstprogrammklassen (z. B. `CPoint`), finden Sie unter [freigegebene Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `tagPOINT`  
  
 `CPoint`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atltypes.h  
  
##  <a name="cpoint"></a>CPoint::CPoint
 Erstellt ein `CPoint`-Objekt.  
  
```  
CPoint() throw();
CPoint(int initX, int initY) throw();
CPoint(POINT initPt) throw();
CPoint(SIZE initSize) throw();
CPoint(LPARAM dwPoint) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `initX`  
 Gibt den Wert des `x`-Members von `CPoint` an.  
  
 `initY`  
 Gibt den Wert des `y`-Members von `CPoint` an.  
  
 `initPt`  
 [Punkt](../../mfc/reference/point-structure1.md) Struktur oder `CPoint` , angibt, dass die Werte, die zum Initialisieren verwendet `CPoint`.  
  
 `initSize`  
 [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder [CSize](../../atl-mfc-shared/reference/csize-class.md) , angibt, dass die Werte, die zum Initialisieren verwendet `CPoint`.  
  
 `dwPoint`  
 Legt den `x`-Member auf das niederwertige Wort von `dwPoint` und den `y`-Member auf das höherwertige Wort von `dwPoint` fest.  
  
### <a name="remarks"></a>Hinweise  
 Wenn keine Argumente angegeben werden, werden die `x`- und `y`-Member auf 0 festgelegt.  
  
### <a name="example"></a>Beispiel  
  
```cpp   
CPoint   ptTopLeft(0, 0); 
// works from a POINT, too  
 
POINT   ptHere;  
ptHere.x = 35;  
ptHere.y = 95;  
 
CPoint   ptMFCHere(ptHere);
 
// works from a SIZE 
SIZE   sHowBig;  
sHowBig.cx = 300;  
sHowBig.cy = 10;  
 
CPoint ptMFCBig(sHowBig); 
// or from a DWORD  
 
DWORD   dwSize;  
dwSize = MAKELONG(35, 95);
 
CPoint ptFromDouble(dwSize);
ASSERT(ptFromDouble == ptMFCHere);
```  
  
##  <a name="offset"></a>CPoint::Offset  
 Fügt Werte für die **x** und **y** Mitglieder der `CPoint`.  
  
```  
void Offset(int xOffset, int yOffset) throw();
void Offset(POINT point) throw();
void Offset(SIZE size) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *xOffset*  
 Gibt den Betrag für den offset der **x** Mitglied der `CPoint`.  
  
 *yOffset*  
 Gibt den Betrag für den offset der **y** Mitglied der `CPoint`.  
  
 `point`  
 Gibt die Menge ( [Punkt](../../mfc/reference/point-structure1.md) oder `CPoint`) für den offset der `CPoint`.  
  
 `size`  
 Gibt die Menge ( [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) oder [CSize](../../atl-mfc-shared/reference/csize-class.md)) für den offset der `CPoint`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#28;](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_1.cpp)]  
  
##  <a name="operator_eq_eq"></a>CPoint::operator ==  
 Überprüft die Gleichheit zwischen zwei Punkten.  
  
```  
BOOL operator==(POINT point) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `point`  
 Enthält eine [Punkt](../../mfc/reference/point-structure1.md) Struktur oder `CPoint` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Punkte gleich sind; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#29;](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_2.cpp)]  
  
##  <a name="operator_neq"></a>CPoint::operator! =  
 Prüft auf Ungleichheit zwischen zwei Punkten.  
  
```  
BOOL operator!=(POINT point) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `point`  
 Enthält eine [Punkt](../../mfc/reference/point-structure1.md) Struktur oder `CPoint` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Punkte nicht gleich sind; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#30;](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_3.cpp)]  
  
##  <a name="operator_add_eq"></a>CPoint::operator +=  
 Die erste Überladung fügt eine Größe der `CPoint`.  
  
```  
void operator+=(SIZE size) throw(); 
void operator+=(POINT point) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `size`  
 Enthält eine [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.  
  
 `point`  
 Enthält eine [Punkt](../../mfc/reference/point-structure1.md) Struktur oder [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die zweite Überladung fügt einen Punkt in der `CPoint`.  
  
 In beiden Fällen erfolgt die Addition durch Hinzufügen der **x** (oder **Cx**) Member des rechten Operanden der **x** Mitglied der `CPoint` und Hinzufügen der **y** (oder **cy**) Member des rechten Operanden der **y** Mitglied der `CPoint`.  
  
 Beispielsweise durch Hinzufügen von `CPoint(5, -7)` einer Variablen mit `CPoint(30, 40)` ändert die Variable `CPoint(35, 33)`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#31;](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_4.cpp)]  
  
##  <a name="operator_-_eq"></a>CPoint::operator =  
 Die erste Überladung subtrahiert einen Schriftgrad aus den `CPoint`.  
  
```  
void operator-=(SIZE size) throw(); 
void operator-=(POINT point) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `size`  
 Enthält eine [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.  
  
 `point`  
 Enthält eine [Punkt](../../mfc/reference/point-structure1.md) Struktur oder [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die zweite Überladung subtrahiert einen Punkt aus dem `CPoint`.  
  
 Subtraktion erfolgt in beiden Fällen wird durch Subtrahieren der **x** (oder **Cx**) Member des rechten Operanden aus der **x** Mitglied der `CPoint` subtrahiert die **y** (oder **cy**) Member des rechten Operanden aus der **y** Mitglied der `CPoint`.  
  
 Beispielsweise subtrahieren `CPoint(5, -7)` aus einer Variablen mit `CPoint(30, 40)` ändert die Variable `CPoint(25, 47)`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#32;](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_5.cpp)]  
  
##  <a name="operator_add"></a>CPoint::operator +  
 Verwenden Sie diesen Operator für den offset `CPoint` durch eine `CPoint` oder `CSize` -Objekt, oder versetzt ein `CRect` durch eine `CPoint`.  
  
```  
CPoint operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `size`  
 Enthält eine [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.  
  
 `point`  
 Enthält eine [Punkt](../../mfc/reference/point-structure1.md) Struktur oder [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Objekt.  
  
 `lpRect`  
 Enthält einen Zeiger auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CPoint` versetzt, um eine Größe einer **CPoint** ausgeglichen, die durch einen Punkt oder ein **CRect** durch einen Punkt ausgeglichen.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie eine der ersten beiden Überladungen z. B. für den offset des Punkts `CPoint(25, -19)` durch einen Punkt `CPoint(15, 5)` oder Größe `CSize(15, 5)` gibt den Wert `CPoint(40, -14)`.  
  
 Hinzufügen von Rechtecken zu einem Punkt gibt das Rechteck nach durch ausgeglichen wird die **x** und **y** in der angegebenen Werte. Verwenden Sie die letzte Überladung z. B. ein Rechteck versetzt `CRect(125, 219, 325, 419)` durch einen Punkt `CPoint(25, -19)` gibt `CRect(150, 200, 350, 400)`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&33;](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_6.cpp)]  
  
##  <a name="operator_-"></a>CPoint::operator-  
 Verwenden Sie eine der ersten beiden Überladungen subtrahiert einen `CPoint` oder `CSize` -Objekt aus `CPoint`.  
  
```  
CSize operator-(POINT point) const throw();
CPoint operator-(SIZE size) const throw();
CRect operator-(const RECT* lpRect) const throw();
CPoint operator-() const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `point`  
 Ein [Punkt](../../mfc/reference/point-structure1.md) Struktur oder [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Objekt.  
  
 `size`  
 Ein [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.  
  
 `lpRect`  
 Ein Zeiger auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CSize` also der Unterschied zwischen zwei Punkten, eine `CPoint` ausgeglichen, die mithilfe der Negation eines ein `CRect` ausgeglichen, die mithilfe der Negation eines Punkts oder `CPoint` also die Negation eines Punkts.  
  
### <a name="remarks"></a>Hinweise  
 Die dritte Überladung Offsets eine `CRect` mithilfe der Negation des `CPoint`. Verwenden Sie schließlich den unäre Operator um zu negierende `CPoint`.  
  
 Verwenden Sie z. B. die erste Überladung finden Sie den Unterschied zwischen zwei Punkten `CPoint(25, -19)` und `CPoint(15, 5)` gibt `CSize(10, -24)`.  
  
 Subtrahiert eine `CSize` aus `CPoint` wird die gleiche Berechnung wie oben beschrieben, gibt jedoch eine `CPoint` -Objekt und keine `CSize` Objekt. Verwenden Sie z. B. die zweite Überladung finden Sie den Unterschied zwischen dem `CPoint(25, -19)` und die Größe des `CSize(15, 5)` gibt `CPoint(10, -24)`.  
  
 Subtrahieren eines Rechtecks von einem Punkt gibt das Rechteck Offset zurück, durch die negative der der **x** und **y** in der angegebenen Werte. Verwenden Sie z. B. die letzte Überladung für den offset des Rechtecks `CRect(125, 200, 325, 400)` vom Punkt `CPoint(25, -19)` gibt `CRect(100, 219, 300, 419)`.  
  
 Verwenden des unäre Operators einen Punkt zu negieren. Verwenden Sie z. B. des unäre Operators mit dem Punkt `CPoint(25, -19)` gibt `CPoint(-25, 19)`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#34;](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_7.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MDI](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [POINT-Struktur](../../mfc/reference/point-structure1.md)   
 [CRect-Klasse](../../atl-mfc-shared/reference/crect-class.md)   
 [CSize-Klasse](../../atl-mfc-shared/reference/csize-class.md)



