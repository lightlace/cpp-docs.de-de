---
title: CFileTimeSpan Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: facf4abc01ed55ec7c6d84755530a776c68e166d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="cfiletimespan-class"></a>CFileTimeSpan-Klasse
Diese Klasse stellt Methoden zum Verwalten von relativen Datums- und Uhrzeitwerten, die einer Datei zugeordnet.  
  
## <a name="syntax"></a>Syntax  
  
```
class CFileTimeSpan
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileTimeSpan::CFileTimeSpan](#cfiletimespan)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileTimeSpan::GetTimeSpan](#gettimespan)|Rufen Sie diese Methode zum Abrufen der Zeitspanne aus der `CFileTimeSpan` Objekt.|  
|[CFileTimeSpan::SetTimeSpan](#settimespan)|Rufen Sie diese Methode zum Festlegen der Zeitspanne der `CFileTimeSpan` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileTimeSpan::operator-](#operator_-)|Führt Subtraktion für ein `CFileTimeSpan` Objekt.|  
|[CFileTimeSpan::operator! =](#operator_neq)|Überprüft zwei `CFileTimeSpan`-Objekte auf Ungleichheit.|  
|[CFileTimeSpan::operator +](#operator_add)|Außerdem führt ein `CFileTimeSpan` Objekt.|  
|[CFileTimeSpan::operator +=](#operator_add_eq)|Außerdem führt ein `CFileTimeSpan` -Objekt und das Ergebnis mit dem aktuellen Objekt zuzuweisen.|  
|[CFileTimeSpan::operator &lt;](#operator_lt)|Vergleicht zwei `CFileTimeSpan` -Objekten, das kleinere zu bestimmen.|  
|[CFileTimeSpan::operator &lt;=](#operator_lt_eq)|Vergleicht zwei `CFileTimeSpan` Objekte auf Gleichheit oder das kleinere zu bestimmen.|  
|[CFileTimeSpan::operator =](#operator_eq)|Der Zuweisungsoperator.|  
|[CFileTimeSpan::operator =](#operator_-_eq)|Führt Subtraktion für ein `CFileTimeSpan` -Objekt und das Ergebnis mit dem aktuellen Objekt zuzuweisen.|  
|[CFileTimeSpan::operator ==](#operator_eq_eq)|Überprüft zwei `CFileTimeSpan`-Objekte auf Gleichheit.|  
|[CFileTimeSpan::operator &gt;](#operator_gt)|Vergleicht zwei `CFileTimeSpan` -Objekten, das größere zu bestimmen.|  
|[CFileTimeSpan::operator &gt;=](#operator_gt_eq)|Vergleicht zwei `CFileTimeSpan` Objekte auf Gleichheit oder das größere zu bestimmen.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt Methoden zum Verwalten von relativen Zeiträume Zeitspanne häufig auftreten, wenn die Ausführung von Vorgängen, die bezüglich der eine Datei erstellt, des letzten Zugriffs auf oder zuletzt geändert wurde. Die Methoden dieser Klasse werden häufig in Verbindung mit verwendet [CFileTime Klasse](../../atl-mfc-shared/reference/cfiletime-class.md) Objekte.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CFileTime::Millisecond](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atltime.h  
  
##  <a name="cfiletimespan"></a>  CFileTimeSpan::CFileTimeSpan  
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
 Die `CFileTimeSpan` Objekt kann erstellt werden, mithilfe eines vorhandenen `CFileTimeSpan` -Objekt oder als 64-Bit-Wert ausgedrückt. Der Standardkonstruktor legt die Zeitspanne auf 0 fest.  
  
##  <a name="gettimespan"></a>  CFileTimeSpan::GetTimeSpan  
 Rufen Sie diese Methode zum Abrufen der Zeitspanne aus der `CFileTimeSpan` Objekt.  
  
```
LONGLONG GetTimeSpan() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Zeitspanne in Millisekunden an.  
  
##  <a name="operator_-"></a>  CFileTimeSpan::operator-  
 Führt Subtraktion für ein **CFileTimeSpan** Objekt.  
  
