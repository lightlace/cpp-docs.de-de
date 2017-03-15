---
title: Linkertoolwarnung Lnk4075 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4075
dev_langs:
- C++
helpviewer_keywords:
- LNK4075
ms.assetid: f39ad3f9-c263-4cf0-9d70-259fc56ac96d
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 9dee257bec0f09bd729bf10c4a1468ecb20dfa61
ms.openlocfilehash: 84dea754a1d2268c92e703dd04b0169ccc258ab3
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4075"></a>Linkertoolwarnung LNK4075
"option1" aufgrund der Spezifikation "option2" werden ignoriert.  
  
 Die zweite Option überschreibt die erste.  
  
 Sich gegenseitig ausschließende Linkeroptionen werden angegeben.  Überprüfen Sie die Linkeroptionen.  Wobei die Optionen des Linkers angegeben werden, hängt davon ab, wie Sie das Projekt erstellen.  
  
-   Wenn Sie in der Entwicklungsumgebung erstellen, in der Linker-Eigenschaftenseiten für das Projekt suchen Sie und finden Sie unter, in denen beide Optionen des Linkers angegeben werden.  Finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md) Weitere Informationen.  
  
-   Wenn Sie in der Befehlszeile erstellen, betrachten Sie den dort angegebenen Linkeroptionen.  
  
-   Wenn Sie mit Buildskripts erstellen, Durchsuchen Sie Ihre Skripts an, in dem diese Optionen des Linkers angegeben werden.  
  
 Wenn Sie feststellen, wo sich gegenseitig ausschließende Linkeroptionen angegeben sind, entfernen Sie eine der Linkeroptionen verfügbar.  
  
 Einige spezifische Beispiele:  
  
-   Wenn Sie ein Modul verknüpfen, die mit kompiliert wurde **/Zi**, d. h. eine interne Linkeroption EDITANDCONTINUE und ein kompiliertes Modul wurde mit/OPT: REF, / OPT: ICF oder/INCREMENTAL: No, das keine EDITANDCONTINUE aufgerufen, wird LNK4075.  Finden Sie unter [/Z7, / Zi, / Zi (Debuginformationsformat)](../../build/reference/z7-zi-zi-debug-information-format.md) für Weitere Informationen.
