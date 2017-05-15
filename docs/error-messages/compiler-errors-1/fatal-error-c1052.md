---
title: Schwerwiegender Fehler C1052 | Microsoft Docs
ms.custom: 
ms.date: 05/08/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1052
dev_langs:
- C++
helpviewer_keywords:
- C1052
ms.assetid: f2c09a2f-d3c1-4420-9501-ffcb65caf87b
caps.latest.revision: 0
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: f3ab91c1c79b822a4d9a33fb0ab5fbd88146fff0
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="fatal-error-c1052"></a>Schwerwiegender Fehler C1052
Programmdatenbankdatei "*Filename*", wurde vom Linker mit Fastlink; generiert Compiler kann nicht solche PDB-Dateien zu aktualisieren; löschen Sie es oder/FD an einem anderen PDB-Dateinamen verwenden  
  
Der Compiler kann nicht aktualisiert die gleichen Programm Programmdatenbankdatei (PDB) Dateien, die vom Linker generiert werden bei der [Fastlink](../../build/reference/debug-generate-debug-info.md) angegeben wird. Die vom Compiler generierte PDB-Dateien und die vom Linker generierte PDB-Dateien werden normalerweise unterschiedliche Namen besitzen. Wenn sie festgelegt wurden, auf die gleichen Namen verwenden, kann dieser Fehler jedoch führen.  
  
Um dieses Problem zu beheben, können Sie explizit löschen die PDB-Dateien vor dem Kompilieren Sie erneut, oder Sie können unterschiedliche Namen für den Compiler generiert und vom Linker generierte PDB-Dateien erstellen. Verwenden Sie zum Erstellen von anderer vom Compiler generierte PDB Dateinamen in der Befehlszeile die [/FD](../../build/reference/fd-program-database-file-name.md) Option. Öffnen Sie zum Generieren von anderer PDB-Dateinamen in der IDE die **Eigenschaftenseiten** Dialogfeld für das Projekt, und klicken Sie in der **Konfigurationseigenschaften**, **C/C++-**, **Ausgabedateien** Seite der **Programmdatenbank-Dateiname** Eigenschaft. Standardmäßig ist diese Eigenschaft `$(IntDir)vc$(PlatformToolsetVersion).pdb`. Alternativ können Sie den Namen der vom Linker generierte PDB-Datei festlegen. Öffnen der **Eigenschaftenseiten** Dialogfeld für das Projekt, und klicken Sie in der **Konfigurationseigenschaften**, **Linker**, **Debuggen** Seite der **Programmdatenbank-Datei erstellen** Eigenschaft. Standardmäßig ist diese Eigenschaft auf `$(OutDir)$(TargetName).pdb` festgelegt.  

