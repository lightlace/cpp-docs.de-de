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
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375313"
---
# <a name="interpretation-of-subscript-operator"></a>Interpretation des Subscript-Operators

Wie andere Operatoren kann der Indexoperator (**\[]**) können vom Benutzer neu definiert werden. Das Standardverhalten des Indexoperators, wenn er nicht überladen ist, besteht darin, den Arraynamen und den Index unter Verwendung der folgenden Methode zu kombinieren:

\*((*array-name*) + (*subscript*))

Wie bei allen Additionen, an denen Zeigertypen beteiligt sind, wird die Skalierung automatisch zur Anpassung an die Größe des Typs ausgeführt. Daher ist der resultierende Wert nicht *Feldindex* Bytes auf den Ursprung des *Array-Name*, sondern es ist die *Feldindex*th-Element des Arrays. (Weitere Informationen zu dieser Konvertierung finden Sie unter [Additive Operatoren](../cpp/additive-operators-plus-and.md).)

Entsprechend wird die Adresse für mehrdimensionale Arrays anhand der folgenden Methode abgeleitet:

((*Arrayname*) + (*Feldindex*1 \* *max*2 \* *max*3 \* ... \* *max*n) + (*Feldindex*2 \* *max*3 \* ... \* *max*n) +... + *Feldindex*n))

## <a name="see-also"></a>Siehe auch

[Arrays](../cpp/arrays-cpp.md)<br/>
