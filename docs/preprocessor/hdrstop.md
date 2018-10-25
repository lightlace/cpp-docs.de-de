---
title: Hdrstop | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- hdrstop_CPP
- vc-pragma.hdrstop
dev_langs:
- C++
helpviewer_keywords:
- hdrstop pragma
- pragmas, hdrstop
ms.assetid: 5ea8370a-10d1-4538-ade6-4c841185da0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e571229602a311633fc7425384544c53813b935
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059713"
---
# <a name="hdrstop"></a>hdrstop
Gibt Ihnen zusätzliche Kontrolle über Vorkompilierungs-Dateinamen und über den Speicherort, an dem der Zustand der Kompilierung gespeichert wird.

## <a name="syntax"></a>Syntax

```
#pragma hdrstop [( "filename" )]
```

## <a name="remarks"></a>Hinweise

Die *Filename* ist der Name der vorkompilierten Headerdatei oder erstellen Sie (je nachdem, ob ["/ Yu"](../build/reference/yu-use-precompiled-header-file.md) oder ["/ Yc"](../build/reference/yc-create-precompiled-header-file.md) angegeben ist). Wenn *Filename* enthält keine Pfadangabe wird angenommen, dass die vorkompilierte Headerdatei um im selben Verzeichnis wie die Quelldatei zu werden.

Wenn eine C- oder C++-Datei enthält eine **Hdrstop** Pragma, bei der Kompilierung mit `/Yc`, speichert der Compiler den Zustand der Kompilierung bis zur Position des Pragmas. Der kompilierte Zustand von Code, der dem Pragma folgt, wird nicht gespeichert.

Verwendung *Filename* die vorkompilierten Headerdatei zu benennen, in der der kompilierte Zustand gespeichert ist. Ein Leerzeichen zwischen **Hdrstop** und *Filename* ist optional. Die Datei im angegebenen Namen der **Hdrstop** Pragma ist eine Zeichenfolge und aus diesem Grund unterliegt den Einschränkungen jeder C- oder C++-Zeichenfolge. Insbesondere ist die Einschließung in Anführungszeichen und die Verwendung von Escapezeichen (umgekehrter Schrägstrich) erforderlich, um Verzeichnisnamen anzugeben. Zum Beispiel:

```
#pragma hdrstop( "c:\\projects\\include\\myinc.pch" )
```

Der Name der vorkompilierten Headerdatei wird gemäß den folgenden Regeln, in Rangfolge aufgelistet, bestimmt:

1. Das Argument für die `/Fp` -Compileroption

2. Die *Filename* Argument `#pragma hdrstop`

3. Der Basisname der Quelldatei mit einer .PCH-Erweiterung

Für die `/Yc` und `/Yu` "Optionen", wenn keine der beiden Kompilierungsoptionen noch das **Hdrstop** Pragma gibt einen Dateinamen an, der Basisname der Quelldatei als Basisname der vorkompilierten Headerdatei verwendet wird.

Sie können auch Präprozessorbefehle wie folgt verwenden, um Makroersetzung auszuführen:

```
#define INCLUDE_PATH "c:\\progra~`1\\devstsu~1\\vc\\include\\"
#define PCH_FNAME "PROG.PCH"
.
.
.
#pragma hdrstop( INCLUDE_PATH PCH_FNAME )
```

Die folgenden Regeln wird bestimmt, wo die **Hdrstop** Pragma platziert werden kann:

- Es muss außerhalb einer Daten- oder Funktionsdeklaration oder -definition angezeigt werden.

- Es muss in der Quelldatei, nicht in einer Headerdatei angegeben werden.

## <a name="example"></a>Beispiel

```
#include <windows.h>                 // Include several files
#include "myhdr.h"

__inline Disp( char *szToDisplay )   // Define an inline function
{
    ...                              // Some code to display string
}
#pragma hdrstop
```

In diesem Beispiel die **Hdrstop** Pragma angezeigt wird, nachdem zwei Dateien einbezogen wurden, und eine Inlinefunktion definiert wurde. Dies erscheint auf den ersten Blick eher als eine ungewöhnliche Platzierung für das Pragma. Betrachten Sie jedoch, mit der manuellen Vorkompilierungsoptionen `/Yc` und `/Yu`, mit der **Hdrstop** Pragma ermöglicht es Ihnen zum Vorkompilieren der ganze Quelldateien, sogar Inlinecode. Mit dem Microsoft-Compiler können nicht nur Datendeklarationen vorkompiliert werden.

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)