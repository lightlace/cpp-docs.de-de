---
title: Accelerator_view-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amprt/Concurrency::accelerator_view
dev_langs:
- C++
helpviewer_keywords:
- accelerator_view class
ms.assetid: 9f298c21-bf62-46e0-88b8-01c5c78ef144
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 78569f1ff21af3ed05cb908a851f0fe05d5d271a
ms.lasthandoff: 02/24/2017

---
# <a name="acceleratorview-class"></a>accelerator_view-Klasse
Stellt die Abstraktion eines virtuellen Geräts für einen datenparallelen C++ AMP-Beschleuniger dar.  
  
### <a name="syntax"></a>Syntax  
  
```  
class accelerator_view;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Accelerator_view-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `accelerator_view`-Klasse.|  
|[~ Accelerator_view-Destruktor](#dtor)|Zerstört das `accelerator_view`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Create_marker-Methode](#create_marker)|Gibt ein future-Objekt zurück, um den Abschluss aller Befehle nachzuverfolgen, die bis jetzt zu diesem `accelerator_view`-Objekt gesendet wurden.|  
|[Flush-Methode](#flush)|Sendet alle ausstehenden Befehle, die im `accelerator_view`-Objekt zur Ausführung der Zugriffstaste in die Warteschlange gestellt werden.|  
|[Get_accelerator-Methode](#get_accelerator)|Gibt das `accelerator`-Objekt für das `accelerator_view`-Objekt zurück.|  
|[Get_is_auto_selection-Methode](#get_is_auto_selection)|Gibt einen booleschen Wert, der angibt, ob die Laufzeit automatisch eine entsprechende Zugriffstaste auswählt, wenn die `accelerator_view` -Objekt übergeben wird ein [Parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).|  
|[Get_is_debug-Methode](#get_is_debug)|Gibt einen booleschen Wert zurück, der angibt, ob für das `accelerator_view`-Objekt die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.|  
|[Get_queuing_mode-Methode](#get_queuing_mode)|Gibt den Queuingmodus für das `accelerator_view`-Objekt zurück.|  
|[Get_version-Methode](#get_version)|Gibt die Version des `accelerator_view`-Objekts zurück.|  
|[Wait-Methode](#wait)|Wartet, bis alle an das `accelerator_view`-Objekt gesendeten Befehle abgeschlossen sind.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Operator! =-Operator](#operator_neq)|Vergleicht dieses `accelerator_view`-Objekt mit einem anderen und gibt `false` zurück, wenn sie identisch sind; gibt andernfalls `true` zurück.|  
|[Operator =-Operator](#operator_eq)|Kopiert den Inhalt des angegebenen `accelerator_view`-Objekts in dieses Objekt.|  
|[Operator ==-Operator](#operator_eq_eq)|Vergleicht dieses `accelerator_view`-Objekt mit einem anderen und gibt `true` zurück, wenn sie identisch sind; gibt andernfalls `false` zurück.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Accelerator-Datenmember](#accelerator)|Ruft das `accelerator`-Objekt für das `accelerator_view`-Objekt ab.|  
|[Is_auto_selection-Datenmember](#is_auto_selection)|Ruft einen booleschen Wert, der angibt, ob die Laufzeit automatisch eine entsprechende Zugriffstaste auswählt, wenn die `accelerator_view` -Objekt übergeben wird ein [Parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).|  
|[Is_debug-Datenmember](#is_debug)|Ruft einen booleschen Wert ab, der angibt, ob für das `accelerator_view`-Objekt die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.|  
|[Queuing_mode-Datenmember](#queuing_mode)|Ruft den Queuingmodus für das `accelerator_view`-Objekt ab.|  
|[Version-Datenmember](#version)|Ruft die Version der Zugriffstaste ab.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `accelerator_view`  
  
### <a name="remarks"></a>Hinweise  
 Ein `accelerator_view`-Objekt stellt eine logische, isolierte Ansicht einer Zugriffstaste dar. Ein einzelnes physisches Berechnungsgerät kann über viele logische, isolierte `accelerator_view`-Objekte verfügen. Jede Zugriffstaste verfügt über ein Standard-`accelerator_view`-Objekt. Zusätzliche `accelerator_view`-Objekte können erstellt werden.  
  
 Physische Geräte können für viele Clientthreads freigegeben werden. Clientthreads können dasselbe `accelerator_view`-Objekt einer Zugriffstaste kooperativ verwenden oder jeder Client kann mit einem Berechnungsgerät über ein unabhängiges `accelerator_view`-Objekt zur Abgrenzung gegenüber anderen Clientthreads kommunizieren.  
  
 Ein `accelerator_view` Objekt kann eine von zwei haben [Queuing_mode-Enumeration](concurrency-namespace-enums-amp.md#queuing_mode) Zustände. Wenn der Queuingmodus `immediate` ist, werden Befehle wie `copy` und `parallel_for_each` an das entsprechende Zugriffstastengerät gesendet, sobald sie zum Aufrufer zurückkehren. Wenn der Queuingmodus `deferred` ist, werden solche Befehle in die Warteschlange einer Befehlswarteschlange gestellt, die dem `accelerator_view`-Objekt entspricht. Die Befehle werden erst an das Gerät gesendet, wenn `flush()` aufgerufen wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amprt.h  
  
 **Namespace:** Parallelität  

## <a name="a-nameacceleratora-accelerator"></a><a name="accelerator"></a>Zugriffstaste 

Ruft die Accelerator-Objekt für das Accelerator_view-Objekt ab.  
  
### <a name="syntax"></a>Syntax  
  
```  
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;  
```  
  
## <a name="a-namectora-acceleratorview"></a><a name="ctor"></a>accelerator_view-Objekt 

Initialisiert eine neue Instanz der Accelerator_view-Klasse durch Kopieren einer vorhandenen `accelerator_view` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
accelerator_view( const accelerator_view & _Other );  
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Das zu kopierende `accelerator_view`-Objekt.  
  
## <a name="a-nameacceleratorviewcreatemarkera-createmarker"></a><a name="accelerator_view__create_marker"></a>create_marker 

Gibt ein future-Objekt zurück, um den Abschluss aller Befehle nachzuverfolgen, die bis jetzt zu diesem `accelerator_view`-Objekt gesendet wurden.  
  
### <a name="syntax"></a>Syntax  
  
```  
concurrency::completion_future create_marker();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein future-Objekt zum Nachverfolgen des Abschlusses aller Befehle, die bis jetzt zu diesem `accelerator_view`-Objekt gesendet wurden.  
  
