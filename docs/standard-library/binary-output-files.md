---
title: "Bin&#228;re Ausgabedateien | Microsoft Docs"
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
  - "Binäre Daten, Binäre Ausgabedateien"
  - "Dateien [C++], Binäre Ausgabedateien"
  - "E/A [C++], Binäre Ausgabedateien"
ms.assetid: 180954af-8cd6-444b-9a76-2f630a3389d8
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Bin&#228;re Ausgabedateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Streams wurden ursprünglich für Text vorgesehen, sodass der Standardausgabemodus Text.  Im Textmodus das Zeilenumbruchzeichen \(hexadezimal 10\) bis zu einem Wagenrücklauf\/Zeilenvorschub \(nur Bits\).  Die Erweiterung kann Probleme verursachen, wie hier gezeigt:  
  
```  
// binary_output_files.cpp  
// compile with: /EHsc  
#include <fstream>  
using namespace std;  
int iarray[2] = { 99, 10 };  
int main( )  
{  
    ofstream os( "test.dat" );  
    os.write( (char *) iarray, sizeof( iarray ) );  
}  
```  
  
 Sie erwarten dieses Programm, um der Bytesequenz {99, 0, 10, 0} auszugeben; stattdessen gibt sie {99, 0, 13, 10, 0} aus, die Probleme für ein Programm verursacht, das Binärdateieingabe erwartet.  Wenn Sie eine echte eine binäre Ausgabe benötigen, in der Zeichen unübersetzt geschrieben werden, können Sie der Binärdatei angeben, die mithilfe des [ofstream](../Topic/ofstream.md)\-Konstruktormodusarguments ausgegeben wurde:  
  
```  
// binary_output_files2.cpp  
// compile with: /EHsc  
#include <fstream>  
using namespace std;  
int iarray[2] = { 99, 10 };  
  
int main()  
{  
   ofstream ofs ( "test.dat", ios_base::binary );  
  
   // Exactly 8 bytes written  
   ofs.write( (char*)&iarray[0], sizeof(int)*2 );   
}  
```  
  
## Siehe auch  
 [Ausgabestreams](../standard-library/output-streams.md)