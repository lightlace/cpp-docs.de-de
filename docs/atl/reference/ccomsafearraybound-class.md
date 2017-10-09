---
title: CComSafeArrayBound Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSafeArrayBound
- ATLSAFE/ATL::CComSafeArrayBound
- ATLSAFE/ATL::CComSafeArrayBound
- ATLSAFE/ATL::GetCount
- ATLSAFE/ATL::GetLowerBound
- ATLSAFE/ATL::GetUpperBound
- ATLSAFE/ATL::SetCount
- ATLSAFE/ATL::SetLowerBound
dev_langs:
- C++
helpviewer_keywords:
- CComSafeArrayBound class
ms.assetid: dd6299db-5f84-4630-bbf0-f5add5318437
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: 01198e8de5f2eb1cbe0787bd287820d222875c20
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="ccomsafearraybound-class"></a>CComSafeArrayBound-Klasse
Diese Klasse ist ein Wrapper für eine [SAFEARRAYBOUND](http://msdn.microsoft.com/en-us/303a9bdb-71d6-4f14-8747-84cf84936c6d) Struktur.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComSafeArrayBound : public SAFEARRAYBOUND
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CComSafeArrayBound](#ccomsafearraybound)|Der Konstruktor.|  
|[GetCount](#getcount)|Rufen Sie diese Methode, um die Anzahl von Elementen zurück.|  
|[GetLowerBound](#getlowerbound)|Rufen Sie diese Methode, um die untere Grenze zurück.|  
|[GetUpperBound](#getupperbound)|Rufen Sie diese Methode, um die obere Grenze zurück.|  
|[SetCount](#setcount)|Rufen Sie diese Methode, um die Anzahl von Elementen festzulegen.|  
|[SetLowerBound](#setlowerbound)|Rufen Sie diese Methode, um die untere Grenze festgelegt.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator =](#operator_eq)|Legt die `CComSafeArrayBound` auf einen neuen Wert.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse ist ein Wrapper für die **SAFEARRAYBOUND** Struktur verwendeten [CComSafeArray](../../atl/reference/ccomsafearray-class.md). Es bietet Methoden zum Abfragen und Festlegen der oberen und unteren Grenzen einer einzelnen Dimension von einem `CComSafeArray` -Objekt und die Anzahl der enthaltenen Elemente. Ein mehrdimensionales `CComSafeArray` Objekt verwendet, ein Array von `CComSafeArrayBound` Objekten, eines für jede Dimension. Aus diesem Grund bei Methoden wie [GetCount](#getcount), beachten Sie, dass diese Methode die Gesamtzahl der Elemente in einem mehrdimensionalen Array nicht zurückgeben.  
  
 **Header:** atlsafe.h  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsafe.h  
  
##  <a name="ccomsafearraybound"></a>CComSafeArrayBound::CComSafeArrayBound  
 Der Konstruktor.  
  
```
CComSafeArrayBound(ULONG ulCount = 0, LONG lLowerBound = 0) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ulCount`  
 Die Anzahl der Elemente im Array.  
  
 `lLowerBound`  
 Die untere Grenze aus dem Array nummeriert wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Array ist ein Visual C++-Programm zugreifen können, empfiehlt es sich, dass die untere Grenze als 0 definiert werden. Möglicherweise bevorzugen, andere Untergrenze Wert zu verwenden, wenn das Array mit anderen Sprachen wie Visual Basic verwendet werden.  
  
##  <a name="getcount"></a>CComSafeArrayBound::GetCount  
 Rufen Sie diese Methode, um die Anzahl von Elementen zurück.  
  
```
ULONG GetCount() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Elemente zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die zugeordnete `CComSafeArray` -Objekt stellt ein mehrdimensionales Array dar, diese Methode gibt nur die Gesamtanzahl der Elemente in der äußersten rechten Dimension zurück. Verwendung [CComSafeArray::GetCount](../../atl/reference/ccomsafearray-class.md#getcount) zum Abrufen der Gesamtanzahl der Elemente.  
  
##  <a name="getlowerbound"></a>CComSafeArrayBound::GetLowerBound  
 Rufen Sie diese Methode, um die untere Grenze zurück.  
  
```
LONG GetLowerBound() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die untere Grenze der `CComSafeArrayBound` Objekt.  
  
##  <a name="getupperbound"></a>CComSafeArrayBound::GetUpperBound  
 Rufen Sie diese Methode, um die obere Grenze zurück.  
  
```
LONG GetUpperBound() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die obere Grenze der `CComSafeArrayBound` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die obere Grenze hängt von der Anzahl von Elementen und den unteren Grenzwert. Beispielsweise wird, wenn die untere Grenze 0 ist, und die Anzahl der Elemente 10 ist, die obere Grenze automatisch auf 9 festgelegt werden.  
  
##  <a name="operator_eq"></a>CComSafeArrayBound::operator =  
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
 Die `CComSafeArrayBound` Objekt kann zugewiesen werden, mithilfe eines vorhandenen `CComSafeArrayBound`, oder indem Sie die Anzahl der Elemente, in dem Fall die untere Grenze standardmäßig auf 0 festgelegt.  
  
##  <a name="setcount"></a>CComSafeArrayBound::SetCount  
 Rufen Sie diese Methode, um die Anzahl von Elementen festzulegen.  
  
```
ULONG SetCount(ULONG ulCount) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ulCount`  
 Die Anzahl der Elemente.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Elemente in der `CComSafeArrayBound` Objekt.  
  
##  <a name="setlowerbound"></a>CComSafeArrayBound::SetLowerBound  
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
 Wenn das Array ist ein Visual C++-Programm zugreifen können, empfiehlt es sich, dass die untere Grenze als 0 definiert werden. Möglicherweise bevorzugen, andere Untergrenze Wert zu verwenden, wenn das Array mit anderen Sprachen wie Visual Basic verwendet werden.  
  
 Die obere Grenze hängt von der Anzahl von Elementen und den unteren Grenzwert. Beispielsweise wird, wenn die untere Grenze 0 ist, und die Anzahl der Elemente 10 ist, die obere Grenze automatisch auf 9 festgelegt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)

