---
title: Parallel_policy-Klasse
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::parallel_policy
ms.openlocfilehash: 7bb2b095a50e664dfc585e0bd4aaa608a6ad8e95
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268962"
---
# <a name="parallelpolicy-class"></a>Parallel_policy-Klasse

Als verwendet ein eindeutiger Typ zu unterscheiden, parallelen Algorithmus überladen und anzugeben, dass die Ausführung eines parallelen Algorithmus parallelisiert werden kann.

## <a name="syntax"></a>Syntax

```cpp
class execution::parallel_policy;
```

## <a name="remarks"></a>Hinweise

Während der Ausführung eines parallelen Algorithmus mit der `execution::parallel_policy` Richtlinie, wenn Sie der Aufruf der Funktion ein Element-Zugriff über eine nicht abgefangene Ausnahme beendet `terminate()` aufgerufen werden soll.
