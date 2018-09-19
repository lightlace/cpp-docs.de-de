---
title: Blöcke | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function definitions, blocks in code
- blocks
- compound statements
- statements, compound
ms.assetid: be231a92-c712-464e-ae25-a4becb20f7f5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9704b499106fc59364f5cc9ae97277939e835a77
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025321"
---
# <a name="blocks"></a>Blöcke

Eine Sequenz von Deklarationen, Definitionen und Anweisungen, die in geschweiften Klammern (**{ }**) eingeschlossen sind, wird als „Block“ bezeichnet. Bei C gibt es zwei Arten von Blöcken. Die „Verbundanweisung“ bestehend aus mindestens einer Anweisung (siehe [Die Verbundanweisung](../c-language/compound-statement-c.md)) ist eine Art von Block. Der andere, die „Funktionsdefinition“, besteht aus einer Verbundanweisung (dem Text der Funktion) und dem zugeordneten „Header“ (dem Funktionsnamen, dem Rückgabetyp und den formalen Parametern). Ein Block in anderen Blöcken wird als "geschachtelt" bezeichnet.

Beachten Sie, dass, während alle Verbundanweisungen in geschweiften Klammern eingeschlossen sind, nicht alles, was innerhalb der geschweiften Klammern eingeschlossen ist, eine Verbundanweisung bildet. Beispielsweise können die Spezifikationen von Array-, Struktur- oder Enumerationselementen zwar innerhalb der geschweiften Klammern angezeigt werden, sie sind jedoch keine Verbundanweisungen.

## <a name="see-also"></a>Siehe auch

[Quelldateien und Quellprogramme](../c-language/source-files-and-source-programs.md)