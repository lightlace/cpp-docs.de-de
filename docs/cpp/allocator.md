---
title: Zuweisung
ms.date: 03/21/2019
f1_keywords:
- allocator_cpp
helpviewer_keywords:
- __declspec keyword [C++], allocator
- allocator __declspec keyword
ms.openlocfilehash: f9c8de7c8686b89a2ab9570a2558e3f649e545b5
ms.sourcegitcommit: 0064d37467f958dd6a5111f20d7660eaccd53ee9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58419084"
---
# <a name="allocator"></a>Zuweisung

**Microsoft-spezifisch**

Die **Allocator** deklarationsspezifizierer kann angewendet werden, um benutzerdefinierte speicherbelegung-Funktionen, um die Zuordnungen über Event Tracing for Windows (ETW) sichtbar zu machen.

## <a name="syntax"></a>Syntax

```
   __declspec(allocator) 
```

## <a name="remarks"></a>Hinweise

Die systemeigene speicherprofilerstellung in Visual Studio funktioniert, indem Sie das Sammeln von ETW-Ereignisdaten, die von ausgegeben werden, während der Laufzeit-Zuordnung. Zuweisungen im CRT und Windows SDK wurden auf Quellebene kommentiert, sodass ihre Speicherbelegungsdaten erfasst werden können. Wenn Sie Ihre eigenen Zuweisungen schreiben, alle Funktionen, die einen Zeiger auf neu zugewiesenen Heapspeicher zurückgibt, können mit ergänzt werden `__declspec(allocator)`, wie in diesem Beispiel für mymalloc zu sehen ist:

```cpp
__declspec(allocator) void* myMalloc(size_t size)
```

Weitere Informationen finden Sie unter [Messen des Speicherverbrauchs in Visual Studio](/visualstudio/profiling/memory-usage) und [Ereignisse für benutzerdefinierte native ETW-Heap](/visualstudio/profiling/custom-native-etw-heap-events).