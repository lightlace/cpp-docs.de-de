---
title: Eingabe-/Ausgabealternativen | Microsoft-Dokumentation
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
- I/O [C++], alternatives
ms.assetid: 9f8401c7-d90d-4285-8918-63573df74a80
caps.latest.revision: 8
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
ms.openlocfilehash: 45cec9f7c4c45ef12c7d22a7c3c311f7ce3f4cb5
ms.lasthandoff: 02/24/2017

---
# <a name="inputoutput-alternatives"></a>Eingabe-/Ausgabealternativen
Visual C++ stellt mehrere Alternativen für die E/A-Programmierung bereit:  
  
-   Direkte C-Laufzeitbibliothek, ungepufferte E/A.  
  
-   ANSI C-Laufzeitbibliotheksstream E/A.  
  
-   Direkte Konsole und Port-E/A.  
  
-   Microsoft Foundation Class-Bibliothek.  
  
-   Microsoft C++ Standardbibliothek.  
  
 Die iostream-Klassen sind für gepufferten, formatierten Text E/A nützlich. Sie sind auch für ungepufferte oder binäre E/A nützlich, wenn Sie eine C++-Programmierschnittstelle benötigen und nicht die Microsoft Foundation Class (MFC)-Bibliothek verwenden möchten. Die iostream-Klassen sind eine objektorientierte E/A-Alternative zu den C-Laufzeitfunktionen.  
  
 Sie können die iostream-Klassen mit dem Microsoft Windows-Betriebssystem verwenden. Zeichenfolgen- und Dateistreams arbeiten ohne Einschränkungen, aber die Streamobjekte im Zeichenmodus `cin`, `cout`, `cerr`, und `clog` sind inkonsistent mit der grafischen Windows-Benutzeroberfläche. Sie können auch benutzerdefinierte stream-Klassen ableiten, die direkt mit der Windows-Umgebung interagieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionsweise eines Streams](../standard-library/what-a-stream-is.md)


