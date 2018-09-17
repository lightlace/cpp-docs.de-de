---
title: Funktionstypen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 7e33d5f4-dabb-406d-afb3-13777b995028
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6dfb36dc9e177fdb9ad196c0e2a8ad0f352d5f2d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709565"
---
# <a name="function-types"></a>Funktionstypen

Es gibt im Grunde zwei Arten von Funktionen. Eine Funktion, die einen Stapelrahmen erfordert wird es sich um ein Frame-Funktion aufgerufen. Eine Funktion, die einen Stapelrahmen nicht erfordert, ist eine blattfunktion aufgerufen.

Eine Frame-Funktion ist eine Funktion, die Stapelspeicher zuweist, andere Funktionen aufruft, nicht flüchtigen Register gespeichert oder mithilfe der Ausnahmebehandlung. Darüber hinaus wird die Funktionstabelleneintrag erforderlich. Eine Frame-Funktion muss einen Prolog und einen Epilog. Eine Funktion des Frames Stapelspeicher kann dynamisch zuordnen und Frame-Pointer nutzen kann. Eine Frame-Funktion verfügt über den vollständigen Funktionsumfang dieses aufrufen, bei denen standard.

Wenn eine Frame-Funktion nicht eine andere Funktion aufruft, muss es ist nicht erforderlich, um den Stapel auszurichten (Siehe den Abschnitt [Stapelreservierung](../build/stack-allocation.md)).

Eine Blattebene-Funktion ist eine, die keine Funktionstabelleneintrag erforderlich ist. Es vornehmen keine Änderungen, um keine nicht flüchtigen Register, einschließlich der RSP, was bedeutet, dass keine Funktionen aufrufen oder Stack Speicherplatz belegt werden. Es ist zulässig, den Stapel nicht ausgerichtete zu verlassen, während es ausgeführt wird.

## <a name="see-also"></a>Siehe auch

[Verwendung von Stapeln](../build/stack-usage.md)
