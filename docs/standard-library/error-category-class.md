---
title: error_category-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- system_error/std::error_category
- error_category
- system_error/std::error_category::value_type
- system_error/std::error_category::default_error_condition
- system_error/std::error_category::equivalent
- system_error/std::error_category::message
- system_error/std::error_category::name
dev_langs:
- C++
helpviewer_keywords:
- error_category class
ms.assetid: e0a71e14-852d-4905-acd6-5f8ed426706d
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 8a2a37464e5edb5a5fde1def70d2f0728524fad2
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="errorcategory-class"></a>error_category-Klasse
Stellt die abstrakte, allgemeine Basis für Objekte dar, die eine Fehlercodekategorie beschreibt.  
  
## <a name="syntax"></a>Syntax  
  
```
class error_category;
```  
  
## <a name="remarks"></a>Hinweise  
 `error_category` wird von zwei vordefinierten Objekten implementiert: [generic_category](../standard-library/system-error-functions.md#generic_category) und [system_category](../standard-library/system-error-functions.md#system_category).  
  
### <a name="typedefs"></a>TypeDefs  
  
|||  
|-|-|  
|[value_type](#value_type)|Ein Typ, der den gespeicherten Fehlercodewert darstellt.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[default_error_condition](#default_error_condition)|Speichert den Fehlercodewert für ein Fehlerbedingungsobjekt.|  
|[equivalent](#equivalent)|Gibt einen Wert zurück, der angibt, ob Fehlerobjekte gleichwertig sind.|  
|[message](#message)|Gibt den Namen des angegebenen Fehlercodes zurück.|  
|[name](#name)|Gibt den Namen der Kategorie zurück.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[operator==](#op_eq_eq)|Prüft auf Gleichheit zwischen `error_category`-Objekten.|  
|[operator!=](#op_neq)|Prüft auf Ungleichheit zwischen `error_category`-Objekten.|  
|[operator<](#op_lt)|Testet, ob das [error_category](../standard-library/error-category-class.md)-Objekt kleiner ist als das `error_category`-Objekt, das für den Vergleich übergeben wurde.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<system_error>  
  
 **Namespace:** std  
  
##  <a name="default_error_condition"></a> error_category::default_error_condition  
 Speichert den Fehlercodewert für ein Fehlerbedingungsobjekt.  
  
```
virtual error_condition default_error_condition(int _Errval) const;
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`_Errval`|Der Fehlercodewert, der in [error_condition](../standard-library/error-condition-class.md) gespeichert werden soll.|  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `error_condition(_Errval, *this)`zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="equivalent"></a> error_category::equivalent  
 Gibt einen Wert zurück, der angibt, ob Fehlerobjekte gleichwertig sind.  
  
```
virtual bool equivalent(value_type _Errval,
    const error_condition& _Cond) const;

virtual bool equivalent(const error_code& _Code,
    value_type _Errval) const;
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`_Errval`|Der zu vergleichende Fehlercodewert.|  
|`_Cond`|Das zu vergleichende [error_condition](../standard-library/error-condition-class.md)-Objekt.|  
|`_Code`|Das zu vergleichende [error_code](../standard-library/error-code-class.md)-Objekt.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn Kategorie und Wert gleich sind; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion gibt `*this == _Cond.category() && _Cond.value() == _Errval` zurück.  
  
 Die zweite Memberfunktion gibt `*this == _Code.category() && _Code.value() == _Errval` zurück.  
  
##  <a name="message"></a> error_category::message  
 Gibt den Namen des angegebenen Fehlercodes zurück.  
  
```
virtual string message(error_code::value_type val) const = 0;
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`val`|Der zu beschreibende Fehlercodewert.|  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen beschreibenden Namen des Fehlercodes `val` für die Kategorie zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="name"></a> error_category::name  
 Gibt den Namen der Kategorie zurück.  
  
```
virtual const char *name() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Namen der Kategorie als Bytezeichenfolge zurück, die mit null endet.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="op_eq_eq"></a> error_category::operator==  
 Prüft auf Gleichheit zwischen `error_category`-Objekten.  
  
```
bool operator==(const error_category& right) const;
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`right`|Das Objekt, das auf Gleichheit getestet werden soll.|  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn die Objekte gleich sind; **FALSE**, wenn die Objekte nicht gleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Memberoperator gibt `this == &right` zurück.  
  
##  <a name="op_neq"></a> error_category::operator!=  
 Prüft auf Ungleichheit zwischen `error_category`-Objekten.  
  
```
bool operator!=(const error_category& right) const;
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`right`|Das Objekt, das auf Ungleichheit geprüft werden soll.|  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn das Objekt `error_category` nicht dem Objekt `error_category` entspricht, das an `right` übergeben wird; andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Der Memberoperator gibt `(!*this == right)` zurück.  
  
##  <a name="op_lt"></a> error_category::operator&lt;  
 Testet, ob das [error_category](../standard-library/error-category-class.md)-Objekt kleiner ist als das `error_category`-Objekt, das für den Vergleich übergeben wurde.  
  
```
bool operator<(const error_category& right) const;
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`right`|Das zu vergleichende `error_category`-Objekt.|  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn das Objekt, das an `error_category` übergeben wird, kleiner ist als das an `error_category` übergebene Objekt; andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Der Memberoperator gibt `this < &right` zurück.  
  
##  <a name="value_type"></a> error_category::value_type  
 Ein Typ, der den gespeicherten Fehlercodewert darstellt.  
  
```
typedef int value_type;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Typdefinition ist ein Synonym für `int`.  
  
## <a name="see-also"></a>Siehe auch  
 [<system_error>](../standard-library/system-error.md)




