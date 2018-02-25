---
title: forward_iterator_tag-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xutility/std::forward_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- forward_iterator_tag struct
- forward_iterator_tag class
ms.assetid: 68b633ac-b135-4e9e-837d-14248a262ec5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0bff4658211840d0bc750bc29d08df44721d340e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="forwarditeratortag-struct"></a>forward_iterator_tag-Struktur
Eine Klasse, die einen Rückgabetyp für eine **iterator_category**-Funktion bereitstellt, die einen Forward-Iterator darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```
struct forward_iterator_tag    : public input_iterator_tag {};
```  
  
## <a name="remarks"></a>Hinweise  
 Die Tagklassen von Kategorien werden als Kompiliertags für die Auswahl des Algorithmus verwendet. Die Vorlagenfunktion muss herausfinden, welche die spezifischste Kategorie ihres Iteratorarguments ist, um zur Kompilierzeit das effizienteste Argument verwenden zu können. Für jeden Iterator des Typs `Iterator` muss `iterator_traits`< `Iterator`> **::iterator_category** definiert werden, um das spezifischste Kategorietag zu werden, das das Iteratorverhalten beschreibt.  
  
 Der Typ ist identisch mit **iterator**\< **Iter**> **::iterator_category**, wenn **Iter** ein Objekt beschreibt, das als Forward-Iterator verwendet werden kann.  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel zur Verwendung der **iterator_tags** finden Sie unter [iterator_traits](../standard-library/iterator-traits-struct.md) oder [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<iterator>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [input_iterator_tag-Struktur](../standard-library/input-iterator-tag-struct.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)