## <a name="a-nameflusha-flush"></a><a name="flush"></a>leeren 

Sendet alle ausstehenden Befehle an das Accelerator_view-Objekt, das die Zugriffstaste für die Ausführung in der Warteschlange befinden.  
  
### <a name="syntax"></a>Syntax  
  
```  
void flush();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `void`zurück.  

## <a name="a-nameacceleratorviewgetacceleratora-getaccelerator"></a><a name="accelerator_view__get_accelerator"></a>get_accelerator 

Gibt das Accelerator für das Accelerator_view-Objekt zurück.
### <a name="syntax"></a>Syntax
```
accelerator get_accelerator() const;
```
### <a name="return-value"></a>Rückgabewert
Der Accelerator-Objekt für das Accelerator_view-Objekt.

## <a name="a-nameacceleratorviewgetisautoselectiona-getisautoselection"></a><a name="accelerator_view__get_is_auto_selection"></a>get_is_auto_selection 

Gibt einen booleschen Wert, der angibt, ob die Laufzeit automatisch eine entsprechende Zugriffstaste auswählt, wenn das accelerator_view-Objekt übergeben wird ein [Parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).  
  
### <a name="syntax"></a>Syntax  
  
```  
bool get_is_auto_selection() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Laufzeit eine entsprechende Zugriffstaste automatisch auswählt; andernfalls `false`.  
  
## <a name="a-nameacceleratorviewgetisdebuga-getisdebug"></a><a name="accelerator_view__get_is_debug"></a>get_is_debug 

Gibt einen booleschen Wert, der angibt, ob das Accelerator_view-Objekt die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.  
  
### <a name="syntax"></a>Syntax  
  
