---
title: "Eingabestreams"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Daten [C++], Lesen aus Eingabesteam"
  - "Eingabestreamobjekte"
  - "Eingabestreams"
  - "Lesen von Daten [C++], aus Eingabestreams"
ms.assetid: f14d8954-8f8c-4c3c-8b99-14ddb3683f94
caps.latest.revision: 11
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Eingabestreams
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Eingabestreamobjekt ist eine Quelle von Bytes.  Die drei wichtigsten Eingabestreamklassen sind [istream](assetId:///6801779e-260e-416d-b4ec-fef5ff1b2371), [ifstream](../Topic/ifstream.md) und [istringstream](../Topic/istringstream.md).  
  
 Die `istream`\-Klasse wird am besten für sequenzielle Textmoduseingabe verwendet.  Sie können Objekte der Klasse `istream` für gepufferten oder nicht zwischengespeicherten Vorgang konfigurieren.  Alle Funktionen der Basisklasse, `ios`, ist in `istream` enthalten.  Sie erstellen Objekte selten von der Klasse `istream`.  Verwenden Sie im Allgemeinen das vordefinierte `cin`\-Objekt, das eigentlich ein Objekt der Klasse [ostream](../standard-library/ostream.md) ist.  In einigen Fällen können Sie `cin` mit anderen Streamobjekten nach Programmstart zuweisen.  
  
 Die `ifstream`\-Klasse unterstützt Datenträgerdateieingabe.  Wenn Sie nur eine für typisierte Datenträgerdatei benötigen, erstellen Sie ein Objekt der Klasse `ifstream`.  Sie können Textmodusdaten Binärdatei oder angeben.  Wenn Sie einen Dateinamen im Konstruktor angeben, wird die Datei automatisch geöffnet, wenn das Objekt erstellt wird.  Andernfalls können Sie die Funktion `open` verwenden, nachdem Sie den Standardkonstruktor aufgerufen haben.  Viele Formatierungsoptionen und Memberfunktionen anwenden auf `ifstream`\-Objekte.  Alle Funktionen der Basisklassen `ios` und `istream` ist in `ifstream` enthalten.  
  
 Wie die Bibliotheksfunktion `sscanf_s`, die `istringstream` Generische eingegebenen Zeichenfolgen von den im Arbeitsspeicher.  Um Daten aus einem Zeichenarray zu extrahieren das über einen Nullterminator verfügt, ordnen Sie zu und initialisieren Sie der Zeichenfolge, erstellen Sie ein Objekt der Klasse `istringstream`.  
  
## In diesem Abschnitt  
 [Konstruieren von Eingabestreamobjekten](../standard-library/constructing-input-stream-objects.md)  
  
 [Verwenden von Extraktionsoperatoren](../standard-library/using-extraction-operators.md)  
  
 [Überprüfen von Extraktionen](../standard-library/testing-for-extraction-errors.md)  
  
 [Eingabestream\-Manipulatoren](../standard-library/input-stream-manipulators.md)  
  
 [Eingabestream\-Memberfunktionen](../standard-library/input-stream-member-functions.md)  
  
 [Überladen des Operators \>\> für eigene Klassen](../standard-library/overloading-the-input-operator-for-your-own-classes.md)  
  
## Siehe auch  
 [iostream\-Programmierung](../standard-library/iostream-programming.md)