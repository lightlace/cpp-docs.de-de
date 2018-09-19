---
title: Überladen von Unäroperatoren | Microsoft-Dokumentation
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
ms.openlocfilehash: f737e262d39b99c2c33b7c91bc3d1e234a9f47db
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018625"
---
# <a name="overloading-unary-operators"></a>Überladen von unären Operatoren

Die unären Operatoren, die überladen werden können, sind Folgende:

1. `!` ([Logisches NOT](../cpp/logical-negation-operator-exclpt.md))

1. `&` ([Adresse der](../cpp/address-of-operator-amp.md))

1. `~` ([Einerkomplement](../cpp/one-s-complement-operator-tilde.md))

1. `*` ([Zeiger-Dereferenzierung](../cpp/indirection-operator-star.md))

1. `+` ([unäres plus](../cpp/additive-operators-plus-and.md))

1. `-` ([unäre Negation](../cpp/additive-operators-plus-and.md))

1. `++` ([Inkrement](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))

1. `--` ([Dekrementieren](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))

9. Konvertierungsoperatoren

Das Postfixinkrement und Dekrement-Operatoren (`++` und `--`) werden separat in behandelt [Inkrement- und Dekrement](../cpp/increment-and-decrement-operator-overloading-cpp.md).

Konvertierungsoperatoren werden auch in einem separaten Thema behandelt; finden Sie unter [User-Defined Type Conversions](../cpp/user-defined-type-conversions-cpp.md).

Die folgenden Regeln sind für alle anderen unären Operatoren erfüllt. Um eine Funktion für einen unären Operator als nicht statischen Member zu deklarieren, müssen Sie sie im folgenden Format deklarieren:

> *ret-Type* **Operator** *Op* **)**

in denen *ret-Type* ist der Rückgabetyp und *Op* ist einer der Operatoren in der obigen Tabelle aufgeführt.

Um eine Funktion für einen unären Operator als globale Funktion zu deklarieren, müssen Sie sie im folgenden Format deklarieren:

> *ret-Type* **Operator** *Op* **(** *Arg* **)**

in denen *ret-Type* und *Op* sind für Member-Operatorfunktionen beschrieben und die *Arg* ist ein Argument des Klassentyps, mit denen Sie arbeiten.

> [!NOTE]
>  Es gibt keine Einschränkung für die Rückgabetypen der unären Operatoren. Beispielsweise macht es Sinn für ein logisches NOT (`!`), einen Ganzzahlwert zurückzugeben. Das wird aber nicht erzwungen.

## <a name="see-also"></a>Siehe auch

[Operatorüberladung](../cpp/operator-overloading.md)