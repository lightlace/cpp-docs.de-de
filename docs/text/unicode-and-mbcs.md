---
title: "Unicode und MBCS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mbcs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MBCS [C++], Unicode"
  - "MFC [C++], Zeichensätze"
  - "Zeichensätze [C++], Multibyte"
  - "Laufzeitbibliotheken [C++], Sprachenportabilität"
  - "Zeichensätze [C++], Unicode"
  - "Unicode [C++], MFC- und C-Laufzeitfunktionen"
  - "Mehrbytezeichen [C++]"
  - "Laufzeit [C++], Sprachenportabilität"
ms.assetid: 677baec6-71b4-4579-94df-64f18bc117c4
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# Unicode und MBCS
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die MFC\-Bibliothek \(Microsoft Foundation Classes\), die C\-Laufzeitbibliothek für Visual C\+\+ und die Visual C\+\+\-Entwicklungsumgebung unterstützen Sie bei der internationalen Programmierung.  Sie bieten:  
  
-   Unterstützung für den Unicode\-Standard unter Windows 2000 \(früher Windows NT\)  Unicode ist der aktuelle Standard und sollte möglichst verwendet werden.  
  
     Unicode ist ein 16\-Bit\-Verfahren für die Zeichencodierung, in dem die Zeichensätze aller Sprachen codiert werden können.  Alle ASCII\-Zeichen sind in Unicode als erweiterte Zeichen enthalten.  
  
    > [!NOTE]
    >  Der Unicode\-Standard wird unter Windows 95, Windows 98 bzw. Windows Millennium Edition \(ME\) nicht unterstützt.  
  
-   Unterstützung für den Doppelbyte\-Zeichensatz \(Double\-Byte Character Set, DBCS\), einer Variante des Mehrbyte\-Zeichensatzes \(MBCS\) auf allen Plattformen  
  
     DBCS\-Zeichen bestehen aus einem oder zwei Bytes.  Bestimmte Bytebereiche sind zur Verwendung als führende Bytes reserviert.  Ein führendes Byte zeigt an, dass es selbst und das nächste Byte \(das nachfolgende Byte\) ein einziges, aus zwei Bytes bestehendes Zeichen darstellen.  Es ist wichtig, stets zu wissen, bei welchen Bytes es sich um führende Bytes handelt.  In einem bestimmten Mehrbyte\-Zeichensatz liegen die führenden Bytes ebenso wie die nachfolgenden Bytes innerhalb eines bestimmten Bereichs.  Wenn sich diese Bereiche überschneiden, muss unter Umständen anhand des Kontexts ermittelt werden, ob ein bestimmtes Byte als führendes oder als nachfolgendes Byte verwendet wird.  
  
-   Unterstützung für Tools, die die MBCS\-Programmierung von Anwendungen für internationale Märkte vereinfachen  
  
     Bei der Ausführung unter einer MBCS\-aktivierten Version des Betriebssystems Windows 2000 ist das Visual C\+\+\-Entwicklungssystem, einschließlich des integrierten Quellcode\-Editors, Debuggers und der Befehlszeilentools, vollständig MBCS\-aktiviert.  Weitere Informationen finden Sie unter [MBCS\-Unterstützung in Visual C\+\+](../text/mbcs-support-in-visual-cpp.md).  
  
> [!NOTE]
>  In der vorliegenden Dokumentation umschreibt der Begriff MBCS jede Nicht\-Unicode\-Unterstützung für Mehrbytezeichen.  In Visual C\+\+ ist MBCS gleichbedeutend mit DBCS.  Zeichensätze, die "breiter" als zwei Byte sind, werden nicht unterstützt.  
  
 Der ASCII\-Zeichensatz ist definitionsgemäß eine Teilmenge jedes Mehrbyte\-Zeichensatzes.  In vielen Mehrbyte\-Zeichensätzen sind die Zeichen im Bereich 0x00 – 0x7F mit den entsprechenden Zeichen des ASCII\-Zeichensatzes identisch.  Das ein Byte lange **NULL**\-Zeichen \('\\0'\) in ASCII\- und MBCS\-Zeichenfolgen hat z. B. den Wert 0x00 und steht für das abschließende NULL\-Zeichen.  
  
## Siehe auch  
 [Text und Zeichenfolgen](../text/text-and-strings-in-visual-cpp.md)   
 [Aktivierung der Internationalen Programmierung](../text/international-enabling.md)