---
title: "Rekursive Funktionen"
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
  - "C"
helpviewer_keywords: 
  - "Funktionsaufrufe, Rekursiv"
  - "Funktionen [C], Rekursives Aufrufen"
  - "Funktionen [C], Rekursiv"
  - "Rekursive Funktionsaufrufe"
ms.assetid: 59739040-3081-4006-abbc-9d8423992bce
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Rekursive Funktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Jede Funktion in einem C\-Programm kann rekursiv aufgerufen werden, d. h. sie kann sich selbst aufrufen.  Die Anzahl von rekursiven Aufrufen ist auf die Größe des Stapels beschränkt.  Weitere Informationen zu Linkeroptionen, die die Stapelgröße festlegen, erhalten Sie unter der [\/STACK \(Stapelreservierungen\)](../build/reference/stack-stack-allocations.md) \(\/STACK\)\-Linkeroption.  Jedes Mal, wenn die Funktion aufgerufen wird, wird neuer Speicherplatz für die Parameter und für die Variablen **auto** und **register** zugeordnet, sodass die Werte in den vorangegangenen, unfertigen Aufrufen nicht überschrieben werden.  Auf Parameter kann nur direkt durch die Instanz der Funktion zugegriffen werden, in der sie erstellt werden.  Auf vorherige Parameter kann nicht direkt durch nachfolgende Instanzen der Funktion zugegriffen werden.  
  
 Beachten Sie, dass die Variablen, die mit **static**\-Speicher deklariert werden, keinen neuen Speicher mit jedem rekursiven Aufruf erfordern.  Der Speicher bleibt so lange erhalten wie das Programm besteht.  Jeder Verweis auf eine solche Variable greift auf denselben Speicherbereich zu.  
  
## Beispiel  
 In diesem Beispiel werden rekursive Aufrufe veranschaulicht:  
  
```  
int factorial( int num );      /* Function prototype */  
  
int main()  
{  
    int result, number;  
    .  
    .  
    .  
    result = factorial( number );  
}  
  
int factorial( int num )      /* Function definition */  
{  
    .  
    .  
    .  
    if ( ( num > 0 ) || ( num <= 10 ) )  
        return( num * factorial( num - 1 ) );  
}  
  
```  
  
## Siehe auch  
 [Funktionsaufrufe](../c-language/function-calls.md)