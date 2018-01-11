---
title: shared_future-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::shared_future
- future/std::shared_future::shared_future
- future/std::shared_future::get
- future/std::shared_future::valid
- future/std::shared_future::wait
- future/std::shared_future::wait_for
- future/std::shared_future::wait_until
dev_langs: C++
ms.assetid: 454ebedd-f42b-405f-99a5-a25cc9ad7c90
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::shared_future [C++]
- std::shared_future [C++], shared_future
- std::shared_future [C++], get
- std::shared_future [C++], valid
- std::shared_future [C++], wait
- std::shared_future [C++], wait_for
- std::shared_future [C++], wait_until
ms.workload: cplusplus
ms.openlocfilehash: c6d7946de6440ad33c844e140ca7cbcc2199a0b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="sharedfuture-class"></a>shared_future-Klasse
Beschreibt ein *asynchrones Rückgabeobjekt*. Im Gegensatz zu einem [zukünftigen](../standard-library/future-class.md) Objekt, kann ein *asynchroner Anbieter* beliebig vielen `shared_future`-Objekten zugeordnet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Ty>
class shared_future;
```  
  
## <a name="remarks"></a>Hinweise  
 Rufen Sie keine anderen Methoden als `valid`, `operator=` und den Destruktor eines `shared_future`-Objekts auf, das *leer* ist.  
  
 `shared_future`-Objekte werden nicht synchronisiert. Aufrufen von Methoden für das gleiche Objekt von mehreren Threads führt zu einem Datenrace mit unvorhersehbaren Ergebnissen.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[shared_future](#shared_future)|Erstellt ein `shared_future`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[get](#get)|Ruft das Ergebnis ab, das im *zugeordneten asynchronen Zustand* gespeichert ist.|  
|[gültige](#valid)|Gibt an, dass das Objekt nicht leer ist.|  
|[Warte](#wait)|Blockiert den aktuellen Thread, bis der zugeordnete asynchrone Zustand bereit ist.|  
|[wait_for](#wait_for)|Blockiert, bis der zugeordnete asynchrone Zustand bereit ist, oder bis die angegebene Zeit verstrichen ist.|  
|[wait_until](#wait_until)|Blockiert, bis der zugeordnete asynchrone Zustand bereit ist, oder bis ein angegebener Zeitpunkt erreicht ist.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[shared_future::operator=](#op_eq)|Weist einen neuen zugeordneten asynchronen Zustand zu.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<zukünftige >  
  
 **Namespace:** std  
  
##  <a name="get"></a>shared_future:: Get
 Ruft das Ergebnis ab, das im *zugeordneten asynchronen Zustand* gespeichert ist.  
  
```
const Ty& get() const;

Ty& get() const;

void get() const;
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Ergebnis eine Ausnahme ist, wird es erneut von der Methode ausgelöst. Andernfalls ist das Ergebnis negativ.  
  
 Bevor sie das Ergebnis abruf, blockiert diese Methode den aktuellen Thread, bis der zugeordnete asynchrone Zustand bereit ist.  
  
 Für die Teilspezialisierung `shared_future<Ty&>` ist der gespeicherte Wert praktisch ein Verweis auf das Objekt, das dem asynchronen *Anbieter als Rückgabewert* übergeben wurde.  
  
 Da für die Spezialisierung `shared_future<void>` kein gespeicherter Wert vorhanden ist, gibt die Methode `void` zurück.  
  
##  <a name="op_eq"></a> shared_future::operator=  
 Überträgt einen *zugeordneten asynchronen Zustand* aus einem angegebenen Objekt.  
  
```
shared_future& operator=(shared_future&& Right) noexcept;
shared_future& operator=(const shared_future& Right);
```  
  
### <a name="parameters"></a>Parameter  
 `Right`  
 Ein `shared_future`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `*this`  
  
