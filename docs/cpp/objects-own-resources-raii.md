---
title: Objekteigene Ressourcen (RAII) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: f86b484e-5a27-4c3b-a92a-dfaa5dd6d93a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 05e23cc81666086bc34352a351ead8006b6c859f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="objects-own-resources-raii"></a>Objekteigene Ressourcen (RAII)
Stellen Sie sicher, dass die eigene Ressourcen Objekte. Dieses Prinzip ist auch bekannt als "Resource Acquisition is Initialization" oder "RAII."  
  
## <a name="example"></a>Beispiel  
 Übergeben Sie jedes Objekt "Neues" als Konstruktorargument in ein anderes benanntes Objekt, das er (fast immer Unique_ptr) besitzt.  
  
```cpp  
void f() {  
    unique_ptr<widget> p( new widget() );  
    my_class x( new widget() );  
    // ...  
} // automatic destruction and deallocation for both widget objects  
  // automatic exception safety, as if "finally { p->dispose(); x.w.dispose(); }"  
```  
  
 Übergeben Sie eine neue Ressource immer sofort in ein anderes Objekt aus, das er besitzt.  
  
```cpp  
void g() {  
    other_class y( OpenFile() );  
    // ...  
} // automatic closing and release for file resource  
  // automatic exception safety, as if "finally { y.file.dispose(); }"  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Willkommen zurück bei C++](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)