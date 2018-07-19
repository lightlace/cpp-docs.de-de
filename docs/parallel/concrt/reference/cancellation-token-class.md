---
title: Cancellation_token-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5d8741763295e96f3d0c221b687c8ef62fbfc55c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33695940"
---
# <a name="cancellationtoken-class"></a>cancellation_token-Klasse
Mit der `cancellation_token`-Klasse kann bestimmt werden, ob für einen Vorgang ein Abbruch angefordert wurde. Dem angegebenen Token kann `task_group`, `structured_task_group` oder `task` zugeordnet werden, um einen impliziten Abbruch bereitzustellen. Es kann auch zum Abbruch abgerufen oder für einen Rückruf registriert werden, wenn das zugeordnete `cancellation_token_source`-Element abgebrochen wird.  
  
## <a name="syntax"></a>Syntax  
  
```
class cancellation_token;
```  
  
## <a name="members"></a>Member  
  
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
  
##  <a name="dtor"></a> ~ Cancellation_token 

```
~cancellation_token();
```  
  
##  <a name="ctor"></a> "cancellation_token" 

```
cancellation_token(const cancellation_token& _Src);

cancellation_token(cancellation_token&& _Src);
```  
  
### <a name="parameters"></a>Parameter  
 `_Src`  
  
##  <a name="deregister_callback"></a> deregister_callback 

 Entfernt einen Rückruf, der zuvor über die Methode `register` registriert wurde, auf Grundlage des `cancellation_token_registration`-Objekts, das zum Zeitpunkt der Registrierung zurückgegeben wurde.  
  
```
void deregister_callback(const cancellation_token_registration& _Registration) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Registration`  
 Das `cancellation_token_registration`-Objekt für den Rückruf, dessen Registrierung aufgehoben werden soll. Dieses Token muss zuvor von einem Aufruf der `register`-Methode zurückgegeben worden sein.  
  
##  <a name="is_cancelable"></a> is_cancelable 

 Gibt einen Hinweis zurück, ob dieses Token abgebrochen werden kann oder nicht.  
  
```
bool is_cancelable() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Hinweis darauf, ob dieses Token abgebrochen werden kann oder nicht.  
  
##  <a name="is_canceled"></a> is_canceled 

 Gibt `true` zurück, wenn das Token abgebrochen wurde.  
  
```
bool is_canceled() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert `true`, wenn das Token abgebrochen wurde, andernfalls der Wert `false`.  
  
##  <a name="none"></a> Keine 

 Gibt ein Abbruchtoken zurück, das nie abgebrochen werden kann.  
  
```
static cancellation_token none();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Abbruchtoken, das nicht abgebrochen werden kann.  
  
##  <a name="operator_neq"></a> Operator! = 

```
bool operator!= (const cancellation_token& _Src) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Src`  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="operator_eq"></a> Operator = 

```
cancellation_token& operator= (const cancellation_token& _Src);

cancellation_token& operator= (cancellation_token&& _Src);
```  
  
### <a name="parameters"></a>Parameter  
 `_Src`  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="operator_eq_eq"></a> Operator == 

```
bool operator== (const cancellation_token& _Src) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Src`  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="register_callback"></a> register_callback 

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
 Ein `cancellation_token_registration`-Objekt, das in der `deregister`-Methode verwendet werden kann, um einen bereits registrierten Rückruf aufzuheben, damit er nicht ausgeführt wird. Die Methode löst eine [Invalid_operation](invalid-operation-class.md) -Ausnahme aus, wenn der Aufruf für eine `cancellation_token` -Objekt, das mit erstellt wurde die [cancellation_token:: None](#none) Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
