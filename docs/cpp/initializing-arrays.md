---
title: Initialisieren von Arrays | Microsoft Docs
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
- initializing arrays [C++]
- arrays [C++], initializing
ms.assetid: 41efe5f0-15b5-4f49-9196-c4902f8fc705
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 42d47f8ba7f7df8285d3c4f685a212c77974b144
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="initializing-arrays"></a>Initialisieren von Arrays
Wenn eine Klasse über einen Konstruktor verfügt, werden Arrays dieser Klasse von einem Konstruktor initialisiert. Wenn weniger Elemente in der Initialisiererliste als Elemente im Array vorhanden sind, wird der Standardkonstruktor für die verbleibenden Elemente verwendet. Wenn kein Standardkonstruktor für die Klasse definiert wird, muss die Initialisiererliste abgeschlossen sein, d. h. es muss ein Initialisierer für jedes Element im Array vorhanden sein.  
  
 Betrachten Sie die `Point`-Klasse, die zwei Konstruktoren definiert:  
  
```  
// initializing_arrays1.cpp  
class Point  
{  
public:  
   Point()   // Default constructor.  
   {  
   }  
   Point( int, int )   // Construct from two ints  
   {  
   }  
};  
  
// An array of Point objects can be declared as follows:  
Point aPoint[3] = {  
   Point( 3, 3 )     // Use int, int constructor.  
};  
  
int main()  
{  
}  
```  
  
 Das erste Element von `aPoint` wird unter Verwendung des Konstruktors `Point( int, int )` erstellt; die verbleibenden zwei Elemente werden unter Verwendung des Standardkonstruktors erstellt.  
  
 Statische Memberarrays (ob **const** oder nicht) können in ihren Definitionen (außerhalb der Klassendeklaration) initialisiert werden. Zum Beispiel:  
  
```  
// initializing_arrays2.cpp  
class WindowColors  
{  
public:  
    static const char *rgszWindowPartList[7];  
};  
  
const char *WindowColors::rgszWindowPartList[7] = {  
    "Active Title Bar", "Inactive Title Bar", "Title Bar Text",  
    "Menu Bar", "Menu Bar Text", "Window Background", "Frame"   };  
int main()  
{  
}  
```  
  
