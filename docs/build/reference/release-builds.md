---
title: Releasebuilds | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- debugging [C++], release builds
- release builds
- debug builds, converting to release build
ms.assetid: fa9a78fa-f4b5-4722-baf4-aec655c4ff0f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 12e81b26cd83214a5d62a42689bfc3a866ef1c10
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="release-builds"></a>Releasebuilds
Ein Releasebuild dahingehend verwendet Optimierungen. Wenn Sie die Optimierungen verwenden, um einen Releasebuild zu erstellen, erstellt der Compiler keine symbolischen Debuginformationen. Die Abwesenheit symbolischen Debuginformationen, zusammen mit der Tatsache, dass der Code nicht für ABLAUFVERFOLGUNG und ASSERT generiert aufgerufen wird, bedeutet, die dass die Größe der ausführbaren Datei wird reduziert, und daher ist es schneller.  
  
 In diesem Abschnitt werden die Informationen auf, wann und warum Sie von einem Debugbuild in ein Releasebuild dahingehend ändern möchten. Er erläutert einige der Probleme, die möglicherweise auftreten, wenn von einem Debugbuild auf ein Releasebuild dahingehend ändern:  
  
-   [Erstellen eines Releasebuilds](../../build/reference/how-to-create-a-release-build.md)  
  
-   [Häufig auftretende Probleme beim Erstellen eines Releasebuilds](../../build/reference/common-problems-when-creating-a-release-build.md)  
  
-   [Beheben von Problemen mit dem Releasebuild](../../build/reference/fixing-release-build-problems.md)  
  
    -   [Untersuchen ASSERT-Anweisungen](../../build/reference/using-verify-instead-of-assert.md)  
  
    -   [Verwenden die Debugbuilds zur Suche nach Speicherüberschreibungen](../../build/reference/using-the-debug-build-to-check-for-memory-overwrite.md)  
  
    -   [Debuggen eines Releasebuilds](../../build/reference/how-to-debug-a-release-build.md)  
  
    -   [Suchen nach Speicherüberschreibungen](../../build/reference/checking-for-memory-overwrites.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von C++-Projekten in Visual Studio](../../ide/building-cpp-projects-in-visual-studio.md)   
 [Referenz zur C/C++-Erstellung](../../build/reference/c-cpp-building-reference.md)