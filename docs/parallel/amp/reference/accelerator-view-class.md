---
title: "\"accelerator_view\"-Klasse | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- accelerator_view
- AMPRT/accelerator_view
- AMPRT/Concurrency::accelerator_view:accelerator_view
- AMPRT/Concurrency::accelerator_view:create_marker
- AMPRT/Concurrency::accelerator_view:flush
- AMPRT/Concurrency::accelerator_view:get_accelerator
- AMPRT/Concurrency::accelerator_view:get_is_auto_selection
- AMPRT/Concurrency::accelerator_view:get_is_debug
- AMPRT/Concurrency::accelerator_view:get_queuing_mode
- AMPRT/Concurrency::accelerator_view:get_version
- AMPRT/Concurrency::accelerator_view:wait
- AMPRT/Concurrency::accelerator_view:accelerator
- AMPRT/Concurrency::accelerator_view:is_auto_selection
- AMPRT/Concurrency::accelerator_view:is_debug
- AMPRT/Concurrency::accelerator_view:queuing_mode
- AMPRT/Concurrency::accelerator_view:version
dev_langs:
- C++
helpviewer_keywords:
- accelerator_view class
ms.assetid: 9f298c21-bf62-46e0-88b8-01c5c78ef144
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5160e0fa37ed8c1c40a3cdfd6ca63d3b76e2d980
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="acceleratorview-class"></a>accelerator_view-Klasse
Stellt die Abstraktion eines virtuellen Geräts für einen datenparallelen C++ AMP-Beschleuniger dar.  
  
### <a name="syntax"></a>Syntax  
  
