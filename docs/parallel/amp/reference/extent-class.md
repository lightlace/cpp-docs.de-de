---
title: Extent-Klasse (C++-AMP) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::extent
dev_langs:
- C++
helpviewer_keywords:
- extent structure
ms.assetid: edb5de3d-3935-4dbb-8365-4cc6c4fb0269
caps.latest.revision: 19
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 8aa89b882ed075a8cdf0166d43fde1a5bfe7683d
ms.lasthandoff: 02/24/2017

---
# <a name="extent-class-c-amp"></a>extent-Klasse (C++ AMP)
Stellt einen Vektor aus *N* ganzzahlige Werte, die die Grenzen angeben einer *N*-dimensionalen Raum mit dem Ursprung 0. Die Werte im Vektor sind vom wichtigsten zum am wenigsten wichtigen Wert sortiert.  
  
### <a name="syntax"></a>Syntax  
  
```  
template <int _Rank>  
class extent;  
```  
  
### <a name="parameters"></a>Parameter  
 `_Rank`  
 Der Rang des `extent`-Objekts.  

 ## <a name="requirements"></a>Anforderungen  
 **Header:** amp.h  
  
 **Namespace:** Parallelität  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Extent-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `extent`-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Contains-Methode](#contains)|Überprüft, ob das angegebene `extent`-Objekt über den angegebenen Rang verfügt.|  
|[Size-Methode](#size)|Gibt die lineare Gesamtgröße des Wertebereichs zurück (in der Einheit Elemente).|  
|[Kachel-Methode](#tile)|Erzeugt ein `tiled_extent`-Objekt mit den Kachelwertebereichen, die durch angegebene Dimensionen festgelegt werden.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Operator-Operator](#operator_min)|Gibt ein neues `extent`-Objekt zurück, das erstellt wird, indem die `index`-Elemente von den entsprechenden `extent`-Elementen subtrahiert werden.|  
|[Operator--Operator](#operator_min_min)|Dekrementiert jedes Element des `extent`-Objekts.|  
|[Operator% = (Operator)](#operator_mod_eq)|Berechnet den Modul (Rest) jedes Elements im `extent`-Objekt, wenn dieses Element durch eine Zahl dividiert wird.|  
|[Operator * =-Operator](#operator_star_eq)|Multipliziert jedes Element des `extent`-Objekts mit einer Zahl.|  
|[Operator / =-Operator](#operator_min_eq)|Dividiert jedes Element des `extent`-Objekts durch eine Zahl.|  
|[Extent::\[\]](#operator_at)|Gibt das Element am angegebenen Index zurück.|  
|[Operator +-Operator](#operator_add)|Gibt ein neues `extent`-Objekt zurück, das durch Hinzufügen der entsprechenden `index`- und `extent`-Elemente erstellt wird.|  
|[Operator ++-Operator](#operator_add_add)|Inkrementiert jedes Element des `extent`-Objekts.|  
|[Operator +=-Operator](#operator_add_eq)|Fügt die angegebene Zahl jedem Element des `extent`-Objekts hinzu.|  
|[Operator =-Operator](#operator_eq)|Kopiert den Inhalt eines anderen `extent`-Objekts in dieses Objekt.|  
|[Operator-=-Operator](#operator_min_eq)|Subtrahiert die angegebene Anzahl von jedem Element des `extent`-Objekts.|  

  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Rank-Konstante](#rank)|Ruft den Rang des `extent`-Objekts ab.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `extent`  


## <a name="a-namecontainsa-contains"></a><a name="contains"></a>enthält 

Gibt an, ob das angegebene [Index](index-class.md) Wert innerhalb des Objekts "Block" enthalten ist.  
  
### <a name="syntax"></a>Syntax  
  
```  
bool contains(const index<rank>& _Index) const restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parameter  
 `_Index`  
 Der zu testende `index`-Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn der angegebene `index`-Wert im `extent`-Objekt enthalten ist; andernfalls `false`.  
  
##  <a name="a-namectora-extent"></a><a name="ctor"></a>Wertebereich 

Initialisiert eine neue Instanz der Klasse "Block".  
  
### <a name="syntax"></a>Syntax  
  
```  
extent() restrict(amp,cpu);    
extent(const extent<_Rank>& _Other) restrict(amp,cpu);    
explicit extent(int _I) restrict(amp,cpu);    
extent(int _I0,  int _I1) restrict(amp,cpu);    
extent(int _I0,  int _I1, int _I2) restrict(amp,cpu);    
explicit extent(const int _Array[_Rank])restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parameter  
 `_Array`  
 Ein Array mit ganzen `_Rank`-Zahlen, mit dem das neue `extent`-Objekt erstellt wird.  
  
 `_I`  
 Die Länge des Wertebereichs.  
  
 `_I0`  
 Die Länge der wichtigsten Dimension.  
  
 `_I1`  
 Die Länge der zweitwichtigsten Dimension.  
  
 `_I2`  
 Die Länge der unwichtigsten Dimension.  
  
 `_Other`  
 Ein `extent`-Objekt, auf dem das neue `extent`-Objekt basiert.  
  
## <a name="remarks"></a>Hinweise  
 Der parameterlose Konstruktor initialisiert ein `extent`-Objekt, das den Rang&3; hat.  
  
 Wenn ein Array verwendet wird, um ein `extent`-Objekt zu erstellen, muss die Länge des Arrays mit dem Rang des `extent`-Objekts übereinstimmen.  
  
##  <a name="a-nameoperatormodeqa-operator"></a><a name="operator_mod_eq"></a>Operator% = 

Berechnet den Modulo (Rest) jedes Elements in der "Block", wenn dieses Element durch eine Zahl dividiert wird.  
  
### <a name="syntax"></a>Syntax  
  
```  
extent<_Rank>& operator%=(int _Rhs) restrict(cpu, direct3d);  
```  
  
### <a name="parameters"></a>Parameter  
 `_Rhs`  
 Die Zahl, die den Modul zu suchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Das `extent`-Objekt.  
  
##  <a name="a-nameoperatorstareqa-operator"></a><a name="operator_star_eq"></a>Operator * = 

Multipliziert jedes Element im Objekt "Block" mit der angegebenen Zahl.  
  
### <a name="syntax"></a>Syntax  
  
```  
extent<_Rank>& operator*=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parameter  
 `_Rhs`  
 Die zu multiplizierende Zahl.  
  
### <a name="return-value"></a>Rückgabewert  
 Das `extent`-Objekt.  
  
## <a name="a-nameoperatoradda-operator"></a><a name="operator_add"></a>Operator + 

Gibt ein neues `extent`-Objekt zurück, das durch Hinzufügen der entsprechenden `index`- und `extent`-Elemente erstellt wird.  
  
### <a name="syntax"></a>Syntax  
  
```  
extent<_Rank> operator+(const index<_Rank>& _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parameter  
 `_Rhs`  
 Das `index`-Objekt, das die hinzuzufügenden Elemente enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Das neue `extent`-Objekt.  
  
##  <a name="a-nameoperatoraddadda-operator"></a><a name="operator_add_add"></a>Operator ++ 

Inkrementiert jedes Element des Objekts "Block".  
  
### <a name="syntax"></a>Syntax  
  
```  
extent<_Rank>& operator++() restrict(amp,cpu);    
extent<_Rank> operator++(int)restrict(amp,cpu);  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Für den Präfixoperator das `extent`-Objekt (`*this`). Für den Suffixoperator ein neues `extent`-Objekt.  
  
##  <a name="a-nameoperatoraddeqa-operator"></a><a name="operator_add_eq"></a>Operator += 

Fügt die angegebene Anzahl auf jedes Element des Objekts "Block".  
  
### <a name="syntax"></a>Syntax  
  
```  
extent<_Rank>& operator+=(const extent<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator+=(const index<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator+=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parameter  
 `_Rhs`  
 Die Zahl, der Index oder der Wertebereich, die bzw. der hinzugefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Das resultierende `extent`-Objekt.  
  
##  <a name="a-nameoperatormina-operator-"></a><a name="operator_min"></a>Operator- 

Erstellt ein neues `extent`-Objekt durch Subtrahieren der einzelnen Elemente im angegebenen `index`-Objekt vom entsprechenden Element in diesem `extent`-Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
extent<_Rank> operator-(const index<_Rank>& _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parameter  
 `_Rhs`  
 Das `index`-Objekt, das die zu subtrahierenden Elemente enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Das neue `extent`-Objekt.  
  
##  <a name="a-nameoperatorminmina-operator--"></a><a name="operator_min_min"></a>Operator-- 

Dekrementiert jedes Element in der "Extent"-Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
extent<_Rank>& operator--() restrict(amp,cpu);    
extent<_Rank> operator--(int)restrict(amp,cpu);  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Für den Präfixoperator das `extent`-Objekt (`*this`). Für den Suffixoperator ein neues `extent`-Objekt.  
  
##  <a name="a-nameoperatordiveqa-operator"></a><a name="operator_div_eq"></a>Operator / = 

Dividiert jedes Element im Objekt "Block" mit der angegebenen Zahl.  
  
### <a name="syntax"></a>Syntax  
  
```  
extent<_Rank>& operator/=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parameter  
 `_Rhs`  
 Die Zahl, durch die dividiert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Das `extent`-Objekt.  
  
##  <a name="a-nameoperatormineqa-operator-"></a><a name="operator_min_eq"></a>Operator = 

Subtrahiert die angegebene Anzahl von jedem Element des Objekts "Block".  
  
### <a name="syntax"></a>Syntax  
  
```  
extent<_Rank>& operator-=(const extent<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator-=(const index<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator-=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parameter  
 `_Rhs`  
 Die zu subtrahierende Zahl.  
  
### <a name="return-value"></a>Rückgabewert  
 Das resultierende `extent`-Objekt.  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>Operator = 

Kopiert den Inhalt eines anderen "Block"-Objekts in dieses Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
extent<_Rank>& operator=(const extent<_Rank>& _Other) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Das `extent`-Objekt, aus dem kopiert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das `extent`-Objekt.  
  
##  <a name="a-nameoperatorata-extentoperator-"></a><a name="operator_at"></a>Extent::\[\] 
Gibt das Element am angegebenen Index zurück.  
  
### <a name="syntax"></a>Syntax  
  
```  
int operator[](unsigned int _Index) const restrict(amp,cpu);    
int& operator[](unsigned int _Index) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parameter  
 `_Index`  
 Eine ganze Zahl von 0 durch den Rang minus 1.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Element am angegebenen Index.  
  
##  <a name="a-namerankconstanta-rank"></a><a name="rank_constant"></a>Rang 

Speichert den Rang des Objekts "Block".  
  
### <a name="syntax"></a>Syntax  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="a-namesizea-size"></a><a name="size"></a>Größe 

Gibt die lineare Gesamtgröße der `extent` Objekt (in Einheiten von Elementen).  
  
### <a name="syntax"></a>Syntax  

```  
unsigned int size() const restrict(amp,cpu);  
```  
  
## <a name="a-nametilea-tile"></a><a name="tile"></a>Kachel 

Erzeugt ein Tiled_extent-Objekt mit den angegebenen kacheldimensionen.

```
template <int _Dim0>
tiled_extent<_Dim0> tile() const ;

template <int _Dim0, int _Dim1>
tiled_extent<_Dim0, _Dim1> tile() const ;

template <int _Dim0, int _Dim1, int _Dim2>
tiled_extent<_Dim0, _Dim1, _Dim2> tile() const ;
```  
### <a name="parameters"></a>Parameter
`_Dim0`Die wichtigste Komponente des unterteilten Wertebereichs.
`_Dim1`Die nächsten-zu-wichtigste Komponente des unterteilten Wertebereichs.
`_Dim2`Die unwichtigste Komponente des unterteilten Wertebereichs.


  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++-AMP)](concurrency-namespace-cpp-amp.md)

