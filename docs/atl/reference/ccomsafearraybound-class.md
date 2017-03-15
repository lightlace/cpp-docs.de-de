---
title: Klasse CComSafeArrayBound | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComSafeArrayBound
- ATL::CComSafeArrayBound
- CComSafeArrayBound
dev_langs:
- C++
helpviewer_keywords:
- CComSafeArrayBound class
ms.assetid: dd6299db-5f84-4630-bbf0-f5add5318437
caps.latest.revision: 21
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 1cc2adef85c902b7ad12b152b35a7ef68e6abacb
ms.lasthandoff: 02/24/2017

---
# <a name="ccomsafearraybound-class"></a>CComSafeArrayBound-Klasse
Diese Klasse ist ein Wrapper für ein [SAFEARRAYBOUND](http://msdn.microsoft.com/en-us/303a9bdb-71d6-4f14-8747-84cf84936c6d) Struktur.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComSafeArrayBound : public SAFEARRAYBOUND
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CComSafeArrayBound](#ccomsafearraybound)|Der Konstruktor.|  
|[GetCount](#getcount)|Rufen Sie diese Methode, um die Anzahl der Elemente zurück.|  
|[GetLowerBound](#getlowerbound)|Rufen Sie diese Methode, um die untere Grenze zurück.|  
|[GetUpperBound](#getupperbound)|Rufen Sie diese Methode, um die obere Grenze zurück.|  
|[SetCount](#setcount)|Rufen Sie diese Methode, um die Anzahl der Elemente festzulegen.|  
|[SetLowerBound](#setlowerbound)|Rufen Sie diese Methode, um die untere Grenze festgelegt.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator =](#operator_eq)|Legt die `CComSafeArrayBound` auf einen neuen Wert.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse ist ein Wrapper für die **SAFEARRAYBOUND** von verwendete Struktur [CComSafeArray](../../atl/reference/ccomsafearray-class.md). Es bietet Methoden zum Abfragen und Festlegen der oberen und unteren Grenzen einer einzelnen Dimension ein `CComSafeArray` -Objekt und die Anzahl der enthaltenen Elemente. Ein mehrdimensionales `CComSafeArray` Objekt verwendet ein Array von `CComSafeArrayBound` Objekten, eines für jede Dimension. Daher bei Verwendung von Methoden wie z. B. [GetCount](#getcount), beachten Sie, dass diese Methode nicht die Gesamtzahl der Elemente in einem mehrdimensionalen Array zurückgibt.  
  
 **Header:** atlsafe.h  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsafe.h  
  
##  <a name="a-nameccomsafearraybounda--ccomsafearrayboundccomsafearraybound"></a><a name="ccomsafearraybound"></a>CComSafeArrayBound::CComSafeArrayBound  
 Der Konstruktor.  
  
```
CComSafeArrayBound(ULONG ulCount = 0, LONG lLowerBound = 0) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ulCount`  
 Die Anzahl der Elemente im Array.  
  
 `lLowerBound`  
 Die untere Grenze aus dem Array nummeriert sind.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Array ist ein Visual C++-Programm zugreifen können, empfiehlt es sich, dass die untere Grenze als 0 definiert werden. Es ist möglicherweise wünschenswert, einen andere Untergrenze-Wert verwenden, wenn das Array mit anderen Sprachen wie Visual Basic verwendet werden.  
  
##  <a name="a-namegetcounta--ccomsafearrayboundgetcount"></a><a name="getcount"></a>CComSafeArrayBound::GetCount  
 Rufen Sie diese Methode, um die Anzahl der Elemente zurück.  
  
```
ULONG GetCount() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Elemente zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die zugeordnete `CComSafeArray` Objekt ein mehrdimensionales Array darstellt, die diese Methode gibt nur die Gesamtanzahl der Elemente in der Dimension ganz rechts zurück. Verwendung [CComSafeArray::GetCount](../../atl/reference/ccomsafearray-class.md#getcount) um die Gesamtzahl der Elemente abzurufen.  
  
##  <a name="a-namegetlowerbounda--ccomsafearrayboundgetlowerbound"></a><a name="getlowerbound"></a>CComSafeArrayBound::GetLowerBound  
 Rufen Sie diese Methode, um die untere Grenze zurück.  
  
```
LONG GetLowerBound() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die untere Grenze der `CComSafeArrayBound` Objekt.  
  
##  <a name="a-namegetupperbounda--ccomsafearrayboundgetupperbound"></a><a name="getupperbound"></a>CComSafeArrayBound::GetUpperBound  
 Rufen Sie diese Methode, um die obere Grenze zurück.  
  
```
LONG GetUpperBound() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Obergrenze für die `CComSafeArrayBound` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die obere Grenze hängt von der Anzahl von Elementen und den unteren Grenzwert. Beispielsweise wird der untere Grenzwert ist 0, und die Anzahl der Elemente ist 10, die obere Grenze automatisch auf 9 festgelegt werden.  
  
##  <a name="a-nameoperatoreqa--ccomsafearrayboundoperator-"></a><a name="operator_eq"></a>CComSafeArrayBound::operator =  
 Legt die `CComSafeArrayBound` auf einen neuen Wert.  
  
```
CComSafeArrayBound& operator= (const CComSafeArrayBound& bound) throw();
CComSafeArrayBound& operator= (ULONG ulCount) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `bound`  
 Ein `CComSafeArrayBound`-Objekt.  
  
 `ulCount`  
 Die Anzahl der Elemente.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die `CComSafeArrayBound` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die `CComSafeArrayBound` Objekt kann unter Verwendung einer vorhandenen zugewiesen `CComSafeArrayBound`, oder indem Sie die Anzahl der Elemente, die in dem Fall die untere Grenze standardmäßig auf 0 festgelegt.  
  
##  <a name="a-namesetcounta--ccomsafearrayboundsetcount"></a><a name="setcount"></a>CComSafeArrayBound::SetCount  
 Rufen Sie diese Methode, um die Anzahl der Elemente festzulegen.  
  
```
ULONG SetCount(ULONG ulCount) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ulCount`  
 Die Anzahl der Elemente.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Elemente in der `CComSafeArrayBound` Objekt.  
  
##  <a name="a-namesetlowerbounda--ccomsafearrayboundsetlowerbound"></a><a name="setlowerbound"></a>CComSafeArrayBound::SetLowerBound  
 Rufen Sie diese Methode, um die untere Grenze festgelegt.  
  
```
LONG SetLowerBound(LONG lLowerBound) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lLowerBound`  
 Die untere Grenze.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die neue untere Grenze der `CComSafeArrayBound` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Array ist ein Visual C++-Programm zugreifen können, empfiehlt es sich, dass die untere Grenze als 0 definiert werden. Es ist möglicherweise wünschenswert, einen andere Untergrenze-Wert verwenden, wenn das Array mit anderen Sprachen wie Visual Basic verwendet werden.  
  
 Die obere Grenze hängt von der Anzahl von Elementen und den unteren Grenzwert. Beispielsweise wird der untere Grenzwert ist 0, und die Anzahl der Elemente ist 10, die obere Grenze automatisch auf 9 festgelegt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

