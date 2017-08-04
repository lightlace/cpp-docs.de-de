---
title: Funktionsaufruf (C) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- function calls, C functions
- functions [C], calling
- function calls
ms.assetid: 35c66719-3f15-4d3b-97da-4e19dc97b308
caps.latest.revision: 8
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: a86b3e45b5a5ce8c681fe267b7de8386b5fbc5c2
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="function-call-c"></a>Funktionsaufruf (C)
Ein „Funktionsaufruf“ ist ein Ausdruck, der den Namen der aufgerufenen Funktion oder den Wert eines Funktionszeigers und optional die Argumente, die der Funktion übergeben werden, enthält.  
  
## <a name="syntax"></a>Syntax  
 *postfix-expression*:  
 *postfix-expression* **(** *argument-expression-list* -Opt**)**  
  
 *argument-expression-list*:  
 *assignment-expression*  
  
 *argument-expression-list*  **,**  *assignment-expression*  
  
 Der *postfix-expression* muss eine Funktionsadresse ergeben (z.B. einen Funktionsbezeichner oder Funktionszeigerwert), und die *argument-expression-list* ist eine Ausdrucksliste (durch Kommas getrennt), deren Werte (die „Argumente“) an die Funktion übergeben werden. Das *argument-expression-list*-Argument kann leer sein.  
  
 Ein Funktionsaufrufausdruck hat den Wert und Typ des Rückgabewerts der Funktion. Eine Funktion kann kein Objekt des Arraytyps zurückgeben. Wenn der Rückgabetyp der Funktion `void` ist (die Funktion also so deklariert wurde, dass sie niemals einen Wert zurückgibt), hat der Funktionsaufrufausdruck ebenfalls den Typ `void`. (Weitere Informationen finden Sie unter [Funktionsaufrufe](../c-language/function-calls.md).)  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionsaufrufoperator: ()](../cpp/function-call-operator-parens.md)
