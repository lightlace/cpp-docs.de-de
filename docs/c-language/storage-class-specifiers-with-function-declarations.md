---
title: Speicherklassenspezifizierer mit Funktionsdeklarationen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function specifiers, storage class
- declaring functions, specifiers
- external declarations
- specifiers, function
- external linkage, function declarations
- external linkage, storage-class specifiers
ms.assetid: 801d7df2-efa9-4924-a725-274a5654cfd4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8816ac8917281ed19dfc1afe9e12d302a3423f74
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111406"
---
# <a name="storage-class-specifiers-with-function-declarations"></a>Speicherklassenspezifizierer mit Funktionsdeklarationen

Sie können in Funktionsdeklarationen entweder den **static**-Speicherklassenspezifizierer oder den `extern`-Speicherklassenspezifizierer verwenden. Funktionen besitzen immer eine globale Lebensdauer.

**Microsoft-spezifisch**

Funktionsdeklarationen auf der internen Ebene haben dieselbe Bedeutung wie Funktionsdeklarationen auf externer Ebene. Dies bedeutet, dass eine Funktion nach der Deklaration in der gesamten Übersetzungseinheit sichtbar ist, selbst wenn sie im lokalen Gültigkeitsbereich deklariert wurde.

**Ende Microsoft-spezifisch**

Die Sichtbarkeitsregeln für Funktionen weichen geringfügig von den Regeln für Variablen ab:

- Eine Funktion, die als **static** deklariert wird, ist nur innerhalb der Quelldatei sichtbar, in der sie definiert ist. Funktionen in der gleichen Quelldatei können die **static**-Funktion aufrufen, aber Funktionen in anderen Quelldateien können auf sie nicht direkt anhand ihres Namens zugreifen. Sie können eine weitere **static**-Funktion gleichen Namens in einer anderen Quelldatei deklarieren, ohne dass ein Konflikt auftritt.

- Die Funktionen, die als `extern` deklariert werden, sind in allen Quelldateien im Programm sichtbar (es sei denn, dass Sie später eine solche Funktion erneut als **static** deklarieren). Jede Funktion kann eine `extern`-Funktion aufrufen.

- Funktionsdeklarationen, die die Speicherklassenspezifizierer auslassen, sind standardmäßig `extern`.

**Microsoft-spezifisch**

Microsoft lässt eine Neudefinition eines `extern`-Bezeichners als **static** zu.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[C-Speicherklassen](../c-language/c-storage-classes.md)