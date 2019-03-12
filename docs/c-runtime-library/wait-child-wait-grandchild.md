---
title: _WAIT_CHILD, _WAIT_GRANDCHILD
ms.date: 11/04/2016
f1_keywords:
- _WAIT_GRANDCHILD
- WAIT_CHILD
- WAIT_GRANDCHILD
- _WAIT_CHILD
helpviewer_keywords:
- WAIT_CHILD constant
- WAIT_GRANDCHILD constant
- _WAIT_CHILD constant
- _WAIT_GRANDCHILD constant
ms.assetid: 7acd96fa-d118-4339-bb00-e5afaf286945
ms.openlocfilehash: 98858058add6a0a11d4f9331989c6816e38130aa
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57745055"
---
# <a name="waitchild-waitgrandchild"></a>_WAIT_CHILD, _WAIT_GRANDCHILD

## <a name="syntax"></a>Syntax

```
#include <process.h>
```

## <a name="remarks"></a>Anmerkungen

Die Funktion `_cwait` kann von jedem Prozess verwendet werden, der auf einen anderen Prozess wartet (wenn die Prozess-ID bekannt ist). Das Aktionsargument kann einen der folgenden Werte aufweisen:

|Konstante|Bedeutung|
|--------------|-------------|
|`_WAIT_CHILD`|Der aufrufende Prozess wartet, bis der angegebene neue Prozess beendet ist.|
|`_WAIT_GRANDCHILD`|Der aufrufende Prozess wartet, bis der angegebene neue Prozess und alle Prozesse, die durch den neuen Prozess erstellt werden, beendet sind.|

## <a name="see-also"></a>Siehe auch

[_cwait](../c-runtime-library/reference/cwait.md)<br/>
[Globale Konstanten](../c-runtime-library/global-constants.md)
