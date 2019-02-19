---
title: Rekursive Funktionen
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C], recursive
- function calls, recursive
- functions [C], calling recursively
- recursive function calls
ms.assetid: 59739040-3081-4006-abbc-9d8423992bce
ms.openlocfilehash: 82f0c820ab75fda4bae83db78fa402d7a07cb7fe
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152429"
---
# <a name="recursive-functions"></a>Rekursive Funktionen

Jede Funktion in einem C-Programm kann rekursiv aufgerufen werden, d. h. sie kann sich selbst aufrufen. Die Anzahl von rekursiven Aufrufen ist auf die Größe des Stapels beschränkt. Weitere Informationen zu Linkeroptionen, die die Stapelgröße festlegen, erhalten Sie unter [/STACK (Stapelreservierungen)](../build/reference/stack-stack-allocations.md). Jedes Mal, wenn die Funktion aufgerufen wird, wird neuer Speicherplatz für die Parameter und für die Variablen **auto** und **register** zugeordnet, sodass die Werte in den vorangegangenen, unfertigen Aufrufen nicht überschrieben werden. Auf Parameter kann nur direkt durch die Instanz der Funktion zugegriffen werden, in der sie erstellt werden. Auf vorherige Parameter kann nicht direkt durch nachfolgende Instanzen der Funktion zugegriffen werden.

Beachten Sie, dass die Variablen, die mit **static**-Speicher deklariert werden, keinen neuen Speicher mit jedem rekursiven Aufruf erfordern. Der Speicher bleibt so lange erhalten wie das Programm besteht. Jeder Verweis auf eine solche Variable greift auf denselben Speicherbereich zu.

## <a name="example"></a>Beispiel

In diesem Beispiel werden rekursive Aufrufe veranschaulicht:

```C
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

## <a name="see-also"></a>Siehe auch

[Funktionsaufrufe](../c-language/function-calls.md)
