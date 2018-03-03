---
title: Linkertoolwarnung Lnk4022 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4022
dev_langs:
- C++
helpviewer_keywords:
- LNK4022
ms.assetid: 890f487e-db98-45dd-a226-c7ccead82b1e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e35974a72de349f94f2189f676b6dc955c48fab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4022"></a>Linkertoolwarnung LNK4022
eindeutige Übereinstimmung für das Symbol 'Symbol' wurde nicht gefunden.  
  
 LINK oder LIB mehrere gefunden für das angegebene nicht ergänzten Symbol entspricht, und es konnte nicht die Mehrdeutigkeit aufzulösen. Es wird keine Ausgabedatei (.exe, .dll, .exp oder .lib) erstellt. Diese Warnung durch eine einzige Warnung folgt [LNK4002](../../error-messages/tool-errors/linker-tools-warning-lnk4002.md) für jedes Symbol doppelt vorhanden und wird schließlich gefolgt von Schwerwiegender Fehler [LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md).  
  
 Um diese Warnung zu vermeiden, geben Sie das Symbol in seiner ergänzten Form. Führen Sie [DUMPBIN](../../build/reference/dumpbin-options.md) für das Objekt anzeigen von ergänzten Namen.