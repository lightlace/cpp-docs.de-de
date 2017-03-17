---
title: Klasse CFileTime | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFileTime
- ATLTIME/ATL::CFileTime
- ATLTIME/ATL::CFileTime::CFileTime
- ATLTIME/ATL::CFileTime::GetCurrentTime
- ATLTIME/ATL::CFileTime::GetTime
- ATLTIME/ATL::CFileTime::LocalToUTC
- ATLTIME/ATL::CFileTime::SetTime
- ATLTIME/ATL::CFileTime::UTCToLocal
- ATLTIME/ATL::CFileTime::Day
- ATLTIME/ATL::CFileTime::Hour
- ATLTIME/ATL::CFileTime::Millisecond
- ATLTIME/ATL::CFileTime::Minute
- ATLTIME/ATL::CFileTime::Second
- ATLTIME/ATL::CFileTime::Week
dev_langs:
- C++
helpviewer_keywords:
- CFileTime class
- shared classes, CFileTime
ms.assetid: 1a358a65-1383-4124-b0d4-59b026e6860f
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
ms.openlocfilehash: 5ff7abc32093691d230787e8eb2d859bb4e77428
ms.lasthandoff: 02/24/2017

---
# <a name="cfiletime-class"></a>CFileTime-Klasse
Diese Klasse stellt Methoden zur Verwaltung der Datum und Uhrzeit-Werte, die einer Datei zugeordnet.  
  
## <a name="syntax"></a>Syntax  
  
