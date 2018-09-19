---
title: Gespeicherte Register von Aufrufer / Aufgerufener | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e8e877387dbb5b0be865e11017a3ac71a0c38faa
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707654"
---
# <a name="callercallee-saved-registers"></a>Gespeicherte Register von Aufrufer/Aufgerufenem

Die Register RAX, RCX, RDX, R8, R9, R10, R11 als flüchtig gelten und berücksichtigt werden muss zerstört, auf den Funktionsaufrufen (es sei denn, andernfalls Sicherheit, belegbare durch Analyse, wie z. B. die Optimierung des ganzen Programms).

Die Register RBX, RBP, RDI, RSI, RSP, R12, R13, R14 und R15 werden als permanenten betrachtet und müssen gespeichert werden und wiederhergestellt, indem eine Funktion, die verwendet werden.

## <a name="see-also"></a>Siehe auch

[Aufrufkonvention](../build/calling-convention.md)