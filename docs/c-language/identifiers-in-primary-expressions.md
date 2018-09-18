---
title: Bezeichner in primären Ausdrücken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- identifiers, designating objects
ms.assetid: d4602fe6-e7e6-40cc-9823-3b1ebf5d3d38
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53498d5a1402d1953df93ea0f2d7c723218174c2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079036"
---
# <a name="identifiers-in-primary-expressions"></a>Bezeichner in primären Ausdrücken

Bezeichner können folgende Typen haben: ganzzahlig, **Float**, `enum`, `struct`, **Union**, Array, Zeiger oder Funktionstyp. Ein Bezeichner ist ein primärer Ausdruck, vorausgesetzt, er wurde als Festlegen eines Objekts deklariert (in diesem Fall ein l-Wert) oder als Funktion (in diesem Fall ist es ein Funktionsbezeichner). Eine Definition des l-Werts finden Sie unter [L-Wert- und R-Wert-Ausdrücke](../c-language/l-value-and-r-value-expressions.md).

Der Zeigerwert, der durch einen Arraybezeichner dargestellt wird, ist keine Variable. Daher kann der Arraybezeichner nicht den linken Operanden eines Zuweisungsvorgangs bilden und ist kein änderbarer L-Wert.

Ein Bezeichner, der als Funktion deklariert wurde, stellt einen Zeiger dar, dessen Wert die Adresse der Funktion darstellt. Der Zeiger adressiert eine Funktion, die einen Wert eines bestimmten Typs zurückgibt. Daher dürfen Funktionsbezeichner auch keine L-Werte in Zuweisungsvorgängen sein. Weitere Informationen finden Sie unter [Identifiers](../c-language/c-identifiers.md).

## <a name="see-also"></a>Siehe auch

[C-Ausdrücke (primär)](../c-language/c-primary-expressions.md)