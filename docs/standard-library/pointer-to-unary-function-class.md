---
title: pointer_to_unary_function-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xfunctional/std::pointer_to_unary
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: c809687243285778d68f9f35b42d3d25d4aa7bcf
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

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
 Der Konstruktor von `pointer_to_unary_function` wird nur selten direkt verwendet. Suchen Sie unter der Hilfsfunktion [ptr_fun](../standard-library/functional-functions.md#ptr_fun) nach einem Beispiel für das Deklarieren und Verwenden des `pointer_to_unary_function`-Adapterprädikats.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<functional>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)




