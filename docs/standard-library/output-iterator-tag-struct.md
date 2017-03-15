---
title: output_iterator_tag-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::output_iterator_tag
- output_iterator_tag
- xutility/std::output_iterator_tag
- std.output_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- output_iterator_tag class
- output_iterator_tag struct
ms.assetid: c23a4331-b069-4fa0-9c3a-1c9be7095553
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
translationtype: Machine Translation
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: a0376983916f511bec198a4b5d7d9e7131ae25b6
ms.lasthandoff: 02/24/2017

---
# <a name="outputiteratortag-struct"></a>output_iterator_tag-Struktur
Eine Klasse, die einen Rückgabetyp für eine **iterator_category**-Funktion bereitstellt, die einen Ausgabe-Iterator darstellt.  
  
## <a name="syntax"></a>Syntax  
  
struct output_iterator_tag {};  
  
## <a name="remarks"></a>Hinweise  
 Die Kategorietagklassen werden als Kompiliertags für die Auswahl des Algorithmus verwendet. Die Vorlagenfunktion muss herausfinden, welche die spezifischste Kategorie ihres Iteratorarguments ist, um zur Kompilierzeit den effizientesten Algorithmus verwenden zu können. Für jeden Iterator des Typs `Iterator` muss `iterator_traits`< `Iterator`> **::iterator_category** als spezifischstes Kategorietag definiert werden, das das Iteratorverhalten beschreibt.  
  
 Der Typ entspricht **iterator**\< **Iter**> **::iterator_category**, wenn **Iter** ein Objekt beschreibt, das als Ausgabeiterator verwendet werden kann.  
  
 Dieses Tag ist nicht auf die `value_type` oder `difference_type` für den Iterator parametrisiert, wie bei anderen Iteratortags, da Ausgabe -Iteratoren nicht entweder `value_type` oder `difference_type` haben.  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel zur Verwendung der **iterator_tag**s finden Sie unter [iterator_traits](../standard-library/iterator-traits-struct.md) oder [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<iterator>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)




