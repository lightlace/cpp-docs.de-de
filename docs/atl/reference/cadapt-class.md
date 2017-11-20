---
title: CAdapt Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAdapt
- ATLCOMCLI/ATL::CAdapt
- ATLCOMCLI/ATL::CAdapt::CAdapt
- ATLCOMCLI/ATL::CAdapt::m_T
dev_langs: C++
helpviewer_keywords:
- address-of operator
- adapter objects
- '& operator, address-of operator'
- CAdapt class
ms.assetid: 0bb695a5-72fe-43d1-8f39-7e4da6e34765
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 37ce02b9493c47a2c93d9e54e14f73b5c980317d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cadapt-class"></a>CAdapt-Klasse
Diese Vorlage dient dazu, Klassen zu umschließen, die den Adressoperator so umdefinieren, dass eine andere als die Adresse des Objekts zurückgegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
class CAdapt
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der angepasste Typ.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAdapt::CAdapt](#cadapt)|Der Konstruktor.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Const T CAdapt::operator &](#operator_const_t_amp)|Gibt einen `const`-Verweis auf `m_T` zurück.|  
|[CAdapt::operator T &](#operator_t_amp)|Gibt einen Verweis auf `m_T` zurück.|  
|[CAdapt::operator <](#operator_lt)|Vergleicht ein Objekt des angepassten Typs mit `m_T`.|  
|[CAdapt::operator =](#operator_eq)|Weist `m_T` ein Objekt des angepassten Typs zu.|  
|[CAdapt::operator ==](#operator_eq_eq)|Vergleicht ein Objekt des angepassten Typs mit `m_T`.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAdapt::m_T](#m_t)|Die Daten, die angepasst werden.|  
  
## <a name="remarks"></a>Hinweise  
 `CAdapt`ist eine einfache Vorlage verwendet, um Klassen zu umschließen, die den Adressoperator neu definieren ( `operator &`) auf eine andere als die Adresse des Objekts zurückgegeben. Zu diesen Klassen gehören die ATL-Klassen `CComBSTR`, `CComPtr` und `CComQIPtr` sowie die Compilerklasse für die COM-Unterstützung `_com_ptr_t`. Alle diese Klassen definieren den Adressoperator neu, sodass er die Adresse eines ihrer Datenmember (`BSTR` bei `CComBSTR` und den Schnittstellenzeiger bei anderen Klassen) zurückgibt.  
  
 Die primäre Funktion von `CAdapt` besteht darin, den Adressoperator auszublenden, der durch die Klasse `T` definiert wird, und trotzdem die Eigenschaften der angepassten Klasse beizubehalten. `CAdapt`enthält den öffentlichen Member, erfüllt diese Funktion [M_T](#m_t), des Typs `T`, und definiert Konvertierungsoperatoren, Vergleichsoperatoren und einen Kopierkonstruktor, sodass spezialisierungen von `CAdapt` behandelt werden, als wären sie Objekte des Typs `T`.  
  
 Die Adapterklasse `CAdapt` ist nützlich, da einige Containerklassen erwarten, dass sie Adressen der in ihnen enthaltenen Objekte unter Verwendung des Adressoperators abrufen können. Die Neudefinition des Adressoperators kann diese Anforderung vereiteln. Das führt in der Regel zu Kompilierungsfehlern und verhindert, dass der nicht angepasste Typ im Zusammenhang mit Klassen verwendet werden kann, die lediglich erwarten, dass er funktioniert. `CAdapt` stellt eine Methode zur Umgehung solcher Probleme bereit.  
  
 Normalerweise verwenden Sie `CAdapt`, wenn `CComBSTR`-, `CComPtr`-, `CComQIPtr`- oder `_com_ptr_t`-Objekte in einer Containerklasse gespeichert werden sollen. Das war bei C++-Standardbibliothekscontainern vor der Unterstützung des C++11-Standards der Regelfall. C++11- Standardbibliothekscontainer funktionieren allerdings automatisch mit Objekttypen, die überladene `operator&()`-Operatoren aufweisen. Die Standardbibliothek erreicht dies durch die interne Verwendung [std::addressof](../../standard-library/memory-functions.md#addressof) die tatsächlichen Adressen von Objekten abgerufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** "atlcomcli.h"  
  
##  <a name="cadapt"></a>CAdapt::CAdapt  
 Die Konstruktoren ermöglichen eine Adapterobjekt an Standardeinstellung erstellt, von einem Objekt des angepassten Typs kopiert oder aus einem anderen Adapterobjekt kopiert werden.  
  
```
CAdapt();
CAdapt(const T& rSrc);
CAdapt(const CAdapt& rSrCA);
CAdapt(T&& rSrCA);  // (Visual Studio 2017)
CAdapt(CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Parameter  
 `rSrc`  
 Eine Variable des Typs angepasst werden, um in das neu erstellte Adapterobjekt kopiert werden soll.  
  
 *rSrCA*  
 Ein Adapterobjekt, dessen enthaltenen Daten kopiert (in der neu erstellten Adapterobjekt oder verschoben werden soll).  
  
##  <a name="m_t"></a>CAdapt::m_T  
 Enthält die Daten, die angepasst werden.  
  
```
T m_T;
```  
  
### <a name="remarks"></a>Hinweise  
 Dies **öffentlichen** -Datenmember kann zugegriffen werden direkt oder indirekt mit [Operator const T &](#operator_const_t_amp) und [Operator T &](#operator_t_amp).  
  
##  <a name="operator_const_t_amp"></a>Const T CAdapt::operator&amp;  
 Gibt eine **const** einen Verweis auf die [M_T](#m_t) Member auf, sodass das Adapterobjekt behandelt werden, als handele es sich um ein Objekt vom Typ `T`.  
  
```  
operator const T&() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **const** einen Verweis auf `m_T`.  
  
##  <a name="operator_t_amp"></a>CAdapt::operator T&amp;  
 Gibt einen Verweis auf die [M_T](#m_t) Member auf, sodass das Adapterobjekt behandelt werden, als handele es sich um ein Objekt vom Typ `T`.  
  
```  
operator T&();
```     
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf `m_T`.  
  
##  <a name="operator_lt"></a>CAdapt::operator&lt;  
 Vergleicht ein Objekt des angepassten Typs mit [M_T](#m_t).  
  
```
bool operator<(const T& rSrc) const;
```  
  
### <a name="parameters"></a>Parameter  
 `rSrc`  
 Ein Verweis auf das Objekt, das verglichen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Ergebnis des Vergleichs zwischen `m_T` und `rSrc`.  
  
##  <a name="operator_eq"></a>CAdapt::operator =  
 Der Zuweisungsoperator weist das Argument `rSrc`, an den Datenmember [M_T](#m_t) und gibt das aktuelle Adapterobjekt.  
  
```
CAdapt& operator= (const T& rSrc);
CAdapt& operator= (T&& rSrCA); // (Visual Studio 2017)
CAdapt& operator= (CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Parameter  
 `rSrc`  
 Ein Verweis auf ein Objekt des angepassten Typs kopiert werden soll. 

 `rSrCA`Ein Verweis auf ein Objekt, das verschoben werden. 
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das aktuelle Objekt.  
  
##  <a name="operator_eq_eq"></a>CAdapt::operator ==  
 Vergleicht ein Objekt des angepassten Typs mit [M_T](#m_t).  
  
```
bool operator== (const T& rSrc) const;
```  
  
### <a name="parameters"></a>Parameter  
 `rSrc`  
 Ein Verweis auf das Objekt, das verglichen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Ergebnis des Vergleichs zwischen `m_T` und `rSrc`.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
