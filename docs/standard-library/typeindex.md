---
title: '&lt;typeindex&gt; | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <typeindex>
dev_langs:
- C++
ms.assetid: a9551137-f74b-4f02-af64-ff00214cea1f
caps.latest.revision: 14
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
translationtype: Machine Translation
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: 4279c10994de9247819e58a06276ef9690b39bb8
ms.lasthandoff: 02/24/2017

---
# <a name="lttypeindexgt"></a>&lt;typeindex&gt;
Verwenden Sie den Standardheader \<typeindex>, um eine Klasse und eine Funktion zu definieren, die die Indizierung von Objekten der Klasse [type_info](../cpp/type-info-class.md) unterstützen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
#include <typeindex>  
```  
  
## <a name="remarks"></a>Hinweise  
 Die [hash-Struktur](../standard-library/hash-structure.md) definiert eine `hash function`, die geeignet ist, um Werte des Typs [type_index](../standard-library/type-index-class.md) einer Verteilung von Indexwerten zuzuordnen.  
  
 Die `type_index`-Klasse umschließt einen Zeiger auf ein `type_info`-Objekt zur Unterstützung der Indizierung.  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)




