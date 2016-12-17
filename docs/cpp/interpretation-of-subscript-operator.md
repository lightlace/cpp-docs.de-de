---
title: "Interpretation des Subscript-Operators"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Arrays [C++], Indizierung"
  - "Interpretieren von Indexoperatoren"
  - "Operatoren [C++], Interpretation von Indexoperatoren"
  - "Indexoperator, Interpretation von"
ms.assetid: 8852ca18-9d5b-43f7-b8bd-abc89364fbf2
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Interpretation des Subscript-Operators
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wie andere Operatoren kann der Indexoperator \(**\[ \]**\) vom Benutzer neu definiert werden.  Das Standardverhalten des Indexoperators, wenn er nicht überladen ist, besteht darin, den Arraynamen und den Index unter Verwendung der folgenden Methode zu kombinieren:  
  
 \*\(\(*array\-name*\) \+ \(*subscript*\)\)  
  
 Wie bei allen Additionen, an denen Zeigertypen beteiligt sind, wird die Skalierung automatisch zur Anpassung an die Größe des Typs ausgeführt.  Daher ist der resultierende Wert nicht *subscript* Bytes vom Ursprung von *array\-name*, sondern das *subscript*. Element des Arrays. \(Weitere Informationen über diese Konvertierung finden Sie unter [Additive Operatoren](../cpp/additive-operators-plus-and.md).\)  
  
 Entsprechend wird die Adresse für mehrdimensionale Arrays anhand der folgenden Methode abgeleitet:  
  
 **\(\(**   
 ***array\-name* \) \+ \(**   
 ***subscript* 1**  *max*2 *\* max*3*...max*n\)               **\+** *subscript*2 *\* max*3*...max*n\)                    . . .  *\+* *subscript*n\)\)  
  
## Siehe auch  
 [Arrays](../cpp/arrays-cpp.md)