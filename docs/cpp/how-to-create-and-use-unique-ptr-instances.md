---
title: 'Vorgehensweise: Erstellen und Verwenden von Unique_ptr-Instanzen | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 9a373030-e587-452f-b9a5-c5f9d58b7673
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ae4610e7b26eecd6ef444f3c7c73e95af365ca71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-and-use-uniqueptr-instances"></a>Gewusst wie: Erstellen und Verwenden von unique_ptr-Instanzen
Ein [Unique_ptr](../standard-library/unique-ptr-class.md) teilt der Zeiger nicht. Es kann nicht in eine andere kopiert werden `unique_ptr`, als Wert an eine Funktion übergeben oder in einen Algorithmus für die C++-Standardbibliothek, die Kopien erfordert verwendet. Ein `unique_ptr`-Objekt kann nur verschoben werden. Dies bedeutet, dass der Besitz der Arbeitsspeicherressource einem anderen `unique_ptr`-Objekt übertragen wird und das ursprüngliche `unique_ptr`-Objekt diese Ressource nicht mehr besitzt. Es empfiehlt sich, ein Objekt auf einen Besitzer zu beschränken, da mehrere Besitzer die Komplexität der Programmlogik erhöhen. Deshalb verwenden, wenn Sie einen intelligenten Zeiger für ein einfaches C++-Objekt benötigen, `unique_ptr`, und bei der Erstellung einer `unique_ptr`, verwenden Sie die [Make_unique](../standard-library/memory-functions.md#make_unique) Hilfsfunktion.  
  
 Das folgende Diagramm veranschaulicht die Eigentumsübertragung zwischen zwei `unique_ptr`-Instanzen.  
  
 ![Verschieben den Besitz einer eindeutigen &#95; Ptr](../cpp/media/unique_ptr.png "Unique_ptr")  
  
 `unique_ptr`wird definiert, der `<memory>` -Header in der C++-Standardbibliothek. Es ist genau effizient wie einen unformatierten Zeiger und kann in C++-Standardbibliothek Container verwendet werden. Das Hinzufügen von `unique_ptr` -Instanzen, die C++-Standardbibliothek Containern ist effizient, da der bewegungskonstruktor des der `unique_ptr` entfällt die Notwendigkeit für einen Kopiervorgang.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie `unique_ptr`-Instanzen erstellt und zwischen Funktionen übergeben werden.  
  
 [!code-cpp[stl_smart_pointers#210](../cpp/codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_1.cpp)]  
  
 Diese Beispiele zeigen diese grundlegende Eigenschaft des `unique_ptr`-Objekts: Es kann verschoben, jedoch nicht kopiert werden. "Wird verschoben" überträgt den Besitz einem neuen `unique_ptr`-Objekt und setzt das alte `unique_ptr`-Objekt zurück.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Erstellung von `unique_ptr`-Instanzen und ihre Verwendung in einem Vektor dargestellt.  
  
 [!code-cpp[stl_smart_pointers#211](../cpp/codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_2.cpp)]  
  
 Im Bereich der for-Schleife wird das `unique_ptr`-Objekt durch einen Verweis übergeben. Wenn Sie versuchen, das Objekt als Wert zu übergeben, löst der Compiler einen Fehler aus, da der `unique_ptr`-Kopierkonstruktor gelöscht wurde.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie ein `unique_ptr`-Objekt initialisiert wird, das ein Klassenmember ist.  
  
 [!code-cpp[stl_smart_pointers#212](../cpp/codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_3.cpp)]  
  
## <a name="example"></a>Beispiel  
 Können Sie [Make_unique](../standard-library/memory-functions.md#make_unique) zum Erstellen einer `unique_ptr` in ein Array, kann jedoch nicht `make_unique` zum Initialisieren der Elemente des Arrays.  
  
 [!code-cpp[stl_smart_pointers#213](../cpp/codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_4.cpp)]  
  
 Weitere Beispiele finden Sie unter [Make_unique](../standard-library/memory-functions.md#make_unique).  
  
## <a name="see-also"></a>Siehe auch  
 [Intelligente Zeiger](../cpp/smart-pointers-modern-cpp.md)   
 [make_unique](../standard-library/memory-functions.md#make_unique)