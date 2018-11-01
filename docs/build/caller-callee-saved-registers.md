---
title: Gespeicherte Register von Aufrufer / Aufgerufener
ms.date: 11/04/2016
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
ms.openlocfilehash: f34fbfff8e6c61b5d568c073f6b7da2a12e34535
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654700"
---
# <a name="callercallee-saved-registers"></a>Gespeicherte Register von Aufrufer/Aufgerufenem

Die Register RAX, RCX, RDX, R8, R9, R10, R11 als flüchtig gelten und berücksichtigt werden muss zerstört, auf den Funktionsaufrufen (es sei denn, andernfalls Sicherheit, belegbare durch Analyse, wie z. B. die Optimierung des ganzen Programms).

Die Register RBX, RBP, RDI, RSI, RSP, R12, R13, R14 und R15 werden als permanenten betrachtet und müssen gespeichert werden und wiederhergestellt, indem eine Funktion, die verwendet werden.

## <a name="see-also"></a>Siehe auch

[Aufrufkonvention](../build/calling-convention.md)