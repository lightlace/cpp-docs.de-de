---
title: Assistentenunterstützung für andere Sprachen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.EastAsianLanguages
dev_langs:
- C++
helpviewer_keywords:
- wizards [C++], language support
- language support for MFC projects
- projects [C++], language support
ms.assetid: b653c673-0687-455c-885f-15d7e2f4149d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c33858e02fd8bad03e03a963e940f215d528157d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46395133"
---
# <a name="wizard-support-for-other-languages"></a>Assistentenunterstützung für andere Sprachen

Wenn Sie Visual Studio installieren, erkennt die Setupanwendung das Gebietsschema Ihres Systems, und die entsprechenden Vorlagen werden für das Gebietsschema installiert. Zum Beispiel installiert das Setup für westeuropäische Gebietsschemas Englisch, Französisch, Italienisch, Spanisch und Deutsch. Diese Sprachen werden in der Liste **Ressourcensprache** auf der Seite [Anwendungstyp](../mfc/reference/application-type-mfc-application-wizard.md) des MFC-Anwendungs-Assistenten angezeigt.

## <a name="language-templates"></a>Sprachvorlagen

Da die Vorlagen auf der ANSI-Codierung basieren, werden nicht alle Vorlagen auf allen Systemen installiert, und nicht alle Ressourcen können auf allen Systemen bearbeitet werden. Zum Beispiel können Sie japanische Ressourcen standardmäßig nicht auf einem französischen System bearbeiten.

Wenn Sie Windows 2000 oder höher verwenden und eine MFC-Anwendung in einer anderen Sprache erstellen möchten, müssen Sie zunächst das Vorlagenverzeichnis für die entsprechende Sprache vom Visual Studio-Installationsmedium (Disk 1) auf Ihr System kopieren.

> [!NOTE]
>  Zum Bearbeiten des erstellten Projekts müssen Sie das Gebietsschema des Systems für die ausgewählte Sprache festlegen.

Die Vorlagen sind, wie in der folgenden Tabelle gezeigt wird, jeweils einem Ordner im Verzeichnis \Microsoft Visual Studio .NET 2003\Vc7\VCWizards\mfcappwiz\templates\ zugeordnet. Kopieren Sie zum Zugreifen auf die gewünschte Sprachvorlage den entsprechenden Ordner in das Verzeichnis \mfcappwiz\templates\ auf Ihrem Computer. Sobald Sie den Ordner kopiert haben, wird die Sprache in der Liste **Ressourcensprache** auf der Seite **Anwendungstyp** des MFC-Anwendungs-Assistenten angezeigt.

### <a name="language-templates-provided-in-visual-studio-net"></a>Von Visual Studio .NET bereitgestellte Sprachvorlagen

|Sprache|Vorlage|
|--------------|--------------|
|Chinesisch (traditionell)|1028|
|Chinesisch (vereinfacht)|2052|
|Englisch|1033|
|Französisch|1036|
|Deutsch|1031|
|Italienisch|1040|
|Japanisch|1041|
|Koreanisch|1042|
|Spanisch|3082|

## <a name="format-of-visual-c-wizard-generated-files"></a>Format der vom Visual C++-Assistenten generierten Dateien

Die Visual C++-Assistenten generieren Projekte in Unicode, wenn die installierte Sprachversion von Visual Studio nicht mit dem Gebietsschema des Systems übereinstimmt. Wenn beispielsweise die japanische Version von Visual Studio auf einem Computer installiert ist, dessen regionale Einstellungen auf eine andere Sprache festgelegt sind, dann generieren Visual C++-Assistenten Projekte, die aus Unicode-Dateien bestehen. Dies tritt häufig bei Computern auf, die mit mehrsprachigen Windows-Paketen (MUI) eingerichtet wurden.

Dieses Verhalten unterscheidet sich von Systemen, die so eingerichtet sind, dass das Gebietsschema des Systems der Sprachversion von Visual Studio entspricht. In diesem Fall werden Projektdateien auf der System-Codepage in ANSI erstellt.

## <a name="see-also"></a>Siehe auch

[Für Visual C++-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)<br>
[Erstellen und Verwalten von Visual C++-Projekten](../ide/creating-and-managing-visual-cpp-projects.md)