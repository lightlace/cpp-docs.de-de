---
title: "Ausgabedateistream-Memberfunktionen | Microsoft Docs"
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
  - "Ausgabestreams, Memberfunktionen"
ms.assetid: 38aaf710-8035-4a34-a0c4-123a5327f28a
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ausgabedateistream-Memberfunktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ausgabestreammemberfunktionen haben drei Typen: die, die an Manipulatoren entsprechen, die, die unformatierte Schreibvorgänge ausführen und die, die andernfalls den Streamzustand ändern und keinen entsprechenden Manipulator oder Einfügungsoperator haben.  Eine sequenzielle, formatiertes Ausgabe können nur Einfügungsoperatoren und \-manipulatoren.  Bei einer direkten binäre Datenträgerausgabe verwenden Sie andere Memberfunktionen, mit oder ohne Einfügungsoperatoren.  
  
## Die geöffnete Funktion für Ausgabestreams  
 Um einen Ausgabedateistream \([ofstream](../Topic/ofstream.md)\) zu verwenden, müssen Sie den Stream mit einer bestimmten Datenträgerdatei im Konstruktor oder in der **open**\-Funktion zuordnen.  Wenn Sie die Funktion **open** verwenden, können Sie das gleiche Streamobjekt mit von Dateien verwenden.  In beiden Fällen sind die Argumente, die die Datei beschreiben, identisch.  
  
 Wenn Sie die Datei öffnen, die mit einem Ausgabestream zugeordnet ist, ist im Grunde ein **open\_mode**\-Flag an.  Sie können diese Flags kombinieren, als die Enumeratoren in der Klasse `ios`, mit dem bitweisen OR \(definiert werden &#124; Operator.\)  [ios\_base::openmode](../Topic/ios_base::openmode.md) finden Sie eine Liste der Enumeratoren.  
  
 Drei allgemeine Ausgabestreamsituationen beziehen Modusoptionen zusammen:  
  
-   Erstellen einer Datei.  Wenn die Datei bereits vorhanden ist, wird die alte Version gelöscht.  
  
    ```  
    ostream ofile( "FILENAME" );  // Default is ios::out  
    ofstream ofile( "FILENAME", ios::out ); // Equivalent to above  
    ```  
  
-   Datensätze zu einer vorhandenen Datei oder dem Erstellen ein anfügen, wenn es nicht vorhanden ist.  
  
    ```  
    ofstream ofile( "FILENAME", ios::app );  
    ```  
  
-   Zwei Dateien einzeln auf demselben Stream öffnen.  
  
    ```  
    ofstream ofile();  
    ofile.open( "FILE1", ios::in );  
    // Do some output  
    ofile.close(); // FILE1 closed  
    ofile.open( "FILE2", ios::in );  
    // Do some more output  
    ofile.close(); // FILE2 closed  
    // When ofile goes out of scope it is destroyed.  
    ```  
  
## Der gesetzte Funktion  
 Die **put**\-Funktion schreibt ein Zeichen in den Ausgabestream.  Die beiden folgenden Anweisungen sind identisch standardmäßig, die zweite wird von der Formatargumente des Streams betroffen:  
  
```  
cout.put( 'A' ); // Exactly one character written  
cout << 'A'; // Format arguments 'width' and 'fill' apply   
```  
  
## Die geschriebene Funktion  
 Die **Schreiben**\-Funktion wird ein Speicherblock in einen Ausgabedateistream.  Das Längenargument gibt die Anzahl von Bytes geschrieben an.  In diesem Beispiel wird ein Ausgabedateistream erstellt und schreibt den Binärwert der `Date`\-Struktur darauf:  
  
```  
// write_function.cpp  
// compile with: /EHsc  
#include <fstream>  
using namespace std;  
  
struct Date  
{  
   int mo, da, yr;  
};  
  
int main( )  
{  
   Date dt = { 6, 10, 92 };  
   ofstream tfile( "date.dat" , ios::binary );  
   tfile.write( (char *) &dt, sizeof dt );  
}  
```  
  
 Die **Schreiben**\-Funktion beendet nicht auf, wenn ein NULL\-Zeichen erreicht, sodass die vollständige Klassenstruktur geschrieben.  Die Funktion akzeptiert zwei Argumente: ein `char` Zeiger und eine Anzahl zu schreiben Zeichen.  Beachten Sie die erforderliche Umwandlung in **char\*** vor die Adresse des Strukturobjekts.  
  
## Die seekp und tellp Funktionen  
 Ein Ausgabedateistream internen enthält einen Zeiger, der auf der Position zeigt, in der Daten als Nächstes geschrieben werden sollen.  Die Memberfunktion `seekp` legt diesen Zeiger fest und stellt daher direkte Datenträgerdateiausgabe.  Die Memberfunktion `tellp` gibt der Dateiposition zurück.  Beispiele, die die Eingabestreamentsprechungen in `seekp` und `tellp` verwenden, finden Sie unter [Die seekg und tellg Funktionen](../standard-library/input-stream-member-functions.md).  
  
## Die Funktion für Ausgabestreams neben  
 Die **schließen**\-Memberfunktion enthält die Datenträgerdatei, die einem Ausgabedateistream zugeordnet ist.  Die Datei muss geschlossen werden, um alle Datenträgerausgabe abzuschließen.  Falls notwendig schließt der `ofstream` Destruktor die Datei für Sie, jedoch können Sie die Funktion **schließen** verwenden, wenn Sie eine andere Datei für dasselbe Streamobjekt öffnen müssen.  
  
 Der Ausgabestreamdestruktor schließt automatisch die Datei eines Streams, wenn der Konstruktor oder die **open**\-Memberfunktion Öffnen der Datei.  Wenn Sie den Konstruktor ein Dateideskriptor für eine BereitsOPEN\-Datei führen oder die **Anfügen**\-Memberfunktion verwenden, müssen Sie die Datei explizit schließen.  
  
##  <a name="vclrferrorprocessingfunctionsanchor10"></a> Fehler, der Funktionen verarbeitet  
 Verwenden Sie diese, Memberfunktionen um für Fehler, beim Schreiben zu testen zu einem Stream:  
  
|Funktion|Rückgabewert|  
|--------------|------------------|  
|[mehrdeutig](../Topic/basic_ios::bad.md)|Gibt **true** zurück, wenn ein nicht behebbarer Fehler gibt.|  
|[Fehler](../Topic/basic_ios::fail.md)|Gibt **true** zurück, wenn ein nicht behebbarer Fehler oder eine "erwarteten" Zustand, wie einem Konvertierungsfehler wird oder wenn die Datei nicht gefunden wird.  Die Verarbeitung kann sich nach einem Aufruf von **nicht aktiviert** mit einem nullargument häufig fortsetzen.|  
|[gut](../Topic/basic_ios::good.md)|Gibt **true** zurück, wenn kein anzubindender Fehlerzustand \(nicht behebbar oder anderes\) und gibt das Dateiendeflag wurde nicht festgelegt.|  
|[EOF](../Topic/basic_ios::eof.md)|Gibt **true** auf der Dateiende\-Bedingung zurück.|  
|[clear](../Topic/basic_ios::clear.md)|Legt den Zustand des internen Fehlers fest.  Wenn es den Standardargumenten aufgerufen wird, wird er alle Fehlerbits.|  
|[rdstate](../Topic/basic_ios::rdstate.md)|Gibt den aktuellen Fehlerzustand zurück.|  
  
 Der **\!**\-Operator wird überladen, um die gleiche Aufgabe wie die **Fehler**\-Funktion auszuführen.  Wenn der Ausdruck:  
  
```  
if( !cout)...  
```  
  
 identisch mit folgendem Ausdruck:  
  
```  
if( cout.fail() )...  
```  
  
 **void\*\(\)** Der Operator wird überladen, um die Invertierung des **\!**\-Operators sein; so der Ausdruck:  
  
```  
if( cout)...  
```  
  
 entspricht:  
  
```  
if( !cout.fail() )...  
```  
  
 Der Operator **void\*\(\)** ist nicht zu **good** äquivalent, da nicht zum Dateiende testet.  
  
## Siehe auch  
 [Ausgabestreams](../standard-library/output-streams.md)