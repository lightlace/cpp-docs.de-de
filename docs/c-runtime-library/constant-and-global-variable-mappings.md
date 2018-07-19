---
title: Zuordnungen von Konstanten und globalen Variablen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _tenviron
- _TEOF
- _tfinddata_t
dev_langs:
- C++
helpviewer_keywords:
- tfinddatat function
- tenviron function
- TEOF type
- _TEOF type
- generic-text mappings
- _tenviron function
- _tfinddata_t function
ms.assetid: 3af4fd3e-9ed5-4ed9-96fd-7031e5126fd1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 96c30f939670931ab031349bc5e9ddcce54e1891
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32387524"
---
# <a name="constant-and-global-variable-mappings"></a>Zuordnungen von Konstanten und globalen Variablen
Diese Konstanten mit generischem Text, die globale Variable und die Standardzuordnungen werden in TCHAR.H definiert. Sie sind abhängig davon, ob die Konstante `_UNICODE` oder die Konstante `_MBCS` im Programm definiert wurde.  
  
### <a name="generic-text-constant-and-global-variable-mappings"></a>Zuordnungen von Konstanten mit generischem Text und globalen Variablen  
  
|Generischer Text - Objektname|SBCS (_UNICODE & MBCS nicht definiert)|_MBCS definiert|_UNICODE definiert|  
|----------------------------------|--------------------------------------------|--------------------|-----------------------|  
|`_TEOF`|`EOF`|`EOF`|`WEOF`|  
|`_tenviron`|`_environ`|`_environ`|`_wenviron`|  
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|  
  
## <a name="see-also"></a>Siehe auch  
 [Generic-Text Mappings (Zuordnungen von Konstanten mit generischem Text)](../c-runtime-library/generic-text-mappings.md)   
 [Data Type Mappings (Datentypzuordnungen)](../c-runtime-library/data-type-mappings.md)   
 [Routine Mappings (Routinezuordnungen)](../c-runtime-library/routine-mappings.md)   
 [A Sample Generic-Text Program (Beispiel für ein Programm mit generischem Text)](../c-runtime-library/a-sample-generic-text-program.md)   
 [Using Generic-Text Mappings (Verwenden von Zuordnungen für generischen Text)](../c-runtime-library/using-generic-text-mappings.md)