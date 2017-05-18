---
title: CSize Class | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSize
- ATLTYPES/ATL::CSize
- ATLTYPES/ATL::CSize::CSize
dev_langs:
- C++
helpviewer_keywords:
- SIZE
- dimensions, MFC
- dimensions
- CSize class
ms.assetid: fb2cf85a-0bc1-46f8-892b-309c108b52ae
caps.latest.revision: 20
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
ms.openlocfilehash: 96905d916dfde8f8a7bf8131a280ae7ccfe511d8
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="csize-class"></a>CSize-Klasse
Ähnelt der Windows-Struktur [SIZE](http://msdn.microsoft.com/library/windows/desktop/dd145106) , bei der eine relative Koordinate oder Position implementiert wird  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSize : public tagSIZE 
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSize::CSize](#csize)|Erstellt ein `CSize`-Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSize::operator-](#operator_-)|Subtrahiert zwei Größen.|  
|[CSize::operator! =](#operator_neq)|Prüft auf Ungleichheit zwischen `CSize` und eine Größe.|  
|[CSize::operator +](#operator_add)|Fügt zwei Größen.|  
|[CSize::operator +=](#operator_add_eq)|Fügt eine Größe `CSize`.|  
|[CSize::operator =](#operator_-_eq)|Subtrahiert eine Größe von `CSize`.|  
|[CSize::operator ==](#operator_eq_eq)|Überprüft die Gleichheit zwischen `CSize` und eine Größe.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse ist abgeleitet von der **Größe** Struktur. Dies bedeutet, Sie können übergeben einer `CSize` in einem Parameter, der erfordert eine **Größe** und Datenmember der der **Größe** Struktur sind zugänglich Datenmember der `CSize`.  
  
 Die **Cx** und **cy** Mitglieder **Größe** (und `CSize`) sind öffentlich. Darüber hinaus `CSize` implementiert Memberfunktionen zum Bearbeiten der **Größe** Struktur.  
  
> [!NOTE]
>  Weitere Informationen zu freigegebenen Dienstprogrammklassen (z. B. `CSize`), finden Sie unter [freigegebene Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `tagSIZE`  
  
 `CSize`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atltypes.h  
  
##  <a name="csize"></a>CSize::CSize  
 Erstellt ein `CSize`-Objekt.  
  
```  
CSize() throw();
CSize( int initCX, int initCY) throw();
CSize( SIZE initSize) throw();
CSize( POINT initPt) throw();
CSize( DWORD dwSize) throw(); 
```  
  
### <a name="parameters"></a>Parameter  
 *initCX*  
 Legt die **Cx** Element für die `CSize`.  
  
 *initCY*  
 Legt die **cy** Element für die `CSize`.  
  
 `initSize`  
 [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder `CSize` -Objekt für die Initialisierung `CSize`.  
  
 `initPt`  
 [Punkt](../../mfc/reference/point-structure1.md) Struktur oder `CPoint` -Objekt für die Initialisierung `CSize`.  
  
 `dwSize`  
 `DWORD`zum Initialisieren verwendet `CSize`. Das niederwertige Wort ist die **Cx** Element und das höherwertige Wort ist die **cy** Member.  
  
### <a name="remarks"></a>Hinweise  
 Wenn keine Argumente angegeben werden, **Cx** und **cy** auf&0; (null) initialisiert werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#97;](../../atl-mfc-shared/codesnippet/cpp/csize-class_1.cpp)]  
  
##  <a name="operator_eq_eq"></a>CSize::operator ==  
 Überprüft die Gleichheit zwischen zwei Größen.  
  
```   
BOOL operator==(SIZE size) const throw(); 
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt einen Wert ungleich NULL, wenn die Größen gleich sind, Otherwize 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#98;](../../atl-mfc-shared/codesnippet/cpp/csize-class_2.cpp)]  
  
##  <a name="operator_neq"></a>CSize::operator! =  
 Prüft auf Ungleichheit zwischen zwei Größen.  
  
```   
BOOL operator!=(SIZE size) const throw(); 
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt einen Wert ungleich NULL, wenn die Größe nicht gleich sind, andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#99;](../../atl-mfc-shared/codesnippet/cpp/csize-class_3.cpp)]  
  
##  <a name="operator_add_eq"></a>CSize::operator +=  
 Fügt eine Größe dieser `CSize`.  
  
```   
void operator+=(SIZE size) throw(); 
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#100;](../../atl-mfc-shared/codesnippet/cpp/csize-class_4.cpp)]  
  
##  <a name="operator_-_eq"></a>CSize::operator =  
 Subtrahiert eine Größe von diesem `CSize`.  
  
```   
void operator-=(SIZE size) throw(); 
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#101;](../../atl-mfc-shared/codesnippet/cpp/csize-class_5.cpp)]  
  
##  <a name="operator_add"></a>CSize::operator +  
 Diese Operatoren hinzufügen `CSize` Wert mit dem Wert des Parameters.  
  
```   
CSize operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw(); 
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter den folgenden Beschreibungen der einzelnen Operatoren:  
  
- **Operator + (** `size` **)**dieser Vorgang fügt zwei `CSize` Werte.  
  
- **Operator + (** `point` **)**dieser Vorgang versetzt (bewegt) eine [Punkt](http://msdn.microsoft.com/library/windows/desktop/dd162805) (oder [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)) Wert von diesem `CSize` Wert. Die **Cx** und **cy** Member dieser `CSize` Wert hinzugefügt werden die **x** und **y** Datenmember der **Punkt** Wert. Es entspricht der Version von [CPoint::operator +](../../atl-mfc-shared/reference/cpoint-class.md#operator_add) , akzeptiert einen [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Parameter.  
  
- **Operator + (** `lpRect` **)**dieser Vorgang versetzt (bewegt) eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) (oder [CRect](../../atl-mfc-shared/reference/crect-class.md)) Wert von diesem `CSize` Wert. Die **Cx** und **cy** Member dieser `CSize` Wert hinzugefügt werden die **linken**, **oben**, **rechten**, und **unten** Datenmember der `RECT` Wert. Es entspricht der Version von [CRect::operator +](../../atl-mfc-shared/reference/crect-class.md#operator_add) , akzeptiert einen [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Parameter.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#102;](../../atl-mfc-shared/codesnippet/cpp/csize-class_6.cpp)]  
  
##  <a name="operator_-"></a>CSize::operator-  
 Die ersten drei dieser Operatoren subtrahieren dieser `CSize` Wert mit dem Wert des Parameters.  
  
```   
CSize operator-(SIZE size) const throw();
CPoint operator-(POINT point) const throw();
CRect operator-(const RECT* lpRect) const throw();
CSize operator-() const throw(); 
```  
  
### <a name="remarks"></a>Hinweise  
 Der vierte Operator, der unäres minus, ändert die Vorzeichen der `CSize` Wert. Finden Sie unter den folgenden Beschreibungen der einzelnen Operatoren:  
  
- **Operator-(** `size` **)**dieser Vorgang subtrahiert zwei `CSize` Werte.  
  
- **Operator-(** `point` **)**dieser Vorgang versetzt (bewegt) eine [Punkt](http://msdn.microsoft.com/library/windows/desktop/dd162805) oder [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Wert durch die Additive Inverse dieses `CSize` Wert. Die **Cx** und **cy** dieses `CSize` Wert subtrahiert die **x** und **y** Datenmember der **Punkt** Wert. Es entspricht der Version von [CPoint::operator -](../../atl-mfc-shared/reference/cpoint-class.md#operator_-) , akzeptiert einen [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Parameter.  
  
- **Operator-(** `lpRect` **)**dieser Vorgang versetzt (bewegt) eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) oder [CRect](../../atl-mfc-shared/reference/crect-class.md) Wert durch die Additive Inverse dieses `CSize` Wert. Die **Cx** und **cy** Member dieser `CSize` Wert subtrahiert die **linken**, **oben**, **rechts**, und **unten** Datenmember der `RECT` Wert. Es entspricht der Version von [CRect::operator -](../../atl-mfc-shared/reference/crect-class.md#operator_-) , akzeptiert einen [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Parameter.  
  
- **Operator-()**dieser Vorgang gibt die Additive Inverse dieses `CSize` Wert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#103;](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MDI](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRect-Klasse](../../atl-mfc-shared/reference/crect-class.md)   
 [CPoint-Klasse](../../atl-mfc-shared/reference/cpoint-class.md)


