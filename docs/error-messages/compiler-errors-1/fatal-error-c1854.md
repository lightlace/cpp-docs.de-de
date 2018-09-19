---
title: Schwerwiegender Fehler C1854 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- devlang-cpp
ms.topic: error-reference
f1_keywords:
- C1854
dev_langs:
- C++
helpviewer_keywords:
- C1854
ms.assetid: 8c21a9cc-1737-475c-9e57-8725cd8937c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 83450169ec928bb77e46916619c84b3b9a3443a3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029389"
---
# <a name="fatal-error-c1854"></a>Schwerwiegender Fehler C1854

> Informationen, die beim Anlegen der vorkompilierten Headerdatei in Objektdatei kann nicht überschrieben werden: "*Filename*"

Sie angegeben haben die [/Yu (vorkompilierte Headerdatei verwenden)](../../build/reference/yu-use-precompiled-header-file.md) Option nach dem Angeben der ["/ Yc" (Erstellen vorkompilierter Headerdatei)](../../build/reference/yc-create-precompiled-header-file.md) Option für die gleiche Datei.

Um dieses Problem zu beheben, legen Sie in der Regel nur eine Datei im Projekt mit kompiliert werden die **"/ Yc"** aus, und legen Sie alle anderen Dateien, die bei der Kompilierung der **"/ Yu"** Option. Weitere Informationen zur Verwendung von der **"/ Yc"** Optionen und legen Sie es in Visual Studio-IDE, finden Sie unter ["/ Yc" (Erstellen vorkompilierter Headerdatei)](../../build/reference/yc-create-precompiled-header-file.md). Weitere Informationen zur Verwendung von vorkompilierter Headers finden Sie unter [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md).
