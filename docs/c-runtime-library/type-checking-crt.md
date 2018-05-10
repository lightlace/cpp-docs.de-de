---
title: Typüberprüfung (CRT) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.types
dev_langs:
- C++
helpviewer_keywords:
- checking type
- variable argument functions
- type checking
ms.assetid: 1ba7590b-d1c0-4636-b6a0-e231395abdad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 959dd52847e6140667671b9992471155d68e9646
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="type-checking-crt"></a>Typüberprüfung (CRT)
Der Compiler führt eine beschränkte Typüberprüfung für Funktionen durch, die eine variable Anzahl von Argumenten aufnehmen können, wie im Folgenden beschrieben wird:  
  
|Funktionsaufruf |Typgeprüfte Argumente|  
|-------------------|-----------------------------|  
|`_cprintf_s`, `_cscanf_s`, `printf_s`, `scanf_s`|Erstes Argument (Formatzeichenfolge)|  
|`fprintf_s`, `fscanf_s`, `sprintf_s`, `sscanf_s`|Die ersten zwei Argumente (Datei oder Puffer und Formatzeichenfolge)|  
|`_snprintf_s`|Die ersten drei Argumente (Datei oder Puffer, Anzahl und Formatzeichenfolge)|  
|`_open`|Die ersten zwei Argumente (Pfad und `_open`-Flag)|  
|`_sopen_s`|Die ersten drei Argumente (Pfad, `_open`-Flag und Freigabemodus)|  
|`_execl`, `_execle`, `_execlp`, `_execlpe`|Die ersten zwei Argumente (Pfad und erster Argumentzeiger)|  
|`_spawnl`, `_spawnle`, `_spawnlp`, `_spawnlpe`|Die ersten drei Argumente (Moduskennzeichnung, Pfad und erster Argumentzeiger)|  
  
 Der Compiler führt dieselbe beschränkte Typüberprüfung für die äquivalenten Breitzeichen dieser Funktionen durch.  
  
## <a name="see-also"></a>Siehe auch  
 [CRT-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)