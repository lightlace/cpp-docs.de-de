---
title: "Übersicht über Memberfunktionen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- this pointer, and nonstatic member functions
- nonstatic member functions [C++]
- inline functions [C++], treating member functions as
- member functions [C++], definition in class declaration
ms.assetid: 9f77a438-500e-40bb-a6c6-544678f3f4c8
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: cc73317962c92a7f35d103b342ca52aa0bef4f2e
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="overview-of-member-functions"></a>Übersicht über Memberfunktionen
Memberfunktionen sind entweder statisch oder nicht statisch. Das Verhalten von statischen Memberfunktionen unterscheidet sich von anderen Memberfunktionen, da statische Memberfunktionen nicht über ein implizites haben **dies** Argument. Nicht statische Memberfunktionen haben einen **dies** Zeiger. Memberfunktionen können, ob statisch oder nicht statisch, entweder inner- oder außerhalb der Klassendeklaration definiert werden.  
  
 Wenn eine Memberfunktion innerhalb einer Klassendeklaration definiert ist, wird sie als Inlinefunktion behandelt, und es ist nicht erforderlich, den Funktionsnamen mit dem Klassennamen zu qualifizieren. Obwohl innerhalb von Klassendeklarationen definierte Funktionen bereits als Inlinefunktionen behandelt werden, können Sie die **Inline** Schlüsselwort zum Dokumentieren von Code.  
  
 Ein Beispiel des Deklarierens einer Funktion innerhalb einer Klassendeklaration folgt:  
  
```  
// overview_of_member_functions1.cpp  
class Account  
{  
public:  
    // Declare the member function Deposit within the declaration  
    //  of class Account.  
    double Deposit( double HowMuch )  
    {  
        balance += HowMuch;  
        return balance;  
    }  
private:  
    double balance;  
};  
  
int main()  
{  
}  
```  
  
 Wenn eine Memberfunktion Definition außerhalb der Klassendeklaration ist, wird dies als behandelt eine Inlinefunktion nur, wenn er als explizit deklariert wird **Inline**. Darüber hinaus muss der Funktionsname in der Definition mit dem Klassennamen mithilfe des Bereichsauflösungsoperators (`::`) qualifiziert sein.  
  
 Das folgende Beispiel ist mit der vorherigen Deklaration der Klasse `Account` identisch, mit der Ausnahme, dass die Funktion `Deposit` außerhalb der Klassendeklaration definiert ist:  
  
```  
// overview_of_member_functions2.cpp  
class Account  
{  
public:  
    // Declare the member function Deposit but do not define it.  
    double Deposit( double HowMuch );  
private:  
    double balance;  
};  
  
inline double Account::Deposit( double HowMuch )  
{  
    balance += HowMuch;  
    return balance;  
}  
  
int main()  
{  
}  
```  
  
> [!NOTE]
>  Obwohl Memberfunktionen entweder innerhalb einer Klassendeklaration definiert werden können oder getrennt, können keine Memberfunktionen einer Klasse hinzugefügt werden, nachdem die Klasse definiert ist.  
  
 Die Klassen, die Memberfunktionen enthalten, können viele Deklarationen haben, aber die Memberfunktionen selbst dürfen nur eine Definition in einem Programm haben. Mehrfache Definitionen verursachen zur Verknüpfungszeit eine Fehlermeldung. Wenn eine Klasse Inlinefunktionsdefinitionen enthält, müssen die Funktionsdefinitionen identisch sein, um dieser ODR (one definition rule) zu entsprechen.  
  

