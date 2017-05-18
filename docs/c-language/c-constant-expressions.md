---
title: "C-Ausdrücke (konstant) | Microsoft-Dokumentation"
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
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: d48a6c47-e44c-4be2-9c8b-7944c7ef8de7
caps.latest.revision: 10
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 0e3323c85ce7668adfe5b4a297ac8bab930c3ae6
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="c-constant-expressions"></a>C-Ausdrücke (konstant)
Ein konstanter Ausdruck wird zur Kompilierzeit, nicht zur Laufzeit, ausgewertet und kann an einem beliebigen Ort verwendet werden, an dem eine Konstante verwendet werden kann. Der konstante Ausdruck muss eine Konstante auswerten, die sich im Bereich der darstellbaren Werte für diesen Typ befindet. Die Operanden eines konstanten Ausdrucks können ganzzahlige Konstanten, Zeichenkonstanten, Gleitkommakonstanten, Enumerationskonstanten, Typumwandlungen, `sizeof`-Ausdrücke und andere konstante Ausdrücke sein.  
  
## <a name="syntax"></a>Syntax  
 *constant-expression*:  
 *conditional-expression*  
  
 *conditional-expression*:  
 *logical-OR-expression*  
  
 *logical-OR-expression* **?**  *expression* **:**  *conditional-expression*  
  
 *expression*:  
 *assignment-expression*  
  
 *expression* **,**  *assignment-expression*  
  
 *assignment-expression*:  
 *conditional-expression*  
  
 *unary-expression assignment-operator assignment-expression*  
  
 *assignment-operator*: Einer von  
 **= \*= /= %= += -= <\<= >>= &= ^= &#124;=**  
  
 Die Nichtterminalen für den Strukturdeklarator, den Enumerator, den direkten Deklarator, den direkt-abstrakten Deklarator und die gekennzeichnete Anweisung enthalten das Nichtterminal *constant-expression*.  
  
 Ein ganzzahliger konstanter Ausdruck muss verwendet werden, um die Größe eines Bitfeldmembers einer Struktur, den Wert einer Enumerationskonstanten, die Größe eines Arrays oder den Wert einer **case**-Konstanten anzugeben.  
  
 Konstante Ausdrücke, die in den Präprozessoranweisungen verwendet werden, unterliegen zusätzlichen Einschränkungen. Daher sind sie als "eingeschränkte konstante Ausdrücke" bekannt. Ein eingeschränkter konstanter Ausdruck kann keine `sizeof`-Ausdrücke, Enumerationskonstanten, Typumwandlungen zu keinem Typ oder Float-Konstanten enthalten. Er kann jedoch den speziellen konstanten Ausdruck `defined (`*identifier*`)` enthalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Operanden und Ausdrücke](../c-language/operands-and-expressions.md)
