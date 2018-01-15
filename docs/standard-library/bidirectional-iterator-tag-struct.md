---
title: bidirectional_iterator_tag-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xutility/std::bidirectional_iterator_tag
dev_langs: C++
helpviewer_keywords:
- bidirectional_iterator_tag class
- bidirectional_iterator_tag struct
ms.assetid: 9ac06066-b8ae-44b6-bee4-b05855f6a31a
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6ac5f22a22ad64e137a56be964068229a6ed0958
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="bidirectionaliteratortag-struct"></a>bidirectional_iterator_tag-Struktur
Eine Klasse, die einen Rückgabetyp für eine **iterator_category**-Funktion bereitstellt, die einen bidirektionalen Iterator darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```
struct bidirectional_iterator_tag    : public forward_iterator_tag {};
```  
  
## <a name="remarks"></a>Hinweise  
 Die Kategorietagklassen werden als Kompiliertags für die Auswahl des Algorithmus verwendet. Die Vorlagenfunktion muss herausfinden, welche die spezifischste Kategorie ihres Iteratorarguments ist, um zur Kompilierzeit den effizientesten Algorithmus verwenden zu können. Für jeden Iterator des Typs `Iterator` muss `iterator_traits`< `Iterator`>::**iterator_category** definiert werden, um das spezifischste Kategorietag zu sein, das das Iteratorverhalten beschreibt.  
  
 Der Typ ist identisch mit **iterator**\< **Iter**>:: **iterator_category** wenn **Iter** ein Objekt beschreibt, das als bidirektionaler Iterator verwendet werden kann.  
  
## <a name="example"></a>Beispiel  
 Unter [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) finden Sie ein Beispiel zur Verwendung von `bidirectional_iterator_tag`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<iterator>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [forward_iterator_tag-Struktur](../standard-library/forward-iterator-tag-struct.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)