```
class CFileTime :  public FILETIME
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileTime::CFileTime](#cfiletime)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileTime::GetCurrentTime](#getcurrenttime)|Rufen Sie die statische Funktion zum Abrufen einer `CFileTime` -Objekt, das aktuelle Systemdatum und die Uhrzeit darstellt.|  
|[CFileTime::GetTime](#gettime)|Rufen Sie diese Methode zum Abrufen der Uhrzeit aus der `CFileTime` Objekt.|  
|[CFileTime::LocalToUTC](#localtoutc)|Rufen Sie diese Methode, um einen lokalen Dateizeit in eine Datei Uhrzeit in Coordinated Universal Time (UTC) konvertiert.|  
|[CFileTime::SetTime](#settime)|Rufen Sie diese Methode zum Festlegen von Datum und Uhrzeit gespeichert, indem die `CFileTime` Objekt.|  
|[CFileTime::UTCToLocal](#utctolocal)|Rufen Sie diese Methode, um basierend auf der Coordinated Universal Time (UTC) an die lokale Zeit zu konvertieren.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileTime::operator-](#operator_-)|Dieser Operator wird verwendet, für die Subtraktion in einem `CFileTime` oder `CFileTimeSpan` Objekt.|  
|[CFileTime::operator! =](#operator_neq)|Dieser Operator vergleicht zwei `CFileTime` -Objekte auf Ungleichheit.|  
|[CFileTime::operator +](#operator_add)|Dieser Operator wird verwendet, um Addition für ein `CFileTimeSpan`-Objekt auszuführen.|  
|[CFileTime::operator +=](#operator_add_eq)|Dieser Operator wird verwendet, um Addition für ein `CFileTimeSpan`-Objekt auszuführen und das Ergebnis dem aktuellen Objekt zuzuweisen.|  
|[CFileTime::operator&lt;](#operator_lt)|Dieser Operator vergleicht zwei `CFileTime`-Objekte, um das kleinere zu bestimmen.|  
|[CFileTime::operator&lt;=](#operator_lt_eq)|Dieser Operator vergleicht zwei `CFileTime`-Objekte, um zu bestimmen, ob sie gleich sind oder welches kleiner ist.|  
|[CFileTime::operator =](#operator_eq)|Der Zuweisungsoperator.|  
|[CFileTime::operator =](#operator_-_eq)|Dieser Operator wird verwendet, für die Subtraktion auf ein `CFileTimeSpan` -Objekt und das Ergebnis mit dem aktuellen Objekt zuweisen.|  
|[CFileTime::operator ==](#operator_eq_eq)|Dieser Operator überprüft zwei `CFileTime`-Objekte auf Gleichheit.|  
|[CFileTime::operator&gt;](#operator_gt)|Dieser Operator vergleicht zwei `CFileTime`-Objekte, um das größere zu bestimmen.|  
|[CFileTime::operator&gt;=](#operator_gt_eq)|Dieser Operator vergleicht zwei `CFileTime`-Objekte, um zu bestimmen, ob sie gleich sind oder welches größer ist.|  
  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileTime::Day](#day)|Ein statischer Datenmember, die die Anzahl der 100-Nanosekunden-Intervalle, aus denen ein Tag gespeichert wird.|  
|[CFileTime::Hour](#hour)|Ein statischer Datenmember, speichern die Anzahl der 100-Nanosekunden-Intervalle, aus denen eine Stunde.|  
|[CFileTime::Millisecond](#millisecond)|Ein statischer Datenmember, speichern die Anzahl der 100-Nanosekunden-Intervalle, aus denen eine Millisekunde besteht.|  
|[CFileTime::Minute](#minute)|Ein statischer Datenmember, speichern die Anzahl der 100-Nanosekunden-Intervalle, aus denen eine Minute.|  
|[CFileTime::Second](#second)|Ein statischer Datenmember, die Anzahl der 100-Nanosekunden-Intervalle, aus denen eine Sekunde gespeichert.|  
|[CFileTime::Week](#week)|Ein statischer Datenmember, die Anzahl der 100-Nanosekunden-Intervalle, aus denen eine Woche gespeichert.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt Methoden zur Verwaltung der Datum und Uhrzeit-Werte, die die Erstellung und Zugriff auf die Änderung von Dateien zugeordnet. Die Methoden und die Daten dieser Klasse werden häufig in Verbindung mit verwendet `CFileTimeSpan` Objekte, die relativen Zeitwerte behandeln.  
  
 Der Wert für Datum und Uhrzeit wird als eine 64-Bit-Wert, der die Anzahl der 100-Nanosekunden-Intervalle seit dem 1. Januar 1601 darstellt gespeichert. Dies ist das Format der koordinierten Weltzeit (Coordinated Universal Time, UTC).  
  
 Die folgenden statischen const Membervariablen werden bereitgestellt, um Berechnungen zu vereinfachen:  
  
|Membervariable|Anzahl der 100-Nanosekunden-Intervalle|  
|---------------------|-----------------------------------------|  
|Millisecond|10,000|  
|Second|Millisekunde * 1.000|  
|Minute|Zweite * 60|  
|Hour|Minuten * 60|  
|Day|Stunde * 24|  
|Woche|Tag * 7|  
  
 **Hinweis** nicht alle Dateisysteme können Erstellung aufzeichnen und Zeitpunkt des letzten Zugriffs und nicht alle Dateisysteme auf die gleiche Weise aufzeichnen. Erstellen Sie beispielsweise auf die Windows NT-FAT-Dateisystem, hat eine Auflösung von 10 Millisekunden, Schreibzugriff hat eine Auflösung von 2 Sekunden und Zugriffszeit hat eine Auflösung von 1 Tag (Tag Zugriff). Auf NTFS hat Zugriff auf eine Auflösung von 1 Stunde. Darüber hinaus FAT zeichnet Zeiten auf dem Datenträger in der lokalen Zeit auf, sondern NTFS zeichnet Zeiten auf dem Datenträger in UTC. Weitere Informationen finden Sie unter [Dateizeiten](http://msdn.microsoft.com/library/windows/desktop/ms724290).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `FILETIME`  
  
 `CFileTime`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atltime.h  
  
##  <a name="cfiletime"></a>CFileTime::CFileTime  
 Der Konstruktor.  
  
```
CFileTime() throw();
CFileTime(const FILETIME& ft) throw();
CFileTime(ULONGLONG nTime) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ft`  
 Ein [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) Struktur.  
  
 `nTime`  
 Das Datum und Uhrzeit ausgedrückt werden als 64-Bit-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die `CFileTime` -Objekt kann erstellt werden, mit einer vorhandenen Datums- und Uhrzeitangabe von einer `FILETIME` -Struktur oder als 64-Bit-Wert (in lokalen oder Zeitformate Coordinated Universal Time (UTC)). Der Standardkonstruktor legt die Zeit auf 0 fest.  
  
##  <a name="day"></a>CFileTime::Day  
 Ein statischer Datenmember, die die Anzahl der 100-Nanosekunden-Intervalle, aus denen ein Tag gespeichert wird.  
  
```
static const ULONGLONG Day = Hour* 24;
```  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CFileTime::Millisecond](#millisecond).  
  
##  <a name="getcurrenttime"></a>CFileTime::GetCurrentTime  
 Rufen Sie die statische Funktion zum Abrufen einer `CFileTime` -Objekt, das aktuelle Systemdatum und die Uhrzeit darstellt.  
  
```
static CFileTime GetCurrentTime() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das aktuelle Systemdatum und die Uhrzeit in Coordinated Universal Time (UTC)-Format zurück.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#41;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_1.cpp)]  
  
