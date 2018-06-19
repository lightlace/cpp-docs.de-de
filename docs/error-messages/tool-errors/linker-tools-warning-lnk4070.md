---
title: Linkertoolwarnung Lnk4070 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4070
dev_langs:
- C++
helpviewer_keywords:
- LNK4070
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e4599e96552f1b98ef0b1af8d38995ebbe5a83e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302502"
---
# <a name="linker-tools-warning-lnk4070"></a>Linkertoolwarnung LNK4070
In/out: Dateiname-Direktive. EXP unterscheidet sich von Ausgabedateiname 'Dateiname'; Direktive wird ignoriert  
  
 Die `filename` angegebenen, in der [Namen](../../build/reference/name-c-cpp.md) oder [Bibliothek](../../build/reference/library.md) -Anweisung, wenn die .exp-Datei erstellt wurde, unterscheidet sich von der Ausgabe `filename` , entweder standardmäßig angenommen oder mit der angegebenwurde[/OUT](../../build/reference/out-output-file-name.md) Option.  
  
 Diese Warnung wird angezeigt werden, wenn Sie ändern Sie den Namen der Ausgabedatei in der Entwicklungsumgebung und, in dem das Projekt DEF-Datei wurde nicht aktualisiert. Aktualisieren Sie manuell der DEF-Datei, um diese Warnung zu beheben.  
  
 Ein Clientprogramm, das die resultierende DLL verwendet, kann Probleme auftreten.