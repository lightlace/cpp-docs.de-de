---
title: include_alias
ms.date: 12/16/2018
f1_keywords:
- vc-pragma.include_alias
- include_alias_CPP
helpviewer_keywords:
- pragmas, include_alias
- include_alias pragma
ms.assetid: 3256d589-12b3-4af0-a586-199e96eabacc
ms.openlocfilehash: 187fa94f7c2a5457df655081b87a7f49d38adfa2
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024100"
---
# <a name="includealias"></a>include_alias

Gibt an, dass *Alias_filename* befindet sich einem `#include` -Anweisung der Compiler ersetzt *Actual_filename* an seiner Stelle.

## <a name="syntax"></a>Syntax

> #<a name="pragma-includealiasaliasfilename-actualfilename"></a>pragma include_alias("*alias_filename*", "*actual_filename*")
> #<a name="pragma-includealiasaliasfilename-actualfilename"></a>pragma include_alias(\<*alias_filename*>, \<*actual_filename*>)

## <a name="remarks"></a>Hinweise

Die **Include_alias** Pragma-Direktive können Sie Dateien zu ersetzen, die verschiedene Namen oder die Pfade für die Dateinamen von Quelldateien enthalten. Einige Dateisysteme können z. B. längere Headerdateinamen als das 8.3 Systemlimit von FAT-Datei. Der Compiler kann die längeren Namen nicht einfach bis 8.3 abschneiden, da die ersten acht Zeichen der längeren Headerdateinamen möglicherweise nicht eindeutig sind. Jedes Mal, wenn der Compiler erkennt die *Alias_filename* Zeichenfolge ist, ersetzt er *Actual_filename*, und sucht nach der Headerdatei *Actual_filename* stattdessen. Dieses Pragma muss vor den entsprechenden `#include`-Anweisungen eingefügt werden. Zum Beispiel:

```cpp
// First eight characters of these two files not unique.
#pragma include_alias( "AppleSystemHeaderQuickdraw.h", "quickdra.h" )
#pragma include_alias( "AppleSystemHeaderFruit.h", "fruit.h" )

#pragma include_alias( "GraphicsMenu.h", "gramenu.h" )

#include "AppleSystemHeaderQuickdraw.h"
#include "AppleSystemHeaderFruit.h"
#include "GraphicsMenu.h"
```

Der Alias, nach dem gesucht wird, muss genau der Spezifikation entsprechen. Dies gilt für den Gebrauch von Groß-/Kleinschreibung, Rechtschreibung, doppelten Anführungszeichen und spitzen Klammern. Die **Include_alias** Pragma führt einfache zeichenfolgenabgleiche die Dateinamen durch; keine weitere dateinamenvalidierung wird durchgeführt. Zum Beispiel wird bei folgenden Anweisungen

```cpp
#pragma include_alias("mymath.h", "math.h")
#include "./mymath.h"
#include "sys/mymath.h"
```

kein Aliasing (Ersetzung) ausgeführt, da die Headerdateizeichenfolgen nicht genau übereinstimmen. Darüber hinaus die Headerdateinamen, die als Argumente für die `/Yu` und `/Yc` Compileroptionen, oder die `hdrstop` Pragma werden nicht ersetzt. Wenn beispielsweise die Quelldatei die folgenden Anweisungen enthält,

```cpp
#include <AppleSystemHeaderStop.h>
```

sollte die entsprechende Compileroption Folgendes sein:

> /YcAppleSystemHeaderStop.h

Sie können die **Include_alias** Pragma, um einen anderen Headerdateinamen einem beliebigen zuzuordnen. Zum Beispiel:

```cpp
#pragma include_alias( "api.h", "c:\version1.0\api.h" )
#pragma include_alias( <stdio.h>, <newstdio.h> )
#include "api.h"
#include <stdio.h>
```

Mischen Sie die Dateinamen, die in Anführungszeichen eingeschlossen sind, nicht mit den Dateinamen in spitzen Klammern. Angenommen, die beiden oben erwähnten `#pragma include_alias` der Compiler führt keinen Ersatz für die folgenden `#include` Anweisungen:

```cpp
#include <api.h>
#include "stdio.h"
```

Außerdem generiert die folgende Direktive einen Fehler:

```cpp
#pragma include_alias(<header.h>, "header.h")  // Error
```

Beachten Sie, dass der Dateiname in Fehlermeldungen oder als Wert für die vordefinierten gemeldet `__FILE__` Makro verwenden, ist der Name der Datei aus, nachdem die Ersetzung ausgeführt wurde. Beispielsweise sehen Sie die Ausgabe nach den folgenden Anweisungen ein:

```cpp
#pragma include_alias( "VERYLONGFILENAME.H", "myfile.h" )
#include "VERYLONGFILENAME.H"
```

Fehler im VERYLONGFILENAME. H erzeugt die folgende Fehlermeldung angezeigt:

```Output
myfile.h(15) : error C2059 : syntax error
```

Beachten Sie außerdem, dass Transitivität nicht unterstützt wird. Im Falle der folgenden Direktiven gilt:

```cpp
#pragma include_alias( "one.h", "two.h" )
#pragma include_alias( "two.h", "three.h" )
#include "one.h"
```

der Compiler sucht nach der Datei Two.h statt Three.h.

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
