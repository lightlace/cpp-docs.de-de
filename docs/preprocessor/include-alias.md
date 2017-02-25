---
title: "include_alias | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.include_alias"
  - "include_alias_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "include_alias-Pragma"
  - "Pragmas, include_alias"
ms.assetid: 3256d589-12b3-4af0-a586-199e96eabacc
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# include_alias
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass *short\_filename* als Alias für *long\_filename* verwendet werden soll.  
  
## Syntax  
  
```  
  
      #pragma include_alias( "  
      long_filename  
      ", "  
      short_filename  
      " )  
#pragma include_alias( <long_filename>, <short_filename> )  
```  
  
## Hinweise  
 Einige Dateisysteme unterstützen längere Headerdateinamen als das 8.3\-FAT\-Dateisystem.  Der Compiler kann die längeren Namen nicht einfach bis 8.3 abschneiden, da die ersten acht Zeichen der längeren Headerdateinamen möglicherweise nicht eindeutig sind.  Wenn der Compiler auf die Zeichenfolge *long\_filename* trifft, ersetzt er *short\_filename* und sucht nach der Headerdatei *short\_filename*.  Dieses Pragma muss vor den entsprechenden `#include`\-Direktiven eingefügt werden.  Beispiel:  
  
```  
// First eight characters of these two files not unique.  
#pragma include_alias( "AppleSystemHeaderQuickdraw.h", "quickdra.h" )  
#pragma include_alias( "AppleSystemHeaderFruit.h", "fruit.h" )  
  
#pragma include_alias( "GraphicsMenu.h", "gramenu.h" )  
  
#include "AppleSystemHeaderQuickdraw.h"  
#include "AppleSystemHeaderFruit.h"  
#include "GraphicsMenu.h"  
```  
  
 Der Alias, nach dem gesucht wird, muss genau der Spezifikation entsprechen. Dies gilt für den Gebrauch von Groß\-\/Kleinschreibung, Rechtschreibung, doppelten Anführungszeichen und spitzen Klammern.  Das Pragma **include\_alias** führt einfache Zeichenfolgenabgleiche von Dateinamen durch; keine weitere Dateinamenvalidierung wird durchgeführt.  Zum Beispiel wird bei folgenden Direktiven  
  
```  
#pragma include_alias("mymath.h", "math.h")  
#include "./mymath.h"  
#include "sys/mymath.h"  
```  
  
 kein Aliasing \(Ersetzung\) ausgeführt, da die Headerdateizeichenfolgen nicht genau übereinstimmen.  Die Headerdateinamen, die als Argumente für die \/Yu\- und \/Yc\- Compileroptionen verwendet werden, oder das **hdrstop**\-Pragma werden nicht ersetzt.  Wenn beispielsweise die Quelldatei die folgenden Direktiven enthält,  
  
```  
#include <AppleSystemHeaderStop.h>  
```  
  
 sollte die entsprechende Compileroption Folgendes sein:  
  
```  
/YcAppleSystemHeaderStop.h  
```  
  
 Sie können das **include\_alias**\-Pragma verwenden, um einen Headerdateinamen einem beliebigen anderen Headerdateinamen zuzuordnen.  Beispiel:  
  
```  
#pragma include_alias( "api.h", "c:\version1.0\api.h" )  
#pragma include_alias( <stdio.h>, <newstdio.h> )  
#include "api.h"  
#include <stdio.h>  
```  
  
 Mischen Sie die Dateinamen, die in Anführungszeichen eingeschlossen sind, nicht mit den Dateinamen in spitzen Klammern.  Beispielsweise führt der Compiler angesichts der beiden oben erwähnten Direktiven **\#pragma include\_alias** keinen Ersatz für die nächsten `#include`\-Direktiven aus:  
  
```  
#include <api.h>  
#include "stdio.h"  
```  
  
 Außerdem generiert die folgende Direktive einen Fehler:  
  
```  
#pragma include_alias(<header.h>, "header.h")  // Error  
```  
  
 Beachten Sie, dass der Dateiname, der in Fehlermeldungen oder als Wert des vordefinierten **\_\_FILE\_\_**\-Makros gemeldet wird, der Name der Datei ist, nachdem die Ersetzung ausgeführt wurde.  Nach den folgenden Direktiven  
  
```  
#pragma include_alias( "VeryLongFileName.H", "myfile.h" )  
#include "VeryLongFileName.H"  
```  
  
 erzeugt beispielsweise ein Fehler in VERYLONGFILENAME.H die folgende Fehlermeldung:  
  
```  
myfile.h(15) : error C2059 : syntax error  
```  
  
 Beachten Sie außerdem, dass Transitivität nicht unterstützt wird.  Im Falle der folgenden Direktiven gilt:  
  
```  
#pragma include_alias( "one.h", "two.h" )  
#pragma include_alias( "two.h", "three.h" )  
#include "one.h"  
```  
  
 Der Compiler sucht die Datei TWO.H. statt THREE.H.  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)