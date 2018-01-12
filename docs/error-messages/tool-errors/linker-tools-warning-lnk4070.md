---
title: Linkertoolwarnung Lnk4070 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4070
dev_langs: C++
helpviewer_keywords: LNK4070
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1c3c683593b9019851b1a330a613adcf7a18c4a1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4070"></a>Linkertoolwarnung LNK4070
In/out: Dateiname-Direktive. EXP unterscheidet sich von Ausgabedateiname 'Dateiname'; Direktive wird ignoriert  
  
 Die `filename` angegebenen, in der [Namen](../../build/reference/name-c-cpp.md) oder [Bibliothek](../../build/reference/library.md) -Anweisung, wenn die .exp-Datei erstellt wurde, unterscheidet sich von der Ausgabe `filename` , entweder standardmäßig angenommen oder mit der angegebenwurde[/OUT](../../build/reference/out-output-file-name.md) Option.  
  
 Diese Warnung wird angezeigt werden, wenn Sie ändern Sie den Namen der Ausgabedatei in der Entwicklungsumgebung und, in dem das Projekt DEF-Datei wurde nicht aktualisiert. Aktualisieren Sie manuell der DEF-Datei, um diese Warnung zu beheben.  
  
 Ein Clientprogramm, das die resultierende DLL verwendet, kann Probleme auftreten.