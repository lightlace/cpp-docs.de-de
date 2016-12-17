---
title: "Verwenden von VERIFY anstelle ASSERT"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "assert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ASSERT-Anweisungen"
  - "Assertionen, Debuggen"
  - "Assertionen, Problembehandlung bei ASSERT-Anweisungen"
  - "Debuggen [MFC], ASSERT-Anweisungen"
  - "Debuggen von Assertionen"
  - "VERIFY-Makro"
ms.assetid: 4c46397b-3fb1-49c1-a09b-41a72fae3797
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Verwenden von VERIFY anstelle ASSERT
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Angenommen, das Ausführen des Debugbuilds der MFC\-Anwendung verläuft ohne Probleme.  Die Releaseversion derselben Anwendung wird jedoch nach einer Fehlfunktion beendet, gibt falsche Ergebnisse zurück und\/oder weist ein anderes nicht normales Verhalten auf.  
  
 Dieses Problem kann entstehen, wenn Sie in eine **ASSERT**\-Anweisung wichtigen Code einfügen, um festzustellen, ob er einwandfrei ausgeführt wird.  Da **ASSERT**\-Anweisungen im Releasebuild eines MFC\-Programms auskommentiert werden, wird der Code im Releasebuild nicht ausgeführt.  
  
 Es wird empfohlen, [VERIFY](../Topic/VERIFY.md) anstelle von ASSERT zu verwenden, um die erfolgreiche Ausführung eines Funktionsaufrufs zu bestätigen.  Das **VERIFY**\-Makro wertet seine eigenen Argumente sowohl im Debug\- als auch im Releasebuild einer Anwendung aus.  
  
 Eine weitere bevorzugte Methode besteht darin, den Rückgabewert der Funktion einer temporären Variablen zuzuweisen und diese Variable dann in einer **ASSERT**\-Anweisung zu testen.  
  
 Beachten Sie das folgende Codefragment:  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
ASSERT(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
 Dieser Code wird in der Debugversion einer MFC\-Anwendung fehlerfrei ausgeführt.  Wenn der Aufruf von `calloc( )` fehlschlägt, wird eine diagnostische Meldung mit dem Dateinamen und der Zeilennummer angezeigt.  Im Releasebuild einer MFC\-Anwendung geschieht jedoch Folgendes:  
  
-   Der Aufruf `calloc( )` findet niemals statt, wodurch `buf` nicht initialisiert wird. Oder  
  
-   `strcpy_s( )` kopiert die Zeichenfolge "`Hello, World`" an eine beliebige Stelle im Arbeitsspeicher, was wahrscheinlich dazu führt, dass das System nach einer Fehlfunktion beendet wird oder hängen bleibt. Oder  
  
-   `free()` versucht, Arbeitsspeicher freizugeben, der niemals belegt war.  
  
 Damit **ASSERT** problemlos verwendet werden kann, sollte das Codebeispiel folgendermaßen geändert werden:  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
buf = (char *) calloc(sizeOfBuffer, sizeof(char) );  
ASSERT( buf != NULL );  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
 Sie können stattdessen auch **VERIFY** verwenden:  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
VERIFY(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
## Siehe auch  
 [Beheben von Problemen mit dem Releasebuild](../../build/reference/fixing-release-build-problems.md)