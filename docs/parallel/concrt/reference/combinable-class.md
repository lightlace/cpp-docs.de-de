---
title: combinable-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- combinable
- PPL/concurrency::combinable
- PPL/concurrency::combinable::combinable
- PPL/concurrency::combinable::clear
- PPL/concurrency::combinable::combine
- PPL/concurrency::combinable::combine_each
- PPL/concurrency::combinable::local
dev_langs:
- C++
helpviewer_keywords:
- combinable class
ms.assetid: fe0bfbf6-6250-47da-b8d0-f75369f0b5be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 695081e6513965a89222d1108c632e2f22580184
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689203"
---
# <a name="combinable-class"></a>combinable-Klasse
Das `combinable<T>`-Objekt ist dazu gedacht, threadprivate Kopien von Daten bereitzustellen, mit denen sperrenfreie, threadlokale Unterberechnungen in parallelen Algorithmen durchgeführt werden können. Am Ende des Parallelvorgangs können die threadprivaten Unterbrechungen in einem Endergebnis zusammengeführt werden. Diese Klasse kann anstelle einer freigegebenen Variable verwendet werden, und sie kann zu einer Leistungsverbesserung führen, wenn andernfalls Konflikte mit dieser freigegebenen Variable entstehen würden.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename T>
class combinable;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Datentyp für das zusammengeführte Endergebnis. Der Typ muss es sich um einen Kopierkonstruktor und einen Standardkonstruktor verfügen.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[combinable](#ctor)|Überladen. Erstellt ein neues `combinable`-Objekt.|  
|[~ combinable-Destruktor](#dtor)|Zerstört ein `combinable`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[clear](#clear)|Löscht alle berechneten Zwischenergebnisse aus einer früheren Verwendung.|  
|[combine](#combine)|Berechnet einen endgültigen Wert aus der Gruppe der threadlokale unterberechnungen durch Aufrufen der Funktionselement angegebenen kombinieren.|  
|[combine_each](#combine_each)|Berechnet einen endgültigen Wert aus der Gruppe der threadlokale unterberechnungen durch Aufrufen der angegebenen kombinieren Funktionselement einmal pro Thread-lokalen untergeordnete Berechnung an. Das Endergebnis werden durch das Funktionsobjekt gesammelt.|  
|[local](#local)|Überladen. Gibt einen Verweis auf die untergeordnete Threads privaten-Berechnung.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[operator=](#operator_eq)|Weist eine `combinable` Objekt von einem anderen `combinable` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `combinable`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ppl.h  
  
 **Namespace:** Parallelität  
  
##  <a name="clear"></a> Deaktivieren 

 Löscht alle berechneten Zwischenergebnisse aus einer früheren Verwendung.  
  
```
void clear();
```  
  
##  <a name="ctor"></a> combinable 

 Erstellt ein neues `combinable`-Objekt.  
  
```
combinable();

template <typename _Function>
explicit combinable(_Function _FnInitialize);

combinable(const combinable& _Copy);
```  
  
### <a name="parameters"></a>Parameter  
 `_Function`  
 Der Typ des Objekts Funktionselement Initialisierung.  
  
 `_FnInitialize`  
 Eine Funktion, die aufgerufen wird, um jeder neuen Threads privaten-Wert des Typs initialisieren `T`. Es muss einen Funktionsaufrufoperator mit der Signatur unterstützen `T ()`.  
  
 `_Copy`  
 Eine vorhandene `combinable` Objekt, das in dieses Objekt kopiert werden.  
  
### <a name="remarks"></a>Hinweise  
 Der erste Konstruktor initialisiert neue Elemente mit dem Standardkonstruktor für den Typ `T`.  
  
 Der zweite Konstruktor initialisiert die neue Elemente, die als angegebene Funktionselement für die Initialisierung mithilfe der `_FnInitialize` Parameter.  
  
 Der dritte Konstruktor ist der Kopierkonstruktor.  
  
##  <a name="dtor"></a> ~ combinable 

 Zerstört ein `combinable`-Objekt.  
  
```
~combinable();
```  
  
##  <a name="combine"></a> Kombinieren 

 Berechnet einen endgültigen Wert aus der Gruppe der threadlokale unterberechnungen durch Aufrufen der Funktionselement angegebenen kombinieren.  
  
```
template<typename _Function>
T combine(_Function _FnCombine) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Function`  
 Der Typ des Funktionsobjekts ab, das aufgerufen wird, um zwei threadlokale unterberechnungen kombinieren.  
  
 `_FnCombine`  
 Das Funktionselement ist, das verwendet wird, um die unterberechnungen kombinieren. Die Signatur lautet `T (T, T)` oder `T (const T&, const T&)`, und assoziativen und kommutativen sein muss.  
  
### <a name="return-value"></a>Rückgabewert  
 Das endgültige Ergebnis der Kombination von allen Threads privaten unterberechnungen.  
  
##  <a name="combine_each"></a> combine_each 

 Berechnet einen endgültigen Wert aus der Gruppe der threadlokale unterberechnungen durch Aufrufen der angegebenen kombinieren Funktionselement einmal pro Thread-lokalen untergeordnete Berechnung an. Das Endergebnis werden durch das Funktionsobjekt gesammelt.  
  
```
template<typename _Function>
void combine_each(_Function _FnCombine) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Function`  
 Der Typ des Funktionsobjekts ab, das aufgerufen wird, um einen einzelnen Thread-lokalen untergeordnete Berechnung zu kombinieren.  
  
 `_FnCombine`  
 Das Funktionselement ist, das verwendet wird, um eine untergeordnete Berechnung zu kombinieren. Die Signatur lautet `void (T)` oder `void (const T&)`, assoziativen und kommutativen muss.  
  
##  <a name="local"></a> lokale 

 Gibt einen Verweis auf die untergeordnete Threads privaten-Berechnung.  
  
```
T& local();

T& local(bool& _Exists);
```  
  
### <a name="parameters"></a>Parameter  
 `_Exists`  
 Ein Verweis auf einen booleschen Wert. Der boolesche Wert, der durch dieses Argument verwiesen wird festgelegt werden `true` , wenn die untergeordnete Berechnung bereits vorhanden, in diesem Thread war, und legen Sie auf `false` war dies die erste untergeordnete Berechnung in diesem Thread.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf die untergeordnete Threads privaten-Berechnung.  
  
##  <a name="operator_eq"></a> Operator = 

 Weist eine `combinable` Objekt von einem anderen `combinable` Objekt.  
  
```
combinable& operator= (const combinable& _Copy);
```  
  
### <a name="parameters"></a>Parameter  
 `_Copy`  
 Eine vorhandene `combinable` Objekt, das in dieses Objekt kopiert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das `combinable`-Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
