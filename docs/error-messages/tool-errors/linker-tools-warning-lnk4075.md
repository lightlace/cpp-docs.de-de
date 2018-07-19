---
title: Linkertoolwarnung Lnk4075 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4075
dev_langs:
- C++
helpviewer_keywords:
- LNK4075
ms.assetid: f39ad3f9-c263-4cf0-9d70-259fc56ac96d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4bd9a4ecdad30a0be2d45300367f6f79a65a6b31
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33301033"
---
# <a name="linker-tools-warning-lnk4075"></a>Linkertoolwarnung LNK4075
ignorieren die Option "1" aufgrund von "option2" Spezifikation  
  
 Die zweite Option überschreibt das erste.  
  
 Sich gegenseitig ausschließende Linkeroptionen werden angegeben wird.  Überprüfen Sie die Optionen des Linkers an.  Wobei die Optionen des Linkers angegeben werden, hängt davon ab, wie Sie das Projekt erstellen.  
  
-   Wenn Sie in der Entwicklungsumgebung erstellen, suchen Sie in den Linker-Eigenschaftenseiten für das Projekt und anzeigen Sie, in denen beide Optionen des Linkers angegeben werden.  Finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md) für Weitere Informationen.  
  
-   Wenn Sie in der Befehlszeile erstellen, sehen Sie sich die dort angegebenen Optionen des Linkers.  
  
-   Wenn Sie mit Buildskripts erstellen, Durchsuchen Sie Ihre Skripts, um anzuzeigen, in dem diese Optionen des Linkers angegeben werden.  
  
 Wenn Sie feststellen, wo sich gegenseitig ausschließende Linkeroptionen angegeben sind, entfernen Sie eine der Optionen des Linkers.  
  
 Einige spezifische Beispiele:  
  
-   Wenn Sie ein Modul verknüpfen, die mit kompiliert wurde **/Zi**, was bedeutet, dass eine interne Linkeroption EDITANDCONTINUE und ein Modul, das kompiliert wurde, die mit/OPT: REF, / OPT: ICF oder Standardlink, das keine/EDITANDCONTINUE aufgerufen wird, werden Sie Rufen Sie LNK4075.  Finden Sie unter ["/ Z7", / Zi, / Zi (Debuginformationsformat)](../../build/reference/z7-zi-zi-debug-information-format.md) für Weitere Informationen.