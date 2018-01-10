---
title: CFileTime Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CFileTime class
- shared classes, CFileTime
ms.assetid: 1a358a65-1383-4124-b0d4-59b026e6860f
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d48e899bb058ed27559a4ef699a3a53267064f98
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cfiletime-class"></a>CFileTime-Klasse
Diese Klasse stellt Methoden zum Verwalten von Datum und Uhrzeit-Werte, die einer Datei zugeordnet.  
  
## <a name="syntax"></a>Syntax  
  
```
class CFileTime :  public FILETIME
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileTime::CFileTime](#cfiletime)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileTime::GetCurrentTime](#getcurrenttime)|Rufen Sie diese statische Funktion zum Abrufen einer `CFileTime` Objekt, das das aktuelle Systemdatum und die Uhrzeit darstellt.|  
|[CFileTime::GetTime](#gettime)|Rufen Sie diese Methode zum Abrufen der Uhrzeit aus der `CFileTime` Objekt.|  
|[CFileTime::LocalToUTC](#localtoutc)|Rufen Sie diese Methode, um eine lokale Datei Uhrzeit eine Datei basierend auf der koordinierten Weltzeit (UTC) konvertieren.|  
|[CFileTime::SetTime](#settime)|Rufen Sie diese Methode zum Festlegen von Datum und Uhrzeit gespeichert, die durch die `CFileTime` Objekt.|  
|[CFileTime::UTCToLocal](#utctolocal)|Rufen Sie diese Methode zum Konvertieren der Uhrzeit basierend auf der koordinierten Weltzeit (UTC) in lokalen-Dateizeit.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileTime::operator-](#operator_-)|Dieser Operator wird verwendet, für die Subtraktion für ein `CFileTime` oder `CFileTimeSpan` Objekt.|  
|[CFileTime::operator! =](#operator_neq)|Dieser Operator vergleicht zwei `CFileTime` -Objekte auf Ungleichheit.|  
|[CFileTime::operator +](#operator_add)|Dieser Operator wird verwendet, um Addition für ein `CFileTimeSpan`-Objekt auszuführen.|  
|[CFileTime::operator +=](#operator_add_eq)|Dieser Operator wird verwendet, um Addition für ein `CFileTimeSpan`-Objekt auszuführen und das Ergebnis dem aktuellen Objekt zuzuweisen.|  
|[CFileTime::operator&lt;](#operator_lt)|Dieser Operator vergleicht zwei `CFileTime`-Objekte, um das kleinere zu bestimmen.|  
|[CFileTime::operator&lt;=](#operator_lt_eq)|Dieser Operator vergleicht zwei `CFileTime`-Objekte, um zu bestimmen, ob sie gleich sind oder welches kleiner ist.|  
|[CFileTime::operator =](#operator_eq)|Der Zuweisungsoperator.|  
|[CFileTime::operator =](#operator_-_eq)|Dieser Operator wird verwendet, für die Subtraktion für ein `CFileTimeSpan` -Objekt und das Ergebnis mit dem aktuellen Objekt zuzuweisen.|  
|[CFileTime::operator ==](#operator_eq_eq)|Dieser Operator überprüft zwei `CFileTime`-Objekte auf Gleichheit.|  
|[CFileTime::operator&gt;](#operator_gt)|Dieser Operator vergleicht zwei `CFileTime`-Objekte, um das größere zu bestimmen.|  
|[CFileTime::operator&gt;=](#operator_gt_eq)|Dieser Operator vergleicht zwei `CFileTime`-Objekte, um zu bestimmen, ob sie gleich sind oder welches größer ist.|  
  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CFileTime::Day](#day)|Ein statischer Datenmember, speichern die Anzahl der 100-Nanosekunden-Intervallen, aus denen eines Tages besteht.|  
|[CFileTime::Hour](#hour)|Ein statischer Datenmember, speichern die Anzahl der 100-Nanosekunden-Intervallen, aus denen einer Stunde besteht.|  
|[CFileTime::Millisecond](#millisecond)|Ein statischer Datenmember, speichern die Anzahl der 100-Nanosekunden-Intervalle, aus denen einer Millisekunde besteht.|  
|[CFileTime::Minute](#minute)|Ein statischer Datenmember, speichern die Anzahl der 100-Nanosekunden-Intervalle, aus denen einer Minute besteht.|  
|[CFileTime::Second](#second)|Ein statischer Datenmember, speichern die Anzahl der 100-Nanosekunden-Intervalle, aus denen einer Sekunde besteht.|  
|[CFileTime::Week](#week)|Ein statischer Datenmember, speichern die Anzahl der 100-Nanosekunden-Intervallen, die eine Woche bilden.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt Methoden zum Verwalten von das Datum und Uhrzeit-Werte, die die Erstellung, die Zugriffsrechte und die Änderung von Dateien zugeordnet. Die Methoden und die Daten dieser Klasse werden häufig in Verbindung mit verwendet `CFileTimeSpan` Objekte, die relative Uhrzeitwerten behandeln.  
  
 Wert für Datum und Zeit wird als 64-Bit-Wert, die die Anzahl der 100-Nanosekunden-Intervalle seit dem 1. Januar 1601 darstellt gespeichert. Dies ist das Format der koordinierten Weltzeit (Coordinated Universal Time, UTC).  
  
 Die folgenden Membervariablen für static const werden bereitgestellt, um Berechnungen zu vereinfachen:  
  
|Membervariablen|Anzahl der 100-Nanosekunden-Intervallen|  
|---------------------|-----------------------------------------|  
|Millisecond|10,000|  
|Second|Millisekunde * 1.000|  
|Minute|Zweite * 60|  
|Hour|Minute * 60|  
|Day|Stunde * 24|  
|Woche|Tag * 7|  
  
 **Hinweis** nicht alle Dateisysteme können Erstellung aufzeichnen und die Uhrzeit des letzten Zugriffs und nicht alle Dateisysteme auf die gleiche Weise aufzeichnen. Erstellen Sie beispielsweise auf die Windows NT-FAT-Dateisystem Zeit besitzt einer Auflösung von 10 Millisekunden, Schreibzeit hat eine Auflösung von 2 Sekunden, und Zugriffszeit einer Auflösung von 1 Tag (das Datum des Zugriffs). Für NTFS verfügt Zugriffszeit eine Auflösung von 1 Stunde. Darüber hinaus wird FAT zeichnet Zeiten auf dem Datenträger in Ortszeit, sondern NTFS zeichnet Zeiten auf dem Datenträger in UTC. Weitere Informationen finden Sie unter [Dateizeiten](http://msdn.microsoft.com/library/windows/desktop/ms724290).  
  
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
 Die `CFileTime` Objekt kann erstellt werden, mithilfe einer vorhandenen Datums- und Uhrzeitangabe von einer `FILETIME` -Struktur oder als 64-Bit-Wert (in lokalen oder Zeitformate Coordinated Universal Time (UTC)). Der Standardkonstruktor legt die Zeit auf 0 fest.  
  
##  <a name="day"></a>CFileTime::Day  
 Ein statischer Datenmember, speichern die Anzahl der 100-Nanosekunden-Intervallen, aus denen eines Tages besteht.  
  
```
static const ULONGLONG Day = Hour* 24;
```  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CFileTime::Millisecond](#millisecond).  
  
##  <a name="getcurrenttime"></a>CFileTime::GetCurrentTime  
 Rufen Sie diese statische Funktion zum Abrufen einer `CFileTime` Objekt, das das aktuelle Systemdatum und die Uhrzeit darstellt.  
  
```
static CFileTime GetCurrentTime() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das aktuelle Systemdatum und die Uhrzeit in Coordinated Universal Time (UTC)-Format zurück.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#41](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_1.cpp)]  
  
