---
title: Manifestgenerierung über die Befehlszeile
ms.date: 11/04/2016
helpviewer_keywords:
- manifests [C++]
- manifest tool (mt.exe)
ms.assetid: fc2ff255-82b1-4c44-af76-8405c5850292
ms.openlocfilehash: 381406213422e286dd9aba26adcdbd6caff7bfe3
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493204"
---
# <a name="manifest-generation-at-the-command-line"></a>Manifestgenerierung über die Befehlszeile

Beim Erstellen von CC++ /Anwendungen über die Befehlszeile mithilfe von NMAKE oder ähnlichen Tools wird das Manifest generiert, nachdem der Linker alle Objektdateien verarbeitet und die endgültige Binärdatei erstellt hat. Der Linker sammelt Assemblyinformationen, die in den Objektdateien gespeichert sind, und kombiniert diese Informationen in einer endgültigen Manifest-Datei. Standardmäßig generiert der Linker eine Datei mit dem Namen *binary_name*. *Erweiterung*. Manifest, um die endgültige Binärdatei zu beschreiben. Der Linker bettet keine Manifest-Datei in die Binärdatei ein und kann nur ein Manifest als externe Datei generieren. Es gibt mehrere Möglichkeiten, ein Manifest in die endgültige Binärdatei einzubetten, z. b. das [Manifest-Tool (Mt. exe)](/windows/win32/sbscs/mt-exe) zu verwenden oder das Manifest in eine Ressourcen Datei zu kompilieren. Beachten Sie, dass beim Einbetten eines Manifests in die endgültige Binärdatei bestimmte Regeln befolgt werden müssen, um Funktionen wie inkrementelles Verknüpfen, Signieren und bearbeiten und fortfahren zu ermöglichen. Diese und andere Optionen werden unter [Vorgehensweise: Einbetten eines Manifests in eine CC++ /](how-to-embed-a-manifest-inside-a-c-cpp-application.md) Anwendung beim Aufbau in der Befehlszeile.

## <a name="see-also"></a>Siehe auch

[Mani](/windows/win32/sbscs/manifests)<br/>
[/INCREMENTAL (Inkrementell verknüpfen)](reference/incremental-link-incrementally.md)<br/>
[Assemblys mit starken Namen (Assemblysignierung) (C++/CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)<br/>
[Bearbeiten und Fortfahren](/visualstudio/debugger/edit-and-continue)<br/>
[Manifestgenerierung für C/C++-Programme](understanding-manifest-generation-for-c-cpp-programs.md)<br/>
