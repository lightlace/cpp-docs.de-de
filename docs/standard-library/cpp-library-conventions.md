---
title: C++-Bibliothekskonventionen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C++ Standard Library, conventions
- classes [C++]
- functions [C++], library naming conventions
- naming conventions [C++], C++ Standard Library
- conventions [C++], C++ Standard Library
- function names [C++]
- coding conventions, C++ Standard Library
- naming conventions [C++], C++ library
ms.assetid: bf41b79a-2d53-4f46-8d05-779358335146
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
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 55d3959b12b1b1a25a6c4b5c65fce59db57cf838
ms.lasthandoff: 02/24/2017

---
# <a name="c-library-conventions"></a>C++-Bibliothekskonventionen
Die C++-Bibliothek erfüllt ähnliche Konventionen wie die C-Standardbibliothek und noch einige weitere, die nachfolgend beschrieben werden.  
  
 Eine Implementierung verfügt über einen gewissen Spielraum, wenn es um die Deklarierung von Typen und Funktionen in der C++-Standardbibliothek geht:  
  
-   Namen von Funktionen in der C-Standardbibliothek enthalten entweder einen externen #„C++“ oder einen extern „C“-Link. Fügen Sie den entsprechenden Standard-C-Header ein anstatt eine Inline-Bibliotheksentität zu deklarieren.  
  
-   Ein Memberfunktionsname in einer Bibliotheksklasse hat möglicherweise weitere Funktionssignaturen zusätzlich zu denen, die in diesem Dokument aufgeführt werden. Sie können davon ausgehen, dass sich ein an dieser Stelle beschriebener Funktionsaufruf wie erwartet verhält. Die Adresse einer Bibliotheksmemberfunktion kann jedoch nicht zuverlässig entgegengenommen werden. (Der Typ entspricht möglicherweise nicht Ihren Erwartungen.)  
  
-   Eine Bibliotheksklasse hat möglicherweise nicht dokumentierte (nicht virtuelle) Basisklassen. Eine von einer anderen Klasse als abgeleitet dokumentierte Klasse kann durchaus über andere nicht dokumentierte Klassen von dieser Klasse abgeleitet werden.  
  
-   Ein Typ, der als Synonym für einen ganzzahligen Typ definiert ist, kann einem von mehreren unterschiedlichen Integertypen entsprechen.  
  
-   Ein Bitmaskentyp kann entweder als ganzzahliger Typ oder als Enumeration implementiert werden. In beiden Fällen können Sie bitweise Operationen (z.B. `AND` und `OR`) auf Werte desselben Bitmaskentyps ausführen. Die Elemente `A` und `B` eines Bitmaskentyps sind Werte ungleich Null. `A`  &  `B` ist somit Null.  
  
-   Eine Bibliotheksfunktion ohne Angabe von Ausnahmen kann eine zufällige Ausnahme auslösen, sofern ihre Definition eine solche Möglichkeit nicht eindeutig einschränkt.  
  
 Andererseits bestehen durchaus einige Einschränkungen:  
  
-   Die C-Standardbibliothek verwendet keine Maskierungsmakros. Nur bestimmte Funktionssignaturen sind reserviert, jedoch nicht die Namen der Funktionen selbst.  
  
-   Der Name einer Bibliotheksfunktion außerhalb einer Klasse verfügt nicht über zusätzliche, nicht dokumentierte Funktionssignaturen. Sie können seine Adresse sicher entgegennehmen.  
  
-   Als virtuell beschriebene Basisklassen und Memberfunktionen sind nachweislich virtuell. Die als nicht virtuell beschriebenen sind ebenso nachweislich nicht virtuell.  
  
-   Zwei durch die C++-Bibliothek definierte Typen sind stets unterschiedlich, sofern nicht ausdrücklich anders in diesem Dokument dargestellt.  
  
-   Von der Bibliothek bereitgestellte Funktionen, einschließlich Standardversionen ersetzbarer Funktionen, können *bestenfalls * jene Ausnahmen auslösen, die in einer Ausnahmespezifikation aufgeführt sind. Von der Bibliothek bereitgestellte Destruktoren können keine Ausnahmen auslösen. Funktionen in der C-Standardbibliothek können möglicherweise eine Ausnahme weitergeben, wenn `qsort` eine Vergleichsfunktion aufruft, die eine Ausnahme auslöst. Anderenfalls lösen sie keine Ausnahmen aus.  
  
## <a name="see-also"></a>Siehe auch  
 [C++ Standard Library Overview (Übersicht über die C++-Standardbibliothek)](../standard-library/cpp-standard-library-overview.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)


