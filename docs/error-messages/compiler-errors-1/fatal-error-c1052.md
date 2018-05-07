---
title: Schwerwiegender Fehler C1052 | Microsoft Docs
ms.custom: ''
ms.date: 05/08/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1052
dev_langs:
- C++
helpviewer_keywords:
- C1052
ms.assetid: f2c09a2f-d3c1-4420-9501-ffcb65caf87b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d8d272b71a527763245ccf7c8d69bd11a915eab7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1052"></a>Schwerwiegender Fehler C1052

> Programmdatenbankdatei "*Filename*", wurde vom Linker mit Fastlink; generiert Compiler kann nicht solche PDB-Dateien zu aktualisieren; löschen Sie es oder/FD an einem anderen PDB-Dateinamen verwenden

Der Compiler kann nicht aktualisiert die gleichen Programm Programmdatenbankdatei (PDB) Dateien, die vom Linker generiert werden bei der [Fastlink](../../build/reference/debug-generate-debug-info.md) angegeben wird. Die vom Compiler generierte PDB-Dateien und die vom Linker generierte PDB-Dateien werden normalerweise unterschiedliche Namen besitzen. Wenn sie festgelegt wurden, auf die gleichen Namen verwenden, kann dieser Fehler jedoch führen.

Um dieses Problem zu beheben, können Sie explizit löschen die PDB-Dateien vor dem Kompilieren Sie erneut, oder Sie können unterschiedliche Namen für den Compiler generiert und vom Linker generierte PDB-Dateien erstellen.

Um den Namen der vom Compiler generierte PDB-Datei in der Befehlszeile anzugeben, verwenden die [/FD](../../build/reference/fd-program-database-file-name.md) -Compileroption. Öffnen Sie zum Angeben der Name der vom Compiler generierte PDB-Datei in der IDE die **Eigenschaftenseiten** Dialogfeld für das Projekt, und klicken Sie in der **Konfigurationseigenschaften**, **C/C++-**,  **Ausgabedateien** Seite der **Programmdatenbank-Dateiname** Eigenschaft. Standardmäßig ist diese Eigenschaft `$(IntDir)vc$(PlatformToolsetVersion).pdb`.

Alternativ können Sie den Namen der vom Linker generierte PDB-Datei festlegen. Um den Namen der vom Linker generierte PDB-Datei in der Befehlszeile anzugeben, verwenden die [/PDB](../../build/reference/pdb-use-program-database.md) (Linkeroption). Öffnen Sie zum Angeben der Name der vom Linker generierte PDB-Datei in der IDE die **Eigenschaftenseiten** Dialogfeld für das Projekt, und klicken Sie in der **Konfigurationseigenschaften**, **Linker**,  **Debuggen** Seite der **Programmdatenbank-Datei erstellen** Eigenschaft. Standardmäßig ist diese Eigenschaft auf `$(OutDir)$(TargetName).pdb` festgelegt.
