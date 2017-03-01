---
title: future-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::future
dev_langs:
- C++
ms.assetid: 495e82c3-5341-4e37-87dd-b40107fbdfb6
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 6de4fecd3f5f65ac48cbb49f2ed4f874f4283487
ms.lasthandoff: 02/24/2017

---
# <a name="future-class"></a>future-Klasse
Beschreibt ein *asynchrones Rückgabeobjekt*.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Ty>
class future;
```  
  
## <a name="remarks"></a>Hinweise  
 Jeder standardmäßige *asynchrone Anbieter* gibt ein Objekt zurück, dessen Typ eine Instanziierung dieser Vorlage ist. Ein `future`-Objekt liefert den Einzigen Zugriff auf einen asynchronen Anbieter, dem es zugeordnet ist. Wenn Sie mehrere asynchrone Rückgabeobjekte benötigen, die dem gleichen asynchronen Anbieter zugeordnet sind,, kopieren Sie das `future`-Objekt in das [shared_future](../standard-library/shared-future-class.md)-Objekt.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[future::future-Konstruktor](#future__future_constructor)|Erstellt ein `future`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[future::get](#future__get_method)|Ruft das Ergebnis ab, das im zugeordneten asynchronen Zustand gespeichert ist.|  
|[future::share](#future__share_method)|Konvertiert das Objekt in ein `shared_future`.|  
|[future::valid](#future__valid_method)|Gibt an, ob das Objekt nicht leer ist.|  
|[future::wait](#future__wait_method)|Blockiert den aktuellen Thread, bis der zugeordnete asynchrone Zustand bereit ist.|  
|[future::wait_for](#future__wait_for_method)|Blockiert, bis der zugeordnete asynchrone Zustand bereit ist, oder bis die angegebene Zeit verstrichen ist.|  
|[future::wait_until](#future__wait_until_method)|Blockiert, bis der zugeordnete asynchrone Zustand bereit ist, oder bis ein angegebener Zeitpunkt erreicht ist.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[future::operator=](#future__operator_eq)|Überträgt den zugeordneten asynchronen Zustand aus einem angegebenen Objekt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** future  
  
 **Namespace:** std  
  
##  <a name="a-namefuturefutureconstructora--futurefuture-constructor"></a><a name="future__future_constructor"></a> future::future-Konstruktor  
 Erstellt ein `future`-Objekt.  
  
```
future() noexcept;
future(future&& Other) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Other`  
 Ein `future`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Mit dem ersten Konstruktor wird ein `future`-Objekt erstellt, das über keinen zugeordneten asynchronen Zustand verfügt.  
  
 Mit dem zweiten Konstruktor wird ein `future`-Objekt erstellt, und der zugeordnete asynchrone Zustand wird von `Other` übertragen. `Other` verfügt nicht mehr über einen asynchron zugeordneten Zustand.  
  
##  <a name="a-namefuturegetmethoda--futureget"></a><a name="future__get_method"></a> future::get  
 Ruft das Ergebnis ab, das im zugeordneten asynchronen Zustand gespeichert ist.  
  
```
Ty get();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn das Ergebnis eine Ausnahme ist, wird es erneut von der Methode ausgelöst. Andernfalls wird das Ergebnis zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Bevor es das Ergebnis abruf, blockiert diese Methode den aktuellen Thread, bis der zugeordnete asynchrone Zustand bereit ist.  
  
 Für die Teilspezialisierung `future<Ty&>` ist der gespeicherte Wert praktisch ein Verweis auf das Objekt, das dem asynchronen Anbieter als Rückgabewert übergeben wurde.  
  
 Weil für die Spezialisierung `future<void>` kein gespeicherten Wert existiert, gibt die Methode `void` zurück.  
  
 In anderen Spezialisierung verschiebt die Methode ihren Rückgabewert aus dem gespeicherten Wert. Deshalb sollten Sie diese Methode nur einmal aufrufen.  
  
##  <a name="a-namefutureoperatoreqa--futureoperator"></a><a name="future__operator_eq"></a> future::operator=  
 Überträgt einen zugeordneten asynchronen Zustand aus einem angegebenen Objekt.  
  
```
future& operator=(future&& Right) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Right`  
 Ein `future`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `*this`  
  
### <a name="remarks"></a>Hinweise  
 Nach der Übertragung verfügt `Right` über keinen asynchronen zugeordneten Zustand mehr.  
  
##  <a name="a-namefuturesharemethoda--futureshare"></a><a name="future__share_method"></a> future::share  
 Konvertiert das Objekt in ein [shared_future](../standard-library/shared-future-class.md)-Objekt.  
  
```
shared_future<Ty> share();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `shared_future(move(*this))`  
  
##  <a name="a-namefuturevalidmethoda--futurevalid"></a><a name="future__valid_method"></a> future::valid  
 Legt fest, ob das Objekt einen zugeordneten asynchronen Zustand hat.  
  
```
bool valid() noexcept;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn das Objekt einen zugeordneten asynchronen Zustand hat; andernfalls `false`.  
  
##  <a name="a-namefuturewaitmethoda--futurewait"></a><a name="future__wait_method"></a> future::wait  
 Blockiert den aktuellen Thread, bis der zugeordnete asynchrone Zustand *bereit* ist.  
  
```cpp  
void wait() const;
```  
  
### <a name="remarks"></a>Hinweise  
 Ein zugeordneter asynchroner Zustand ist nur dann *bereit*, wenn sein asynchroner Anbieter einen Rückgabewert oder eine Ausnahme gespeichert hat.  
  
##  <a name="a-namefuturewaitformethoda--futurewaitfor"></a><a name="future__wait_for_method"></a> future::wait_for  
 Blockiert dem aktuelle Thread, bis der zugeordnete asynchrone Zustand *bereit* ist, oder bis ein angegebenes Zeitintervall verstrichen ist.  
  
```
template <class Rep, class Period>
future_status wait_for(const chrono::duration<Rep, Period>& Rel_time) const;
```  
  
### <a name="parameters"></a>Parameter  
 `Rel_time`  
 Ein [chrono::duration](../standard-library/duration-class.md)-Objekt, das ein maximales Zeitintervall angibt, das der Thread blockiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [future_status](../standard-library/future-enums.md#future_status_enumeration), das den Grund für die Rückgabe angibt.  
  
### <a name="remarks"></a>Hinweise  
 Ein zugeordneter asynchroner Zustand ist nur dann bereit, wenn sein asynchroner Anbieter einen Rückgabewert oder eine Ausnahme gespeichert hat.  
  
##  <a name="a-namefuturewaituntilmethoda--futurewaituntil"></a><a name="future__wait_until_method"></a> future::wait_until  
 Blockiert den aktuelle Thread, bis der zugeordnete asynchrone Zustand *bereit* ist, oder bis ein angegebener Zeitpunkt verstrichen ist.  
  
```cpp  
template <class Clock, class Duration>
future_status wait_until(const chrono::time_point<Clock, Duration>& Abs_time) const;
```  
  
### <a name="parameters"></a>Parameter  
 `Abs_time`  
 Ein [chrono::time_point](../standard-library/time-point-class.md)-Objekt, das eine Zeit angibt, nach der der Thread die Blockierung aufheben kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [future_status](../standard-library/future-enums.md#future_status_enumeration), das den Grund für die Rückgabe angibt.  
  
### <a name="remarks"></a>Hinweise  
 Ein zugeordneter asynchroner Zustand ist nur dann *bereit*, wenn sein asynchroner Anbieter einen Rückgabewert oder eine Ausnahme gespeichert hat.  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<future>](../standard-library/future.md)




