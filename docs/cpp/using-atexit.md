---
title: Verwenden von "atexit"
ms.date: 11/04/2016
f1_keywords:
- atexit
helpviewer_keywords:
- atexit function
ms.assetid: d28fda17-c3d4-4af6-ba44-f44886bbb237
ms.openlocfilehash: 06baba59b5765f853f081b34d73be28a187730ba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257997"
---
# <a name="using-atexit"></a>Verwenden von "atexit"

Mit der [von "atexit"](../c-runtime-library/reference/atexit.md) -Funktion, Sie können angeben, eine Beendigung der Verarbeitung-Funktion, die vor der Beendigung des Programms ausgeführt wird. Keine globalen statischen Objekts vor dem Aufruf von initialisiert **von "atexit"** werden vor der Ausführung der Funktion für die Beendigung der Verarbeitung zerstört.

## <a name="see-also"></a>Siehe auch

[Weitere Überlegungen zur Beendigung](../cpp/additional-termination-considerations.md)