---
title: Cancellation_token-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cancellation_token
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::cancellation_token
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::deregister_callback
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::is_cancelable
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::is_canceled
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::none
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::register_callback
dev_langs:
- C++
helpviewer_keywords:
- cancellation_token class
ms.assetid: 2787df2b-e9d3-440e-bfd0-841a46a9835f
caps.latest.revision: 10
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
ms.openlocfilehash: d17505a117c0affd8106afad9004e6ec86602a26
ms.contentlocale: de-de
ms.lasthandoff: 03/17/2017

---
# <a name="cancellationtoken-class"></a>cancellation_token-Klasse
Mit der `cancellation_token`-Klasse kann bestimmt werden, ob für einen Vorgang ein Abbruch angefordert wurde. Dem angegebenen Token kann `task_group`, `structured_task_group` oder `task` zugeordnet werden, um einen impliziten Abbruch bereitzustellen. Es kann auch zum Abbruch abgerufen oder für einen Rückruf registriert werden, wenn das zugeordnete `cancellation_token_source`-Element abgebrochen wird.  
  
## <a name="syntax"></a>Syntax  
  
```
class cancellation_token;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[cancellation_token](#ctor)||  
|[~ Cancellation_token-Destruktor](#dtor)||  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[deregister_callback](#deregister_callback)|Entfernt einen Rückruf, der zuvor über die Methode `register` registriert wurde, auf Grundlage des `cancellation_token_registration`-Objekts, das zum Zeitpunkt der Registrierung zurückgegeben wurde.|  
|[is_cancelable](#is_cancelable)|Gibt einen Hinweis zurück, ob dieses Token abgebrochen werden kann oder nicht.|  
|[is_canceled](#is_canceled)|Gibt `true` zurück, wenn das Token abgebrochen wurde.|  
|[none](#none)|Gibt ein Abbruchtoken zurück, das nie abgebrochen werden kann.|  
|[register_callback](#register_callback)|Verknüpft eine Rückruffunktion mit dem Token. Wenn das Token abgebrochen wird, wird der Rückruf vorgenommen. Wurde das Token bereits abgebrochen, wenn diese Methode aufgerufen wird, wird der Rückruf sofort und synchron ausgeführt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[operator!=](#operator_neq)||  
|[operator=](#operator_eq)||  
|[operator==](#operator_eq_eq)||  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `cancellation_token`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** pplcancellation_token.h  
  
 **Namespace:** Parallelität  
  
##  <a name="dtor"></a>~ Cancellation_token 

```
~cancellation_token();
```  
  
##  <a name="ctor"></a>cancellation_token 

```
cancellation_token(const cancellation_token& _Src);

cancellation_token(cancellation_token&& _Src);
```  
  
### <a name="parameters"></a>Parameter  
 `_Src`  
  
##  <a name="deregister_callback"></a>deregister_callback 

 Entfernt einen Rückruf, der zuvor über die Methode `register` registriert wurde, auf Grundlage des `cancellation_token_registration`-Objekts, das zum Zeitpunkt der Registrierung zurückgegeben wurde.  
  
```
void deregister_callback(const cancellation_token_registration& _Registration) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Registration`  
 Das `cancellation_token_registration`-Objekt für den Rückruf, dessen Registrierung aufgehoben werden soll. Dieses Token muss zuvor von einem Aufruf der `register`-Methode zurückgegeben worden sein.  
  
##  <a name="is_cancelable"></a>is_cancelable 

 Gibt einen Hinweis zurück, ob dieses Token abgebrochen werden kann oder nicht.  
  
```
bool is_cancelable() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Hinweis darauf, ob dieses Token abgebrochen werden kann oder nicht.  
  
##  <a name="is_canceled"></a>is_canceled 

 Gibt `true` zurück, wenn das Token abgebrochen wurde.  
  
```
bool is_canceled() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert `true`, wenn das Token abgebrochen wurde, andernfalls der Wert `false`.  
  
##  <a name="none"></a>keine 

 Gibt ein Abbruchtoken zurück, das nie abgebrochen werden kann.  
  
```
static cancellation_token none();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Abbruchtoken, das nicht abgebrochen werden kann.  
  
##  <a name="operator_neq"></a>Operator! = 

```
bool operator!= (const cancellation_token& _Src) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Src`  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="operator_eq"></a>Operator = 

```
cancellation_token& operator= (const cancellation_token& _Src);

cancellation_token& operator= (cancellation_token&& _Src);
```  
  
### <a name="parameters"></a>Parameter  
 `_Src`  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="operator_eq_eq"></a>Operator == 

```
bool operator== (const cancellation_token& _Src) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Src`  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="register_callback"></a>register_callback 

 Verknüpft eine Rückruffunktion mit dem Token. Wenn das Token abgebrochen wird, wird der Rückruf vorgenommen. Wurde das Token bereits abgebrochen, wenn diese Methode aufgerufen wird, wird der Rückruf sofort und synchron ausgeführt.  
  
```
template<typename _Function>
::Concurrency::cancellation_token_registration register_callback(const _Function& _Func) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Function`  
 Der Typ des Funktionsobjekts, das zurückgerufen wird, wenn dieses `cancellation_token` abgebrochen wird.  
  
 `_Func`  
 Das Funktionsobjekt, das zurückgerufen wird, wenn dieses `cancellation_token` abgebrochen wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `cancellation_token_registration`-Objekt, das in der `deregister`-Methode verwendet werden kann, um einen bereits registrierten Rückruf aufzuheben, damit er nicht ausgeführt wird. Löst die Methode eine [Invalid_operation](invalid-operation-class.md) -Ausnahme aus, wenn der Aufruf für einen `cancellation_token` -Objekt, das mit der [cancellation_token:: None](#none) Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

