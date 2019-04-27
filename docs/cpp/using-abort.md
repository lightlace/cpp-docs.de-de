---
title: Verwenden von "abort"
ms.date: 11/04/2016
f1_keywords:
- Abort
helpviewer_keywords:
- abort function
ms.assetid: 3ba39b78-ef74-4a8d-8dee-2d62442de174
ms.openlocfilehash: 0961f6f88f5de4d435fa65e50b9dbdbc478e7608
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62244207"
---
# <a name="using-abort"></a>Verwenden von "abort"

Aufrufen der [Abbrechen](../c-runtime-library/reference/abort.md) Funktion bewirkt, dass sofort beendet. Dies umgeht den normalen Zerstörungsprozess für initialisierte globale statische Objekte. Außerdem wird jegliche spezielle Verarbeitung umgangen, die mit der `atexit`-Funktion angegeben wurde.

## <a name="see-also"></a>Siehe auch

[Weitere Überlegungen zur Beendigung](../cpp/additional-termination-considerations.md)