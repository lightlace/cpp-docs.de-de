---
title: Mithilfe von Abort | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Abort
dev_langs:
- C++
helpviewer_keywords:
- abort function
ms.assetid: 3ba39b78-ef74-4a8d-8dee-2d62442de174
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3edc24b2b8dc869022039d4aaaea73af06eac16b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092530"
---
# <a name="using-abort"></a>Verwenden von "abort"

Aufrufen der [Abbrechen](../c-runtime-library/reference/abort.md) Funktion bewirkt, dass sofort beendet. Dies umgeht den normalen Zerstörungsprozess für initialisierte globale statische Objekte. Außerdem wird jegliche spezielle Verarbeitung umgangen, die mit der `atexit`-Funktion angegeben wurde.

## <a name="see-also"></a>Siehe auch

[Weitere Überlegungen zur Beendigung](../cpp/additional-termination-considerations.md)