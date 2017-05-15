---
title: srand | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- srand
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- srand
dev_langs:
- C++
helpviewer_keywords:
- random starting point
- random starting point, setting
- random numbers, generating
- srand function
- numbers, pseudorandom
- numbers, random
- pseudorandom numbers
- starting points, setting random
- starting points
ms.assetid: 7bf56dc5-5692-4182-a3c1-18af98d2dd1a
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: e86ea8aa561af584a6825d4225820aca7baeced2
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="srand"></a>srand
Legt den Startwert für den Pseudozufallszahlengenerator fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
void srand(  
   unsigned int seed   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `seed`  
 Startwert für die Pseudozufallszahlengenerierung  
  
## <a name="remarks"></a>Hinweise  
 Die `srand`-Funktion legt den Ausgangspunkt für das Generieren von Pseudozufallsganzzahlen im aktuellen Thread fest. Um den Generators zum Erzeugen derselben Sequenz von Ergebnissen erneut zu initialisieren, rufen Sie die `srand`-Funktion auf, und verwenden Sie das gleiche `seed`-Argument erneut. Jeder andere Wert für `seed` legt den Generator in der Pseudozufallssequenz auf einen anderen Startpunkt fest. `rand` ruft die generierten Pseudozufallszahlen ab. Der Aufruf von `rand` vor irgendeinem Aufruf von `srand` generiert die gleiche Sequenz wie der Aufruf von `srand` mit `seed` übergeben als 1.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`srand`|\<stdlib.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel hierfür finden Sie unter [rand](../../c-runtime-library/reference/rand.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [rand](../../c-runtime-library/reference/rand.md)
