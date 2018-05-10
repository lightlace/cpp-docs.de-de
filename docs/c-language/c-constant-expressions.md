---
title: Konstante Ausdrücke in C | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: d48a6c47-e44c-4be2-9c8b-7944c7ef8de7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aaeb7ab79777d247f0bc0b2e6d749d8df5a7f8e9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="c-constant-expressions"></a>Konstante Ausdrücke in C
Ein konstanter Ausdruck wird nicht zur Laufzeit, sondern zur Kompilierzeit ausgewertet, Er kann überall dort eingesetzt werden, wo auch eine Konstante verwendet werden kann. Ergebnis des konstanten Ausdrucks muss eine Konstante sein, deren Wert für den betreffenden Typ darstellbar sein muss. Die Operanden eines konstanten Ausdrucks können ganzzahlige Konstanten, Zeichenkonstanten, Gleitkommakonstanten, Enumerationskonstanten, Typumwandlungen, `sizeof`-Ausdrücke oder sonstige konstante Ausdrücke sein.  
  
## <a name="syntax"></a>Syntax  
 *constant-expression*:  
 *conditional-expression*  
  
 *conditional-expression*:  
 *logical-OR-expression*  
  
 *logical-OR-expression* **?**  *expression* **:**  *conditional-expression*  
  
 *expression*:  
 *assignment-expression*  
  
 *expression* **,** *assignment-expression*  
  
 *assignment-expression*:  
 *conditional-expression*  
  
 *unary-expression assignment-operator assignment-expression*  
  
 *assignment-operator*: eines der folgenden Zeichen:  
 **= \*= /= %= += -= <\<= >>= &= ^= &#124;=**  
  
 Die Non-Terminals für den Strukturdeklarator, den Enumerator, den direkten Deklarator, den direkt-abstrakten Deklarator und die Anweisung mit Bezeichnung enthalten das Non-Terminal *constant-expression*.  
  
 Ein ganzzahliger konstanter Ausdruck muss verwendet werden, um die Größe eines Bitfeldmembers einer Struktur, den Wert einer Enumerationskonstanten, die Größe eines Arrays oder den Wert einer **case**-Konstanten anzugeben.  
  
 Konstante Ausdrücke, die in Präprozessoranweisungen verwendet werden, unterliegen zusätzlichen Einschränkungen. Daher werden sie als „eingeschränkte konstante Ausdrücke“ bezeichnet. Ein eingeschränkter konstanter Ausdruck darf keine `sizeof`-Ausdrücke, Enumerationskonstanten, Typumwandlungen in beliebige Typen oder Gleitkommakonstanten enthalten. Dagegen kann der spezielle konstante Ausdruck `defined (`*identifier*`)` enthalten sein.  
  
## <a name="see-also"></a>Siehe auch  
 [Operanden und Ausdrücke](../c-language/operands-and-expressions.md)