### <a name="remarks"></a>Hinweise  
 Für den ersten Operator weist `Right` nach dem Vorgang keinen zugeordneten asynchronen Zustand mehr auf.  
  
 Für die zweite Methode verwaltet `Right` ihren zugeordneten asynchronen Zustand.  
  
##  <a name="shared_future"></a> shared_future::shared_future-Konstruktor  
 Erstellt ein `shared_future`-Objekt.  
  
```
shared_future() noexcept;
shared_future(future<Ty>&& Right) noexcept;
shared_future(shared_future&& Right) noexcept;
shared_future(const shared_future& Right);
```  
  
### <a name="parameters"></a>Parameter  
 `Right`  
 Ein [zukünftiges](../standard-library/future-class.md) oder `shared_future`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Mit dem ersten Konstruktor wird ein `shared_future`-Objekt erstellt, das über keinen *zugeordneten asynchronen Zustand* verfügt.  
  
 Mit dem zweiten und dritten Konstruktor wird ein `shared_future`-Objekt erstellt, und der zugeordnete asynchrone Zustand wird von `Right` übertragen. `Right` verfügt nicht mehr über einen zugeordneten asynchronen Zustand.  
  
 Mit dem vierten Konstruktor wird ein `shared_future`-Objekt erstellt, das den gleichen zugeordneten asynchronen Zustand aufweist wie `Right`.  
  
##  <a name="valid"></a>shared_future:: Valid
 Gibt an, ob das Objekt einen *zugeordneten asynchronen Zustand* hat.  
  
```
bool valid() noexcept;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn das Objekt einen zugeordneten asynchronen Zustand hat; andernfalls `false`.  
  
##  <a name="wait"></a>shared_future:: wait
 Blockiert den aktuellen Thread, bis der *zugeordnete asynchrone Zustand* *bereit* ist.  
  
```
void wait() const;
```  
  
### <a name="remarks"></a>Hinweise  
 Ein zugeordneter asynchroner Zustand ist nur dann bereit, wenn sein asynchroner Anbieter einen Rückgabewert oder eine Ausnahme gespeichert hat.  
  
##  <a name="wait_for"></a>shared_future:: wait_for
 Blockiert den aktuellen Thread, bis der zugeordnete asynchrone Zustand *bereit* oder eine angegebene Zeit verstrichen ist.  
  
```
template <class Rep, class Period>
future_status wait_for(
    const chrono::duration<Rep, Period>& Rel_time) const;
```  
  
### <a name="parameters"></a>Parameter  
 `Rel_time`  
 Ein [chrono::duration](../standard-library/duration-class.md)-Objekt, das ein maximales Zeitintervall angibt, das der Thread blockiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [future_status](../standard-library/future-enums.md#future_status), das den Grund für die Rückgabe angibt.  
  
### <a name="remarks"></a>Hinweise  
 Ein zugeordneter asynchroner Zustand ist nur dann *bereit*, wenn sein asynchroner Anbieter einen Rückgabewert oder eine Ausnahme gespeichert hat.  
  
##  <a name="wait_until"></a>shared_future:: wait_until
 Blockiert den aktuelle Thread, bis der zugeordnete asynchrone Zustand *bereit* oder ein angegebener Zeitpunkt verstrichen ist.  
  
```
template <class Clock, class Duration>
future_status wait_until(
    const chrono::time_point<Clock, Duration>& Abs_time) const;
```  
  
### <a name="parameters"></a>Parameter  
 `Abs_time`  
 Ein [chrono::time_point](../standard-library/time-point-class.md)-Objekt, das eine Zeit angibt, nach der der Thread die Blockierung aufheben kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [future_status](../standard-library/future-enums.md#future_status), das den Grund für die Rückgabe angibt.  
  
### <a name="remarks"></a>Hinweise  
 Ein zugeordneter asynchroner Zustand ist nur dann bereit, wenn sein asynchroner Anbieter einen Rückgabewert oder eine Ausnahme gespeichert hat.  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<future>](../standard-library/future.md)



