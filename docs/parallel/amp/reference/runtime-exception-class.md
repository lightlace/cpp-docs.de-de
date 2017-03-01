---
title: Runtime_exception-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::direct3d_abort
dev_langs:
- C++
helpviewer_keywords:
- runtime_exception class
ms.assetid: 8fe3ce2c-3d4c-4b9c-95e8-e592f37adefd
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 1a2655ed4c8783dd5f7a3b8af2a7d6a9db88f43e
ms.lasthandoff: 02/24/2017

---
# <a name="runtimeexception-class"></a>runtime_exception-Klasse
Der Basistyp für Ausnahmen in der C++ Accelerated Massive Parallelism (AMP)-Bibliothek.  
  
### <a name="syntax"></a>Syntax  
  
```  
class runtime_exception : public std::exception;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Runtime_exception-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `runtime_exception`-Klasse.|  
|[~ Runtime_exception-Destruktor](#dtor)|Zerstört das `runtime_exception`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Get_error_code-Methode](#runtime_exception__get_error_code)|Gibt den Fehlercode zurück, der die Ausnahme verursacht hat.|  

  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Operator =-Operator](#operator_eq)|Kopiert den Inhalt des angegebenen `runtime_exception`-Objekts in dieses Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `runtime_exception`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amprt.h  
  
 **Namespace:** Parallelität  

## <a name="a-nameruntimeexceptionctora--runtimeexception-constructor"></a><a name="runtime_exception__ctor"></a>Runtime_exception-Konstruktor  
Initialisiert eine neue Instanz der Klasse.  
  
### <a name="syntax"></a>Syntax  
  
```  
runtime_exception(  
    const char * _Message,  
    HRESULT _Hresult ) throw();  
  
explicit runtime_exception(  
    HRESULT _Hresult ) throw();  
  
runtime_exception(  
    const runtime_exception & _Other ) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 `_Message`  
 Eine Beschreibung des Fehlers, das diese Ausnahme verursacht hat.  
  
 `_Hresult`  
 Der HRESULT-Wert des Fehlers, der diese Ausnahme verursacht hat.  
  
 `_Other`  
 Das zu kopierende `runtime_exception`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Das `runtime_exception`-Objekt.  

## <a name="a-namedtora--runtimeexception-destructor"></a><a name="dtor"></a>~ Runtime_exception-Destruktor  
Das Objekt zerstört.  
  
### <a name="syntax"></a>Syntax  
  
```  
virtual ~runtime_exception() throw();  
```  
  
## <a name="a-nameruntimeexceptiongeterrorcodea--geterrorcode"></a><a name="runtime_exception__get_error_code"></a>get_error_code   
Gibt den Fehlercode zurück, der die Ausnahme verursacht hat.  
  
### <a name="syntax"></a>Syntax  
  
```  
HRESULT get_error_code() const throw();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der HRESULT-Wert des Fehlers, der diese Ausnahme verursacht hat.  
  
## <a name="a-nameruntimeexceptionoperatoreqa--operator"></a><a name="runtime_exception__operator_eq"></a> operator=   
  Kopiert den Inhalt des angegebenen `runtime_exception`-Objekts in dieses Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
runtime_exception & operator= (    const runtime_exception & _Other ) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Das zu kopierende `runtime_exception`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das `runtime_exception`-Objekt.  
  

  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++-AMP)](concurrency-namespace-cpp-amp.md)

