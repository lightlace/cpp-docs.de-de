---
title: Interpretation des Subscript-Operators | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- subscript operator, interpretation of
- arrays [C++], subscripting
- interpreting subscript operators
- operators [C++], interpretation of subscript
ms.assetid: 8852ca18-9d5b-43f7-b8bd-abc89364fbf2
caps.latest.revision: 7
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 1a83ff6aea4380688d3b6298b93e04caab1dbb7f
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="interpretation-of-subscript-operator"></a>Interpretation des Subscript-Operators
Wie andere Operatoren kann der Indexoperator (**[]**) können vom Benutzer neu definiert werden. Das Standardverhalten des Indexoperators, wenn er nicht überladen ist, besteht darin, den Arraynamen und den Index unter Verwendung der folgenden Methode zu kombinieren:  
  
 \*((*Arrayname*) + (*Feldindex*))  
  
 Wie bei allen Additionen, an denen Zeigertypen beteiligt sind, wird die Skalierung automatisch zur Anpassung an die Größe des Typs ausgeführt. Aus diesem Grund ist der resultierende Wert nicht *Feldindex* Bytes vom Ursprung des *Arrayname*, sondern es ist die *Feldindex*th-Element des Arrays. (Weitere Informationen über diese Konvertierung finden Sie unter [Additive Operatoren](../cpp/additive-operators-plus-and.md).)  
  
 Entsprechend wird die Adresse für mehrdimensionale Arrays anhand der folgenden Methode abgeleitet:  
  
 **((**   
 ***Array-Name* ) + ()**   
 ***Tiefgestellt* 1***max*2 * \* max*3*...max*n) ** + ** *Feldindex*2 * \* max*3*...max*n).   . . *+**Feldindex*n))  
  
## <a name="see-also"></a>Siehe auch  
 [Arrays](../cpp/arrays-cpp.md)
