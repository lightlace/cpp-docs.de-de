---
title: Überladen von Unäroperatoren | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- unary operators [C++], plus
- increment operators [C++], overloaded
- unary operators [C++], minus
- operators [C++], unary
- redefinable unary operators [C++]
- unary operators [C++]
- pointer dereference operator overloading
- plus operator
ms.assetid: 7683ef08-42a4-4283-928f-d3dd4f3ab4c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d7f242fac0d81c6d46c2d810bf07459fde2fb2ae
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="overloading-unary-operators"></a>Überladen von unären Operatoren
Die unären Operatoren, die überladen werden können, sind Folgende:  
  
1.  `!` ([Logisches NOT](../cpp/logical-negation-operator-exclpt.md))  
  
2.  `&` ([Adresse des](../cpp/address-of-operator-amp.md))  
  
3.  `~` ([Einerkomplement](../cpp/one-s-complement-operator-tilde.md))  
  
4.  `*` ([zeigerdereferenzierungen](../cpp/indirection-operator-star.md))  
  
5.  `+` ([unäres plus](../cpp/additive-operators-plus-and.md))  
  
6.  `-` ([unäre Negation](../cpp/additive-operators-plus-and.md))  
  
7.  `++` ([Inkrement](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))  
  
8.  `--` ([Dekrementieren](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))  
  
9. Konvertierungsoperatoren  
  
 Die Postfix-Inkrementoperatoren und Dekrementoperatoren (`++` und **--**) werden separat in behandelt [Inkrementieren und Dekrementieren](../cpp/increment-and-decrement-operator-overloading-cpp.md).  
  
 Konvertierungsoperatoren sind auch in einem separaten Thema erörtert. finden Sie unter [benutzerdefinierte Typkonvertierungen](../cpp/user-defined-type-conversions-cpp.md).  
  
 Die folgenden Regeln sind für alle anderen unären Operatoren erfüllt. Um eine Funktion für einen unären Operator als nicht statischen Member zu deklarieren, müssen Sie sie im folgenden Format deklarieren:  
  
 `ret-type operator` `op` `()`  
  
 dabei ist `ret-type` der Rückgabetyp und `op` ist einer der in der vorhergehenden Tabelle aufgelisteten Operatoren.  
  
 Um eine Funktion für einen unären Operator als globale Funktion zu deklarieren, müssen Sie sie im folgenden Format deklarieren:  
  
 `ret-type operator` `op` (`arg` )  
  
 wo `ret-type` und `op`, wie beschrieben, für Memberoperatorfunktionen sind und das `arg` ein Argument des Klassentyps ist, mit dem Vorgänge ausgeführt werden sollen.  
  
> [!NOTE]
>  Es gibt keine Einschränkung für die Rückgabetypen der unären Operatoren. Beispielsweise macht es Sinn für ein logisches NOT (`!`), einen Ganzzahlwert zurückzugeben. Das wird aber nicht erzwungen.  
  
## <a name="see-also"></a>Siehe auch  
 [Operatorüberladung](../cpp/operator-overloading.md)