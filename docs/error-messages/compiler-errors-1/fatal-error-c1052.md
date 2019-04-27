---
title: Schwerwiegender Fehler C1052
ms.date: 05/08/2017
f1_keywords:
- C1052
helpviewer_keywords:
- C1052
ms.assetid: f2c09a2f-d3c1-4420-9501-ffcb65caf87b
ms.openlocfilehash: b381cc3cfe27d4c4a9d744a6b854a0e43727fe71
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243668"
---
# <a name="fatal-error-c1052"></a>Schwerwiegender Fehler C1052

> Programmdatenbankdatei "*Filename*', wurde vom Linker mit/Debug: Fastlink; generiert Compiler kann nicht solche PDB-Dateien zu aktualisieren, löschen Sie es oder/FD an einen anderen PDB-Dateinamen verwenden

Der Compiler kann nicht aktualisiert werden die gleichen Programm Programmdatenbankdatei (PDB)-Dateien, die vom Linker generiert werden bei der [/Debug: Fastlink](../../build/reference/debug-generate-debug-info.md) angegeben wird. Die vom Compiler generierte PDB-Dateien und die vom Linker generierte PDB-Dateien werden normalerweise unterschiedliche Namen besitzen. Wenn sie mit den gleichen Namen festgelegt werden, kann dieser Fehler jedoch führen.

Um dieses Problem zu beheben, können Sie explizit löschen die PDB-Dateien vor dem Kompilieren Sie erneut, oder Sie können unterschiedliche Namen für die vom Compiler generierte und vom Linker generierte PDB-Dateien erstellen.

Verwenden Sie zum Angeben der Name der vom Compiler generierte PDB-Datei in der Befehlszeile die [/FD](../../build/reference/fd-program-database-file-name.md) -Compileroption. Öffnen Sie zum Angeben der Name der vom Compiler generierte PDB-Datei in die IDE die **Eigenschaftenseiten** Dialogfeld für das Projekt, und klicken Sie in der **Konfigurationseigenschaften**, **C/C++-**,  **Ausgabedateien** Seite die **Programmdatenbank-Dateiname** Eigenschaft. Diese Eigenschaft ist standardmäßig `$(IntDir)vc$(PlatformToolsetVersion).pdb`.

Alternativ können Sie den Namen der vom Linker generierte PDB-Datei festlegen. Verwenden Sie zum Angeben der Name der vom Linker generierte PDB-Datei in der Befehlszeile die [/PDB](../../build/reference/pdb-use-program-database.md) -Linkeroption. Öffnen Sie zum Angeben der Name der vom Linker generierte PDB-Datei in die IDE die **Eigenschaftenseiten** Dialogfeld für das Projekt, und klicken Sie in der **Konfigurationseigenschaften**, **Linker**,  **Debuggen von** Seite die **Programmdatenbank-Datei erstellen** Eigenschaft. Standardmäßig ist diese Eigenschaft auf `$(OutDir)$(TargetName).pdb`festgelegt.
