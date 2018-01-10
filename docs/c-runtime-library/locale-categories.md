---
title: Gebietsschemakategorien | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LC_MAX
- LC_MIN
- LC_MONETARY
- LC_TIME
- LC_NUMERIC
- LC_COLLATE
- LC_CTYPE
- LC_ALL
dev_langs: C++
helpviewer_keywords:
- LC_MIN constant
- LC_MONETARY constant
- LC_CTYPE constant
- locale constants
- LC_MAX constant
- LC_ALL constant
- LC_TIME constant
- LC_NUMERIC constant
- LC_COLLATE constant
ms.assetid: 868f1493-fe5d-4722-acab-bfcd374a063a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8e2188dc477a81477b65db22bcd06390a4b6773c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="locale-categories"></a>Gebietsschemakategorien
## <a name="syntax"></a>Syntax  
  
```  
  
#include <locale.h>  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Gebietsschemakategorien sind Manifestkonstanten, die von den Lokalisierungsroutinen verwendet werden, um anzugeben, welcher Teil der Gebietsschemainformationen eines Programms verwendet wird. Das Gebietsschema verweist auf den Ort (oder Land/Region), für den Sie bestimmte Aspekte des Programms anpassen können. Vom Gebietsschema abhängige Bereiche umfassen u.a. die Formatierung von Daten oder das Anzeigeformat für monetäre Werte.  
  
|Gebietsschemakategorie|Teile des betroffenen Programms|  
|---------------------|-------------------------------|  
|`LC_ALL`|Alle gebietsschemaspezifischen Verhalten (alle Kategorien)|  
|`LC_COLLATE`|Verhalten der `strcoll`- und `strxfrm`-Funktion|  
|`LC_CTYPE`|Das Verhalten von Funktionen zur Zeichenbehandlung (außer **isdigit**, `isxdigit`, `mbstowcs` und `mbtowc`, die nicht betroffen sind)|  
|`LC_MAX`|Identisch mit `LC_TIME`|  
|`LC_MIN`|Identisch mit `LC_ALL`|  
|`LC_MONETARY`|Durch die `localeconv`-Funktion zurückgegebene Informationen zur Währungsformatierung|  
|`LC_NUMERIC`|Dezimaltrennzeichen für formatierte Ausgaberoutinen (z.B. `printf`), Datenkonvertierungsroutinen und nicht monetäre Formatierungsinformationen, die von der `localeconv`-Funktion zurückgegeben werden|  
|`LC_TIME`|Verhalten der `strftime`-Funktion|  
  
 Ein Beispiel finden Sie unter [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
## <a name="see-also"></a>Siehe auch  
 [localeconv](../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcoll-Funktionen](../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)