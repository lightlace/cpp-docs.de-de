---
title: CAdapt-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAdapt
- ATLCOMCLI/ATL::CAdapt
- ATLCOMCLI/ATL::CAdapt::CAdapt
- ATLCOMCLI/ATL::CAdapt::m_T
dev_langs:
- C++
helpviewer_keywords:
- address-of operator
- adapter objects
- '& operator, address-of operator'
- CAdapt class
ms.assetid: 0bb695a5-72fe-43d1-8f39-7e4da6e34765
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5bf0739c92513519147e9aed3b88210c4f61d0b4
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882981"
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
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAdapt::CAdapt](#cadapt)|Der Konstruktor.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAdapt::operator const T &](#operator_const_t_amp)|Gibt eine **const** Verweis auf `m_T`.|  
|[CAdapt::operator T &](#operator_t_amp)|Gibt einen Verweis auf `m_T` zurück.|  
|[CAdapt::operator <](#operator_lt)|Vergleicht ein Objekt des angepassten Typs mit `m_T`.|  
|[CAdapt::operator =](#operator_eq)|Weist `m_T` ein Objekt des angepassten Typs zu.|  
|[CAdapt::operator ==](#operator_eq_eq)|Vergleicht ein Objekt des angepassten Typs mit `m_T`.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAdapt::m_T](#m_t)|Die Daten, die angepasst werden.|  
  
## <a name="remarks"></a>Hinweise  
 `CAdapt` ist eine einfache Vorlage. Sie dient dazu, Klassen zu umschließen, die den Adressoperator (`operator &`) so umdefinieren, dass eine andere als die Adresse des Objekts zurückgegeben wird. Zu diesen Klassen gehören die ATL-Klassen `CComBSTR`, `CComPtr` und `CComQIPtr` sowie die Compilerklasse für die COM-Unterstützung `_com_ptr_t`. Diese Klassen sind alle neu definieren, die Address-of-Operator zum Zurückgeben der Adresse eines ihrer Datenmember (BSTR in der `CComBSTR`, und einen Schnittstellenzeiger bei anderen Klassen).  
  
 Die primäre Funktion von `CAdapt` besteht darin, den Adressoperator auszublenden, der durch die Klasse `T` definiert wird, und trotzdem die Eigenschaften der angepassten Klasse beizubehalten. `CAdapt` enthält den öffentlichen Member, erfüllt diese Funktion [M_T](#m_t), des Typs `T`, und definiert Konvertierungsoperatoren, Vergleichsoperatoren und einen Kopierkonstruktor, sodass spezialisierungen von `CAdapt` behandelt werden soll, als wären sie Objekte des Typs `T`.  
  
 Die Adapterklasse `CAdapt` ist nützlich, da einige Containerklassen erwarten, dass sie Adressen der in ihnen enthaltenen Objekte unter Verwendung des Adressoperators abrufen können. Die Neudefinition des Adressoperators kann diese Anforderung vereiteln. Das führt in der Regel zu Kompilierungsfehlern und verhindert, dass der nicht angepasste Typ im Zusammenhang mit Klassen verwendet werden kann, die lediglich erwarten, dass er funktioniert. `CAdapt` stellt eine Methode zur Umgehung solcher Probleme bereit.  
  
 Normalerweise verwenden Sie `CAdapt`, wenn `CComBSTR`-, `CComPtr`-, `CComQIPtr`- oder `_com_ptr_t`-Objekte in einer Containerklasse gespeichert werden sollen. Das war bei C++-Standardbibliothekscontainern vor der Unterstützung des C++11-Standards der Regelfall. C++11- Standardbibliothekscontainer funktionieren allerdings automatisch mit Objekttypen, die überladene `operator&()`-Operatoren aufweisen. Die Standardbibliothek erreicht dies durch die interne Verwendung [std::addressof](../../standard-library/memory-functions.md#addressof) um die tatsächlichen Adressen von Objekten zu erhalten.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** "atlcomcli.h"  
  
##  <a name="cadapt"></a>  CAdapt::CAdapt  
 Die Konstruktoren ermöglichen ein Hostnetzwerkadapter-Objekt als Standard erstellt, von einem Objekt des angepassten Typs kopiert oder aus einem anderen Hostnetzwerkadapter-Objekt kopiert.  
  
```
CAdapt();
CAdapt(const T& rSrc);
CAdapt(const CAdapt& rSrCA);
CAdapt(T&& rSrCA);  // (Visual Studio 2017)
CAdapt(CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Parameter  
 *rSrc*  
 Eine Variable des Typs angepasst werden, um in die neu erstellte Hostnetzwerkadapter-Objekt kopiert werden.  
  
 *rSrCA*  
 Ein Adapterobjekt, dessen enthaltenen Daten kopiert (in der neu erstellte Hostnetzwerkadapter-Objekt oder verschoben werden sollte).  
  
##  <a name="m_t"></a>  CAdapt::m_T  
 Enthält die Daten, die angepasst werden.  
  
```
T m_T;
```  
  
### <a name="remarks"></a>Hinweise  
 Dies **öffentliche** Datenmember möglich direkt oder indirekt mit [Operator const T &](#operator_const_t_amp) und [Operator T &](#operator_t_amp).  
  
##  <a name="operator_const_t_amp"></a>  Const T CAdapt::operator&amp;  
 Gibt eine **const** Verweis auf die [M_T](#m_t) Member, und mit dem Adapterobjekt behandelt werden soll, als handele es sich um ein Objekt des Typs `T`.  
  
```  
operator const T&() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **const** Verweis auf `m_T`.  
  
##  <a name="operator_t_amp"></a>  CAdapt::operator T&amp;  
 Gibt einen Verweis auf die [M_T](#m_t) Member, und mit dem Adapterobjekt behandelt werden soll, als handele es sich um ein Objekt des Typs `T`.  
  
```  
operator T&();
```     
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf `m_T`.  
  
##  <a name="operator_lt"></a>  CAdapt::operator &lt;  
 Vergleicht ein Objekt des angepassten Typs mit [M_T](#m_t).  
  
```
bool operator<(const T& rSrc) const;
```  
  
### <a name="parameters"></a>Parameter  
 *rSrc*  
 Ein Verweis auf das Objekt, das verglichen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Ergebnis des Vergleichs zweier `m_T` und *rSrc*.  
  
##  <a name="operator_eq"></a>  CAdapt::operator =  
 Der Zuweisungsoperator weist das Argument, *rSrc*, für den Datenmember [M_T](#m_t) und gibt den aktuellen Adapterobjekt zurück.  
  
```
CAdapt& operator= (const T& rSrc);
CAdapt& operator= (T&& rSrCA); // (Visual Studio 2017)
CAdapt& operator= (CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Parameter  
 *rSrc*  
 Ein Verweis auf ein Objekt des angepassten Typs kopiert werden soll. 

 *rSrCA* einen Verweis auf ein Objekt, das verschoben werden. 
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das aktuelle Objekt.  
  
##  <a name="operator_eq_eq"></a>  CAdapt::operator ==  
 Vergleicht ein Objekt des angepassten Typs mit [M_T](#m_t).  
  
```
bool operator== (const T& rSrc) const;
```  
  
### <a name="parameters"></a>Parameter  
 *rSrc*  
 Ein Verweis auf das Objekt, das verglichen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Ergebnis des Vergleichs zweier `m_T` und *rSrc*.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
