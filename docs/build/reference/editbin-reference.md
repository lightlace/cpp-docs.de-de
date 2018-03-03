---
title: EDITBIN-Referenz | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- editbin
dev_langs:
- C++
helpviewer_keywords:
- binary data, editing
- object files, modifying
- EDITBIN program
- COFF files, editing
ms.assetid: efdda03b-3dfc-4d31-90e6-caf5b3977914
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e0ff9c0c58498361764dcc1b6c454c9b629d9bed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="editbin-reference"></a>EDITBIN-Referenz
Der Microsoft COFF-Binär-Editor (EDITBIN. EXE-Datei) ändert die Binärdateien Common Object File Format (COFF). EDITBIN können um Objektdateien, ausführbaren Dateien und Dynamic Link Libraries (DLL) zu ändern.  
  
> [!NOTE]
>  Sie können dieses Tool nur von der [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]-Eingabeaufforderung aus starten. Sie können es nicht von einer Systemeingabeaufforderung oder vom Datei-Explorer aus starten.  
  
 EDITBIN ist nicht verfügbar für die Verwendung in den Dateien erstellt wird, mit der [/GL](../../build/reference/gl-whole-program-optimization.md) -Compileroption. Alle Änderungen auf die Binärdateien, die mit/GL erzeugten müssen erreicht werden, indem Sie neu zu kompilieren und verknüpfen.  
  
-   [EDITBIN-Befehlszeile](../../build/reference/editbin-command-line.md)  
  
-   [EDITBIN-Optionen](../../build/reference/editbin-options.md)  
  
## <a name="see-also"></a>Siehe auch  
 [C/C++-Buildtools](../../build/reference/c-cpp-build-tools.md)