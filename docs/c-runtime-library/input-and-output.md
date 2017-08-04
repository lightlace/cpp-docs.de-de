---
title: Eingabe und Ausgabe | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.io
dev_langs:
- C++
helpviewer_keywords:
- input routines
- I/O [CRT]
- I/O routines
- I/O [CRT], routines
- output routines
ms.assetid: 1c177301-e341-4ca0-aedc-0a87fe1c75ae
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 79ede2f4d96f0dd985b5b68cf83e641cbba10f3e
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="input-and-output"></a>Eingabe und Ausgabe
Die E/A-Funktionen lesen Daten aus Dateien und Geräten und schreiben sie dorthin. Datei-E/A-Vorgänge finden im Textmodus oder Binärmodus statt. Die Microsoft-Laufzeitbibliothek verfügt über drei Arten von E/A-Funktionen:  
  
-   [Datenstrom-E/A](../c-runtime-library/stream-i-o.md)-Funktionen behandeln Daten als Datenstrom einzelner Zeichen.  
  
-   [Low-Level E/A](../c-runtime-library/low-level-i-o.md)-Funktionen rufen das Betriebssystem direkt für einen Vorgang auf, der sich auf einer niedrigeren Ebene befindet als der durch Datenstrom-E/A bereitgestellte Vorgang.  
  
-   [Konsolen- und Port-E/A](../c-runtime-library/console-and-port-i-o.md)-Funktionen führen Lese- bzw. Schreibvorgänge direkt auf einer Konsole (Tastatur und Bildschirm) oder einem E/A-Port (z.B. einem Druckeranschluss) durch.  
  
    > [!NOTE]
    >  Da Datenstromfunktionen gepuffert werden und Low-Level-Funktionen nicht, sind diese zwei Arten von Funktionen generell nicht kompatibel. Verwenden Sie für die Verarbeitung einer bestimmten Datei ausschließlich entweder Datenstrom- oder Low-Level-Funktionen.  
  
## <a name="see-also"></a>Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)
