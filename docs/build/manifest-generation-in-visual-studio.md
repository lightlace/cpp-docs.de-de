---
title: Manifestgenerierung in Visual Studio
ms.date: 11/04/2016
helpviewer_keywords:
- manifests [C++]
ms.assetid: 0af60aa9-d223-42cd-8426-b3fc543a2a81
ms.openlocfilehash: 69e1868990358aeb4d790366b3a0bfa8d8999823
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57414746"
---
# <a name="manifest-generation-in-visual-studio"></a>Manifestgenerierung in Visual Studio

Generieren einer Manifestdatei für ein bestimmtes Projekt kann gesteuert werden, in dem Projekt **Eigenschaftenseiten** Dialogfeld. Auf der **Konfigurationseigenschaften** auf **Linker**, klicken Sie dann **Manifestdatei**, klicken Sie dann **Manifest generieren**. Standardmäßig werden die Projekteigenschaften an neuen Projekten festgelegt, um eine Manifestdatei generieren. Jedoch ist es möglich, deaktivieren Sie die Generierung des Manifests für ein Projekt mit der **Manifest generieren** -Eigenschaft des Projekts. Wenn diese Eigenschaft auf festgelegt ist **Ja**, wird das Manifest für dieses Projekt generiert. Der Linker ignoriert Assemblyinformationen beim Auflösen von Abhängigkeiten des Anwendungscodes, und das Manifest nicht generiert.

Das Buildsystem von Visual Studio ermöglicht das Manifest in die endgültige Binärdatei der Anwendung-Datei eingebettet oder als externe Datei generiert werden. Dieses Verhalten wird gesteuert, indem die **Manifest einbetten** option die **Projekteigenschaften** Dialogfeld. Öffnen Sie zum Festlegen dieser Eigenschaft die **Manifesttool** Knoten, wählen Sie dann **ein- und Ausgabe**. Wenn das Manifest nicht eingebettet werden, ist als externe Datei generiert und im gleichen Verzeichnis wie die endgültige Binärdatei gespeichert. Wenn das Manifest eingebettet ist, bettet Visual Studio die endgültige Manifeste mithilfe des folgenden Prozesses:

1. Nachdem Sie der Quellcode in Objektdateien kompiliert wird, erfasst der Linker Informationen der abhängigen Assembly an. Beim Verknüpfen der endgültigen Binärdatei, generiert der Linker ein intermediate-Manifest, das später verwendet wird, um die endgültige Manifest zu generieren.

1. Nachdem der temporäre Bereitstellungsmanifest und das Verknüpfen abgeschlossen sind, wird das Manifesttool ausgeführt werden, um eine endgültige Manifest zusammenführen und speichern Sie sie als externe Datei.

1. Das Projekt Buildsystem dann erkennt, ob das Manifest generiert, die für das Manifesttool unterschiedliche Informationen bereits in der Binärdatei eingebettetes Manifest enthält.

1. Wenn das Manifest in die Binärdatei eingebettet unterscheidet sich von das Manifest generiert, die für das Manifesttool oder die Binärdatei kein eingebettetes Manifest enthält, Visual Studio ruft den Linker ein weiteres Mal die externe Manifestdatei als in die Binärdatei eingebettet ein die Ressource.

1. Wenn in der Binärdatei eingebettetes Manifest generiert, die für das Manifesttool identisch ist, wird der Build mit dem nächsten Schritt fortgesetzt.

Das Manifest in die endgültige Binärdatei als Textressource eingebettet ist, und es kann angezeigt werden, indem Sie die endgültige Binärdatei als Datei in Visual Studio öffnen. Um sicherzustellen, dass das Manifest auf die richtigen Bibliotheken verweist, die Schritte [Grundlegendes zu den Abhängigkeiten einer Visual C++-Anwendung](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md) oder führen Sie die Vorschläge in beschrieben die [Problembehandlung](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md) Abschnitt.

## <a name="see-also"></a>Siehe auch

[Vorgehensweise: Einbetten eines Manifests in eine C- bzw. C++-Anwendung](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md)<br/>
[Über Private Assemblys](/windows/desktop/SbsCs/about-private-assemblies-)<br/>
[Manifesttool](/windows/desktop/SbsCs/mt-exe)<br/>
[Manifestgenerierung für C/C++-Programme](../build/understanding-manifest-generation-for-c-cpp-programs.md)
