---
title: mem_fun1_t-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mem_fun1_t
- std.mem_fun1_t
- std::mem_fun1_t
- xfunctional/std::mem_fun1_t
dev_langs:
- C++
helpviewer_keywords:
- mem_fun1_t class
ms.assetid: 01a8c2c2-b2f7-4e3f-869c-5b5b9f06ea54
caps.latest.revision: 20
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
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: 434e4032216922071d60d7a7ad6a36b7f6135f7e
ms.lasthandoff: 02/24/2017

---
# <a name="memfun1t-class"></a>mem_fun1_t-Klasse
Eine Adapterklasse, die einer **non_const**-Memberfunktion, die ein einzelnes Argument akzeptiert, ermöglicht, als binäres Funktionsobjekt aufgerufen zu werden, wenn sie mit einem Zeigerargument initialisiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Result, class Type, class Arg>
class mem_fun1_t : public binary_function<Type *, Arg, Result> {
    explicit mem_fun1_t(
    Result (Type::* _Pm)(Arg));

    Result operator()(
    Type* _Pleft,
    Arg right) const;

 };
```  
  
#### <a name="parameters"></a>Parameter  
 `_Pm`  
 Ein Zeiger auf die Memberfunktion der Klasse **Type**, die in ein Funktionsobjekt konvertiert werden soll  
  
 `_Pleft`  
 Das Objekt, das für die `_Pm`-Memberfunktion aufgerufen wird.  
  
 `right`  
 Das Argument, das an `_Pm` übergeben wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Eine anpassungsfähige binäre Funktion.  
  
## <a name="remarks"></a>Hinweise  
 Die Vorlagenklasse speichert eine Kopie von `_Pm`, die ein Zeiger auf eine Memberfunktion der Klasse **Type** in einem privaten Memberobjekt sein muss. Für seine Memberfunktion `operator()` definiert sie als Rückgabewert (**_Pleft**->\* `_Pm`)(**right**).  
  
## <a name="example"></a>Beispiel  
  Der Konstruktor von `mem_fun1_t` wird in der Regel nicht direkt verwendet; die Hilfsfunktion `mem_fun` wird verwendet, um Memberfunktionen anzupassen. Weitere Beispiele für die Verwendung von Memberfunktionsadaptern finden Sie unter [mem_fun](../standard-library/functional-functions.md#mem_fun_function).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<functional>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)




