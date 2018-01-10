---
title: "Verweistyp-Funktionsrückgaben | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- function return types [C++], reference type
- data types [C++], function return types
- functions [C++], return types
ms.assetid: 5b73be1d-2dc7-41df-ab0a-adcba36f2ad1
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a3a5d0b299b2bc38c95420515ab49eabd1268305
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="reference-type-function-returns"></a>Verweistyp-Funktionsrückgaben
Funktionen können deklariert werden, um einen Verweistyp zurückzugeben. Es gibt zwei Gründe, eine solche Deklaration vorzunehmen:  
  
-   Bei der zurückgegebenen Information handelt es sich um ein ausreichend großes Objekt, so dass die Rückgabe eines Verweises effizienter ist als die Rückgabe einer Kopie.  
  
-   Der Typ der Funktion muss ein l-Wert sein.  
  
-   Das verwiesene Objekt geht bei Rückgabe der Funktion nicht außerhalb des gültigen Bereichs.  
  
 So fest, wie es effizienter, große Objekte übergeben werden kann *auf* Funktionen als Verweis es auch kann effizienter sein, große Objekte zurückgeben *aus* Funktionen als Verweis. Durch das Verweisrückgabeprotokoll entfällt die Notwendigkeit, das Objekt vor der Rückgabe in einen temporären Speicherort zu kopieren.  
  
 Verweisrückgabetypen können auch nützlich sein, wenn die Funktion als l-Wert ausgewertet werden muss. Die meisten überladenen Operatoren fallen in diese Kategorie, vor allem der Zuweisungsoperator. Überladene Operatoren werden in behandelt [überladene Operatoren](../cpp/operator-overloading.md).  
  
## <a name="example"></a>Beispiel  
 Betrachten Sie das `Point`-Beispiel:  
  
```  
// refType_function_returns.cpp  
// compile with: /EHsc  
  
#include <iostream>  
using namespace std;  
  
class Point  
{  
public:  
// Define "accessor" functions as  
//  reference types.  
unsigned& x();  
unsigned& y();  
private:  
// Note that these are declared at class scope:  
unsigned obj_x;   
unsigned obj_y;   
};  
  
unsigned& Point :: x()  
{  
return obj_x;  
}  
unsigned& Point :: y()  
{  
return obj_y;  
}  
  
int main()  
{  
Point ThePoint;  
// Use x() and y() as l-values.  
ThePoint.x() = 7;  
ThePoint.y() = 9;  
  
// Use x() and y() as r-values.  
cout << "x = " << ThePoint.x() << "\n"  
<< "y = " << ThePoint.y() << "\n";  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
x = 7  
y = 9  
```  
  
 Beachten Sie, dass die Funktionen `x` und `y` als zurückgebende Verweistypen deklariert werden. Diese Funktionen können auf beiden Seiten einer Zuweisungsanweisung verwendet werden.  
  
 Beachten Sie auch, dass in Main das Punktobjekt im Gültigkeitsbereich bleibt und daher seine Verweismember noch aktiv sind und sicher auf sie zugegriffen werden kann.  
  
 Deklarationen von Verweistypen müssen Initialisierer enthalten, ausgenommen in den folgenden Fällen:  
  
-   Explizite `extern`-Deklaration  
  
-   Deklaration eines Klassenmembers  
  
-   Deklaration innerhalb einer Klasse  
  
-   Deklaration eines Arguments für eine Funktion oder der Rückgabetyp für eine Funktion  
  
## <a name="caution-returning-address-of-local"></a>Vorsicht, Rückgabe einer Adresse einer lokalen  
 Wenn Sie ein Objekt im lokalen Gültigkeitsbereich deklarieren, wird das Objekt bei Rückgabe der Funktion zerstört. Gibt die Funktion einen Verweis auf das Objekt zurück, verursacht dieser Verweis wahrscheinlich eine Zugriffsverletzung zur Laufzeit, wenn der Aufrufer versucht, den NULL-Verweis zu verwenden.  
  
```  
// C4172 means Don’t do this!!!  
Foo& GetFoo()  
{  
    Foo f;  
    ...  
    return f;  
} // f is destroyed here  
```  
  
 Der Compiler einer Warnung in diesem Fall: `warning C4172: returning address of local variable or temporary`. In einfachen Programmen ist es möglich, dass gelegentlich keine Zugriffsverletzung auftritt, wenn der Verweis vom Aufrufer erfolgt, bevor die Speicheradresse überschrieben wird. Dies ist einfach auf Glück zurückzuführen. Warnung beachten.  
  
## <a name="see-also"></a>Siehe auch  
 [Verweise](../cpp/references-cpp.md)