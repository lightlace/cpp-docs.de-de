---
title: stdin, stdout, stderr | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/23/2018
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- stdin
- stderr
- stdout
dev_langs:
- C++
helpviewer_keywords:
- stdout function
- standard output stream
- standard error stream
- stdin function
- standard input stream
- stderr function
ms.assetid: badd4735-596d-4498-857c-ec8b7e670e4c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 707811a9c05135cb46520dd72895d677cdc0a6e4
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808705"
---
# <a name="stdin-stdout-stderr"></a>stdin, stdout, stderr

## <a name="syntax"></a>Syntax

```
FILE *stdin; 
FILE *stdout; 
FILE *stderr; 
#include <stdio.h>
```

## <a name="remarks"></a>Hinweise

Hierbei handelt es sich um Standarddatenströme für Eingabe, Ausgabe und Fehlerausgabe.

Standardmäßig erfolgt die Eingabe über die Tastatur, während die Standardausgabe und die Standardfehlerausgabe auf dem Bildschirm erfolgt.

Die folgenden Datenstromzeiger sind für den Zugriff auf die Standarddatenströme verfügbar:

|Zeiger|Stream|
|-------------|------------|
|`stdin`|Standardeingabe|
|`stdout`|Standardausgabe|
|`stderr`|Standardfehler|

Diese Zeiger können als Argumente für Funktionen verwendet werden. Einige Funktionen wie [getchar](../c-runtime-library/reference/getchar-getwchar.md) und [putchar](../c-runtime-library/reference/putchar-putwchar.md) verwenden `stdin` und `stdout` automatisch.

Diese Zeiger sind Konstanten, und es können ihnen keine neuen Werte zugewiesen werden. Die [freopen](../c-runtime-library/reference/freopen-wfreopen.md)-Funktion kann verwendet werden, um Datenströme auf Dateien auf Datenträgern oder andere Geräte umzuleiten. Das Betriebssystem ermöglicht Ihnen, die Standardein- und -ausgabe eines Programms auf Befehlsebene umzuleiten.

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../c-runtime-library/stream-i-o.md)<br/>
[Globale Konstanten](../c-runtime-library/global-constants.md)
