---
title: 'Eigenschaftenseite für benutzerdefinierten Buildschritt: Allgemein | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCCustomBuildStep.AdditionalInputs
- VC.Project.VCCustomBuildStep.CustomBuildAfterTargets
- VC.Project.VCCustomBuildStep.CustomBuildBeforeTargets
- VC.Project.VCCustomBuildStep.Outputs
- VC.Project.VCCustomBuildStep.Message
- VC.Project.VCCustomBuildStep.Command
dev_langs:
- C++
helpviewer_keywords:
- project properties, custom build step
- custom build step (general)
ms.assetid: bd319741-0491-46c4-a428-7c61b4b46a02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f34628ddd11c8cefdd00553f779a22448c2ec99d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404799"
---
# <a name="custom-build-step-property-page-general"></a>Eigenschaftenseite für benutzerdefinierten Buildschritt: Allgemein

Für jede Kombination von Projektkonfiguration und Zielplattform im Projekt können Sie einen benutzerdefinierten Schritt angeben, der ausgeführt werden muss, wenn das Projekt erstellt wird.

Die Linux-Version dieser Seite finden Sie unter [Benutzerdefinierte Buildschritteigenschaften (Linux C++)](../linux/prop-pages/custom-build-step-linux.md).

## <a name="uielement-list"></a>UIElement-Liste

- **Befehlszeile**

   Der vom benutzerdefinierten Buildschritt auszuführende Befehl.

- **Beschreibung**

   Eine Meldung, die anzeigt, wann der benutzerdefinierte Buildschritt läuft.

- **Ausgaben**

   Die Ausgabedatei, die der benutzerdefinierte Buildschritt generiert. Diese Einstellung ist erforderlich, damit inkrementelle Builds ordnungsgemäß funktionieren.

- **Zusätzliche Abhängigkeiten**

   Eine durch Semikolons getrennte Liste von zusätzlichen Eingabedateien, die für den benutzerdefinierten Buildschritt verwendet werden soll.

- **Im Anschluss ausführen und vorher ausführen**

   Diese Optionen definieren, wann ein benutzerdefinierter Buildschritt im Buildprozess relativ zu den aufgelisteten Zielen ausgeführt wird. Die am häufigste aufgelisteten Ziele sind BuildGenerateSources, BuildCompile und BuildLink, da sie die Hauptschritte im Buildprozess darstellen. Andere oft aufgelisteten Ziele sind Midl, CLCompile und Link.

- **Ausgabe als Inhalt behandeln**

   Diese Option ist nur bei der Universellen Windows-Plattform oder Windows Phone-Apps von Bedeutung, bei denen alle Inhaltsdateien im APPX-Paket enthalten sind.

### <a name="to-specify-a-custom-build-step"></a>So legen Sie einen benutzerdefinierten Buildschritt fest

1. Wählen Sie in der Menüleiste **Projekt** und **Eigenschaften** aus. Weitere Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../ide/working-with-project-properties.md).

1. Navigieren Sie im Dialogfeld **Eigenschaftenseiten** zur Seite **Konfigurationseigenschaften** > **Benutzerdefinierter Buildschritt** > **Allgemein**.

1. Ändern Sie die Einstellungen.

## <a name="see-also"></a>Siehe auch

[Eigenschaftenseiten](../ide/property-pages-visual-cpp.md)