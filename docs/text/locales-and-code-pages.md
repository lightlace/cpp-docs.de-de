---
title: "Gebietsschemas und Codepages | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zeichensätze [C++], Codepages"
  - "Zeichensätze [C++], Gebietsschemas"
  - "Codepages [C++]"
  - "Codepages [C++], Dynamisches Ändern"
  - "Codepages [C++], Gebietsschemas"
  - "Konventionen [C++], Unterstützung für internationale Zeichen"
  - "Gebietsschema-IDs [C++]"
  - "Gebietsschemas [C++]"
  - "Gebietsschemas [C++], Informationen über Gebietsschemas"
  - "Lokalisierung [C++], Codepages"
  - "Lokalisierung [C++], Gebietsschemas"
  - "Mehrbytecodepages [C++]"
ms.assetid: bd937361-b6d3-4c98-af95-beb7c903187b
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# Gebietsschemas und Codepages
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Gebietsschema\-ID spiegelt die lokalen Konventionen sowie die Sprache eines bestimmten geografischen Bereichs wider.  Viele Sprachen werden in mehreren Ländern\/Regionen gesprochen, z. B. wird Portugiesisch in Brasilien und Portugal gesprochen.  Umgekehrt gibt es in einem Land\/einer Region möglicherweise mehrere Amtssprachen.  In Kanada gibt es z. B. zwei Amtssprachen: Englisch und Französisch.  Für Kanada gibt es foglich zwei unterschiedliche Gebietsschemas: Englisch \(Kanada\) und Französisch \(Kanada\).  Vom Gebietsschema abhängig sind u. a. Datumsformat und Währungsformat.  
  
 Durch die Sprache werden die Konventionen für die Text\- und Datenformatierung bestimmt, während durch das Land\/die Region die länderspezifischen Konventionen festlegt werden.  Jede Sprache weist eine eindeutige, durch Codepages dargestellte Zuordnung auf, in der Zeichen enthalten sind, die nicht im Alphabet vorkommen \(z. B. Satzzeichen und Zahlen\).  Bei einer Codepage handelt es sich um einen Zeichensatz; sie ist mit der Sprache verknüpft.  Daher ist ein [Gebietsschema](../c-runtime-library/locale.md) eine eindeutige Kombination aus Sprache, Land\/Region und Codepage.  Die Gebietsschema\- und Codepage\-Einstellung kann zur Laufzeit durch Aufrufen der [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)\-Funktion geändert werden.  
  
 Von unterschiedlichen Sprachen werden möglicherweise unterschiedliche Codepages verwendet.  Die ANSI\-Codepage 1252 wird z. B. für Englisch und die meisten europäischen Sprachen verwendet, während die ANSI\-Codepage 932 für das japanische Kanji eingesetzt wird.  Nahezu alle Codepages verwenden für die ersten 128 Zeichen \(0 x 00 to 0 x 7 F\) den ASCII\-Zeichensatz.  
  
 Jede Einzelbyte\-Codepage kann in einer Tabelle \(mit 256 Einträgen\) als Zuordnung von Bytewerten zu Zeichen \(einschließlich Ziffern und Satzzeichen\) oder Symbolen dargestellt werden.  Jede Mehrbyte\-Codepage kann ebenfalls als umfangreiche Tabelle \(mit Einträgen im Umfang von 64 KB\) dargestellt werden, in der Doppelbytewerte Zeichen zugeordnet werden.  In der Praxis werden diese Codepages normalerweise jedoch anders dargestellt: als Tabelle für die ersten 256 Zeichen \(Einzelbyte\) und als Bereiche für die Doppelbytewerte.  
  
 Weitere Informationen über Codepages finden Sie unter [Codepages](../c-runtime-library/code-pages.md).  
  
 Die C\-Laufzeitbibliothek weist zwei Arten interner Codepages auf: die Gebietsschema\-Codepage und die Mehrbyte\-Codepage.  Sie können die aktuelle Codepage während der Programmausführung ändern \(siehe Dokumentation der Funktionen [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) und [\_setmbcp](../c-runtime-library/reference/setmbcp.md)\).  Darüber hinaus kann von der Laufzeitbibliothek der Wert der Betriebssystem\-Codepage abgerufen und verwendet werden.  Unter Windows 2000 handelt es sich bei der Betriebssystem\-Codepage um die Codepage mit dem Systemstandard ANSI.  Diese Codepage bleibt für die Dauer der Ausführung des jeweiligen Programms unverändert.  
  
 Wenn sich die Codepage eines Gebietsschemas ändert, ändert sich das Verhalten der vom jeweiligen Gebietsschema abhängigen Funktionen gemäß des von der ausgewählten Codepage vorgegebenen Verhaltens.  Standardmäßig beginnen alle vom Gebietsschema abhängigen Funktionen die Ausführung mit einer Gebietsschema\-Codepage, die für das "C"\-Gebietsschema eindeutig ist.  Sie können die interne Codepage für das Gebietsschema \(ebenso wie andere Gebietsschema\-spezifische Eigenschaften\) durch Aufruf der `setlocale`\-Funktion ändern.  Durch den Aufruf von `setlocale`\(LC\_ALL, ""\) wird das Gebietsschema gemäß den Vorgaben für das Gebietsschema des Benutzers des Betriebssystem eingestellt.  
  
 Wenn sich die Mehrbyte\-Codepage ändert, ändert sich entsprechend das Verhalten der Mehrbytefunktionen gemäß des von der ausgewählten Codepage vorgegebenen Verhaltens.  Standardmäßig beginnen alle Mehrbytefunktionen die Ausführung mit der Mehrbyte\-Codepage, die der Standard\-Codepage des Betriebssystems entspricht.  Sie können die interne Mehrbyte\-Codepage durch Aufruf der `_setmbcp`\-Funktion ändern.  
  
 Mit der C\-Laufzeitbibliotheksfunktion `setlocale` können Sie alle Gebietsschemainformationen des aktuellen Programms oder Teile davon einstellen, ändern und abfragen.  Bei der Routine [\_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) handelt es sich um eine Breitzeichen\-Version von `setlocale`; bei den Argumenten und Rückgabewerten von `_wsetlocale` handelt es sich um Breitzeichen\-Zeichenfolgen.  
  
## Siehe auch  
 [Unicode und MBCS](../text/unicode-and-mbcs.md)   
 [Vorteile der Zeichensatzportabilität](../text/benefits-of-character-set-portability.md)