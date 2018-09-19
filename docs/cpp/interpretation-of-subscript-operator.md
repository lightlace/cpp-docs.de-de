---
title: Interpretation des Subscript-Operators | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- subscript operator [C++], interpretation of
- arrays [C++], subscripting
- interpreting subscript operators [C++]
- operators [C++], interpretation of subscript
ms.assetid: 8852ca18-9d5b-43f7-b8bd-abc89364fbf2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6e1457744747ee3638d7f0b9485ac12af60e5cdd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058340"
---
# <a name="interpretation-of-subscript-operator"></a>Interpretation des Subscript-Operators

Wie andere Operatoren kann der Indexoperator (**\[]**) können vom Benutzer neu definiert werden. Das Standardverhalten des Indexoperators, wenn er nicht überladen ist, besteht darin, den Arraynamen und den Index unter Verwendung der folgenden Methode zu kombinieren:

\*((*Arrayname*) + (*Feldindex*))

Wie bei allen Additionen, an denen Zeigertypen beteiligt sind, wird die Skalierung automatisch zur Anpassung an die Größe des Typs ausgeführt. Daher ist der resultierende Wert nicht *Feldindex* Bytes auf den Ursprung des *Array-Name*, sondern es ist die *Feldindex*th-Element des Arrays. (Weitere Informationen zu dieser Konvertierung finden Sie unter [Additive Operatoren](../cpp/additive-operators-plus-and.md).)

Entsprechend wird die Adresse für mehrdimensionale Arrays anhand der folgenden Methode abgeleitet:

((*Arrayname*) + (*Feldindex*1 \* *max*2 \* *max*3 \* ... \* *max*n) + (*Feldindex*2 \* *max*3 \* ... \* *max*n) +... + *Feldindex*n))

## <a name="see-also"></a>Siehe auch

[Arrays](../cpp/arrays-cpp.md)<br/>
