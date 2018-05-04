---
title: Binden von Importen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- /DELAY:NOBIND linker option
- DELAY:NOBIND linker option
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7519fb18ac7f24e79a5f7f664cb35f8eb5b3fd77
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="binding-imports"></a>Binden von Importen
Das Standardverhalten der Linker ist eine bindbare Importadresstabelle für die verzögert geladenen DLL zu erstellen. Wenn die DLL gebunden ist, versucht die Hilfsfunktion, die gebundene Informationen verwenden, statt **GetProcAddress** auf jedem der referenzierten Importe. Wenn der Zeitstempel oder die bevorzugte Adresse nicht den der geladenen DLL übereinstimmen, wird die Hilfsfunktion davon ausgegangen werden, die gebundenen Import Local Address Table ist veraltet und wird fortgesetzt, als wäre sie nicht vorhanden ist.  
  
 Wenn Sie nie die DLL verzögert geladenen Importen binden möchten, die Angabe [/delay](../../build/reference/delay-delay-load-import-settings.md): Nobind in der Linker-Befehlszeile verhindert werden, dass die gebundene Import Local Address Table erzeugten und verwendeten Speicherplatz in der Bilddatei enthaltenen wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)