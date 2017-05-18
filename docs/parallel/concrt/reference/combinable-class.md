---
title: combinable-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: a491f8eef59978808608917531a5237cceacdb21
ms.contentlocale: de-de
ms.lasthandoff: 03/17/2017

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
 Der Datentyp des endgültigen zusammengeführten Ergebnisses. Der Typ muss es sich um einen Kopierkonstruktor und einen Standardkonstruktor verfügen.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[combinable](#ctor)|Überladen. Erstellt ein neues `combinable`-Objekt.|  
|[~ combinable-Destruktor](#dtor)|Zerstört ein `combinable`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[clear](#clear)|Löscht alle berechneten Zwischenergebnisse aus einer vorherigen Verwendung.|  
|[combine](#combine)|Berechnet einen endgültigen Wert aus dem Satz von threadlokale unterberechnungen durch Aufrufen der Funktionselement bereitgestellten kombinieren.|  
|[combine_each](#combine_each)|Berechnet einen endgültigen Wert aus dem Satz von threadlokale unterberechnungen durch Aufrufen der angegebenen kombinieren Funktionselement einmal pro Thread-lokalen untergeordnete Berechnung. Das Endergebnis wird vom Funktionsobjekt akkumuliert.|  
|[lokale](#local)|Überladen. Gibt einen Verweis auf die untergeordnete threadprivate-Berechnung.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[operator=](#operator_eq)|Weist eine `combinable` -Objekt von einem anderen `combinable` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `combinable`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ppl.h  
  
 **Namespace:** Parallelität  
  
##  <a name="clear"></a>Deaktivieren 

 Löscht alle berechneten Zwischenergebnisse aus einer vorherigen Verwendung.  
  
```
void clear();
```  
  
##  <a name="ctor"></a>combinable 

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
 Eine Funktion, die aufgerufen wird, um jeden neuen privaten-Wert des Typs initialisieren `T`. Es muss einen Funktionsaufrufoperator mit der Signatur unterstützen `T ()`.  
  
 `_Copy`  
 Eine vorhandene `combinable` Objekt, das in dieses Objekt kopiert werden.  
  
### <a name="remarks"></a>Hinweise  
 Der erste Konstruktor initialisiert neue Elemente mit dem Standardkonstruktor für den Typ `T`.  
  
 Der zweite Konstruktor initialisiert neue Elemente als angegebene Funktionselement für die Initialisierung mithilfe der `_FnInitialize` Parameter.  
  
 Der dritte Konstruktor ist der Kopierkonstruktor.  
  
##  <a name="dtor"></a>~ combinable 

 Zerstört ein `combinable`-Objekt.  
  
```
~combinable();
```  
  
##  <a name="combine"></a>Kombinieren 

 Berechnet einen endgültigen Wert aus dem Satz von threadlokale unterberechnungen durch Aufrufen der Funktionselement bereitgestellten kombinieren.  
  
```
template<typename _Function>
T combine(_Function _FnCombine) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Function`  
 Der Typ des Funktionsobjekts, das aufgerufen wird, um zwei threadlokale unterberechnungen kombinieren.  
  
 `_FnCombine`  
 Das Funktionselement ist, das verwendet wird, um die unterberechnungen zu kombinieren. Die Signatur ist `T (T, T)` oder `T (const T&, const T&)`, und sie muss assoziativ und kommutativ sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Das endgültige Ergebnis der Kombination aller privaten unterberechnungen.  
  
##  <a name="combine_each"></a>combine_each 

 Berechnet einen endgültigen Wert aus dem Satz von threadlokale unterberechnungen durch Aufrufen der angegebenen kombinieren Funktionselement einmal pro Thread-lokalen untergeordnete Berechnung. Das Endergebnis wird vom Funktionsobjekt akkumuliert.  
  
```
template<typename _Function>
void combine_each(_Function _FnCombine) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Function`  
 Der Typ des Funktionsobjekts, das aufgerufen wird, um eine einzelne untergeordnete Thread-Local-Berechnung zu kombinieren.  
  
 `_FnCombine`  
 Das Funktionselement, das verwendet wird, um eine untergeordnete Berechnung zu kombinieren. Die Signatur ist `void (T)` oder `void (const T&)`, und Sie muss assoziativ und kommutativ sein.  
  
##  <a name="local"></a>lokale 

 Gibt einen Verweis auf die untergeordnete threadprivate-Berechnung.  
  
```
T& local();

T& local(bool& _Exists);
```  
  
### <a name="parameters"></a>Parameter  
 `_Exists`  
 Ein Verweis auf einen booleschen Wert. Der boolesche Wert, der durch dieses Argument verwiesen wird festgelegt werden `true` Wenn untergeordnete Berechnung bereits auf diesem Thread vorhanden war, und legen Sie auf `false` war dies die erste untergeordnete Berechnung in diesem Thread.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf die untergeordnete threadprivate-Berechnung.  
  
##  <a name="operator_eq"></a>Operator = 

 Weist eine `combinable` -Objekt von einem anderen `combinable` Objekt.  
  
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

