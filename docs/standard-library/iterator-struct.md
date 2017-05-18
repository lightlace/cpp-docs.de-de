---
title: iterator-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iterator
- xutility/std::iterator
dev_langs:
- C++
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
caps.latest.revision: 18
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: b14712f36d8cc7b4dbbdd4fd6a0cef3cb0667d8b
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="iterator-struct"></a>iterator-Struktur
Eine leere Basisstruktur wird verwendet, um sicherzustellen, dass eine benutzerdefinierte Iteratorklasse ordnungsgemäß mit **iterator_trait**s funktioniert.  
  
## <a name="syntax"></a>Syntax  
```    
struct iterator {
   typedef Category iterator_category;
   typedef Type value_type;
   typedef Distance difference_type;
   typedef Distance distance_type;
   typedef Pointer pointer;
   typedef Reference reference;
   };  
```    
## <a name="remarks"></a>Hinweise  
 Die Vorlagenstruktur wird als Basistyp für alle Iteratoren verwendet. Definiert den Membertypen  
  
- `iterator_category` (ein Synonym für den Vorlagenparameter `Category`).  
  
- `value_type` ( ein Synonym für den Vorlagenparameter **Type**).  
  
- `difference_type` (ein Synonym für den Vorlagenparameter `Distance`).  
  
- `distance_type` (ein Synonym für den Vorlagenparameter `Distance`).  
  
- `pointer` (ein Synonym für den Vorlagenparameter `Pointer`).  
  
- `reference` (ein Synonym für den Vorlagenparameter `Reference`).  
  
 Beachten Sie, dass `value_type` kein konstanter Typ sein darf, auch wenn der **Zeiger** auf ein Objekt vom const-**Type** verweist und der Verweis ein Objekt vom const-**Type** kennzeichnet.  
  
## <a name="example"></a>Beispiel  
 Unter [iterator_traits](../standard-library/iterator-traits-struct.md) finden Sie ein Beispiel für das Deklarieren und Verwenden von Typen in der Iterator-Basisklasse.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<iterator>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [\<iterator>](../standard-library/iterator.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)




