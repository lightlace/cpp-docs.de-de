---
title: "&#220;berladen des Operators &lt;&lt; f&#252;r eigene Klassen"
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
  - "Operator <<, Überladen für eigene Klassen"
  - "operator<<, Überladen für eigene Klassen"
ms.assetid: ad1d2c49-d84e-48a8-9c09-121f28b10bf0
caps.latest.revision: 12
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# &#220;berladen des Operators &lt;&lt; f&#252;r eigene Klassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ausgabestreams verwenden den Operator Einfüge\- \(`<<`\) für Standardtypen.  Sie können den Operator `<<` für eigene Klassen überladen.  
  
## Beispiel  
 Das `write` Arbeitsbeispiel wurde die Verwendung einer `Date`\-Struktur.  Ein idealer Datum ist ein Kandidat für eine C\+\+\-Klasse, in der die Datenmember \(Monat, Tag und Jahr\) in der Ansicht ausgeblendet werden.  Ein Ausgabestream ist das logische Ziel zum Anzeigen für eine solche Struktur.  Dieser Code zeigt ein Datum unter Verwendung des `cout`\-Objekts an:  
  
```  
Date dt( 1, 2, 92 );  
cout << dt;  
```  
  
 Zum Abrufen von `cout` um ein `Date`\-Objekt nach dem Einfügungsoperator akzeptiert, überladen Sie den Einfügungsoperator um ein `ostream`\-Objekt auf der linken und `Date` auf der rechten Seite zu erkennen.  Die überladene `<<`\-Operatorfunktion muss anschließend deklariert werden, wie ein Friend der Klasse `Date` daher auf die privaten Daten innerhalb eines `Date`\-Objekts zugreifen kann.  
  
```  
// overload_date.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
class Date  
{  
    int mo, da, yr;  
public:  
    Date(int m, int d, int y)  
    {  
        mo = m; da = d; yr = y;  
    }  
    friend ostream& operator<<(ostream& os, const Date& dt);  
};  
  
ostream& operator<<(ostream& os, const Date& dt)  
{  
    os << dt.mo << '/' << dt.da << '/' << dt.yr;  
    return os;  
}  
  
int main()  
{  
    Date dt(5, 6, 92);  
    cout << dt;  
}  
```  
  
  **5\/6\/92**   
## Hinweise  
 Der überladene Operator gibt einen Verweis auf den ursprünglichen `ostream`\-Objekt zurück, das heißt Sie Einfügungen kombinieren kann:  
  
```  
cout << "The date is" << dt << flush;  
```  
  
## Siehe auch  
 [Ausgabestreams](../standard-library/output-streams.md)