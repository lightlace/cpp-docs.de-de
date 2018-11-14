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
ms.openlocfilehash: 9419ae53cd04812f45f5feeee73fa0f89c408a0c
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51522297"
---
# <a name="heap-constants"></a>Heap-Konstanten

## <a name="syntax"></a>Syntax

```

#include <malloc.h>
```

## <a name="remarks"></a>Hinweise

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