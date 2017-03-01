---
title: pointer_to_binary_function-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::pointer_to_binary_function
- xfunctional/std::pointer_to_binary_function
- pointer_to_binary_function
- std.pointer_to_binary_function
dev_langs:
- C++
helpviewer_keywords:
- pointer_to_binary_function function
- pointer_to_binary_function class
ms.assetid: fb50599f-bcb3-4076-a669-6dcc3eb189a5
caps.latest.revision: 21
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
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 9a806934810286e22fdea70c2af982de10f48ee5
ms.lasthandoff: 02/24/2017

---
# <a name="pointertobinaryfunction-class"></a>pointer_to_binary_function-Klasse
Konvertiert einen binären Funktionszeiger in eine anwendbare binäre Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Arg1, class Arg2, class Result>
class pointer_to_binary_function
    : public binary_function <Arg1, Arg2, Result>
{
public:
    explicit pointer_to_binary_function(
        Result(*pfunc)(Arg1, Arg2));
    Result operator()(Arg1 left, Arg2 right) const;
};
```  
  
#### <a name="parameters"></a>Parameter  
 `pfunc`  
 Die binäre Funktion, die konvertiert werden soll.  
  
 `left`  
 Das linke Objekt, auf dem *\*pfunc* aufgerufen wird.  
  
 `right`  
 Das rechte Objekt, auf dem *\*pfunc* aufgerufen wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Die Vorlagenklasse speichert eine Kopie von **pfunc**. Sie definiert ihre Memberfunktion `operator()` als Rückgabewert (\* **pfunc**)(_ *Left*, \_ *Right*).  
  
## <a name="remarks"></a>Hinweise  
 Ein binärer Funktionszeiger ist ein Funktionsobjekt und kann an alle C++-Standardbibliotheksalgorithmen übergeben werden, die eine binäre Funktion als Parameter erwarten, aber er kann nicht angepasst werden. Für die Verwendung mit einem Adapter, z.B. um einen Wert zuzuordnen oder ihn mit einer Negator zu verwenden, müssen die geschachtelten Typen **first_argument_type**, **second_argument_type** und **result_type** angegeben werden, die eine solche Anpassung möglich machen. Die Konvertierung durch `pointer_to_binary_function` ermöglicht den Funktionsadaptern mit binären Funktionszeigern zusammenzuarbeiten.  
  
## <a name="example"></a>Beispiel  
 Der Konstruktor von `pointer_to_binary_function` wird nur selten direkt verwendet. Suchen Sie unter der Hilfsfunktion [ptr_fun](../standard-library/functional-functions.md#ptr_fun_function) nach einem Beispiel für das Deklarieren und Verwenden des `pointer_to_binary_function`-Adapterprädikats.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<functional>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)




