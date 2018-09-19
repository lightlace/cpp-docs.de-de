---
title: Schwerwiegender Fehler C1055 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1055
dev_langs:
- C++
helpviewer_keywords:
- C1055
ms.assetid: a9fb9190-d7eb-4d5f-b1a2-a41e584a28c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6960d8168bd818e4d1baa30e5e54940e6e4dc2e9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115449"
---
# <a name="fatal-error-c1055"></a>Schwerwiegender Fehler C1055

Compilerlimit: keine weiteren Schlüssel

Die Quelldatei enthält zu viele Symbole. Der Compiler nicht genügend Hash-Schlüssel für die Symboltabelle.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)

1. Teilen Sie die Quelldatei, in kleinere Dateien.

1. Vermeiden Sie unnötige Headerdateien.

1. Wiederverwenden von temporären und globale Variablen, statt neue zu erstellen.