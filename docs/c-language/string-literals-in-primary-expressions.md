---
title: Zeichenfolgenliterale in primären Ausdrücken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- string literals, in primary expressions
ms.assetid: 3ec31278-527b-40d2-8c83-6b09e2d81ca6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 818284a0eabce779d9f52e8fe7b3af4cc1d8df4b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095524"
---
# <a name="string-literals-in-primary-expressions"></a>Zeichenfolgenliterale in primären Ausdrücken

Ein "Zeichenfolgenliteral" ist ein Zeichen, ein Breitzeichen oder eine Sequenz von angrenzenden Zeichen, die in Anführungszeichen gesetzt werden. Da es keine Variablen sind, können weder Zeichenfolgenliterale noch deren Elemente als linksseitige Operanden in einer Zuweisungsoperation verwendet werden. Der Typ eines Zeichenfolgenliterals ist ein Array von `char` (oder ein Array von `wchar_t` für Breitzeichenliterale). Arrays in Ausdrücken werden in Zeiger konvertiert. Weitere Informationen zu Zeichenfolgen finden Sie unter [Zeichenfolgenliterale](../c-language/c-string-literals.md).

## <a name="see-also"></a>Siehe auch

[C-Ausdrücke (primär)](../c-language/c-primary-expressions.md)