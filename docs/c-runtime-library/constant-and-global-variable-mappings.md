---
title: Zuordnungen von Konstanten und globalen Variablen
ms.date: 11/04/2016
f1_keywords:
- _tenviron
- _TEOF
- _tfinddata_t
helpviewer_keywords:
- tfinddatat function
- tenviron function
- TEOF type
- _TEOF type
- generic-text mappings
- _tenviron function
- _tfinddata_t function
ms.assetid: 3af4fd3e-9ed5-4ed9-96fd-7031e5126fd1
ms.openlocfilehash: 1bd96c7a305f588a24b0c6d31b2a0132d6546574
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750194"
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

[Allgemeintext-Zuordnungen](../c-runtime-library/generic-text-mappings.md)<br/>
[Datentypzuordnungen](../c-runtime-library/data-type-mappings.md)<br/>
[Routinezuordnungen](../c-runtime-library/routine-mappings.md)<br/>
[Beispiel für ein Programm mit generischem Text](../c-runtime-library/a-sample-generic-text-program.md)<br/>
[Using Generic-Text Mappings (Verwenden von Zuordnungen für generischen Text)](../c-runtime-library/using-generic-text-mappings.md)
