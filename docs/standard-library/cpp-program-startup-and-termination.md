---
title: Starten und Beenden eines C++-Programms | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C++ Standard Library, program startup and termination
- terminating execution
- Function Main procedures
- control text streams
- startup code, and C++ program termination
- main function, program startup
ms.assetid: f72c8f76-f507-4ddd-a270-7b60f4fed625
caps.latest.revision: 9
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
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 53e31f3f3a175013a248401f4231bb87cf444681
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="c-program-startup-and-termination"></a>Starten und Beenden eines C++-Programms
Ein C++-Programm führt beim Programmstart und bei Beendigung des Programms die gleichen Vorgänge wie ein C-Programm durch und noch einige weitere, die nachfolgend beschrieben werden.  
  
 Bevor die Zielumgebung die Funktion `main` aufruft, und nachdem sie alle anfänglichen Konstantenwerte gespeichert hat, die Sie in allen Objekten mit statischer Dauer festgelegt haben, führt das Programm alle übrigen Konstruktoren für solche statischen Objekte aus. Die Reihenfolge der Ausführung wird zwischen den Übersetzungseinheiten nicht angegeben. Sie können dennoch davon ausgeben, dass einige [iostreams](../standard-library/iostreams-conventions.md)-Objekte ordnungsgemäß für die Verwendung durch diese statischen Konstruktoren initialisiert werden. Zu diesen Steuerungtextstreams zählen:  
  
-   [cin](../standard-library/iostream.md#cin) – für die Standardeingabe  
  
-   [cin](../standard-library/iostream.md#cout) – für die Standardausgabe  
  
-   [cerr](../standard-library/iostream.md#cerr) – für die ungepufferte Standardfehlerausgabe  
  
-   [clog](../standard-library/iostream.md#clog) – für die gepufferte Standardfehlerausgabe  
  
 Sie können diese Objekte auch innerhalb der Destruktoren verwenden, die für statische Objekte während der Beendigung des Programms aufgerufen werden.  
  
 Ähnlich wie bei C ruft die Rückgabe von `main` oder der Aufruf von `exit` alle Funktionen auf, die bei `atexit` in umgekehrter Reihenfolge der Registrierung registriert wurden. Eine von einer solchen registrierten Funktion ausgelöste Ausnahme ruft `terminate` auf.  
  
## <a name="see-also"></a>Siehe auch  
 [C++ Standard Library Overview (Übersicht über die C++-Standardbibliothek)](../standard-library/cpp-standard-library-overview.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)



