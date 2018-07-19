---
title: Interpretation des Subscript-Operators | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 9bba312c6969acf95be8899f58f65e31c75386c4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32420472"
---
# <a name="interpretation-of-subscript-operator"></a>Interpretation des Subscript-Operators
Wie andere Operatoren kann der Indexoperator (**[]**) können vom Benutzer neu definiert werden. Das Standardverhalten des Indexoperators, wenn er nicht überladen ist, besteht darin, den Arraynamen und den Index unter Verwendung der folgenden Methode zu kombinieren:  
  
 \*((*Arrayname*) + (*Feldindex*))  
  
 Wie bei allen Additionen, an denen Zeigertypen beteiligt sind, wird die Skalierung automatisch zur Anpassung an die Größe des Typs ausgeführt. Aus diesem Grund ist der resultierende Wert nicht *Feldindex* Bytes vom Ursprung des *Arrayname*, sondern es ist die *Feldindex*th-Element des Arrays. (Weitere Informationen über diese Konvertierung finden Sie unter [Additive Operatoren](../cpp/additive-operators-plus-and.md).)  
  
 Entsprechend wird die Adresse für mehrdimensionale Arrays anhand der folgenden Methode abgeleitet:  
  
 **((**   
 ***Array-Name* ) + ()**   
 ***Tiefgestellt* 1***max*2  *\* max*3 *.. .max*n) **+** *Feldindex*2  *\* max*3 *.. .max*n).   sein. sein. *+* *Tiefgestellt*n))  
  
## <a name="see-also"></a>Siehe auch  
 [Arrays](../cpp/arrays-cpp.md)