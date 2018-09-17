---
title: Releasebuilds | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- debugging [C++], release builds
- release builds
- debug builds, converting to release build
ms.assetid: fa9a78fa-f4b5-4722-baf4-aec655c4ff0f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b8d4f0d9b1bf0401cc6630b61449e87d72ff675
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722123"
---
# <a name="release-builds"></a>Releasebuilds

Ein Releasebuild verwendet Optimierungen. Wenn Sie Optimierungen verwenden, um einen Releasebuild zu erstellen, erzeugt der Compiler keine symbolischen Debuginformationen. Das Fehlen von symbolischen Debuginformationen, zusammen mit der Tatsache, dass der Code nicht für die ABLAUFVERFOLGUNG und ASSERT generiert aufgerufen wird, bedeutet, die dass die Größe Ihrer ausführbaren Datei wird reduziert, und daher ist es schneller.

In diesem Abschnitt werden Informationen zu warum und wann Sie von einem Debugbuild in ein Releasebuild ändern möchten. Außerdem wird erläutert, einige der Probleme, die möglicherweise auftreten, wenn von einer Debugversion in einem Releasebuild ändern:

- [Erstellen eines Releasebuilds](../../build/reference/how-to-create-a-release-build.md)

- [Häufig auftretende Probleme beim Erstellen eines Releasebuilds](../../build/reference/common-problems-when-creating-a-release-build.md)

- [Beheben von Problemen mit dem Releasebuild](../../build/reference/fixing-release-build-problems.md)

   - [Untersuchen ASSERT-Anweisungen](../../build/reference/using-verify-instead-of-assert.md)

   - [Verwenden die Debugbuilds zur Suche nach Speicherüberschreibungen](../../build/reference/using-the-debug-build-to-check-for-memory-overwrite.md)

   - [Debuggen eines Releasebuilds](../../build/reference/how-to-debug-a-release-build.md)

   - [Suchen nach Speicherüberschreibungen](../../build/reference/checking-for-memory-overwrites.md)

## <a name="see-also"></a>Siehe auch

[Erstellen von C++-Projekten in Visual Studio](../../ide/building-cpp-projects-in-visual-studio.md)<br/>
[Referenz zur C/C++-Erstellung](../../build/reference/c-cpp-building-reference.md)