```  
class accelerator_view;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Accelerator_view-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `accelerator_view`-Klasse.|  
|[~ Accelerator_view-Destruktor](#dtor)|Zerstört das `accelerator_view`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[create_marker](#create_marker)|Gibt ein future-Objekt zurück, um den Abschluss aller Befehle nachzuverfolgen, die bis jetzt zu diesem `accelerator_view`-Objekt gesendet wurden.|  
|[flush](#flush)|Sendet alle ausstehenden Befehle, die im `accelerator_view`-Objekt zur Ausführung der Zugriffstaste in die Warteschlange gestellt werden.|  
|[get_accelerator](#get_accelerator)|Gibt das `accelerator`-Objekt für das `accelerator_view`-Objekt zurück.|  
|[get_is_auto_selection](#get_is_auto_selection)|Gibt einen booleschen Wert, der angibt, ob die Laufzeit automatisch eine entsprechende Zugriffstaste auswählt, wenn die `accelerator_view` -Objekt übergeben wird eine [Parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).|  
|[get_is_debug](#get_is_debug)|Gibt einen booleschen Wert zurück, der angibt, ob für das `accelerator_view`-Objekt die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.|  
|[get_queuing_mode](#get_queuing_mode)|Gibt den Queuingmodus für das `accelerator_view`-Objekt zurück.|  
|[get_version](#get_version)|Gibt die Version des `accelerator_view`-Objekts zurück.|  
|[wait](#wait)|Wartet, bis alle an das `accelerator_view`-Objekt gesendeten Befehle abgeschlossen sind.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[operator!=](#operator_neq)|Vergleicht dieses `accelerator_view`-Objekt mit einem anderen und gibt `false` zurück, wenn sie identisch sind; gibt andernfalls `true` zurück.|  
|[operator=](#operator_eq)|Kopiert den Inhalt des angegebenen `accelerator_view`-Objekts in dieses Objekt.|  
|[operator==](#operator_eq_eq)|Vergleicht dieses `accelerator_view`-Objekt mit einem anderen und gibt `true` zurück, wenn sie identisch sind; gibt andernfalls `false` zurück.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[accelerator](#accelerator)|Ruft das `accelerator`-Objekt für das `accelerator_view`-Objekt ab.|  
|[is_auto_selection](#is_auto_selection)|Ruft einen booleschen Wert, der angibt, ob die Laufzeit automatisch eine entsprechende Zugriffstaste auswählt, wenn die `accelerator_view` -Objekt übergeben wird eine [Parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).|  
|[is_debug](#is_debug)|Ruft einen booleschen Wert ab, der angibt, ob für das `accelerator_view`-Objekt die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.|  
|[queuing_mode](#queuing_mode)|Ruft den Queuingmodus für das `accelerator_view`-Objekt ab.|  
|[version](#version)|Ruft die Version der Zugriffstaste ab.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `accelerator_view`  
  
### <a name="remarks"></a>Hinweise  
 Ein `accelerator_view`-Objekt stellt eine logische, isolierte Ansicht einer Zugriffstaste dar. Ein einzelnes physisches Berechnungsgerät kann über viele logische, isolierte `accelerator_view`-Objekte verfügen. Jede Zugriffstaste verfügt über ein Standard-`accelerator_view`-Objekt. Zusätzliche `accelerator_view`-Objekte können erstellt werden.  
  
 Physische Geräte können für viele Clientthreads freigegeben werden. Clientthreads können dasselbe `accelerator_view`-Objekt einer Zugriffstaste kooperativ verwenden oder jeder Client kann mit einem Berechnungsgerät über ein unabhängiges `accelerator_view`-Objekt zur Abgrenzung gegenüber anderen Clientthreads kommunizieren.  
  
 Ein `accelerator_view` Objekt kann eine von zwei haben [Queuing_mode-Enumeration](concurrency-namespace-enums-amp.md#queuing_mode) Status. Wenn der Queuingmodus `immediate` ist, werden Befehle wie `copy` und `parallel_for_each` an das entsprechende Zugriffstastengerät gesendet, sobald sie zum Aufrufer zurückkehren. Wenn der Queuingmodus `deferred` ist, werden solche Befehle in die Warteschlange einer Befehlswarteschlange gestellt, die dem `accelerator_view`-Objekt entspricht. Die Befehle werden erst an das Gerät gesendet, wenn `flush()` aufgerufen wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amprt.h  
  
 **Namespace:** Parallelität  

## <a name="accelerator"></a> Zugriffstaste 

Ruft die Zugriffstaste-Objekt für das Objekt "accelerator_view" ab.  
  
### <a name="syntax"></a>Syntax  
  
```  
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;  
```  
  
## <a name="ctor"></a> "accelerator_view" 

Initialisiert eine neue Instanz der Klasse "accelerator_view" durch Kopieren einer vorhandenen `accelerator_view` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
accelerator_view( const accelerator_view & _Other );  
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Das zu kopierende `accelerator_view`-Objekt.  
  
## <a name="accelerator_view__create_marker"></a> create_marker 

Gibt ein future-Objekt zurück, um den Abschluss aller Befehle nachzuverfolgen, die bis jetzt zu diesem `accelerator_view`-Objekt gesendet wurden.  
  
### <a name="syntax"></a>Syntax  
  
```  
concurrency::completion_future create_marker();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein future-Objekt zum Nachverfolgen des Abschlusses aller Befehle, die bis jetzt zu diesem `accelerator_view`-Objekt gesendet wurden.  
  
## <a name="flush"></a> leeren 

Sendet, dass alle ausstehenden Befehle für das Accelerator_view-Objekt, das die Zugriffstaste für die Ausführung in der Warteschlange an.  
  
### <a name="syntax"></a>Syntax  
  
```  
void flush();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `void`zurück.  

## <a name="accelerator_view__get_accelerator"></a> get_accelerator 

Gibt das Zugriffstaste für das Accelerator_view-Objekt zurück.
### <a name="syntax"></a>Syntax
```
accelerator get_accelerator() const;
```
### <a name="return-value"></a>Rückgabewert
Die Zugriffstaste-Objekt für das Accelerator_view-Objekt.

## <a name="accelerator_view__get_is_auto_selection"></a> get_is_auto_selection 

Gibt einen booleschen Wert, der angibt, ob die Common Language Runtime automatisch eine entsprechende Zugriffstaste auswählt, wenn an die "accelerator_view" übergeben wird eine [Parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).  
  
### <a name="syntax"></a>Syntax  
  
```  
bool get_is_auto_selection() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Laufzeit eine entsprechende Zugriffstaste automatisch auswählt; andernfalls `false`.  
  
