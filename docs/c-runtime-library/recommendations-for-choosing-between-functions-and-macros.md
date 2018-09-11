---
title: Empfehlungen für die Wahl zwischen Funktionen und Makros | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.functions
dev_langs:
- C++
helpviewer_keywords:
- functions [CRT], vs. macros
- macros, vs. functions
ms.assetid: 18a633d6-cf1c-470c-a649-fa7677473e2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5185b3b39ad74381113bd858f9db20ccddfe0fa8
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752598"
---
# <a name="recommendations-for-choosing-between-functions-and-macros"></a>Empfehlungen für die Wahl zwischen Funktionen und Macros
Die meisten Microsoft-Laufzeitbibliotheken-Routinen sind kompilierte oder assemblierte Funktionen, aber einige Routinen werden als Makros implementiert. Wenn eine Headerdatei sowohl die Funktions- als auch Makroversion einer Routine deklariert, hat die Makrodefinition Vorrang, da sie immer auf die Funktionsdeklaration folgt. Wenn Sie eine Routine aufrufen, die sowohl als Funktion als auch als Makro implementiert ist, können Sie den Compiler auf zwei Arten zwingen, die Funktionsversion zu verwenden:  
  
-   Schließen Sie den Routinennamen in Klammern ein.  
  
    ```C
    #include <ctype.h>  
    a = _toupper(a);    // Use macro version of toupper.  
    a = (_toupper)(a);  // Force compiler to use   
                        // function version of toupper.  
    ```  
  
-   Heben Sie die Makrodefinition mit der `#undef`-Richtlinie auf:  
  
    ```C
    #include <ctype.h>  
    #undef _toupper  
    ```  
  
Wenn Sie zwischen einer Funktions- und Makroimplementierung einer Bibliotheksroutine wählen müssen, sollten Sie die folgenden Vor- und Nachteile abwägen:  
  
-   **Geschwindigkeit im Vergleich zur Größe**: Der Hauptvorteil der Verwendung von Makros ist die schnellere Ausführung. Während der Vorverarbeitung wird ein Makro bei jeder Verwendung inline erweitert (durch seine Definition ersetzt). Eine Funktionsdefinition tritt nur einmal auf, unabhängig davon, wie oft sie aufgerufen wird. Makros können die Codegröße erhöhen, erfordern jedoch nicht den mit Funktionsaufrufen verbunden Mehraufwand.  
  
-   **Funktionsauswertung**: Eine Funktion wird als Adresse ausgewertet, ein Makro aber nicht. Sie können also keinen Makronamen in Kontexten verwenden, die einen Zeiger erfordern. Sie können z.B. einen Zeiger auf eine Funktion, aber keinen Zeiger auf ein Makro deklarieren.  
  
-   **Typüberprüfung**: Wenn Sie eine Funktion deklarieren, kann der Compiler die Argumenttypen überprüfen. Da Sie kein Makro deklarieren können, kann der Compiler die Makroargumenttypen nicht überprüfen; obwohl er die Anzahl von Argumenten überprüfen kann, die Sie einem Makro übergeben.  
  
## <a name="see-also"></a>Siehe auch  
[CRT-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)