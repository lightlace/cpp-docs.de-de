---
title: pointer_to_unary_function-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xfunctional/std::pointer_to_unary_function
- pointer_to_unary_function
- std.pointer_to_unary_function
- std::pointer_to_unary_function
dev_langs:
- C++
helpviewer_keywords:
- pointer_to_unary_function function
- pointer_to_unary_function class
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
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
ms.openlocfilehash: f9e9b21833eb3d8c46d9bdf817a29350a77c22d4
ms.lasthandoff: 02/24/2017

---
# <a name="pointertounaryfunction-class"></a>pointer_to_unary_function-Klasse
Konvertiert einen unären Funktionszeiger in eine anwendbare unäre Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Arg, class Result>
class pointer_to_unary_function
    : public unary_function<Arg, Result>
{
public:
    explicit pointer_to_unary_function(Result(*pfunc)(Arg));
    Result operator()(Arg left) const;
};
```  
  
#### <a name="parameters"></a>Parameter  
 `pfunc`  
 Die binäre Funktion, die konvertiert werden soll.  
  
 `left`  
 Das Objekt, auf dem *\*pfunc* aufgerufen wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Die Vorlagenklasse speichert eine Kopie von **pfunc**. Sie definiert ihre Memberfunktion `operator()` als Rückgabewert (\* **pfunc**)(_ *Left*).  
  
## <a name="remarks"></a>Hinweise  
 Ein binärer Funktionszeiger ist ein Funktionsobjekt und kann an alle C++-Standardbibliotheksalgorithmen übergeben werden, die eine unäre Funktion als Parameter erwarten, aber er kann nicht angepasst werden. Für die Verwendung mit einem Adapter, z.B. um einen Wert zuzuordnen oder ihn mit einer Negator zu verwenden, müssen die geschachtelten Typen **argument_type** und **result_type** angegeben werden, die eine solche Anpassung möglich machen. Die Konvertierung durch `pointer_to_unary_function` ermöglicht den Funktionsadaptern mit binären Funktionszeigern zusammenzuarbeiten.  
  
## <a name="example"></a>Beispiel  
 Der Konstruktor von `pointer_to_unary_function` wird nur selten direkt verwendet. Suchen Sie unter der Hilfsfunktion [ptr_fun](../standard-library/functional-functions.md#ptr_fun_function) nach einem Beispiel für das Deklarieren und Verwenden des `pointer_to_unary_function`-Adapterprädikats.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<functional>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)




