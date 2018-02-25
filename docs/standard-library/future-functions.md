---
title: '&lt;future&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- future/std::async
- future/std::future_category
- future/std::make_error_code
- future/std::make_error_condition
- future/std::swap
ms.assetid: 1e3acc1e-736a-42dc-ade2-b2fe69aa96bc
caps.latest.revision: 
manager: ghogen
helpviewer_keywords:
- std::async [C++]
- std::future_category [C++]
- std::make_error_code [C++]
- std::make_error_condition [C++]
- std::swap [C++]
ms.openlocfilehash: d136f972786938e453d5a9116ea198ac2a5d8f46
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ltfuturegt-functions"></a>&lt;future&gt;-Funktionen
||||  
|-|-|-|  
|[async](#async)|[future_category](#future_category)|[make_error_code](#make_error_code)|  
|[make_error_condition](#make_error_condition)|[swap](#swap)|  
  
##  <a name="async"></a> async  
 Stellt einen *asynchronen Anbieter* dar.  
  
```
template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(Fn&& fn, ArgTypes&&... args);

template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(launch policy, Fn&& fn, ArgTypes&&... args);
```  
  
### <a name="parameters"></a>Parameter  
 `policy`  
 Ein [launch](../standard-library/future-enums.md#launch)-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Definitionen von Abkürzungen:  
  
|||  
|-|-|  
|*dfn*|Das Ergebnis des Aufrufs von `decay_copy(forward<Fn>(fn))`.|  
|*dargs*|Die Ergebnisse des Aufrufs von `decay_copy(forward<ArgsTypes>(args...))`.|  
|*Ty*|Typ `result_of<Fn(ArgTypes...)>::type`.|  
  
 Die erste Vorlagenfunktion gibt `async(launch::any, fn, args...)` zurück.  
  
 Die zweite Funktion gibt ein `future<Ty>`-Objekt zurück, dessen *assoziierter asynchroner Zustand* ein Ergebnis zusammen mit den Werten von *dfn* und *dargs* sowie ein Threadobjekt enthält, um einen separaten Ausführungsthread zu verwalten.  
  
 Sofern `decay<Fn>::type` nicht ein anderer Typ als "launch" ist, ist die zweite Funktion nicht an der Überladungsauflösung beteiligt.  
  
 Wenn `policy` `launch::any` ist, wird von der Funktion vielleicht `launch::async` oder `launch::deferred` ausgewählt. In dieser Implementierung wird von der Funktion `launch::async` verwendet.  
  
 Wenn `policy` `launch::async` ist, wird von der Funktion ein Thread erstellt, der `INVOKE(dfn, dargs..., Ty)` ergibt. Die Funktion wird zurückgegeben, nachdem der Thread ohne Warteergebnisse erstellt wurde. Wenn vom System kein neuer Thread gestartet werden kann, wird von der Funktion ein [system_error](../standard-library/system-error-class.md) ausgelöst, der einen Fehlercode von `resource_unavailable_try_again` aufweist.  
  
 Wenn `policy` `launch::deferred` ist, wird von der Funktion der assoziierte asynchronen Zustand als das Enthalten einer *verzögerten Funktion* markiert, und sie wird zurückgegeben. Der erste Aufruf einer nicht zeitgesteuerten Funktion, die darauf wartet, dass der entsprechende assoziierte asynchrone Zustand bereit ist, ruft effektiv die verzögerte Funktion auf, indem `INVOKE(dfn, dargs..., Ty)` ausgewertet wird.  
  
 In allen Fällen wird der assoziierte asynchrone Zustand des `future`-Objekts nicht auf *bereit* festgelegt, bis die Auswertung von `INVOKE(dfn, dargs..., Ty)` abgeschlossen ist; entweder, indem eine Ausnahme ausgelöst wird oder indem die Rückgabe auf die normale Weise erfolgt. Das Ergebnis des assoziierten asynchronen Zustands ist eine Ausnahm, sofern eine ausgelöst wurde, oder ein beliebiger Wert, der von der Auswertung zurückgegeben wird.  
  
> [!NOTE]
>  Für ein `future`-Element oder das letzte [shared_future](../standard-library/shared-future-class.md)-Element, das der Aufgabe angefügt ist, die mit `std::async` gestartet ist, wird der Destruktor blockiert, wenn die Aufgabe nicht abgeschlossen wurde. Das heißt, er wird blockiert, wenn vom Thread weder `.get()` noch `.wait()` aufgerufen wurde, und die Aufgabe noch ausgeführt wird. Wenn ein `future`-Element, das von `std::async` erhalten wurde, außerhalb des lokalen Bereich verschoben wird, muss beim Schreiben von anderem Code, bei dem es verwendet wird, beachtet werden, dass der Destruktor möglicherweise blockiert, damit der Freigabezustand in den Bereitschaftszustand wechseln kann.  
  
 Die Pseudofunktion `INVOKE` wird in [\<functional>](../standard-library/functional.md) definiert.  
  
##  <a name="future_category"></a> future_category  
 Gibt einen Verweis auf das [error_category](../standard-library/error-category-class.md)-Objekt zurück, das Fehler bestimmt, die `future`-Objekten zugeordnet werden.  
  
```
const error_category& future_category() noexcept;
```  
  
##  <a name="make_error_code"></a> make_error_code  
 Erstellt ein [error_code](../standard-library/error-code-class.md)-Objekt zusammen mit dem [error_category](../standard-library/error-category-class.md)-Objekt, mit dem [zukünftige](../standard-library/future-class.md) Fehler bestimmt werden.  
  
```
inline error_code make_error_code(future_errc Errno) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Errno`  
 Ein [future_errc](../standard-library/future-enums.md#future_errc)-Wert, mit dem die gemeldeten Fehler identifiziert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 `error_code(static_cast<int>(Errno), future_category());`  
  
##  <a name="make_error_condition"></a> make_error_condition  
 Erstellt ein [error_condition](../standard-library/error-condition-class.md)-Objekt zusammen mit dem [error_category](../standard-library/error-category-class.md)-Objekt, das [future](../standard-library/future-class.md)-Fehler bestimmt.  
  
```
inline error_condition make_error_condition(future_errc Errno) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Errno`  
 Ein [future_errc](../standard-library/future-enums.md#future_errc)-Wert, mit dem die gemeldeten Fehler identifiziert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 `error_condition(static_cast<int>(Errno), future_category());`  
  
##  <a name="swap"></a>  swap  
 Tauscht den *zugeordneten asynchronen Zustand* eines `promise`-Objekts mit dem des anderen aus.  
  
```
template <class Ty>
void swap(promise<Ty>& Left, promise<Ty>& Right) noexcept;

template <class Ty, class... ArgTypes>
void swap(packaged_task<Ty(ArgTypes...)>& Left, packaged_task<Ty(ArgTypes...)>& Right) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
 `Left`  
 Das linke `promise`-Objekt.  
  
 `Right`  
 Das rechte `promise`-Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [\<future>](../standard-library/future.md)



