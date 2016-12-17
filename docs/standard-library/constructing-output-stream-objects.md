---
title: "Konstruieren von Ausgabestreamobjekten"
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
  - "Ausgabestreamobjekte"
ms.assetid: 93c8eab6-610c-4f48-b76d-1d960cac7641
caps.latest.revision: 9
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Konstruieren von Ausgabestreamobjekten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn nur Sie vordefinierte `cout`, `cerr` oder `clog`\-Objekte verwenden, ist es nicht erforderlich, um einen Ausgabestream zu erstellen.  Sie müssen für Konstruktoren verwenden:  
  
-   [Ausgabedatei\-Stream\-Konstruktoren](#vclrfoutputfilestreamconstructorsanchor1)  
  
-   [Ausgabe\-Zeichenfolgen\-Stream\-Konstruktoren](#vclrfoutputstringstreamconstructorsanchor2)  
  
##  <a name="vclrfoutputfilestreamconstructorsanchor1"></a> Ausgabedatei\-Stream\-Konstruktoren  
 Sie können einen Ausgabedateistream auf zwei Arten erstellen:  
  
-   Verwenden Sie den Standardkonstruktor, und rufen Sie dann die `open`\-Memberfunktion auf.  
  
    ```  
    ofstream myFile; // Static or on the stack  
    myFile.open( "filename" );  
  
    ofstream* pmyFile = new ofstream; // On the heap  
    pmyFile->open( "filename" );  
    ```  
  
-   Geben Sie Flags eines Dateinamens und \- Modus im Konstruktoraufruf an.  
  
    ```  
    ofstream myFile( "filename", ios_base::out);  
    ```  
  
##  <a name="vclrfoutputstringstreamconstructorsanchor2"></a> Ausgabe\-Zeichenfolgen\-Stream\-Konstruktoren  
 Um einen Ausgabezeichenfolgenstream zu erstellen, können Sie `ostringstream` folgendermaßen verwenden:  
  
```  
   using namespace std;  
string sp;  
ostringstream myString;  
myString << "this is a test" << ends;  
sp = myString.str();  // Obtain string  
cout << sp < endl;   
```  
  
 `ends` "Manipulator" fügt dem erforderlichen NULL der Zeichenfolge hinzu.  
  
## Siehe auch  
 [Ausgabestreams](../standard-library/output-streams.md)