##  <a name="gettime"></a>CFileTime::GetTime  
 Rufen Sie diese Methode zum Abrufen der Uhrzeit aus der `CFileTime` Objekt.  
  
```
ULONGLONG GetTime() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Datum und die Uhrzeit als 64-Bit-Zahl, in lokalen oder Format der koordinierten Weltzeit (Coordinated Universal Time, UTC) u. u. an.  
  
##  <a name="hour"></a>CFileTime::Hour  
 Ein statischer Datenmember, speichern die Anzahl der 100-Nanosekunden-Intervallen, aus denen einer Stunde besteht.  
  
```
static const ULONGLONG Hour = Minute* 60;
```  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CFileTime::Millisecond](#millisecond).  
  
##  <a name="localtoutc"></a>CFileTime::LocalToUTC  
 Rufen Sie diese Methode, um eine lokale Datei Uhrzeit eine Datei basierend auf der koordinierten Weltzeit (UTC) konvertieren.  
  
```
CFileTime LocalToUTC() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine `CFileTime` Objekt, das die Zeit im UTC-Format enthält.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CFileTime::UTCToLocal](#utctolocal).  
  
##  <a name="millisecond"></a>CFileTime::Millisecond  
 Ein statischer Datenmember, speichern die Anzahl der 100-Nanosekunden-Intervalle, aus denen einer Millisekunde besteht.  
  
```
static const ULONGLONG Millisecond = 10000;
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#44](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_2.cpp)]  
  
##  <a name="minute"></a>CFileTime::Minute  
 Ein statischer Datenmember, speichern die Anzahl der 100-Nanosekunden-Intervalle, aus denen einer Minute besteht.  
  
```
static const ULONGLONG Minute = Second* 60;
```  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CFileTime::Millisecond](#millisecond).  
  
##  <a name="operator_-"></a>CFileTime::operator-  
 Dieser Operator wird verwendet, für die Subtraktion für ein `CFileTime` oder `CFileTimeSpan` Objekt.  
  
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
 Gibt **"true"** ist das Element verglichenen nicht gleich der `CFileTime` Objekt ist, andernfalls **"false"**.  
  
##  <a name="operator_add"></a>CFileTime::operator +  
 Dieser Operator wird verwendet, um Addition für ein `CFileTimeSpan`-Objekt auszuführen.  
  
```
CFileTime operator+(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Ein `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine `CFileTime` Objekt, das das Ergebnis des ursprünglichen Zeit plus ein relativer Zeitpunkt darstellt.  
  
##  <a name="operator_add_eq"></a>CFileTime::operator +=  
 Dieser Operator wird verwendet, um Addition für ein `CFileTimeSpan`-Objekt auszuführen und das Ergebnis dem aktuellen Objekt zuzuweisen.  
  
```
CFileTime& operator+=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Ein `CFileTimeSpan`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die aktualisierte `CFileTime` Objekt, das das Ergebnis des ursprünglichen Zeit plus ein relativer Zeitpunkt darstellt.  
  
##  <a name="operator_lt"></a>CFileTime::operator&lt;  
 Dieser Operator vergleicht zwei `CFileTime`-Objekte, um das kleinere zu bestimmen.  
  
```
bool operator<(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ft`  
 Das zu vergleichende `CFileTime`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** ist das erste Objekt kleiner (weiter oben in Time) als das zweite **"false"** andernfalls.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#43](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_3.cpp)]  
  
##  <a name="operator_lt_eq"></a>CFileTime::operator&lt;=  
 Dieser Operator vergleicht zwei `CFileTime`-Objekte, um zu bestimmen, ob sie gleich sind oder welches kleiner ist.  
  
```
bool operator<=(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ft`  
 Das zu vergleichende `CFileTime`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** , wenn das erste Objekt kleiner als (liegt zeitlich) oder gleich dem zweiten ist **"false"**.  
  
##  <a name="operator_eq"></a>CFileTime::operator =  
 Der Zuweisungsoperator.  
  
```
CFileTime& operator=(const FILETIME& ft) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ft`  
 Ein `CFileTime` Objekt, das die Zeit und Datum enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die aktualisierte `CFileTime` Objekt.  
  
##  <a name="operator_-_eq"></a>CFileTime::operator =  
 Dieser Operator wird verwendet, für die Subtraktion für ein `CFileTimeSpan` -Objekt und das Ergebnis mit dem aktuellen Objekt zuzuweisen.  
  
```
CFileTime& operator-=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Ein `CFileTimeSpan` Objekt, das die zu subtrahierende relative Zeit enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die aktualisierte `CFileTime` Objekt.  
  
##  <a name="operator_eq_eq"></a>CFileTime::operator ==  
 Dieser Operator überprüft zwei `CFileTime`-Objekte auf Gleichheit.  
  
```
bool operator==(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ft`  
 Die `CFileTime` zu vergleichende Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** , wenn die Objekte gleich, andernfalls sind **"false"**.  
  
##  <a name="operator_gt"></a>CFileTime::operator&gt;  
 Dieser Operator vergleicht zwei `CFileTime`-Objekte, um das größere zu bestimmen.  
  
```
bool operator>(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ft`  
 Das zu vergleichende `CFileTime`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** ist das erste Objekt größer als (später in Time) als das zweite andernfalls **"false"**.  
  
##  <a name="operator_gt_eq"></a>CFileTime::operator&gt;=  
 Dieser Operator vergleicht zwei `CFileTime`-Objekte, um zu bestimmen, ob sie gleich sind oder welches größer ist.  
  
```
bool operator>=(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `ft`  
 Das zu vergleichende `CFileTime`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** , wenn das erste Objekt größer als (später in Time) oder gleich dem zweiten ist **"false"**.  
  
##  <a name="second"></a>CFileTime::Second  
 Ein statischer Datenmember, speichern die Anzahl der 100-Nanosekunden-Intervallen, aus denen eines Tages besteht.  
  
```
static const ULONGLONG Second = Millisecond* 1000;
```  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CFileTime::Millisecond](#millisecond).  
  
##  <a name="settime"></a>CFileTime::SetTime  
 Rufen Sie diese Methode zum Festlegen von Datum und Uhrzeit gespeichert, die durch die `CFileTime` Objekt.  
  
```
void SetTime(ULONGLONG nTime) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nTime`  
 Der 64-Bit-Wert, die das Datum und die Uhrzeit in Coordinated Universal Time (UTC) Format oder lokalen darstellt.  
  
##  <a name="utctolocal"></a>CFileTime::UTCToLocal  
 Rufen Sie diese Methode zum Konvertieren der Uhrzeit basierend auf der koordinierten Weltzeit (UTC) in lokalen-Dateizeit.  
  
```
CFileTime UTCToLocal() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine `CFileTime` Objekt, das die Zeit in der lokalen Datei Zeitformat enthält.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#42](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_4.cpp)]  
  
##  <a name="week"></a>CFileTime::Week  
 Ein statischer Datenmember, speichern die Anzahl der 100-Nanosekunden-Intervallen, die eine Woche bilden.  
  
```
static const ULONGLONG Week = Day* 7;
```  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CFileTime::Millisecond](#millisecond).  
  
## <a name="see-also"></a>Siehe auch  
 [FILETIME-ELEMENT](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [CFileTimeSpan-Klasse](../../atl-mfc-shared/reference/cfiletimespan-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)


