---
title: Cancellation_token_registration-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- pplcancellation_token/concurrency::cancellation_token_registration
dev_langs:
- C++
helpviewer_keywords:
- cancellation_token_registration class
ms.assetid: 823d63f4-7233-4d65-8976-6152ccf12d0e
caps.latest.revision: 9
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
ms.openlocfilehash: 72c317bb95b646a3a97b361ac3248f015cd0f29a
ms.lasthandoff: 02/24/2017

---
# <a name="cancellationtokenregistration-class"></a>cancellation_token_registration-Klasse
Die `cancellation_token_registration`-Klasse stellt eine Rückrufbenachrichtigung von `cancellation_token` dar. Bei Verwendung der `register`-Methode auf `cancellation_token` zum Empfangen von Benachrichtigungen darüber, wann ein Abbruch auftritt, wird ein `cancellation_token_registration`-Objekt als Handle an den Rückruf zurückgegeben, damit der Aufrufer mithilfe der `deregister`-Methode anfordern kann, dass ein bestimmter Rückruf nicht mehr erfolgt.  
  
## <a name="syntax"></a>Syntax  
  
```
class cancellation_token_registration;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Cancellation_token_registration-Konstruktor](#ctor)||  
|[~ Cancellation_token_registration-Destruktor](#dtor)||  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Operator! =-Operator](#operator_neq)||  
|[Operator =-Operator](#operator_eq)||  
|[Operator ==-Operator](#operator_eq_eq)||  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `cancellation_token_registration`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** pplcancellation_token.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namedtora-cancellationtokenregistration"></a><a name="dtor"></a>~ Cancellation_token_registration 

```
~cancellation_token_registration();
```  
  
##  <a name="a-namectora-cancellationtokenregistration"></a><a name="ctor"></a>cancellation_token_registration 

```
cancellation_token_registration();

cancellation_token_registration(const cancellation_token_registration& _Src);

cancellation_token_registration(cancellation_token_registration&& _Src);
```  
  
### <a name="parameters"></a>Parameter  
 `_Src`  
  
##  <a name="a-nameoperatorneqa-operator"></a><a name="operator_neq"></a>Operator! = 

```
bool operator!= (const cancellation_token_registration& _Rhs) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Rhs`  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>Operator = 

```
cancellation_token_registration& operator= (const cancellation_token_registration& _Src);

cancellation_token_registration& operator= (cancellation_token_registration&& _Src);
```  
  
### <a name="parameters"></a>Parameter  
 `_Src`  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="a-nameoperatoreqeqa-operator"></a><a name="operator_eq_eq"></a>Operator == 

```
bool operator== (const cancellation_token_registration& _Rhs) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Rhs`  
  
### <a name="return-value"></a>Rückgabewert  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

