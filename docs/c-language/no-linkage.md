---
title: Keine Verknüpfung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- no linkage
- linkage [C++], none
ms.assetid: 5a413082-1034-4e04-b76b-8d14668bf434
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: acbce1b4a4a19c5fa1a015e01bd2078fc70f6e1c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063083"
---
# <a name="no-linkage"></a>Keine Verknüpfung

Wenn eine Deklaration für einen Bezeichner in einem Block den `extern`-Speicherklassenspezifizierer nicht enthält, hat der Bezeichner keine Bindung und ist für die Funktion eindeutig.

Die folgenden Bezeichner haben keine Verknüpfung:

- Ein Bezeichner, der als etwas anderes als ein Objekt oder eine Funktion deklariert wurde

- Ein Bezeichner, der zum Funktionsparameter deklariert wurde

- Ein Blockbereichsbezeichner für ein Objekt, das ohne den `extern`-Speicherklassenspezifizierer deklariert wurde

Wenn ein Bezeichner keine Verknüpfung aufweist, wird durch erneutes Deklarieren des gleichen Namens (in einem Deklarator oder Typspezifizierer) auf der gleichen Gültigkeitsebene einen Fehler bei der Symbolneudefinition.

## <a name="see-also"></a>Siehe auch

[Verwenden von "extern" zur Angabe der Verknüpfung](../cpp/using-extern-to-specify-linkage.md)