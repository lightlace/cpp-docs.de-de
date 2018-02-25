---
title: Include_alias | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.include_alias
- include_alias_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, include_alias
- include_alias pragma
ms.assetid: 3256d589-12b3-4af0-a586-199e96eabacc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5a2e3b6f6b8bbbc17073b5bf43b54fff3a619793
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="includealias"></a>include_alias

Gibt an, dass *Short_filename* als Alias für verwendet werden soll *Long_filename*.

## <a name="syntax"></a>Syntax

> #<a name="pragma-includealiaslongfilename-shortfilename"></a>pragma include_alias("*long_filename*", "*short_filename*")  
> #<a name="pragma-includealiaslongfilename-shortfilename"></a>Pragma-Include_alias (*Long_filename*, *Short_filename*)

## <a name="remarks"></a>Hinweise

Einige Dateisysteme unterstützen längere Headerdateinamen als das 8.3-FAT-Dateisystem. Der Compiler kann die längeren Namen nicht einfach bis 8.3 abschneiden, da die ersten acht Zeichen der längeren Headerdateinamen möglicherweise nicht eindeutig sind. Wenn der Compiler erkennt die *Long_filename* Zeichenfolge ist, ersetzt er *Short_filename*, und sucht nach der Headerdatei *Short_filename* stattdessen. Dieses Pragma muss vor den entsprechenden `#include`-Direktiven eingefügt werden. Zum Beispiel:

```cpp
// First eight characters of these two files not unique.
#pragma include_alias( "AppleSystemHeaderQuickdraw.h", "quickdra.h" )
#pragma include_alias( "AppleSystemHeaderFruit.h", "fruit.h" )

#pragma include_alias( "GraphicsMenu.h", "gramenu.h" )

#include "AppleSystemHeaderQuickdraw.h"
#include "AppleSystemHeaderFruit.h"
#include "GraphicsMenu.h"
```

Der Alias, nach dem gesucht wird, muss genau der Spezifikation entsprechen. Dies gilt für den Gebrauch von Groß-/Kleinschreibung, Rechtschreibung, doppelten Anführungszeichen und spitzen Klammern. Die **Include_alias** Pragma führt einfache zeichenfolgenabgleiche von Dateinamen durch; keine weitere dateinamenvalidierung wird durchgeführt. Zum Beispiel wird bei folgenden Anweisungen

```cpp
#pragma include_alias("mymath.h", "math.h")
#include "./mymath.h"
#include "sys/mymath.h"
```

kein Aliasing (Ersetzung) ausgeführt, da die Headerdateizeichenfolgen nicht genau übereinstimmen. Darüber hinaus die Headerdateinamen, die als Argumente für die/Yu- und/Yc-Compileroptionen verwendet oder die **Hdrstop** Pragma werden nicht ersetzt. Wenn beispielsweise die Quelldatei die folgenden Anweisungen enthält,
  
```cpp
#include <AppleSystemHeaderStop.h>
```

sollte die entsprechende Compileroption Folgendes sein:

> /YcAppleSystemHeaderStop.h

Sie können die **Include_alias** Pragma verwenden, um alle Headerdateinamen zu einem anderen zuordnen. Zum Beispiel:

```cpp
#pragma include_alias( "api.h", "c:\version1.0\api.h" )
#pragma include_alias( <stdio.h>, <newstdio.h> )
#include "api.h"
#include <stdio.h>
```

Mischen Sie die Dateinamen, die in Anführungszeichen eingeschlossen sind, nicht mit den Dateinamen in spitzen Klammern. Angenommen, die beiden oben erwähnten **#pragma Include_alias** Direktiven, die der Compiler führt keinen Ersatz für die folgenden `#include` Direktiven:

```cpp
#include <api.h>
#include "stdio.h"
```

Außerdem generiert die folgende Anweisung einen Fehler:

```cpp
#pragma include_alias(<header.h>, "header.h")  // Error
```

Beachten Sie, dass der Dateiname in Fehlermeldungen oder als Wert des vordefinierten gemeldet **&#95; &#95; Datei &#95; &#95;**  -Makro, ist der Name der Datei, nachdem die Ersetzung ausgeführt wurde. Beispielsweise finden Sie die Ausgabe nach den folgenden Anweisungen ein:

```cpp
#pragma include_alias( "VeryLongFileName.H", "myfile.h" )
#include "VeryLongFileName.H"
```

Ein Fehler in VERYLONGFILENAME. H erzeugt die folgende Fehlermeldung angezeigt:

```Output
myfile.h(15) : error C2059 : syntax error
```

Beachten Sie außerdem, dass Transitivität nicht unterstützt wird. Im Falle der folgenden Direktiven gilt:

```cpp
#pragma include_alias( "one.h", "two.h" )
#pragma include_alias( "two.h", "three.h" )
#include "one.h"
```

Der Compiler sucht die Datei TWO.H. statt THREE.H.  

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)