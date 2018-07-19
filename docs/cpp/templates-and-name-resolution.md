---
title: Vorlagen und namensauflösung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 519ba7b5-cd25-4549-865a-9a7b9dffdc28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2b27f6f7f56604976bb1004594fc7c0ac6fdc923
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32422812"
---
# <a name="templates-and-name-resolution"></a>Vorlagen und Namensauflösung

In den Vorlagendefinitionen gibt es drei Typen von Namen.  
  
-   Lokal deklarierte Namen, einschließlich des Namens der Vorlage selbst sowie aller Namen, die innerhalb der Vorlagendefinition deklariert werden.  
  
-   Namen des einschließenden Bereichs außerhalb der Vorlagendefinition.  
  
-   Namen, die in irgendeiner Form von Vorlagenargumenten abhängig sind, die als abhängige Namen bezeichnet werden.  
  
 Während die ersten beiden Namen sich auch auf Gültigkeitsbereiche für Klassen und Funktionen beziehen, sind spezielle Regeln für die Namensauflösung in Vorlagendefinitionen erforderlich, um komplexere abhängige Namen zu verarbeiten. Dies liegt daran, dass dem Compiler nur wenig über diese Namen bekannt ist, bevor die Vorlage instanziiert wird, da sie je nach verwendeten Vorlagenargumenten völlig unterschiedliche Typen aufweisen können. Nicht abhängige Namen werden nach den üblichen Regeln und zum Zeitpunkt der Definition der Vorlage gesucht. Diese Namen sind unabhängig von den Vorlagenargumenten und werden einmal für alle Vorlagenspezialisierungen nachgeschlagen. Abhängige Namen werden erst nach dem Instanziieren der Vorlage und für jede Spezialisierung separat gesucht.  
  
 Ein Typ ist abhängig, wenn er von Vorlagenargumenten abhängt. Ein Typ ist insbesondere abhängig, wenn:  
  
-   Das Vorlagenargument selbst:  
  
    ```cpp
    T  
    ```  
  
-   Ein qualifizierter Name einer Qualifikation einschließlich eines abhängigen Typs:  
  
    ```cpp
    T::myType  
    ```  
  
-   Ein qualifizierter Name, wenn der nicht qualifizierte Teil einen abhängigen Typ bezeichnet:  
  
    ```cpp
    N::T  
    ```  
  
-   Ein konstanter oder ein flüchtiger Typ, für den der Basistyp ein abhängiger Typ ist:  
  
    ```cpp
    const T  
    ```  
  
-   Ein Zeiger, ein Verweis, ein Array oder ein Funktionszeigertyp, basierend auf einem abhängigen Typ:  
  
    ```cpp
    T *, T &, T [10], T (*)()  
    ```  
  
-   Ein Array, dessen Größe auf einem Vorlagenparameter basiert:  
  
    ```cpp
    template <int arg> class X {  
    int x[arg] ; // dependent type  
    }  
    ```  
  
-   Ein aus einem Vorlagenparameter erstellter Vorlagentyp:  
  
    ```cpp
    T<int>, MyTemplate<T>  
    ```  
  
## <a name="type-dependence-and-value-dependence"></a>Typabhängigkeit und Werteabhängigkeit

 Namen und Ausdrücke, die von einem Vorlagenparameter abhängig sind, werden als typabhängig oder wertabhängig kategorisiert, je nachdem, ob der Vorlagenparameter ein Typparameter oder ein Werteparameter ist. Außerdem gelten alle Bezeichner, die in einer Vorlage mit einem abhängigen Typ vom Vorlagenargument deklariert werden, als wertabhängiges Element, z. B. eine ganze Zahl oder ein Enumerationstyp, die mit einem wertabhängigen Ausdruck initialisiert werden.  
  
 Typabhängige und wertabhängige Ausdrücke sind Ausdrücke, die Variablen einschließen, die typabhängig oder wertabhängig sind. Diese Begriffe können je nach Parametern, die für die Vorlage verwendet werden, eine abweichende Semantik aufweisen.  
  
## <a name="see-also"></a>Siehe auch

 [Vorlagen](../cpp/templates-cpp.md)
