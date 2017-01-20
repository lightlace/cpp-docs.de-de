---
title: "Konstruieren von Eingabestreamobjekten"
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
  - "Eingabestreamobjekte"
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
caps.latest.revision: 8
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Konstruieren von Eingabestreamobjekten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie nur das `cin`\-Objekt verwenden, müssen Sie nicht, einen Eingabestream zu erstellen.  Sie müssen einen Eingabestream erstellen, wenn Sie verwenden:  
  
-   [Eingabedatei\-Stream\-Konstruktoren](#vclrfinputfilestreamconstructorsanchor8)  
  
-   [Eingabezeichenfolgen\-Stream\-Konstruktoren](#vclrfinputstringstreamconstructorsanchor9)  
  
##  <a name="vclrfinputfilestreamconstructorsanchor8"></a> Eingabedatei\-Stream\-Konstruktoren  
 Es gibt zwei Möglichkeiten, einen Eingabedateistream zu erstellen:  
  
-   Verwenden Sie den `void`\-Argumentkonstruktor, und rufen Sie die `open`\-Memberfunktion auf:  
  
    ```  
    ifstream myFile; // On the stack  
    myFile.open( "filename" );  
  
    ifstream* pmyFile = new ifstream; // On the heap  
    pmyFile->open( "filename" );  
    ```  
  
-   Geben Sie Flags eines Dateinamens und \- Modus im Konstruktoraufruf an, die Sie öffnen Sie die Datei während des Bauprozesses:  
  
    ```  
    ifstream myFile( "filename" );  
    ```  
  
##  <a name="vclrfinputstringstreamconstructorsanchor9"></a> Eingabezeichenfolgen\-Stream\-Konstruktoren  
 Eingabezeichenfolgenstreamkonstruktoren benötigen die Adresse der zugeteilten, preinitialized Speicher:  
  
```  
string s("123.45");  
double amt;  
istringstream myString( s );   
//istringstream myString( "123.45" ) also works  
myString >> amt; // amt contains 123.45  
```  
  
## Siehe auch  
 [Eingabestreams](../standard-library/input-streams.md)