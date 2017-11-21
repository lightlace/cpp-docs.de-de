---
title: Index-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AMP/index
- AMP/Concurrency::index::index
- AMP/Concurrency::index::rank
dev_langs: C++
helpviewer_keywords: index structure
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8a1c4213ee94c063a7dff2a5b2c5e156b0ee91a7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="index-class"></a>index-Klasse
Definiert eine *N*-dimensionalen Index Pographics-Cpp-amp.md.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <int _Rank>  
class index;  
```  
  
#### <a name="parameters"></a>Parameter  
 `_Rank`  
 Der Rang oder die Anzahl von Dimensionen.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Index-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `index`-Klasse.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[operator--](#operator--)|Dekrementiert jedes Element des `index`-Objekts.|  
|[Operator(MOD) =](#operator_mod_eq)|Berechnet den Modul (Rest) jedes Elements im `index`-Objekt, wenn dieses Element durch eine Zahl dividiert wird.|  
|[operator*=](#operator_star_eq)|Multipliziert jedes Element des `index`-Objekts mit einer Zahl.|  
|[operator/=](#operator_div_eq)|Dividiert jedes Element des `index`-Objekts durch eine Zahl.|  
|[Index::\[\]](#operator_at)|Gibt das Element am angegebenen Index zurück.|  
|[operator++](#operator_add_add)|Inkrementiert jedes Element des `index`-Objekts.|  
|[operator+=](#operator_add_eq)|Fügt die angegebene Zahl jedem Element des `index`-Objekts hinzu.|  
|[operator=](#operator_eq)|Kopiert den Inhalt des angegebenen `index`-Objekts in dieses Objekt.|  
|[operator-=](#operator_-_eq)|Subtrahiert die angegebene Anzahl von jedem Element des `index`-Objekts.|  

  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Rank-Konstante](#rank)|Speichert den Rang des `index`-Objekts.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `index`  
  
## <a name="remarks"></a>Hinweise  
 Die `index` Struktur stellt einen-Koordinate Vektor eines *N* ganze Zahlen, der angibt, in eine eindeutige Position ein *N*-dimensionalen Raum. Die Werte im Vektor sind vom wichtigsten zum am wenigsten wichtigen Wert sortiert. Sie können die Werte der Komponenten mit abrufen [Operator =](#operator_eq).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amp.h  
  
 **Namespace:** Parallelität  


## <a name="index_ctor"></a>Index-Konstruktor
Initialisiert eine neue Instanz der indexklasse an.

```  
index() restrict(amp,cpu);

index(
   const index<_Rank>& _Other
) restrict(amp,cpu);

explicit index(
   int _I
) restrict(amp,cpu);

index(
   int _I0,
   int _I1
) restrict(amp,cpu);

index(
   int _I0,
   int _I1,
   int _I2
) restrict(amp,cpu);

explicit index(
   const int _Array[_Rank]
) restrict(amp,cpu);
``` 

### <a name="parameters"></a>Parameter

_Array  
Ein eindimensionales Array mit den Rangwerten.  
_ICH  
Die Indexposition in einem eindimensionalen Index.  
_I0  
Die Länge der wichtigsten Dimension.  
_I1  
Die Länge der zweitwichtigsten Dimension.  
_I2  
Die Länge der unwichtigsten Dimension.  
_Other  
Ein Indexobjekt, das auf dem das neue Indexobjekt basiert.  

## <a name="operator--"></a>Operator--
Dekrementiert jedes Element des Index-Objekts.  
```  
index<_Rank>& operator--() restrict(amp,cpu);  

index operator--(
   int
) restrict(amp,cpu);
```  
### <a name="return-values"></a>Rückgabewert
Für den Präfixoperator das Indexobjekt (* dies). Für den suffixoperator ein neues Indexobjekt.

## <a name="operator_mod_eq"></a>Operator(MOD) =   
Berechnet den Modul (Rest) jedes Elements im Index-Objekt, wenn dieses Element mit der angegebenen Zahl dividiert wird.

```  
index<_Rank>& operator%=(
   int _Rhs
) restrict(cpu, amp);
```  
### <a name="parameters"></a>Parameter
_Rhs die Zahl, dividiert durch den Modulo finden.
Der Rückgabewert die Index-Objekt.

## <a name="operator_star_eq"></a>Operator * =   
Multipliziert jedes Element in das Indexobjekt, um die angegebene Anzahl an.
```
index<_Rank>& operator*=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parameter
_Rhs die zu multiplizierende Zahl.

## <a name="operator_div_eq"></a>Operator / = 
Dividiert jedes Element in die Index-Objekt mit der angegebenen Zahl.

```
index<_Rank>& operator/=(
   int _Rhs
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>Parameter
_Rhs die Zahl, durch die dividiert.

## <a name="operator_at"></a> operator\[\]  
Gibt die Komponente des Index an der angegebenen Position zurück.

```
int operator[] (
   unsigned _Index
) const restrict(amp,cpu);

int& operator[] (
   unsigned _Index
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parameter
_Index eine ganze Zahl zwischen 0 und den Rang minus 1.

### <a name="return-value"></a>Rückgabewert
Das Element am angegebenen Index.

### <a name="remarks"></a>Hinweise
Im folgenden Beispiel werden die Komponentenwerte des Index angezeigt.
```  
// Prints 1 2 3.
concurrency::index<3> idx(1, 2, 3);
std::cout << idx[0] << "\n";
std::cout << idx[1] << "\n";
std::cout << idx[2] << "\n";
```

## <a name="operator_add_add"></a>Operator ++   
Inkrementiert jedes Element des Index-Objekts.
```  
index<_Rank>& operator++() restrict(amp,cpu);

index<_Rank> operator++(
   int
) restrict(amp,cpu);
```  
### <a name="return-value"></a>Rückgabewert
Für den Präfixoperator das Indexobjekt (* dies). Für den suffixoperator ein neues Indexobjekt.

## <a name="operator_add_eq"></a>Operator +=   
Fügt die angegebene Anzahl auf jedes Element des Index-Objekts.
```  
index<_Rank>& operator+=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator+=(
   int _Rhs
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>Parameter
_Rhs die zu addierende Zahl.

### <a name="return-value"></a>Rückgabewert
Die Indexobjekt.

## <a name="operator_eq"></a> operator=   
Kopiert den Inhalt des Objekts angegebenen Index in dieses Objekt.
```  
index<_Rank>& operator=(
   const index<_Rank>& _Other
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>Parameter
_Other die Indexobjekt, das kopiert.

### <a name="return-value"></a>Rückgabewert
Ein Verweis auf dieses Indexobjekt.

## <a name="operator_-_eq"></a>Operator =
Subtrahiert die angegebene Anzahl von jedem Element des Index-Objekt.
```  
index<_Rank>& operator-=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator-=(
   int _Rhs
) restrict(amp,cpu);
```  
### <a name="parameters"></a>Parameter
_Rhs die zu subtrahierende Zahl.

### <a name="return-value"></a>Rückgabewert
Die Indexobjekt.   

## <a name="rank"></a>Rang  
  Ruft den Rang des Index-Objekts ab.
```
static const int rank = _Rank;
``` 
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