```  
bool get_is_debug() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein boolescher Wert, der angibt, ob die `accelerator_view` -Objekt die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.  

## <a name="a-nameacceleratorviewgetqueuingmodea-getqueuingmode"></a><a name="accelerator_view__get_queuing_mode"></a>get_queuing_mode 

Gibt den queuingmodus für das Accelerator_view-Objekt zurück.  
  
### <a name="syntax"></a>Syntax  
  
```  
queuing_mode get_queuing_mode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Den queuingmodus für das `accelerator_view` Objekt.  
  
## <a name="a-nameacceleratorviewgetversiona-getversion"></a><a name="accelerator_view__get_version"></a>get_version 

Gibt die Version der "accelerator_view" zurück.  
  
### <a name="syntax"></a>Syntax  
  
```  
unsigned int get_version() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Version der `accelerator_view`.  
  
## <a name="a-nameacceleratorviewisautoselectiona-isautoselection"></a><a name="accelerator_view__is_auto_selection"></a>is_auto_selection 

Ruft einen booleschen Wert, der angibt, ob die Laufzeit automatisch eine entsprechende Zugriffstaste auswählt, wenn das accelerator_view-Objekt übergeben wird ein [Parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).  
  
### <a name="syntax"></a>Syntax  
  
```  
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;  
```  
  
## <a name="a-nameacceleratorviewisdebuga-isdebug"></a><a name="accelerator_view__is_debug"></a>is_debug 

Ruft einen booleschen Wert, der angibt, ob das Accelerator_view-Objekt die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.  
  
### <a name="syntax"></a>Syntax  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
## <a name="a-nameacceleratorviewoperatorneqa-operator"></a><a name="accelerator_view__operator_neq"></a>Operator! = 

Vergleicht dieses Accelerator_view-Objekt mit einem anderen und gibt `false` werden; andernfalls `true`.  
  
### <a name="syntax"></a>Syntax  
  
```  
bool operator!= (    const accelerator_view & _Other ) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Die `accelerator_view` dieses Objekt zu vergleichende Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `false`, wenn die beiden Objekte identisch sind, andernfalls `true`.  
  
## <a name="a-nameacceleratorviewoperatoreqa-operator"></a><a name="accelerator_view__operator_eq"></a>Operator = 

Kopiert den Inhalt der angegebenen Accelerator_view-Objekt in dieses Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
accelerator_view & operator= (    const accelerator_view & _Other );  
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Das `accelerator_view`-Objekt, aus dem kopiert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf die geänderte `accelerator_view` Objekt.  
  
## <a name="a-nameacceleratorviewoperatoreqeqa-operator"></a><a name="accelerator_view__operator_eq_eq"></a>Operator == 

Vergleicht dieses Accelerator_view-Objekt mit einem anderen und gibt `true` werden; andernfalls `false`.  
  
### <a name="syntax"></a>Syntax  
  
```  
bool operator= = (    const accelerator_view & _Other ) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Die `accelerator_view` dieses Objekt zu vergleichende Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die beiden Objekte identisch sind, andernfalls `false`.  
  
## <a name="a-nameacceleratorviewqueuingmodea-queuingmode"></a><a name="accelerator_view__queuing_mode"></a>queuing_mode 

Ruft den queuingmodus für das Accelerator_view-Objekt ab.  
  
### <a name="syntax"></a>Syntax  
  
```  
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;  
```  
  
## <a name="a-nameacceleratorviewversiona-version"></a><a name="accelerator_view__version"></a>Version 

Ruft die Version der "accelerator_view" ab.  
  
### <a name="syntax"></a>Syntax  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
## <a name="a-nameacceleratorviewwaita-wait"></a><a name="accelerator_view__wait"></a>Warte 

Wartet, bis alle Befehle an das Accelerator_view-Objekt übermittelt auf Fertig stellen.  
  
### <a name="syntax"></a>Syntax  
  
```  
void wait();  
```  
  
#### <a name="return-value"></a>Rückgabewert  
 Gibt `void`zurück.  
  
#### <a name="remarks"></a>Hinweise  
 Wenn die [Queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) ist `immediate`, diese Methode kehrt sofort zurück, ohne zu blockieren.  
  
##  <a name="a-namedtora-acceleratorview"></a><a name="dtor"></a>~ accelerator_view-Objekt 

 Zerstört das Accelerator_view-Objekt.  
  
#### <a name="syntax"></a>Syntax  
  
```  
~accelerator_view();  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
 
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++-AMP)](concurrency-namespace-cpp-amp.md)

