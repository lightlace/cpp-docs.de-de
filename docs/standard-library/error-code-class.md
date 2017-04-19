---
title: error_code-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- error_code
- system_error/std::error_code
- system_error/std::error_code::value_type
- system_error/std::error_code::assign
- system_error/std::error_code::category
- system_error/std::error_code::clear
- system_error/std::error_code::default_error_condition
- system_error/std::error_code::message
- system_error/std::error_code::operator bool
dev_langs:
- C++
helpviewer_keywords:
- error_code class
ms.assetid: c09b4a96-cb14-4281-a319-63543f9b2b4a
caps.latest.revision: 17
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 4959d72feaae22cb31a5bc7b6f6aa1b5f5b8be02
ms.lasthandoff: 02/24/2017

---
# <a name="errorcode-class"></a>error_code-Klasse
Stellt Systemfehler auf niedriger Ebene dar, die spezifisch für die Implementierung sind.  
  
## <a name="syntax"></a>Syntax  
  
```
class error_code;
```  
  
## <a name="remarks"></a>Hinweise  
 Ein Objekt vom Typ `error_code`-Klasse enthält einen Fehlercodewert und einen Zeiger auf ein Objekt, das eine [Kategorie](../standard-library/error-category-class.md) von Fehlercodes darstellt, die gemeldete Systemfehler auf niedriger Ebene beschreiben.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[error_code](#error_code__error_code)|Konstruiert ein Objekt vom Typ `error_code`.|  
  
### <a name="typedefs"></a>TypeDefs  
  
|||  
|-|-|  
|[value_type](#error_code__value_type)|Ein Typ, der den gespeicherten Fehlercodewert darstellt.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[assign](#error_code__assign)|Weist einen Fehlercodewert und die Kategorie an einen Fehlercode zu.|  
|[category](#error_code__category)|Gibt die Fehlerkategorie zurück.|  
|[clear](#error_code__clear)|Löscht den Fehlercodewert und die Kategorie.|  
|[default_error_condition](#error_code__default_error_condition)|Gibt die Standardfehlerbedingung zurück.|  
|[message](#error_code__message)|Gibt den Namen des Fehlercodes zurück.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[operator==](#error_code__operator_eq_eq)|Prüft auf Gleichheit zwischen `error_code`-Objekten.|  
|[operator!=](#error_code__operator_neq)|Prüft auf Ungleichheit zwischen `error_code`-Objekten.|  
|[operator<](#error_code__operator_lt_)|Testet, ob das `error_code`-Objekt kleiner ist als das `error_code`-Objekt, das für den Vergleich übergeben wurde.|  
|[operator=](#error_code__operator_eq)|Weist dem `error_code`-Objekt einen neuen Enumerationswert zu.|  
|[operator bool](#error_code__operator_bool)|Wandelt eine Variable vom Typ `error_code` um.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<system_error>  
  
 **Namespace:** std  
  
##  <a name="error_code__assign"></a> error_code::assign  
 Weist einen Fehlercodewert und die Kategorie an einen Fehlercode zu.  
  
```
void assign(value_type val, const error_category& _Cat);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`val`|Der Fehlercodewert, der in `error_code` gespeichert werden soll.|  
|`_Cat`|Die Fehlerkategorie, die in `error_code` gespeichert werden soll.|  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion speichert `val` als Fehlercodewert und einen Zeiger auf `_Cat`.  
  
##  <a name="error_code__category"></a> error_code::category  
 Gibt die Fehlerkategorie zurück.  
  
```
const error_category& category() const;
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="error_code__clear"></a> error_code::clear  
 Löscht den Fehlercodewert und die Kategorie.  
  
```
clear();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion speichert einen Fehlercodewert „Null“ und einen Zeiger auf das Objekt [generic_category](../standard-library/system-error-functions.md#generic_category).  
  
##  <a name="error_code__default_error_condition"></a> error_code::default_error_condition  
 Gibt die Standardfehlerbedingung zurück.  
  
```
error_condition default_error_condition() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die von [default_error_condition](../standard-library/error-category-class.md#error_category__default_error_condition) angegebene Funktion [error_condition](../standard-library/error-condition-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion gibt `category().default_error_condition(value())` zurück.  
  
##  <a name="error_code__error_code"></a> error_code::error_code  
 Konstruiert ein Objekt vom Typ `error_code`.  
  
```
error_code();

error_code(value_type val, const error_category& _Cat);

template <class _Enum>
error_code(_Enum _Errcode,
    typename enable_if<is_error_code_enum<_Enum>::value,
    error_code>::type* = 0);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`val`|Der Fehlercodewert, der in `error_code` gespeichert werden soll.|  
|`_Cat`|Die Fehlerkategorie, die in `error_code` gespeichert werden soll.|  
|`_Errcode`|Der Enumerationswert, der in `error_code` gespeichert werden soll.|  
  
### <a name="remarks"></a>Hinweise  
 Der erste Konstruktor speichert einen Fehlercodewert „Null“ und einen Zeiger auf [generic_category](../standard-library/system-error-functions.md#generic_category).  
  
 Der zweite Konstruktor speichert `val` als Fehlercodewert und einen Zeiger auf [error_category](http://msdn.microsoft.com/en-us/6fe57a15-63a1-4e79-8af4-6738e43e19c8).  
  
 Der dritte Konstruktor speichert `(value_type)_Errcode` als Fehlercodewert und einen Zeiger auf [generic_category](../standard-library/system-error-functions.md#generic_category).  
  
##  <a name="error_code__message"></a> error_code::message  
 Gibt den Namen des Fehlercodes zurück.  
  
```
string message() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `string`, der den Namen des Fehlercodes darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion gibt `category().message(value())` zurück.  
  
##  <a name="error_code__operator_eq_eq"></a> error_code::operator==  
 Prüft auf Gleichheit zwischen `error_code`-Objekten.  
  
```
bool operator==(const error_code& right) const;
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`right`|Das Objekt, das auf Gleichheit getestet werden soll.|  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn die Objekte gleich sind; **FALSE**, wenn die Objekte nicht gleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Der Memberoperator gibt `category() == right.category() && value == right.value()` zurück.  
  
##  <a name="error_code__operator_neq"></a> error_code::operator!=  
 Prüft auf Ungleichheit zwischen `error_code`-Objekten.  
  
```
bool operator!=(const error_code& right) const;
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`right`|Das Objekt, das auf Ungleichheit geprüft werden soll.|  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn das Objekt `error_code` nicht dem Objekt `error_code` entspricht, das an `right` übergeben wird; andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Der Memberoperator gibt `!(*this == right)` zurück.  
  
##  <a name="error_code__operator_lt_"></a> error_code::operator bool&lt;  
 Testet, ob ein [error_code](http://msdn.microsoft.com/en-us/09c6ef90-b6f8-430a-b584-e168716c7e31)-Objekt kleiner ist als das Objekt `error_code`, das für den Vergleich übergeben wurde.  
  
```
bool operator<(const error_code& right) const;
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`right`|Das zu vergleichende error_code-Objekt.|  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn das Objekt, das an `error_code` übergeben wird, kleiner ist als das an `error_code` übergebene Objekt; andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Der Memberoperator gibt `category() < right.category() || category() == right.category() && value < right.value()` zurück.  
  
##  <a name="error_code__operator_eq"></a> error_code::operator=  
 Weist dem [error_code](http://msdn.microsoft.com/en-us/09c6ef90-b6f8-430a-b584-e168716c7e31)-Objekt einen neuen Enumerationswert zu.  
  
```
template <class _Enum>
typename enable_if<is_error_code_enum<_Enum>::value,
    error_code>::type&
 operator=(_Enum _Errcode);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`_Errcode`|Der Enumerationswert, der dem `error_code`-Objekt zugewiesen wird.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das `error_code`-Objekt, dem der neue Enumerationswert durch die Memberfunktion zugewiesen wird.  
  
### <a name="remarks"></a>Hinweise  
 Der Memberoperator speichert `(value_type)_Errcode` als Fehlercodewert und einen Zeiger auf [generic_category](../standard-library/system-error-functions.md#generic_category). Er gibt `*this` zurück.  
  
##  <a name="error_code__operator_bool"></a> error_code::operator bool  
 Wandelt eine Variable vom Typ `error_code` um.  
  
```
explicit operator bool() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der boolesche Wert des Objekts `error_code`.  
  
### <a name="remarks"></a>Hinweise  
 Der Operator gibt einen Wert zurück, der zu `true` konvertiert werden kann, allerdings nur wenn [value](#error_code__value) nicht null entspricht. Der Rückgabetyp kann nur zu `bool` konvertiert werden, nicht zu `void *` oder zu anderen bekannten skalaren Typen.  
  
##  <a name="error_code__value"></a> error_code::value  
 Gibt den gespeicherten Fehlercodewert zurück.  
  
```
value_type value() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der gespeicherte Fehlercodewert vom Typ [value_type](#error_code__value_type).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="error_code__value_type"></a> error_code::value_type  
 Ein Typ, der den gespeicherten Fehlercodewert darstellt.  
  
```
typedef int value_type;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Typdefinition ist ein Synonym für `int`.  
  
## <a name="see-also"></a>Siehe auch  
 [error_category-Klasse](../standard-library/error-category-class.md)   
 [<system_error>](../standard-library/system-error.md)




