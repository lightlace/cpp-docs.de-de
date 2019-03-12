---
title: Heap-Konstanten
ms.date: 11/04/2016
f1_keywords:
- _HEAPBADPTR
- _HEAPEMPTY
- _HEAPBADBEGIN
- _HEAPOK
- _HEAPBADNODE
- _HEAPEND
helpviewer_keywords:
- _HEAPOK constants
- _HEAPEND constants
- HEAPBADBEGIN constants
- _HEAPBADNODE constants
- HEAPBADNODE constants
- HEAPBADPTR constants
- _HEAPEMPTY constants
- HEAPEND constants
- HEAPOK constants
- HEAPEMPTY constants
- _HEAPBADBEGIN constants
- _HEAPBADPTR constants
- heap constants
ms.assetid: 3f751bb9-2dc4-486f-b5f5-9061c96d3754
ms.openlocfilehash: 44c7a280ebffd0073f1dfb3a0a3cbdbd2efee0fb
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57745364"
---
# <a name="heap-constants"></a>Heap-Konstanten

## <a name="syntax"></a>Syntax

```
#include <malloc.h>
```

## <a name="remarks"></a>Anmerkungen

Diese Konstanten geben den Rückgabewert an, der den Heapstatus angibt.

|Konstante|Bedeutung|
|--------------|-------------|
|`_HEAPBADBEGIN`|Ursprüngliche Headerinformationen wurden nicht gefunden oder sind ungültig.|
|`_HEAPBADNODE`|Ein ungültiger Knoten wurde gefunden, oder der Heap ist beschädigt.|
|`_HEAPBADPTR`|**_pentry**-Feld der **_HEAPINFO**-Struktur enthält keinen gültigen Zeiger auf einen Heap (nur `_heapwalk`-Routine).|
|`_HEAPEMPTY`|Der Heap wurde noch nicht initialisiert.|
|`_HEAPEND`|Ende des Heaps wurde erfolgreich erreicht (nur `_heapwalk`-Routine).|
|`_HEAPOK`|Heap ist konsistent (nur `_heapset`- und `_heapchk`-Routinen). Keine Fehler bisher; **_HEAPINFO**-Struktur enthält Informationen zum nächsten Eintrag (nur `_heapwalk`-Routine).|

## <a name="see-also"></a>Siehe auch

[_heapchk](../c-runtime-library/reference/heapchk.md)<br/>
[_heapset](../c-runtime-library/heapset.md)<br/>
[_heapwalk](../c-runtime-library/reference/heapwalk.md)<br/>
[Globale Konstanten](../c-runtime-library/global-constants.md)
