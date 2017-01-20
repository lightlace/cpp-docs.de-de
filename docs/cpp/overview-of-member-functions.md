---
title: "&#220;bersicht &#252;ber Memberfunktionen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Inlinefunktionen, Behandeln von Memberfunktionen als"
  - "Memberfunktionen, Definition in der Klassendeklaration"
  - "Nicht statische Memberfunktionen"
  - "This-Zeiger, Und nicht statische Memberfunktionen"
ms.assetid: 9f77a438-500e-40bb-a6c6-544678f3f4c8
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# &#220;bersicht &#252;ber Memberfunktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Memberfunktionen sind entweder statisch oder nicht statisch.  Das Verhalten von statischen Memberfunktionen unterscheidet sich von anderen Memberfunktionen, da statische Memberfunktionen nicht über ein implizites **this**\-Argument verfügen.  Nicht statische Memberfunktionen haben einen **this**\-Zeiger.  Memberfunktionen können, ob statisch oder nicht statisch, entweder inner\- oder außerhalb der Klassendeklaration definiert werden.  
  
 Wenn eine Memberfunktion innerhalb einer Klassendeklaration definiert ist, wird sie als Inlinefunktion behandelt, und es ist nicht erforderlich, den Funktionsnamen mit dem Klassennamen zu qualifizieren.  Obwohl innerhalb von Klassendeklarationen definierte Funktionen bereits als Inlinefunktionen behandelt werden, können Sie das **inline**\-Schlüsselwort verwenden, um Code zu dokumentieren.  
  
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
  
 Wenn die Definition einer Memberfunktion außerhalb der Klassendeklaration liegt, wird sie nur als Inlinefunktion behandelt, wenn sie explizit als **inline** deklariert ist.  Darüber hinaus muss der Funktionsname in der Definition mit dem Klassennamen mithilfe des Bereichsauflösungsoperators \(`::`\) qualifiziert sein.  
  
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
  
 Die Klassen, die Memberfunktionen enthalten, können viele Deklarationen haben, aber die Memberfunktionen selbst dürfen nur eine Definition in einem Programm haben.  Mehrfache Definitionen verursachen zur Verknüpfungszeit eine Fehlermeldung.  Wenn eine Klasse Inlinefunktionsdefinitionen enthält, müssen die Funktionsdefinitionen identisch sein, um dieser ODR \(one definition rule\) zu entsprechen.  
  
## Siehe auch  
 [Memberfunktionen](../misc/member-functions-cpp.md)