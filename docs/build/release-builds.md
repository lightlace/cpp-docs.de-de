---
title: C++-Releasebuilds – Visual Studio
ms.date: 12/10/2018
helpviewer_keywords:
- debugging [C++], release builds
- release builds
- debug builds, converting to release build
ms.assetid: fa9a78fa-f4b5-4722-baf4-aec655c4ff0f
ms.openlocfilehash: cf11e63354502be000ba5f7259d9e36dfa774060
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315065"
---
# <a name="release-builds"></a>Releasebuilds

Ein Releasebuild verwendet Optimierungen. Wenn Sie Optimierungen verwenden, um einen Releasebuild zu erstellen, erzeugt der Compiler keine symbolischen Debuginformationen. Das Fehlen von symbolischen Debuginformationen, zusammen mit der Tatsache, dass der Code nicht für die ABLAUFVERFOLGUNG und ASSERT generiert aufgerufen wird, bedeutet, die dass die Größe Ihrer ausführbaren Datei wird reduziert, und daher ist es schneller.

## <a name="in-this-section"></a>In diesem Abschnitt

[Häufig auftretende Probleme beim Erstellen eines Releasebuilds](common-problems-when-creating-a-release-build.md)<br/>
[Beheben von Problemen mit dem Releasebuild](fixing-release-build-problems.md)<br/>
[Verwenden von VERIFY anstelle ASSERT](using-verify-instead-of-assert.md)<br/>
[Verwenden des Debugbuilds zur Suche nach Speicherüberschreibungen](using-the-debug-build-to-check-for-memory-overwrite.md)<br/>
[Vorgehensweise: Debuggen eines Releasebuilds](how-to-debug-a-release-build.md)<br/>
[Suchen nach Speicherüberschreibungen](checking-for-memory-overwrites.md)<br/>
[Codeoptimierung](optimizing-your-code.md)<br/>

## <a name="see-also"></a>Siehe auch

[Referenz zur C/C++-Erstellung](reference/c-cpp-building-reference.md)