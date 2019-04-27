---
title: Schwerwiegender Fehler C1854
ms.date: 11/04/2016
f1_keywords:
- C1854
helpviewer_keywords:
- C1854
ms.assetid: 8c21a9cc-1737-475c-9e57-8725cd8937c1
ms.openlocfilehash: 83eb5e01eac377b8f19a0e94dc1518e3ed557c3b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165637"
---
# <a name="fatal-error-c1854"></a>Schwerwiegender Fehler C1854

> Informationen, die beim Anlegen der vorkompilierten Headerdatei in Objektdatei kann nicht überschrieben werden: "*Filename*"

Sie angegeben haben die [/Yu (vorkompilierte Headerdatei verwenden)](../../build/reference/yu-use-precompiled-header-file.md) Option nach dem Angeben der ["/ Yc" (Erstellen vorkompilierter Headerdatei)](../../build/reference/yc-create-precompiled-header-file.md) Option für die gleiche Datei.

Um dieses Problem zu beheben, legen Sie in der Regel nur eine Datei im Projekt mit kompiliert werden die **"/ Yc"** aus, und legen Sie alle anderen Dateien, die bei der Kompilierung der **"/ Yu"** Option. Weitere Informationen zur Verwendung von der **"/ Yc"** Optionen und legen Sie es in Visual Studio-IDE, finden Sie unter ["/ Yc" (Erstellen vorkompilierter Headerdatei)](../../build/reference/yc-create-precompiled-header-file.md). Weitere Informationen zur Verwendung von vorkompilierter Headers finden Sie unter [Erstellen vorkompilierter Headerdateien](../../build/creating-precompiled-header-files.md).
