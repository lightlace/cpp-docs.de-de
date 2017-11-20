---
title: Binden von Importen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- /DELAY:NOBIND linker option
- DELAY:NOBIND linker option
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cd9bee6423c0eea98941331dcff86c002dd4ef9d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="binding-imports"></a>Binden von Importen
Das Standardverhalten der Linker ist eine bindbare Importadresstabelle für die verzögert geladenen DLL zu erstellen. Wenn die DLL gebunden ist, versucht die Hilfsfunktion, die gebundene Informationen verwenden, statt **GetProcAddress** auf jedem der referenzierten Importe. Wenn der Zeitstempel oder die bevorzugte Adresse nicht den der geladenen DLL übereinstimmen, wird die Hilfsfunktion davon ausgegangen werden, die gebundenen Import Local Address Table ist veraltet und wird fortgesetzt, als wäre sie nicht vorhanden ist.  
  
 Wenn Sie nie die DLL verzögert geladenen Importen binden möchten, die Angabe [/delay](../../build/reference/delay-delay-load-import-settings.md): Nobind in der Linker-Befehlszeile verhindert werden, dass die gebundene Import Local Address Table erzeugten und verwendeten Speicherplatz in der Bilddatei enthaltenen wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)