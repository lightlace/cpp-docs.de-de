---
title: Threadprivate | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- threadprivate
dev_langs:
- C++
helpviewer_keywords:
- threadprivate OpenMP directive
ms.assetid: 3515aaed-6f9d-4d59-85eb-342378bea2d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a9313934744f6eae66736f25b0d0b8592743cf12
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376979"
---
# <a name="threadprivate"></a>threadprivate

Gibt an, dass eine Variable einem Thread zugehörig ist.

## <a name="syntax"></a>Syntax

```
#pragma omp threadprivate(var)
```

### <a name="parameters"></a>Parameter

*var*<br/>
Eine durch Trennzeichen getrennte Liste von Variablen, die Sie an einen Thread als privat kennzeichnen möchten. `var` Hierbei muss es sich um eine globale oder Namespace-bezogenen Variable oder eine statische lokale Variable sein.

## <a name="remarks"></a>Hinweise

Die `threadprivate` -Anweisung unterstützt keine OpenMP-Klauseln.

Weitere Informationen finden Sie unter [2.7.1 Threadprivate-Direktive](../../../parallel/openmp/2-7-1-threadprivate-directive.md).

Die `threadprivate` Richtlinie basiert auf der [Thread](../../../cpp/thread.md) `__declspec` -Attribut; die Beschränkungen für **__declspec(thread)** gelten für `threadprivate`.

Sie können keine `threadprivate` in einer DLL, die über geladen werden [LoadLibrary](https://msdn.microsoft.com/library/windows/desktop/ms684175).  Dies schließt die DLLs, die mit geladen werden [/DELAYLOAD (Laden von Import verzögern)](../../../build/reference/delayload-delay-load-import.md), die auch verwendet **LoadLibrary**.

Sie können `threadprivate` in einer DLL, die beim Starten des Prozesses statisch geladen wird.

Da `threadprivate` basiert auf **__declspec(thread)**, `threadprivate` Variable befindet sich in jedem Thread im Prozess gestartet, nicht nur die Threads, die Teil eines Thread-Teams, die von einem parallelen Bereich Anwendungen erzeugt werden.  Dies ist ein Implementierungsdetail, der ggf. zu beachten, da Sie, z. B. Konstruktoren für ggf. bemerken einen `threadprivate` einen benutzerdefinierten Typ namens Weitere häufig wird erwartet.

Ein `threadprivate` destructable Variablentyp nicht notwendigerweise sein Destruktor aufgerufen haben.  Zum Beispiel:

```
struct MyType
{
    ~MyType();
};

MyType threaded_var;
#pragma omp threadprivate(threaded_var)
int main()
{
    #pragma omp parallel
    {}
}
```

Benutzer haben keine Kontrolle, wenn die Threads enthalten sind, die den parallelen Bereich beendet wird.  Wenn diese Threads vorhanden sind, wenn der Prozess beendet wird, die Threads nicht über das Beenden des Prozesses benachrichtigt werden und der Destruktor nicht aufgerufen werden, für die wird `threaded_var` auf einem beliebigen Thread mit der Ausnahme, die beendet wird (Hier wird der primäre Thread).  So können Code nicht auf ordnungsgemäße Zerstörung von verlassen sollten `threadprivate` Variablen.

## <a name="example"></a>Beispiel

Ein Beispiel der Verwendung von `threadprivate`, finden Sie unter [private](../../../parallel/openmp/reference/private-openmp.md).

## <a name="see-also"></a>Siehe auch

[Anweisungen](../../../parallel/openmp/reference/openmp-directives.md)