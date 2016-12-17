---
title: "Codepages"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "c.international"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "ANSI [C++], Codepages"
  - "Zeichensätze [C++], Codepages"
  - "Codepages [C++], Typen"
  - "Gebietsschema-Codepages [C++]"
  - "Lokalisierung [C++], Codepages"
  - "Mehrbytecodepages [C++]"
  - "System-Standardcodepage"
ms.assetid: 4a26fc42-185a-4add-98bf-a7b314ae6186
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Codepages
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`code page` ist ein Zeichensatz, Zahlen, Interpunktionszeichen und andere Symbole enthalten kann.  Verschiedene Sprachen und Gebietsschemas verwenden möglicherweise unterschiedliche Codepages.  Beispielsweise wird ANSI\-Codepage 1252 für Englisch und die meisten europäischen Sprachen verwendet; OEM\-Codepage 932 wird für das japanische Kanji eingesetzt wird.  
  
 Eine Codepage kann in einer Tabelle als Zuordnung von Zeichen an Einzelbytewerten oder den Mehrbytewerten dargestellt werden.  Viele Codepages geben den ASCII\-Zeichensatz für Zeichen im Bereich 0x00 \- 0x7F frei.  
  
 Die Microsoft\-Laufzeitbibliothek werden die folgenden Typen von Codepages:  
  
-   System\-Standard ANSI\-Codepage.  Standardmäßig Hardwareausstattung legt das Laufzeitsystem automatisch die Mehrbyte\-Codepage auf die SystemStandard ANSI\-Codepage fest, die vom Betriebssystem abgerufen wird.  Der Aufruf:  
  
    ```  
    setlocale ( LC_ALL, "" );  
    ```  
  
     wird das Gebietsschema auf die SystemStandard ANSI\-Codepage fest.  
  
-   Gebietsschema\-Codepage.  Das Verhalten einiger Ablaufroutinen ist der aktuellen Gebietsschemaeinstellung abhängig, die sich die Codepage eines Gebietsschemas enthält. \(Weitere Informationen, finden Sie unter [Gebietsschemaabhängige Routinen](../c-runtime-library/locale.md).\) Standardmäßig verwenden alle vom Routinen in der Microsoft\-Laufzeitbibliothek die Codepage, die für das "C " \- Gebietsschema entspricht.  Zur Laufzeit können Sie die Codepage eines Gebietsschemas mit einem Aufruf von [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) ändern oder in Verwendung abfragen.  
  
-   Mehrbyte\-Codepage.  Das Verhalten der meisten Mehrbytezeichenroutinen in der Laufzeitbibliothek hängt von der aktuellen Mehrbyte\-Codepage\-Einstellung ab.  Standardmäßig verwenden diese Routinen die SystemStandard ANSI\-Codepage.  Zur Laufzeit können Sie die Mehrbyte\-Codepage mit [\_getmbcp](../c-runtime-library/reference/getmbcp.md) und [\_setmbcp](../c-runtime-library/reference/setmbcp.md) abfragen und ändern, bzw.  
  
-   Im "C " \- Gebietsschema wird von ANSI definiert, um das Gebietsschema zu entsprechen, in dem C\-Programme bisher ausgeführt haben.  Die Codepage für das "C " \- Gebietsschema \("C Codepage\) entspricht dem ASCII\-Zeichensatz.  Im "C " \- Gebietsschema, `islower` true für die Werte 0x61 \- nur 0x7A.  In einem anderen Gebietsschema kann `islower` true für diese sowie andere Werte zurück, z von diesem Gebietsschema definiert.  
  
## Siehe auch  
 [Internationalisierung](../c-runtime-library/internationalization.md)   
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)