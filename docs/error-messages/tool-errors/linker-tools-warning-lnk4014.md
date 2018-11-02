---
title: Linkertoolwarnung LNK4014
ms.date: 11/04/2016
f1_keywords:
- LNK4014
helpviewer_keywords:
- LNK4014
ms.assetid: 394903e9-3ded-4ea4-b7c0-a3535d4b4da4
ms.openlocfilehash: f67990ed74f500f1b954edcf1d6437f64f93f0d6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511707"
---
# <a name="linker-tools-warning-lnk4014"></a>Linkertoolwarnung LNK4014

Memberobjekt "Objectname" wurde nicht gefunden.

LIB wurde nicht gefunden. `objectname` in der Bibliothek.

Die **/REMOVE** und **/EXTRACT** Optionen sind erforderlich, den vollständigen Namen der Members-Objekts, das gelöscht oder in eine Datei kopiert werden soll. Der vollständige Name enthält den Pfad der ursprünglichen Objektdatei. Zum Anzeigen der vollständigen Namen der Memberobjekte in einer Bibliothek verwenden DUMPBIN [ARCHIVEMEMBERS](../../build/reference/archivemembers.md) oder LIB [/LIST](../../build/reference/managing-a-library.md).