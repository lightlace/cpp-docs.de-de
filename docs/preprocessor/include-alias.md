---
title: include_alias-Pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.include_alias
- include_alias_CPP
helpviewer_keywords:
- pragmas, include_alias
- include_alias pragma
ms.assetid: 3256d589-12b3-4af0-a586-199e96eabacc
ms.openlocfilehash: aa3714186e8f95d4044ba5a3b2bc2d5fcfb1fc9c
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218904"
---
# <a name="include_alias-pragma"></a>include_alias-Pragma

Gibt an, dass der Compiler *actual_filename* an `#include` seiner Stelle ersetzt, wenn *alias_filename* in einer-Direktive gefunden wird.

## <a name="syntax"></a>Syntax

<!-- localization note - it's important to have the italic and bold characters immediately adjacent here. -->
> **#pragma Include_alias (** "*alias_filename*" **,** "*actual_filename*" **)** \
> **#pragma Include_alias (** \< *alias_filename*>  **,** *actual_filename*) \<> 

## <a name="remarks"></a>Hinweise

Mit der **Include_alias** -pragma-Direktive können Sie Dateien ersetzen, die unterschiedliche Namen oder Pfade für die in den Quelldateien enthaltenen Dateinamen haben. Einige Dateisysteme erlauben z. b. längere Header Dateinamen als das Limit von 8,3 FAT-Dateisystemen. Der Compiler kann die längeren Namen nicht einfach auf 8,3 kürzen, da die ersten acht Zeichen der längeren Header Dateinamen möglicherweise nicht eindeutig sind. Wenn der Compiler die *alias_filename* -Zeichenfolge in `#include` einer-Direktive sieht, ersetzt er stattdessen den Namen *actual_filename* . Anschließend wird die Header Datei *actual_filename* geladen. Dieses Pragma muss vor den entsprechenden `#include`-Anweisungen eingefügt werden. Beispiel:

```cpp
// First eight characters of these two files not unique.
#pragma include_alias( "AppleSystemHeaderQuickdraw.h", "quickdra.h" )
#pragma include_alias( "AppleSystemHeaderFruit.h", "fruit.h" )

#pragma include_alias( "GraphicsMenu.h", "gramenu.h" )

#include "AppleSystemHeaderQuickdraw.h"
#include "AppleSystemHeaderFruit.h"
#include "GraphicsMenu.h"
```

Der zu suchende Alias muss genau mit der Spezifikation übereinstimmen. Die Groß-/Kleinschreibung, Rechtschreibung und Verwendung von doppelten Anführungszeichen oder spitzen Klammern müssen identisch sein. Das **Include_alias** -Pragma führt einfache Zeichen folgen Übereinstimmungen in den Dateinamen aus. Es wird keine andere Dateinamen Überprüfung durchgeführt. Zum Beispiel wird bei folgenden Anweisungen

```cpp
#pragma include_alias("mymath.h", "math.h")
#include "./mymath.h"
#include "sys/mymath.h"
```

Es wird keine Alias Ersetzung durchgeführt, da die Header Datei Zeichenfolgen nicht exakt übereinstimmen. Außerdem werden Header Dateinamen, die als Argumente `/Yu` für `/Yc` die-und-Compileroptionen oder das `hdrstop` -Pragma verwendet werden, nicht ersetzt. Wenn beispielsweise die Quelldatei die folgenden Anweisungen enthält,

```cpp
#include <AppleSystemHeaderStop.h>
```

sollte die entsprechende Compileroption Folgendes sein:

> **/YcAppleSystemHeaderStop.h**

Sie können das **Include_alias** -Pragma verwenden, um einen beliebigen Header Dateinamen einem anderen zuzuordnen. Beispiel:

```cpp
#pragma include_alias( "api.h", "c:\version1.0\api.h" )
#pragma include_alias( <stdio.h>, <newstdio.h> )
#include "api.h"
#include <stdio.h>
```

Kombinieren Sie die in doppelten Anführungszeichen eingeschlossenen Dateinamen nicht mit Dateinamen, die in spitzen Klammern eingeschlossen sind. Beispielsweise führt der Compiler bei Angabe `#pragma include_alias` der obigen beiden Direktiven keine Ersetzung der folgenden `#include` Direktiven aus:

```cpp
#include <api.h>
#include "stdio.h"
```

Außerdem generiert die folgende Direktive einen Fehler:

```cpp
#pragma include_alias(<header.h>, "header.h")  // Error
```

Der in Fehlermeldungen oder als Wert des vordefinierten `__FILE__` Makros gemeldete Dateiname ist der Name der Datei, nachdem die Ersetzung durchgeführt wurde. Betrachten Sie z. b. die Ausgabe nach den folgenden Anweisungen:

```cpp
#pragma include_alias( "VERYLONGFILENAME.H", "myfile.h" )
#include "VERYLONGFILENAME.H"
```

Ein Fehler in " *VERYLONGFILENAME". H* erzeugt die folgende Fehlermeldung:

```Output
myfile.h(15) : error C2059 : syntax error
```

Beachten Sie außerdem, dass Transitivität nicht unterstützt wird. Im Falle der folgenden Direktiven gilt:

```cpp
#pragma include_alias( "one.h", "two.h" )
#pragma include_alias( "two.h", "three.h" )
#include "one.h"
```

der Compiler sucht nach der Datei " *Two. h* " und nicht nach " *3. h*".

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