```
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Ein `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine `CFileTimeSpan` Objekt, das das Ergebnis des Unterschieds zwischen zwei Zeitspannen darstellt.  
  
##  <a name="operator_neq"></a>  CFileTimeSpan::operator! =  
 Überprüft zwei `CFileTimeSpan`-Objekte auf Ungleichheit.  
  
```
bool operator!=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Das zu vergleichende `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** ist das Element verglichenen nicht gleich der `CFileTimeSpan` Objekt; andernfalls **"false"**.  
  
##  <a name="operator_add"></a>  CFileTimeSpan::operator +  
 Außerdem führt ein `CFileTimeSpan` Objekt.  
  
```
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Ein `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine `CFileTimeSpan` -Objekt umfasst, enthält die Summe von zwei Mal.  
  
##  <a name="operator_add_eq"></a>  CFileTimeSpan::operator +=  
 Außerdem führt ein `CFileTimeSpan` Objekt, und weist das Ergebnis mit dem aktuellen Objekt.  
  
```
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Ein `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die aktualisierte `CFileTimeSpan` -Objekt umfasst, enthält die Summe von zwei Mal.  
  
##  <a name="operator_lt"></a>  CFileTimeSpan::operator &lt;  
 Vergleicht zwei `CFileTimeSpan` -Objekten, das kleinere zu bestimmen.  
  
```
bool operator<(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Das zu vergleichende `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** , wenn das erste Objekt kleiner ist (d. h. einen kürzeren Zeitraum darstellt) als das zweite andernfalls **"false"**.  
  
##  <a name="operator_lt_eq"></a>  CFileTimeSpan::operator &lt;=  
 Vergleicht zwei `CFileTimeSpan` Objekte auf Gleichheit oder das kleinere zu bestimmen.  
  
```
bool operator<=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Das zu vergleichende `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** ist das erste Objekt kleiner als (d. h. einen kürzeren Zeitraum darstellt) oder gleich dem zweiten andernfalls **"false"**.  
  
##  <a name="operator_eq"></a>  CFileTimeSpan::operator =  
 Der Zuweisungsoperator.  
  
```
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Ein `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die aktualisierte `CFileTimeSpan` Objekt.  
  
##  <a name="operator_-_eq"></a>  CFileTimeSpan::operator =  
 Führt Subtraktion für ein `CFileTimeSpan` Objekt, und weist das Ergebnis mit dem aktuellen Objekt.  
  
```
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Ein `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die aktualisierte `CFileTimeSpan` Objekt.  
  
##  <a name="operator_eq_eq"></a>  CFileTimeSpan::operator ==  
 Überprüft zwei `CFileTimeSpan`-Objekte auf Gleichheit.  
  
```
bool operator==(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Das zu vergleichende `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** , wenn die Objekte gleich, andernfalls sind **"false"**.  
  
##  <a name="operator_gt"></a>  CFileTimeSpan::operator &gt;  
 Vergleicht zwei `CFileTimeSpan` -Objekten, das größere zu bestimmen.  
  
```
bool operator>(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Das zu vergleichende `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** ist das erste Objekt größer als (d. h. einen längeren Zeitraum darstellt) als das zweite andernfalls **"false"**.  
  
##  <a name="operator_gt_eq"></a>  CFileTimeSpan::operator &gt;=  
 Vergleicht zwei `CFileTimeSpan` Objekte auf Gleichheit oder das größere zu bestimmen.  
  
```
bool operator>=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Das zu vergleichende `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** ist das erste Objekt größer als (d. h. einen längeren Zeitraum darstellt) oder gleich dem zweiten andernfalls **"false"**.  
  
##  <a name="settimespan"></a>  CFileTimeSpan::SetTimeSpan  
 Rufen Sie diese Methode zum Festlegen der Zeitspanne der `CFileTimeSpan` Objekt.  
  
```
void SetTimeSpan(LONGLONG nSpan) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nSpan`  
 Der neue Wert für die Zeitspanne in Millisekunden.  
  
## <a name="see-also"></a>Siehe auch  
 [FILETIME-ELEMENT](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [CFileTime-Klasse](../../atl-mfc-shared/reference/cfiletime-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)


