---
title: Eingabe-/Ausgabealternativen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: I/O [C++], alternatives
ms.assetid: 9f8401c7-d90d-4285-8918-63573df74a80
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 56b7268083239fbec6b1744e1905e100fc357cc7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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

