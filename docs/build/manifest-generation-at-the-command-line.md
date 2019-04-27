---
title: Manifestgenerierung über die Befehlszeile
ms.date: 11/04/2016
helpviewer_keywords:
- manifests [C++]
- manifest tool (mt.exe)
ms.assetid: fc2ff255-82b1-4c44-af76-8405c5850292
ms.openlocfilehash: 37036ceedc59e20374fd1106a051ab2a66edd143
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273775"
---
# <a name="manifest-generation-at-the-command-line"></a>Manifestgenerierung über die Befehlszeile

Beim Erstellen von C/C++-Anwendungen über die Befehlszeile mithilfe von Nmake oder ähnliche Tools wird das Manifest generiert, nachdem der Linker verarbeitet alle Objektdateien und die endgültige Binärdatei erstellt hat. Der Linker sammelt Assemblyinformationen, die in den Objektdateien gespeichert und kombiniert diese Informationen in eine endgültige Manifestdatei. Standardmäßig generiert der Linker eine Datei namens *name_der_binärdatei*. *Erweiterung*Manifest, um die endgültige Binärdatei zu beschreiben. Der Linker eine Manifestdatei in die Binärdatei nicht einbetten und kann nur ein Manifest als externe Datei generieren. Es gibt mehrere Möglichkeiten zum Einbetten eines Manifests in die endgültige Binärdatei, z. B. die Verwendung der [Manifesttool (mt.exe)](https://msdn.microsoft.com/library/aa375649) oder Kompilieren das Manifest in eine Ressourcendatei. Es ist wichtig zu bedenken, die bestimmte Regeln befolgt werden, wenn das Einbetten eines Manifests in die endgültige Binärdatei zum Aktivieren von Funktionen wie inkrementelle Verknüpfungen, "Signierung", und bearbeiten und fortfahren. Diese und weitere Optionen finden Sie im [Vorgehensweise: Betten Sie ein Manifest in einer C/C++-Anwendung](how-to-embed-a-manifest-inside-a-c-cpp-application.md) beim Erstellen über die Befehlszeile.

## <a name="see-also"></a>Siehe auch

[Manifeste](/windows/desktop/sbscs/manifests)<br/>
[/INCREMENTAL (Inkrementell verknüpfen)](reference/incremental-link-incrementally.md)<br/>
[Assemblys mit starken Namen (Assemblysignierung) (C++/CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)<br/>
[Bearbeiten und Fortfahren](/visualstudio/debugger/edit-and-continue)<br/>
[Manifestgenerierung für C/C++-Programme](understanding-manifest-generation-for-c-cpp-programs.md)<br/>
