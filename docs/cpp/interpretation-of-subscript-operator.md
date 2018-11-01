---
title: Interpretation des Subscript-Operators
ms.date: 08/27/2018
helpviewer_keywords:
- subscript operator [C++], interpretation of
- arrays [C++], subscripting
- interpreting subscript operators [C++]
- operators [C++], interpretation of subscript
ms.assetid: 8852ca18-9d5b-43f7-b8bd-abc89364fbf2
ms.openlocfilehash: 1c3d5bca66cb294503805fd5b7691331ac380ae5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50446604"
---
# <a name="interpretation-of-subscript-operator"></a>Interpretation des Subscript-Operators

Wie andere Operatoren kann der Indexoperator (**\[]**) können vom Benutzer neu definiert werden. Das Standardverhalten des Indexoperators, wenn er nicht überladen ist, besteht darin, den Arraynamen und den Index unter Verwendung der folgenden Methode zu kombinieren:

\*((*Arrayname*) + (*Feldindex*))

Wie bei allen Additionen, an denen Zeigertypen beteiligt sind, wird die Skalierung automatisch zur Anpassung an die Größe des Typs ausgeführt. Daher ist der resultierende Wert nicht *Feldindex* Bytes auf den Ursprung des *Array-Name*, sondern es ist die *Feldindex*th-Element des Arrays. (Weitere Informationen zu dieser Konvertierung finden Sie unter [Additive Operatoren](../cpp/additive-operators-plus-and.md).)

Entsprechend wird die Adresse für mehrdimensionale Arrays anhand der folgenden Methode abgeleitet:

((*Arrayname*) + (*Feldindex*1 \* *max*2 \* *max*3 \* ... \* *max*n) + (*Feldindex*2 \* *max*3 \* ... \* *max*n) +... + *Feldindex*n))

## <a name="see-also"></a>Siehe auch

[Arrays](../cpp/arrays-cpp.md)<br/>
