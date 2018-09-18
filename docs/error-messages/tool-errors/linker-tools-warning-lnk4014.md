---
title: Linkertoolwarnung LNK4014 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4014
dev_langs:
- C++
helpviewer_keywords:
- LNK4014
ms.assetid: 394903e9-3ded-4ea4-b7c0-a3535d4b4da4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df0a3b6f30733413a0f27c0b8daa07394bb04b07
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023110"
---
# <a name="linker-tools-warning-lnk4014"></a>Linkertoolwarnung LNK4014

Memberobjekt "Objectname" wurde nicht gefunden.

LIB wurde nicht gefunden. `objectname` in der Bibliothek.

Die **/REMOVE** und **/EXTRACT** Optionen sind erforderlich, den vollständigen Namen der Members-Objekts, das gelöscht oder in eine Datei kopiert werden soll. Der vollständige Name enthält den Pfad der ursprünglichen Objektdatei. Zum Anzeigen der vollständigen Namen der Memberobjekte in einer Bibliothek verwenden DUMPBIN [ARCHIVEMEMBERS](../../build/reference/archivemembers.md) oder LIB [/LIST](../../build/reference/managing-a-library.md).