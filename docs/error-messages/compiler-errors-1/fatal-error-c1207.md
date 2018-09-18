---
title: Schwerwiegender Fehler C1207 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1207
dev_langs:
- C++
helpviewer_keywords:
- C1207
ms.assetid: cd31b410-9523-47db-883c-e69a9351ffa2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8042782477b402f2e09d1d67c8fd5c126647285
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072627"
---
# <a name="fatal-error-c1207"></a>Schwerwiegender Fehler C1207

Verwaltete Vorlagen werden von der installierten Laufzeitversion nicht unterstützt.

C1207 tritt auf, wenn Sie einen Compiler der aktuellen Version, aber eine Common Language Runtime (CLR) einer früheren Version verwenden.

Bestimmte Funktionen des Compilers funktionieren möglicherweise nicht in einer früheren Version der Laufzeit.

Installieren Sie die CLR-Version, die für die Verwendung mit dem Compiler vorgesehen ist, um den Fehler C1207 zu beheben.