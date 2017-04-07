---
title: Klasse CFileTimeSpan | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::GetTimeSpan
- ATLTIME/ATL::CFileTimeSpan::SetTimeSpan
dev_langs:
- C++
helpviewer_keywords:
- shared classes, CFileTimeSpan
- CFileTimeSpan class
ms.assetid: 5856fb39-9c82-4027-8ccf-8760890491ec
caps.latest.revision: 18
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 8a25bab65d9e5705a71eddde901e747c43a5a002
ms.lasthandoff: 02/24/2017

---
# <a name="cfiletimespan-class"></a>CFileTimeSpan-Klasse
Diese Klasse stellt Methoden zum Verwalten von relativen Datums- und Uhrzeitwerte einer Datei zugeordnet.  
  
## <a name="syntax"></a>Syntax  
  
```
class CFileTimeSpan
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileTimeSpan::CFileTimeSpan](#cfiletimespan)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileTimeSpan::GetTimeSpan](#gettimespan)|Rufen Sie diese Methode zum Abrufen der Zeitspanne aus der `CFileTimeSpan` Objekt.|  
|[CFileTimeSpan::SetTimeSpan](#settimespan)|Rufen Sie diese Methode, um die Zeitspanne der Festlegen der `CFileTimeSpan` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileTimeSpan::operator-](#operator_-)|Führt Subtraktionen aus auf ein `CFileTimeSpan` Objekt.|  
|[CFileTimeSpan::operator! =](#operator_neq)|Überprüft zwei `CFileTimeSpan`-Objekte auf Ungleichheit.|  
|[CFileTimeSpan::operator +](#operator_add)|Außerdem führt ein `CFileTimeSpan` Objekt.|  
|[CFileTimeSpan::operator +=](#operator_add_eq)|Außerdem führt ein `CFileTimeSpan` Objekt, und weisen Sie das Ergebnis mit dem aktuellen Objekt.|  
|[CFileTimeSpan::operator&lt;](#operator_lt)|Vergleicht zwei `CFileTimeSpan` Objekte kleiner bestimmen.|  
|[CFileTimeSpan::operator&lt;=](#operator_lt_eq)|Vergleicht zwei `CFileTimeSpan` -Objekten auf Gleichheit oder kleiner festgelegt.|  
|[CFileTimeSpan::operator =](#operator_eq)|Der Zuweisungsoperator.|  
|[CFileTimeSpan::operator =](#operator_-_eq)|Führt Subtraktionen aus auf ein `CFileTimeSpan` -Objekt und das Ergebnis mit dem aktuellen Objekt zuweisen.|  
|[CFileTimeSpan::operator ==](#operator_eq_eq)|Überprüft zwei `CFileTimeSpan`-Objekte auf Gleichheit.|  
|[CFileTimeSpan::operator&gt;](#operator_gt)|Vergleicht zwei `CFileTimeSpan` -Objekten, die größere zu bestimmen.|  
|[CFileTimeSpan::operator&gt;=](#operator_gt_eq)|Vergleicht zwei `CFileTimeSpan` Objekte auf Gleichheit oder größer fest.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt Methoden für die Verwaltung von relativen Zeiträume Zeit häufig auftreten, wenn das Ausführen von Vorgängen, die bei der Anwendung eine Datei erstellt, des letzten Zugriffs auf oder zuletzt geändert wurde. Die Methoden dieser Klasse werden häufig in Verbindung mit verwendet [CFileTime Klasse](../../atl-mfc-shared/reference/cfiletime-class.md) Objekte.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CFileTime::Millisecond](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atltime.h  
  
##  <a name="cfiletimespan"></a>CFileTimeSpan::CFileTimeSpan  
 Der Konstruktor.  
  
```
CFileTimeSpan() throw();
CFileTimeSpan(const CFileTimeSpan& span) throw();
CFileTimeSpan(LONGLONG nSpan) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Ein vorhandenes `CFileTimeSpan`-Objekt.  
  
 `nSpan`  
 Eine Zeitspanne in Millisekunden.  
  
### <a name="remarks"></a>Hinweise  
 Die `CFileTimeSpan` Objekt kann erstellt werden, mit einer vorhandenen `CFileTimeSpan` -Objekt oder als 64-Bit-Wert. Der Standardkonstruktor legt die Zeitspanne auf 0 fest.  
  
##  <a name="gettimespan"></a>CFileTimeSpan::GetTimeSpan  
 Rufen Sie diese Methode zum Abrufen der Zeitspanne aus der `CFileTimeSpan` Objekt.  
  
