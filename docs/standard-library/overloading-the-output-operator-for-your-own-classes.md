---
title: "Überladen des &lt;&lt;-Operators für eigene Klassen | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- operator<<, overloading for your own classes
- operator <<, overloading for your own classes
ms.assetid: ad1d2c49-d84e-48a8-9c09-121f28b10bf0
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d86b9192e955e0aa42fcb7de5d472c94ffa443d7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="overloading-the-ltlt-operator-for-your-own-classes"></a>Überladen des &lt;&lt;-Operators für eigene Klassen
Eingabestreams verwenden die Extraktion (`<<`)-Operator für die Standardtypen. Sie können auch den `<<`-Operator für eigene Klassen überladen.  
  
## <a name="example"></a>Beispiel  
 Die `write`-Beispielfunktion zeigt die Verwendung einer `Date`-Struktur. Ein Datum ist ein idealer Kandidat für eine C++-Klasse, in der Datenmember (Monat, Tag und Jahr) aus der Ansicht ausgeblendet werden. Ein Ausgabestream ist das logische Ziel für die Anzeige einer solchen Struktur. Dieser Code zeigt ein Datum unter Verwendung des `cout`-Objekts:  
  
```  
Date dt(1, 2, 92);

cout <<dt;  
```  
  
 Damit `cout` ein `Date`-Objekt nach den Einfügeoperator akzeptiert, müssen Sie den Einfügeoperator zum Erkennen eines `ostream`-Objekts auf der linken Seite und eines `Date`-Objekts auf der rechten Seite überladen. Die überladenen `<<` Operatorfunktion muss dann als Friend der Klasse `Date` deklariert werden, sodass sie mit einem `Date`-Objekt auf die privaten Daten zugreifen kann.  
  
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
  
```Output  
5/6/92  
```  
  
## <a name="remarks"></a>Hinweise  
 Der überladene Operator gibt einen Verweis auf das ursprüngliche `ostream`-Objekt zurück, d.h., Sie können Einfügevorgängen kombinieren:  
  
```  
cout <<"The date is" <<dt <<flush;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ausgabestreams](../standard-library/output-streams.md)

