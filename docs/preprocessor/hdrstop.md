---
title: hdrstop-Pragma
ms.date: 08/29/2019
f1_keywords:
- hdrstop_CPP
- vc-pragma.hdrstop
helpviewer_keywords:
- hdrstop pragma
- pragmas, hdrstop
ms.assetid: 5ea8370a-10d1-4538-ade6-4c841185da0e
ms.openlocfilehash: f540f0f01fe654213af15afa8fbf5cbd94e4b7e2
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221015"
---
# <a name="hdrstop-pragma"></a>hdrstop-Pragma

Bietet Ihnen zusätzliche Kontrolle über die Dateinamen der Vorkompilierung und über den Speicherort, an dem der Kompilierungs Status gespeichert wird.

## <a name="syntax"></a>Syntax

> **#pragma hdrstopps** [("*Dateiname*")]

## <a name="remarks"></a>Hinweise

Der *Dateiname* ist der Name der vorkompilierten Header Datei, die verwendet oder erstellt werden soll (abhängig davon, ob [/Yu](../build/reference/yu-use-precompiled-header-file.md) oder [/Yc](../build/reference/yc-create-precompiled-header-file.md) angegeben ist). Wenn *filename* keine Pfadangabe enthält, wird davon ausgegangen, dass sich die vorkompilierte Header Datei im selben Verzeichnis wie die Quelldatei befindet.

Wenn eine C- C++ Datei oder eine Datei ein **hdrstopp-** Pragma `/Yc`enthält, wenn Sie mit kompiliert wird, speichert der Compiler den Zustand der Kompilierung bis zum Speicherort des Pragmas. Der kompilierte Zustand eines beliebigen Codes, der auf das Pragma folgt, wird nicht gespeichert.

Verwenden Sie *filename* , um die vorkompilierte Header Datei zu benennen, in der der kompilierte Zustand gespeichert ist. Ein Leerzeichen zwischen **hdrstopps** und *filename* ist optional. Der im **hdrstopps** -Pragma angegebene Dateiname ist eine Zeichenfolge und unterliegt daher den Einschränkungen aller C- C++ oder Zeichen folgen. Insbesondere ist die Einschließung in Anführungszeichen und die Verwendung von Escapezeichen (umgekehrter Schrägstrich) erforderlich, um Verzeichnisnamen anzugeben. Beispiel:

```C
#pragma hdrstop( "c:\\projects\\include\\myinc.pch" )
```

Der Name der vorkompilierten Headerdatei wird gemäß den folgenden Regeln, in Rangfolge aufgelistet, bestimmt:

1. Das Argument `/Fp` der Compileroption.

2. Das *filename* -Argument für.`#pragma hdrstop`

3. Der Basisname der Quelldatei mit einer .PCH-Erweiterung

Wenn für `/Yc` die `/Yu` Optionen und keine der beiden Kompilierungsoptionen und das **hdrstopp-** Pragma einen Dateinamen angeben, wird der Basisname der Quelldatei als Basis Name der vorkompilierten Header Datei verwendet.

Sie können auch Präprozessorbefehle wie folgt verwenden, um Makroersetzung auszuführen:

```C
#define INCLUDE_PATH "c:\\progra~`1\\devstsu~1\\vc\\include\\"
#define PCH_FNAME "PROG.PCH"
.
.
.
#pragma hdrstop( INCLUDE_PATH PCH_FNAME )
```

Die folgenden Regeln steuern, wo das **hdrstopp-** Pragma platziert werden kann:

- Es muss außerhalb einer Daten- oder Funktionsdeklaration oder -definition angezeigt werden.

- Es muss in der Quelldatei, nicht in einer Headerdatei angegeben werden.

## <a name="example"></a>Beispiel

```C
#include <windows.h>                 // Include several files
#include "myhdr.h"

__inline Disp( char *szToDisplay )   // Define an inline function
{
    // ...                           // Some code to display string
}
#pragma hdrstop
```

In diesem Beispiel wird das **hdrstopp-** Pragma angezeigt, nachdem zwei Dateien eingeschlossen und eine Inline Funktion definiert wurde. Dieser Speicherort scheint zunächst eine ungerade Platzierung für das Pragma zu sein. Bedenken Sie jedoch, dass bei Verwendung der manuellen vorkompilierungs `/Yc` Optionen `/Yu`und mit dem **hdrstopp-** Pragma die Vorkompilierung ganzer Quelldateien möglich ist – auch Inline Code. Mit dem Microsoft-Compiler können nicht nur Datendeklarationen vorkompiliert werden.

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
