---
title: Unterlauf von Gleitkommawerten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 78af8016-643c-47db-b4f1-7f06cb4b243e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 980000932c8cc4a6be3798976d273dae8608324f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089163"
---
# <a name="underflow-of-floating-point-values"></a>Unterlauf von Gleitkommawerten

**ANSI 4.5.1** Ob die mathematischen Funktionen den ganzzahligen Ausdruck `errno` bei Unterlaufbereichsfehlern auf den Wert des `ERANGE`-Makros festlegen

Ein Gleitkommaunterlauf legt den Ausdruck `errno` nicht auf `ERANGE` fest. Wenn ein Wert nahe 0 (Null) ist und schließlich ein Unterlauf stattfindet, wird der Wert auf 0 (Null) festgelegt.

## <a name="see-also"></a>Siehe auch

[Bibliotheksfunktionen](../c-language/library-functions.md)