---
title: stdin, stdout, stderr | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdin
- stderr
- stdout
dev_langs: C++
helpviewer_keywords:
- stdout function
- standard output stream
- standard error stream
- stdin function
- standard input stream
- stderr function
ms.assetid: badd4735-596d-4498-857c-ec8b7e670e4c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8350cb0cea07298eefb9b3aa54b69a5b9d786d88
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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