```
LONGLONG GetTimeSpan() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Zeitspanne in Millisekunden an.  
  
##  <a name="operator_-"></a>CFileTimeSpan::operator-  
 Führt Subtraktionen aus auf eine **CFileTimeSpan** Objekt.  
  
```
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Ein `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein `CFileTimeSpan` Objekt, das das Ergebnis des Unterschieds zwischen zwei Zeitspannen darstellt.  
  
##  <a name="operator_neq"></a>CFileTimeSpan::operator! =  
 Überprüft zwei `CFileTimeSpan`-Objekte auf Ungleichheit.  
  
```
bool operator!=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Das zu vergleichende `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** ist das Element wird im Vergleich nicht gleich der `CFileTimeSpan` Objekt; andernfalls **false**.  
  
##  <a name="operator_add"></a>CFileTimeSpan::operator +  
 Außerdem führt ein `CFileTimeSpan` Objekt.  
  
```
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Ein `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein `CFileTimeSpan` -Objekt umfasst, enthält die Summe der zwei Mal.  
  
##  <a name="operator_add_eq"></a>CFileTimeSpan::operator +=  
 Außerdem führt ein `CFileTimeSpan` -Objekt und das Ergebnis mit dem aktuellen Objekt zugewiesen.  
  
```
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Ein `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den aktualisierten `CFileTimeSpan` -Objekt umfasst, enthält die Summe der zwei Mal.  
  
##  <a name="operator_lt"></a>CFileTimeSpan::operator&lt;  
 Vergleicht zwei `CFileTimeSpan` Objekte kleiner bestimmen.  
  
```
bool operator<(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Das zu vergleichende `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** Wenn das erste Objekt kleiner ist (d. h. einen kürzeren Zeitraum darstellt) als die zweite andernfalls **false**.  
  
##  <a name="operator_lt_eq"></a>CFileTimeSpan::operator&lt;=  
 Vergleicht zwei `CFileTimeSpan` -Objekten auf Gleichheit oder kleiner festgelegt.  
  
```
bool operator<=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Das zu vergleichende `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** ist das erste Objekt kleiner als (d. h. einen kürzeren Zeitraum darstellt) oder gleich dem zweiten andernfalls **false**.  
  
##  <a name="operator_eq"></a>CFileTimeSpan::operator =  
 Der Zuweisungsoperator.  
  
```
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Ein `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den aktualisierten `CFileTimeSpan` Objekt.  
  
##  <a name="operator_-_eq"></a>CFileTimeSpan::operator =  
 Führt Subtraktionen aus auf ein `CFileTimeSpan` -Objekt und das Ergebnis mit dem aktuellen Objekt zugewiesen.  
  
```
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Ein `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den aktualisierten `CFileTimeSpan` Objekt.  
  
##  <a name="operator_eq_eq"></a>CFileTimeSpan::operator ==  
 Überprüft zwei `CFileTimeSpan`-Objekte auf Gleichheit.  
  
```
bool operator==(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Das zu vergleichende `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** , wenn die Objekte gleich, andernfalls sind **false**.  
  
##  <a name="operator_gt"></a>CFileTimeSpan::operator&gt;  
 Vergleicht zwei `CFileTimeSpan` -Objekten, die größere zu bestimmen.  
  
```
bool operator>(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Das zu vergleichende `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** ist das erste Objekt größer als (d. h. mehr Zeit steht) als die zweite andernfalls **false**.  
  
##  <a name="operator_gt_eq"></a>CFileTimeSpan::operator&gt;=  
 Vergleicht zwei `CFileTimeSpan` Objekte auf Gleichheit oder größer fest.  
  
```
bool operator>=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Das zu vergleichende `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** ist das erste Objekt größer als (d. h. einen längeren Zeitraum darstellt) oder gleich dem zweiten andernfalls **false**.  
  
##  <a name="settimespan"></a>CFileTimeSpan::SetTimeSpan  
 Rufen Sie diese Methode, um die Zeitspanne der Festlegen der `CFileTimeSpan` Objekt.  
  
```
void SetTimeSpan(LONGLONG nSpan) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nSpan`  
 Der neue Wert für die Zeitspanne in Millisekunden.  
  
## <a name="see-also"></a>Siehe auch  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [CFileTime-Klasse](../../atl-mfc-shared/reference/cfiletime-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL/MFC-freigegeben Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)