##  <a name="gettime"></a>CFileTime::GetTime  
 Rufen Sie diese Methode zum Abrufen der Uhrzeit aus der `CFileTime` Objekt.  
  
```
ULONGLONG GetTime() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Datum und die Uhrzeit als 64-Bit-Zahl, die in lokalen oder der koordinierten Weltzeit (Coordinated Universal Time, UTC) Format möglicherweise.  
  
##  <a name="hour"></a>CFileTime::Hour  
 Ein statischer Datenmember, speichern die Anzahl der 100-Nanosekunden-Intervalle, aus denen eine Stunde.  
  
```
static const ULONGLONG Hour = Minute* 60;
```  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CFileTime::Millisecond](#millisecond).  
  
##  <a name="localtoutc"></a>CFileTime::LocalToUTC  
 Rufen Sie diese Methode, um einen lokalen Dateizeit in eine Datei Uhrzeit in Coordinated Universal Time (UTC) konvertiert.  
  
```
CFileTime LocalToUTC() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein `CFileTime` -Objekt, das die Uhrzeit im UTC-Format enthält.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CFileTime::UTCToLocal](#utctolocal).  
  
##  <a name="millisecond"></a>CFileTime::Millisecond  
 Ein statischer Datenmember, speichern die Anzahl der 100-Nanosekunden-Intervalle, aus denen eine Millisekunde besteht.  
  
```
static const ULONGLONG Millisecond = 10000;
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#44;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_2.cpp)]  
  
##  <a name="minute"></a>CFileTime::Minute  
 Ein statischer Datenmember, speichern die Anzahl der 100-Nanosekunden-Intervalle, aus denen eine Minute.  
  
```
static const ULONGLONG Minute = Second* 60;
```  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CFileTime::Millisecond](#millisecond).  
  
##  <a name="operator_-"></a>CFileTime::operator-  
 Dieser Operator wird verwendet, für die Subtraktion in einem `CFileTime` oder `CFileTimeSpan` Objekt.  
  
```
CFileTime operator-(CFileTimeSpan span) const throw();
CFileTimeSpan operator-(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Ein `CFileTimeSpan`-Objekt.  
  
 `ft`  
 Ein `CFileTime`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine `CFileTime` Objekt oder ein `CFileTimeSpan` Objekt, das das Ergebnis der Zeitunterschied zwischen den beiden Objekten darstellt.  
  
##  <a name="operator_neq"></a>CFileTime::operator! =  
 Dieser Operator vergleicht zwei `CFileTime` -Objekte auf Ungleichheit.  
  
```
bool operator!=(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ft`  
 Das zu vergleichende `CFileTime`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** ist das Element wird im Vergleich nicht gleich der `CFileTime` Objekt ist, andernfalls **false**.  
  
##  <a name="operator_add"></a>CFileTime::operator +  
 Dieser Operator wird verwendet, um Addition für ein `CFileTimeSpan`-Objekt auszuführen.  
  
```
CFileTime operator+(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Ein `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein `CFileTime` Objekt, das das Ergebnis der ursprünglichen Zeit plus ein relativer Zeitpunkt darstellt.  
  
##  <a name="operator_add_eq"></a>CFileTime::operator +=  
 Dieser Operator wird verwendet, um Addition für ein `CFileTimeSpan`-Objekt auszuführen und das Ergebnis dem aktuellen Objekt zuzuweisen.  
  
```
CFileTime& operator+=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Ein `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den aktualisierten `CFileTime` Objekt, das das Ergebnis der ursprünglichen Zeit plus ein relativer Zeitpunkt darstellt.  
  
##  <a name="operator_lt"></a>CFileTime::operator&lt;  
 Dieser Operator vergleicht zwei `CFileTime`-Objekte, um das kleinere zu bestimmen.  
  
```
bool operator<(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ft`  
 Das zu vergleichende `CFileTime`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** ist das erste Objekt kleiner (zeitlich) als das zweite **false** andernfalls.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#43;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_3.cpp)]  
  
##  <a name="operator_lt_eq"></a>CFileTime::operator&lt;=  
 Dieser Operator vergleicht zwei `CFileTime`-Objekte, um zu bestimmen, ob sie gleich sind oder welches kleiner ist.  
  
```
bool operator<=(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ft`  
 Das zu vergleichende `CFileTime`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** Wenn das erste Objekt kleiner als (liegt in-Time) oder gleich dem zweiten ist **false**.  
  
##  <a name="operator_eq"></a>CFileTime::operator =  
 Der Zuweisungsoperator.  
  
```
CFileTime& operator=(const FILETIME& ft) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ft`  
 Ein `CFileTime` Objekt mit der Zeit und Datum.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den aktualisierten `CFileTime` Objekt.  
  
##  <a name="operator_-_eq"></a>CFileTime::operator =  
 Dieser Operator wird verwendet, für die Subtraktion auf ein `CFileTimeSpan` -Objekt und das Ergebnis mit dem aktuellen Objekt zuweisen.  
  
```
CFileTime& operator-=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Ein `CFileTimeSpan` Objekt, das die zu subtrahierende relative Zeit enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den aktualisierten `CFileTime` Objekt.  
  
##  <a name="operator_eq_eq"></a>CFileTime::operator ==  
 Dieser Operator überprüft zwei `CFileTime`-Objekte auf Gleichheit.  
  
```
bool operator==(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ft`  
 Die `CFileTime` zu vergleichende Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** , wenn die Objekte gleich, andernfalls sind **false**.  
  
##  <a name="operator_gt"></a>CFileTime::operator&gt;  
 Dieser Operator vergleicht zwei `CFileTime`-Objekte, um das größere zu bestimmen.  
  
```
bool operator>(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ft`  
 Das zu vergleichende `CFileTime`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** ist das erste Objekt größer als (später in der Zeit) als die zweite andernfalls **false**.  
  
##  <a name="operator_gt_eq"></a>CFileTime::operator&gt;=  
 Dieser Operator vergleicht zwei `CFileTime`-Objekte, um zu bestimmen, ob sie gleich sind oder welches größer ist.  
  
```
bool operator>=(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ft`  
 Das zu vergleichende `CFileTime`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** Wenn das erste Objekt größer als (später in Time) oder gleich dem zweiten ist **false**.  
  
##  <a name="second"></a>CFileTime::Second  
 Ein statischer Datenmember, die die Anzahl der 100-Nanosekunden-Intervalle, aus denen ein Tag gespeichert wird.  
  
```
static const ULONGLONG Second = Millisecond* 1000;
```  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CFileTime::Millisecond](#millisecond).  
  
##  <a name="settime"></a>CFileTime::SetTime  
 Rufen Sie diese Methode zum Festlegen von Datum und Uhrzeit gespeichert, indem die `CFileTime` Objekt.  
  
```
void SetTime(ULONGLONG nTime) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nTime`  
 Der 64-Bit-Wert darstellt, das Datum und die Uhrzeit in Coordinated Universal Time (UTC) Format oder lokal.  
  
##  <a name="utctolocal"></a>CFileTime::UTCToLocal  
 Rufen Sie diese Methode, um basierend auf der Coordinated Universal Time (UTC) an die lokale Zeit zu konvertieren.  
  
```
CFileTime UTCToLocal() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein `CFileTime` -Objekt, das die Zeit im lokalen Zeitformat enthält.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#42;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_4.cpp)]  
  
##  <a name="week"></a>CFileTime::Week  
 Ein statischer Datenmember, die Anzahl der 100-Nanosekunden-Intervalle, aus denen eine Woche gespeichert.  
  
```
static const ULONGLONG Week = Day* 7;
```  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CFileTime::Millisecond](#millisecond).  
  
## <a name="see-also"></a>Siehe auch  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [CFileTimeSpan-Klasse](../../atl-mfc-shared/reference/cfiletimespan-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL/MFC-freigegeben Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)



