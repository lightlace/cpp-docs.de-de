---
title: const_mem_fun1_t-Klasse| Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.const_mem_fun1_t
- xfunctional/std::const_mem_fun1_t
- std::const_mem_fun1_t
- const_mem_fun1_t
dev_langs:
- C++
helpviewer_keywords:
- const_mem_fun1_t class
ms.assetid: 250fac30-9663-4133-9051-6303f76ea259
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
ms.openlocfilehash: 3a2664541cd1f1a44988f81e227e553b75b4faa6
ms.lasthandoff: 02/24/2017

---
# <a name="constmemfun1t-class"></a>const_mem_fun1_t-Klasse
Eine Adapterklasse, die einer **const**-Memberfunktion, die ein einzelnes Argument akzeptiert, ermöglicht, als binäres Funktionsobjekt aufgerufen zu werden, wenn sie mit einem Zeigerargument initialisiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Result, class Type, class Arg>
class const_mem_fun1_t
 : public binary_function<const Type *, Arg, Result>  
{
    explicit const_mem_fun1_t(Result (Type::* _Pm)(Arg) const);
    Result operator()(const Type* _Pleft, Arg right) const;
 };
```  
  
#### <a name="parameters"></a>Parameter  
 `_Pm`  
 Ein Zeiger auf die Memberfunktion der Klasse **Type**, die in ein Funktionsobjekt konvertiert werden soll  
  
 `_Pleft`  
 Das **const**-Objekt, das `_Pm` für die Memberfunktion aufgerufen wird  
  
 `right`  
 Das Argument, das an `_Pm` übergeben wird  
  
## <a name="return-value"></a>Rückgabewert  
 Eine anpassungsfähige binäre Funktion.  
  
## <a name="remarks"></a>Hinweise  
 Die Vorlagenklasse speichert eine Kopie von `_Pm`, die ein Zeiger auf eine Memberfunktion der Klasse **Type** in einem privaten Memberobjekt sein muss. Für seine Memberfunktion `operator()` definiert sie als Rückgabewert ( **_Pleft**->\* *Pm)(***Right**) **const**.  
  
## <a name="example"></a>Beispiel  
 Der Konstruktor von `const_mem_fun1_t` wird in der Regel nicht direkt verwendet; die Hilfsfunktion `mem_fun` wird verwendet, um Memberfunktionen anzupassen. Weitere Beispiele für die Verwendung von Memberfunktionsadaptern finden Sie unter [mem_fun](../standard-library/functional-functions.md#mem_fun_function).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<functional>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)




