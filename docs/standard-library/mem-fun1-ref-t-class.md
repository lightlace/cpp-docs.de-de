---
title: mem_fun1_ref_t-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xfunctional/std::mem_fun1_ref_t
- std::mem_fun1_ref_t
- mem_fun1_ref_t
- std.mem_fun1_ref_t
dev_langs:
- C++
helpviewer_keywords:
- mem_fun1_ref_t class
ms.assetid: 7d6742f6-19ba-4523-b3c8-0e5b8f11464f
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
ms.openlocfilehash: 32430ca2b66fc9772c01a29451986403c8d1d4b0
ms.lasthandoff: 02/24/2017

---
# <a name="memfun1reft-class"></a>mem_fun1_ref_t-Klasse
Eine Adapterklasse, die einer **non_const**-Memberfunktion, die ein einzelnes Argument akzeptiert, ermöglicht, als binäres Funktionsobjekt aufgerufen zu werden, wenn sie mit einem Verweisargument initialisiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Result, class Type, class Arg>
class mem_fun1_ref_t : public binary_function<Type, Arg, Result> {
    explicit mem_fun1_ref_t(
    Result (Type::* _Pm)(Arg));

    Result operator()(
    Type& left,
    Arg right) const;

 };
```  
  
#### <a name="parameters"></a>Parameter  
 `_Pm`  
 Ein Zeiger auf die Memberfunktion der Klasse **Type**, die in ein Funktionsobjekt konvertiert werden soll  
  
 `left`  
 Das Objekt, das für die `_Pm`-Memberfunktion aufgerufen wird.  
  
 `right`  
 Das Argument, das an `_Pm` übergeben wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Eine anpassungsfähige binäre Funktion.  
  
## <a name="remarks"></a>Hinweise  
 Die Vorlagenklasse speichert eine Kopie von `_Pm`, die ein Zeiger auf eine Memberfunktion der Klasse **Type** in einem privaten Memberobjekt sein muss. Für seine Memberfunktion `operator()` definiert sie als Rückgabewert (**left**.\* `_Pm`)(**right**).  
  
## <a name="example"></a>Beispiel  
 Der Konstruktor von `mem_fun1_ref_t` wird in der Regel nicht direkt verwendet; die Hilfsfunktion `mem_fun_ref` wird verwendet, um Memberfunktionen anzupassen. Weitere Beispiele für die Verwendung von Memberfunktionsadaptern finden Sie unter [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref_function).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<functional>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)




