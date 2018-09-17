---
title: Binden von Importen | Microsoft-Dokumentation
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
ms.openlocfilehash: 551028999d11379c06d3319f01e882a33ad57936
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705197"
---
# <a name="binding-imports"></a>Binden von Importen

Das Standardverhalten der Linker ist eine bindbare Importadresstabelle für den verzögert geladenen DLL zu erstellen. Wenn die DLL gebunden ist, versucht die Hilfsfunktion, die die gebundene Informationen zu verwenden, statt **GetProcAddress** auf jedem der referenzierten Importe. Wenn entweder der Zeitstempel oder die Adresse des bevorzugten nicht denen der geladenen DLL übereinstimmen, geht die Hilfsfunktion davon aus, die gebundene Importadresstabelle ist veraltet und wird fortgesetzt, als ob er nicht vorhanden ist.

Wenn Sie nicht mehr der DLL verzögert geladenen Importen binden möchten, wird durch Angabe [/delay](../../build/reference/delay-delay-load-import-settings.md): Nobind in der Befehlszeile des Linkers verhindert werden, dass die gebundene Importadresstabelle wird generiert und verwendeten Speicherplatz in der Imagedatei.

## <a name="see-also"></a>Siehe auch

[Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)