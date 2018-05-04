---
title: CSize-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 18c48ccf2d1d7f424ca9b95f9dcbf7a2953a52aa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="csize-class"></a>CSize-Klasse
Ähnelt der Windows-Struktur [SIZE](http://msdn.microsoft.com/library/windows/desktop/dd145106) , bei der eine relative Koordinate oder Position implementiert wird  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSize : public tagSIZE 
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSize::CSize](#csize)|Erstellt ein `CSize`-Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSize::operator-](#operator_-)|Subtrahiert zwei Größen.|  
|[CSize::operator! =](#operator_neq)|Prüft auf Ungleichheit zwischen `CSize` und eine Größe.|  
|[CSize::operator +](#operator_add)|Fügt zwei Größen hinzu.|  
|[CSize::operator +=](#operator_add_eq)|Fügt eine Größe `CSize`.|  
|[CSize::operator =](#operator_-_eq)|Subtrahiert eine Größe von `CSize`.|  
|[CSize::operator ==](#operator_eq_eq)|Überprüft die Gleichheit zwischen `CSize` und eine Größe.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse ist abgeleitet von der **Größe** Struktur. Dies bedeutet, Sie können übergeben, eine `CSize` in einem Parameter, der erfordert eine **Größe** und Datenmember der der **Größe** Struktur stehen zugegriffen werden die Datenmember der `CSize`.  
  
 Die **Cx** und **cy** Mitglied **Größe** (und `CSize`) sind öffentlich. Darüber hinaus `CSize` implementiert Memberfunktionen zum Bearbeiten der **Größe** Struktur.  
  
> [!NOTE]
>  Weitere Informationen zu freigegebenen hilfsprogrammklassen (z. B. `CSize`), finden Sie unter [gemeinsam genutzten Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `tagSIZE`  
  
 `CSize`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atltypes.h  
  
##  <a name="csize"></a>  CSize::CSize  
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
 [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur oder `CSize` zur Initialisierung verwendete Objekt `CSize`.  
  
 `initPt`  
 [Punkt](../../mfc/reference/point-structure1.md) Struktur oder `CPoint` zur Initialisierung verwendete Objekt `CSize`.  
  
 `dwSize`  
 `DWORD` zur Initialisierung `CSize`. Das niederwertige Wort ist die **Cx** Element ist und das höherwertige Wort die **cy** Member.  
  
### <a name="remarks"></a>Hinweise  
 Wenn keine Argumente angegeben werden, **Cx** und **cy** werden auf 0 (null) initialisiert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#97](../../atl-mfc-shared/codesnippet/cpp/csize-class_1.cpp)]  
  
##  <a name="operator_eq_eq"></a>  CSize::operator ==  
 Überprüft die Gleichheit zwischen zwei Größen.  
  
```   
BOOL operator==(SIZE size) const throw(); 
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt zurück, die ungleich NULL, wenn die Größen gleich sind, Otherwize 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#98](../../atl-mfc-shared/codesnippet/cpp/csize-class_2.cpp)]  
  
##  <a name="operator_neq"></a>  CSize::operator! =  
 Prüft auf Ungleichheit zwischen zwei Größen.  
  
```   
BOOL operator!=(SIZE size) const throw(); 
```  
  
### <a name="remarks"></a>Hinweise  
 Ungleich NULL, wenn die Größe nicht gleich sind, gibt andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#99](../../atl-mfc-shared/codesnippet/cpp/csize-class_3.cpp)]  
  
##  <a name="operator_add_eq"></a>  CSize::operator +=  
 Fügt eine Größe dieser `CSize`.  
  
```   
void operator+=(SIZE size) throw(); 
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#100](../../atl-mfc-shared/codesnippet/cpp/csize-class_4.cpp)]  
  
##  <a name="operator_-_eq"></a>  CSize::operator =  
 Subtrahiert eine Größe von diesem `CSize`.  
  
```   
void operator-=(SIZE size) throw(); 
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#101](../../atl-mfc-shared/codesnippet/cpp/csize-class_5.cpp)]  
  
##  <a name="operator_add"></a>  CSize::operator +  
 Fügen Sie diese Operatoren der `CSize` Wert, der den Wert des Parameters.  
  
```   
CSize operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw(); 
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter den folgenden Beschreibungen der einzelnen Operatoren:  
  
- **Operator + (** `size` **)** dieser Vorgang fügt zwei `CSize` Werte.  
  
- **Operator + (** `point` **)** UTC-offsets (wechselt) diesen Vorgang eine [Punkt](http://msdn.microsoft.com/library/windows/desktop/dd162805) (oder [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)) Wert von diesem `CSize` Wert. Die **Cx** und **cy** Mitglieder dieser `CSize` Wert hinzugefügt werden die **x** und **y** Datenmember der **Punkt**  Wert. Es ist analog zu die Version des [CPoint::operator +](../../atl-mfc-shared/reference/cpoint-class.md#operator_add) , akzeptiert eine [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Parameter.  
  
- **Operator + (** `lpRect` **)** UTC-offsets (wechselt) diesen Vorgang eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) (oder [CRect](../../atl-mfc-shared/reference/crect-class.md)) Wert von diesem `CSize` Wert. Die **Cx** und **cy** Mitglieder dieser `CSize` Wert hinzugefügt werden die **linken**, **oben**, **rechts**, und **unteren** Datenmember der `RECT` Wert. Es ist analog zu die Version des [CRect::operator +](../../atl-mfc-shared/reference/crect-class.md#operator_add) , akzeptiert eine [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Parameter.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#102](../../atl-mfc-shared/codesnippet/cpp/csize-class_6.cpp)]  
  
##  <a name="operator_-"></a>  CSize::operator-  
 Die ersten drei dieser Operatoren subtrahieren dies `CSize` Wert, der den Wert des Parameters.  
  
```   
CSize operator-(SIZE size) const throw();
CPoint operator-(POINT point) const throw();
CRect operator-(const RECT* lpRect) const throw();
CSize operator-() const throw(); 
```  
  
### <a name="remarks"></a>Hinweise  
 Der vierte Operator, der unäres minus, ändert die Vorzeichen der `CSize` Wert. Finden Sie unter den folgenden Beschreibungen der einzelnen Operatoren:  
  
- **Operator-(** `size` **)** dieses Vorgangs subtrahiert zwei `CSize` Werte.  
  
- **Operator-(** `point` **)** UTC-offsets (wechselt) diesen Vorgang eine [Punkt](http://msdn.microsoft.com/library/windows/desktop/dd162805) oder [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Wert durch die Additive Inverse dieses `CSize` Wert. Die **Cx** und **cy** dieses `CSize` Wert subtrahiert die **x** und **y** Datenmember von der **Punkt**  Wert. Es ist analog zu die Version des [CPoint::operator -](../../atl-mfc-shared/reference/cpoint-class.md#operator_-) , akzeptiert eine [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Parameter.  
  
- **Operator-(** `lpRect` **)** UTC-offsets (wechselt) diesen Vorgang eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) oder [CRect](../../atl-mfc-shared/reference/crect-class.md) Wert durch die Additive Inverse dieses `CSize` Wert. Die **Cx** und **cy** Mitglieder dieser `CSize` Wert subtrahiert die **linken**, **oben**, **rechts**, und **unteren** Datenmember der `RECT` Wert. Es ist analog zu die Version des [CRect::operator -](../../atl-mfc-shared/reference/crect-class.md#operator_-) , akzeptiert eine [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Parameter.  
  
- **Operator-()** dieser Vorgang gibt die Additive Inverse dieses `CSize` Wert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#103](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MDI](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRect-Klasse](../../atl-mfc-shared/reference/crect-class.md)   
 [CPoint-Klasse](../../atl-mfc-shared/reference/cpoint-class.md)

