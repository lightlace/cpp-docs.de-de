---
title: Ausgabedateistream-Memberfunktionen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- output streams, member functions
f1_keywords: []
ms.assetid: 38aaf710-8035-4a34-a0c4-123a5327f28a
caps.latest.revision: 8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: baa226c95d396232ea8ac545c839352c5df4c22f
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="output-file-stream-member-functions"></a>Ausgabedateistream-Memberfunktionen
Ausgabedateistream-Memberfunktionen verfügen über drei Arten: die, die Manipulatoren entsprechen, die, die unformatierte Schreibvorgänge ausführen, und die, die andernfalls den Streamstatus ändern und keinen entsprechenden Manipulator oder Einfügungsoperator haben. Für die sequenzielle, formatierte Ausgabe können Sie nur Einfügungsoperatoren und Manipulatoren verwenden. Bei einer binäre Datenträgerausgabe verwenden Sie andere Memberfunktionen, mit oder ohne Einfügungsoperatoren.  
  
## <a name="the-open-function-for-output-streams"></a>Die open-Funktion für Ausgabestreams  
 Um einen Ausgabedateistream ([ofstream](../standard-library/basic-ofstream-class.md)) zu verwenden, müssen Sie diesen Stream einer bestimmten Datenträgerdatei im Konstruktor oder der **open**-Funktion zuweisen. Bei Verwendung der **open**-Funktion können Sie das gleiche Streamobjekt mit einer Reihe von Dateien wiederverwenden. In beiden Fällen sind die Argumente, die die Datei beschreiben identisch.  
  
 Wenn Sie die Datei öffnen, die einem Ausgabestream zugeordnet ist, geben Sie in der Regel ein **open_mode**-Flag an. Sie können diese Flags kombinieren, die in der `ios`-Klasse mit dem bitweisen OR-Operator ( &#124; ) als Enumeratoren definiert werden. Finden Sie unter [ios_base:: openmode](../standard-library/ios-base-class.md#openmode) eine Liste der Enumeratoren.  
  
 Drei allgemeine Situationen für die Ausgabestreams umfassen Modusoptionen:  
  
-   Erstellen einer Datei. Wenn die Datei bereits vorhanden ist, wird die alte Version gelöscht.  
  
 ```  
    ostream ofile("FILENAME");
// Default is ios::out  
    ofstream ofile("FILENAME", ios::out);

// Equivalent to above  
```  
  
-   Anfügen von Datensätzen an eine vorhandene Datei oder Erstellen derselben, wenn sie nicht vorhanden ist.  
  
 ```  
    ofstream ofile("FILENAME", ios::app);
```  
  
-   Einzelnes Öffnen von zwei Dateien auf demselben Stream.  
  
 ```  
    ofstream ofile();
ofile.open("FILE1",
    ios::in);
// Do some output  
    ofile.close();

// FILE1 closed  
    ofile.open("FILE2",
    ios::in);
// Do some more output  
    ofile.close();

// FILE2 closed  // When ofile goes out of scope it is destroyed.  
```  
  
## <a name="the-put"></a>Der put
 Die **put**-Funktion schreibt ein Zeichen in den Ausgabestream. Die beiden folgenden Anweisungen sind standardmäßig identisch, aber die zweite ist von den Streamformatargumenten betroffen:  
  
```  
cout.put('A');

// Exactly one character written  
cout <<'A'; // Format arguments 'width' and 'fill' apply   
```  
  
## <a name="the-write"></a>Der Schreibvorgang
 Die **write**-Funktion schreibt einen Speicherblock in einen Ausgabestream für die Datei. Das Längenargument bestimmt die Anzahl geschriebener Bytes. Dieses Beispiel erstellt einen Ausgabestream für die Datei und schreibt den binären Wert der `Date`-Struktur hinein:  
  
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
  
 Die **write**-Funktion wird nicht beendet, wenn ein NULL-Zeichen erreicht wird, sodass die vollständige Klassenstruktur geschrieben wird. Die Funktion akzeptiert zwei Argumente: ein `char`-Zeiger und die Anzahl der zu schreibenden Zeichen. Beachten Sie die erforderliche Umwandlung in **char\*** vor der Adressierung des Strukturobjekts.  
  
## <a name="the-seekp-and-tellp-functions"></a>Die Funktionen seekp und tellp  
 Ein Ausgabestream für die Datei hält einen internen Zeiger, der auf die Position zeigt, in der die Daten als nächstes geschrieben werden sollen. Die `seekp`-Memberfunktion legt diesen Zeiger fest und bietet somit Random_Access-Datenträgerdateiausgaben. Die `tellp`-Memberfunktion gibt die gespeicherte Dateiposition zurück. Beispiele für die Verwendung von Entsprechungen des Eingabestreams für `seekp` und `tellp`, finden Sie unter [Die Funktionen seekg und tellg](../standard-library/input-stream-member-functions.md).  
  
## <a name="the-close-function-for-output-streams"></a>Die close-Funktion für Ausgabestreams  
 Die **close**-Memberfunktion schließt die Datenträgerdatei, die einem Ausgabestream für Dateien zugeordnet ist. Die Datei muss geschlossen werden, um alle Datenträgerausgaben abzuschließen. Wenn nötig, schließt der `ofstream`-Destruktor die Datei für Sie, aber Sie können die **close**-Funktion verwenden, wenn Sie eine andere Datei für das gleiche Streamobjekt öffnen müssen.  
  
 Der Destruktor der Ausgabestream schließt eine Streamdatei nur automatisch, wenn den Konstruktor oder die **open**-Memberfunktion die Datei geöffnet haben. Wenn Sie einen Dateideskriptor einer bereits geöffneten Datei dem Konstruktor übergeben oder die **attach**-Memberfunktion nutzen, müssen Sie die Datei explizit schließen.  
  
##  <a name="vclrferrorprocessingfunctionsanchor10"></a> Fehlerverarbeitende Funktionen  
 Verwenden Sie diese Memberfunktionen, um beim Schreiben in einen Stream auf Fehler zu testen:  
  
|Funktion|Rückgabewert|  
|--------------|------------------|  
|[bad](http://msdn.microsoft.com/Library/4038d331-e9c9-48b0-bf49-c6505744469c)|Gibt **TRUE** zurück, wenn ein nicht behebbarer Fehler vorhanden ist.|  
|[fail](http://msdn.microsoft.com/Library/619f1b36-1e72-4551-8b48-888ae4e370d2)|Gibt **TRUE** zurück, wenn ein nicht behebbarer Fehler oder eine „erwartete“ Bedingung, wie z.B. ein Konvertierungsfehler vorhanden ist oder wenn die Datei nicht gefunden wird. Die Verarbeitung kann oft nach einem **clear**-Aufruf mit einem null-Argument fortgesetzt werden.|  
|[good](http://msdn.microsoft.com/Library/77f0aa17-2ae1-48ae-8040-592d301e3972)|Gibt **TRUE** zurück, wenn kein Fehler (nicht behebbar oder anderweitig) vorhanden und das End-of-File-Flag nicht festgelegt ist.|  
|[eof](http://msdn.microsoft.com/Library/3087f631-1268-49cd-86cf-ff4108862329)|Gibt **TRUE** auf das End-of-File-Bedingung zurück.|  
|[clear](http://msdn.microsoft.com/Library/dc172694-1267-45f8-8f5c-e822e16fc271)|Legt den internen Fehlerzustand fest. Wenn mit den Standardargumenten aufgerufen, löscht er alle Fehlerbits.|  
|[rdstate](http://msdn.microsoft.com/Library/e235e4e2-7e95-4777-a160-3938d263dd9c)|Gibt den aktuellen Fehlerstatus zurück.|  
  
 Der **!** Operator wird überladen, um dieselbe Funktion wie die **fail**-Funktion auszuführen. Daher ist der Ausdruck:  
  
```  
if(!cout)...  
```  
  
 identisch mit folgendem Ausdruck:  
  
```  
if(cout.fail())...  
```  
  
 Der **void\*()**-Operator wird überladen, um das Gegenteil des **!** Operator zu sein; daher kommt der Ausdruck:  
  
```  
if(cout)...  
```  
  
 gleich:  
  
```  
if(!cout.fail())...  
```  
  
 Der **void\*()**-Operator entspricht nicht **good**, da er nicht das Ende der Datei testet.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausgabestreams](../standard-library/output-streams.md)


