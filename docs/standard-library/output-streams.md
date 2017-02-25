---
title: "Ausgabestreams | Microsoft Docs"
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
  - "Ausgabestreams"
ms.assetid: b49410e3-5caa-4153-9d0d-c4266408dc83
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Ausgabestreams
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Ausgabestreamobjekt ist ein Ziel für Bytes.  Die drei wichtigsten Ausgabestreamklassen sind `ostream`, `ofstream` und `ostringstream`.  
  
 Die `ostream`\-Klasse, durch die abgeleitete Klasse `basic_ostream`, unterstützt die vordefinierten Streamobjekte:  
  
-   `cout` Standardausgabe  
  
-   `cerr` Standardfehler mit beschränkter Pufferung  
  
-   `clog` wie `cerr` jedoch mit voller Pufferung  
  
 Objekte werden selten von `ostream` erstellt; vordefinierte Objekte werden im Allgemeinen verwendet.  In einigen Fällen können Sie vordefinierte Objekte nach Programmstart neu zuweisen.  Die `ostream`\-Klasse, die für gepufferten oder nicht zwischengespeicherten Vorgang konfiguriert werden kann, ist zur sequenziellen Textmodusausgabe geeignet.  Alle Funktionen der Basisklasse, `ios`, ist in `ostream` enthalten.  Wenn Sie ein Objekt der Klasse `ostream` erstellen, müssen Sie ein `streambuf`\-Objekt an den Konstruktor.  
  
 Die `ofstream`\-Klasse unterstützt Datenträgerdateiausgabe.  Wenn Sie nur online ausgegebene Datenträger benötigen, erstellen Sie ein Objekt der Klasse `ofstream`.  Sie können angeben, ob `ofstream`\-Objekte Binärdatei oder Textmodusdaten akzeptieren, wenn das `ofstream`\-Objekt oder die `open` aufrufen, Memberfunktion des Objekts erstellen.  Viele Formatierungsoptionen und Memberfunktionen anwenden auf `ofstream`\-Objekte, und alle Funktionen der Basisklassen `ios` und `ostream` ist enthalten.  
  
 Wenn Sie einen Dateinamen im Konstruktor angeben, wird diese Datei automatisch geöffnet, wenn das Objekt erstellt wird.  Andernfalls können Sie die Memberfunktion `open` verwenden, nachdem Sie den Standardkonstruktor aufgerufen haben.  
  
 Wie die Laufzeitfunktion `sprintf_s`, wurden die `ostringstream` Generische Zeichenfolgen in den speicherresidenten aus.  Um eine Zeichenfolge im Arbeitsspeicher indem Sie E\/A\-Streamformatierung zu erstellen, erstellen Sie ein Objekt der Klasse `ostringstream`.  
  
## In diesem Abschnitt  
 [Konstruieren von Ausgabestreamobjekten](../standard-library/constructing-output-stream-objects.md)  
  
 [Verwenden von Einfügeoperatoren und Festlegen des Formats](../standard-library/using-insertion-operators-and-controlling-format.md)  
  
 [Ausgabedateistream\-Memberfunktionen](../standard-library/output-file-stream-member-functions.md)  
  
 [Pufferungseffekte](../standard-library/effects-of-buffering.md)  
  
 [Binäre Ausgabedateien](../standard-library/binary-output-files.md)  
  
 [Überladen des Operators \<\< für eigene Klassen](../standard-library/overloading-the-output-operator-for-your-own-classes.md)  
  
 [Schreiben eigener Manipulatoren ohne Argumente](../standard-library/writing-your-own-manipulators-without-arguments.md)  
  
## Siehe auch  
 [\<ostream\> Members](assetId:///a5afd034-0e3c-41ee-bbd7-468d9188da1d)   
 [ofstream](../Topic/ofstream.md)   
 [ostringstream](../Topic/ostringstream.md)   
 [basic\_ostream Members](assetId:///82e5cc91-7c0c-4950-a8ce-ac779cfbbd93)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)