## <a name="accelerator_view__get_is_debug"></a> get_is_debug 

Gibt einen booleschen Wert, der angibt, ob das Objekt "accelerator_view" die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.  
  
### <a name="syntax"></a>Syntax  
  
```  
bool get_is_debug() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein boolescher Wert, der angibt, ob die `accelerator_view` Objekt hat die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert.  

## <a name="accelerator_view__get_queuing_mode"></a> get_queuing_mode 

Gibt den queuingmodus für das Accelerator_view-Objekt zurück.  
  
### <a name="syntax"></a>Syntax  
  
```  
queuing_mode get_queuing_mode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Den queuingmodus für das `accelerator_view` Objekt.  
  
## <a name="accelerator_view__get_version"></a> get_version 

Gibt die Version der "accelerator_view" zurück.  
  
### <a name="syntax"></a>Syntax  
  
```  
unsigned int get_version() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Version der `accelerator_view`.  
  
## <a name="accelerator_view__is_auto_selection"></a> is_auto_selection 

Ruft einen booleschen Wert, der angibt, ob die Common Language Runtime automatisch eine entsprechende Zugriffstaste auswählt, wenn an die "accelerator_view" übergeben wird eine [Parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).  
  
### <a name="syntax"></a>Syntax  
  
```  
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;  
```  
  
## <a name="accelerator_view__is_debug"></a> is_debug 

Ruft einen booleschen Wert, der angibt, ob das Objekt "accelerator_view" die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.  
  
### <a name="syntax"></a>Syntax  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
## <a name="accelerator_view__operator_neq"></a> Operator! = 

Vergleicht dieses "accelerator_view"-Objekt mit einem anderen und gibt `false` , wenn sie identisch sind; gibt andernfalls wird `true`.  
  
### <a name="syntax"></a>Syntax  
  
```  
bool operator!= (    const accelerator_view & _Other ) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Die `accelerator_view` mit dieses Objekt zu vergleichende Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `false`, wenn die beiden Objekte identisch sind, andernfalls `true`.  
  
## <a name="accelerator_view__operator_eq"></a> Operator = 

Kopiert den Inhalt des Objekts angegebene "accelerator_view" in dieses Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
accelerator_view & operator= (    const accelerator_view & _Other );  
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Das `accelerator_view`-Objekt, aus dem kopiert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das geänderte `accelerator_view` Objekt.  
  
## <a name="accelerator_view__operator_eq_eq"></a> Operator == 

Vergleicht dieses "accelerator_view"-Objekt mit einem anderen und gibt `true` , wenn sie identisch sind; gibt andernfalls wird `false`.  
  
### <a name="syntax"></a>Syntax  
  
```  
bool operator= = (    const accelerator_view & _Other ) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Die `accelerator_view` mit dieses Objekt zu vergleichende Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die beiden Objekte identisch sind, andernfalls `false`.  
  
## <a name="accelerator_view__queuing_mode"></a> queuing_mode 

Ruft den queuingmodus für das Objekt "accelerator_view" ab.  
  
### <a name="syntax"></a>Syntax  
  
```  
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;  
```  
  
## <a name="accelerator_view__version"></a> Version 

Ruft die Version der "accelerator_view" ab.  
  
### <a name="syntax"></a>Syntax  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
## <a name="accelerator_view__wait"></a> Warte 

Wartet, bis alle gesendeten Befehle mit dem Accelerator_view-Objekt abgeschlossen.  
  
### <a name="syntax"></a>Syntax  
  
```  
void wait();  
```  
  
#### <a name="return-value"></a>Rückgabewert  
 Gibt `void`zurück.  
  
#### <a name="remarks"></a>Hinweise  
 Wenn die [Queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) ist `immediate`, diese Methode wird sofort zurückgegeben, ohne zu blockieren.  
  
##  <a name="dtor"></a> ~ accelerator_view-Objekt 

 Zerstört das Accelerator_view-Objekt.  
  
#### <a name="syntax"></a>Syntax  
  
```  
~accelerator_view();  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
 
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
