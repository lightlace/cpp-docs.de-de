---
title: Releasebuilds
ms.date: 11/04/2016
helpviewer_keywords:
- debugging [C++], release builds
- release builds
- debug builds, converting to release build
ms.assetid: fa9a78fa-f4b5-4722-baf4-aec655c4ff0f
ms.openlocfilehash: 77e02b424b10b5e9606cc49152c2e21d7eeed9cb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667453"
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