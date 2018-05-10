---
title: stdin, stdout, stderr | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 0f6226a6e38326a39ce2921e2a0d6219d01f005b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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
|**stdout**|Standardausgabe|  
|`stderr`|Standardfehler|  
  
 Diese Zeiger können als Argumente für Funktionen verwendet werden. Einige Funktionen wie **getchar** und `putchar` verwenden `stdin` und **stdout** automatisch.  
  
 Diese Zeiger sind Konstanten, und es können ihnen keine neuen Werte zugewiesen werden. Die `freopen`-Funktion kann verwendet werden, um Datenströme auf Dateien auf Datenträgern oder andere Geräte umzuleiten. Das Betriebssystem ermöglicht Ihnen, die Standardein- und -ausgabe eines Programms auf Befehlsebene umzuleiten.  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../c-runtime-library/stream-i-o.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)