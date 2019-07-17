---
title: Sequenced_policy-Klasse
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::parallel_policy
ms.openlocfilehash: 63be7166b84fa452f53baf6b6de16831eb657a23
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68269192"
---
# <a name="sequencedpolicy-class"></a>Sequenced_policy-Klasse

Als verwendet ein eindeutiger Typ zu unterscheiden, parallelen Algorithmus überladen und erfordern, dass die Ausführung eines parallelen Algorithmus nicht parallelisiert werden kann.

## <a name="syntax"></a>Syntax

```cpp
class execution::sequenced_policy;
```

## <a name="remarks"></a>Hinweise

Während der Ausführung eines parallelen Algorithmus mit der `execution::sequenced_policy` Richtlinie, wenn Sie der Aufruf der Funktion ein Element-Zugriff über eine nicht abgefangene Ausnahme beendet `terminate()` aufgerufen werden soll.
