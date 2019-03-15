---
title: 'Vorgehensweise: Integrieren von benutzerdefinierte Tools in den Projekteigenschaften'
ms.date: 04/27/2016
f1_keywords:
- msbuild.cpp.howto.integratecustomtools
helpviewer_keywords:
- 'msbuild (c++), howto: integrate custom tools'
ms.assetid: f32d91a4-44e9-4de3-aa9a-1c7f709ad2ee
ms.openlocfilehash: a959eddb36a2de90ebd5b5b1b9eb5e2f4e67c03a
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810158"
---
# <a name="how-to-integrate-custom-tools-into-the-project-properties"></a>Vorgehensweise: Integrieren von benutzerdefinierte Tools in den Projekteigenschaften

Sie können Optionen für benutzerdefinierte Tools in Visual Studio hinzufügen **Eigenschaftenseiten** Fenster durch das Erstellen einer zugrunde liegenden XML-Schemadatei.

Die **Konfigurationseigenschaften** Teil der **Eigenschaftenseiten** Fenster zeigt enthalten, die so genannte *Regeln*. Jede Regel enthält die Einstellungen für ein Tool oder einer Gruppe von Features. Z. B. die **Linker** Regel enthält die Einstellungen für den Linker-Tool. Die Einstellungen in einer Regel können unterteilt *Kategorien*.

In diesem Dokument wird erläutert, wie Sie eine Datei in einem Set-Verzeichnis zu erstellen, die Eigenschaften für das benutzerdefinierte Tool enthält, damit die Eigenschaften beim Start von Visual Studio geladen werden. Informationen dazu, wie Sie die Datei ändern, finden Sie unter [Plattform Erweiterbarkeit Teil 2](https://blogs.msdn.microsoft.com/vsproject/2009/06/18/platform-extensibility-part-2/) im Visual Studio-Projekt-Team-Blog.

### <a name="to-add-or-change-project-properties"></a>Hinzufügen oder Ändern von Projekteigenschaften

1. Erstellen Sie in der XML-Editor eine XML-Datei.

1. Speichern Sie die Datei in der Visual Studio 2017 `VCTargets\1033` Ordner. Sie müssen einen anderen Pfad für jede Edition von Visual Studio 2017, die installiert ist und jede Sprache. Beispielsweise ist der Pfad des Ordners für Visual Studio Enterprise-Edition, in englischer Sprache `%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033`. Passen Sie den Pfad für die Sprache und Visual Studio-Edition an. Jede Regel in der **Eigenschaftenseiten** Fenster wird durch eine XML-Datei in diesem Ordner dargestellt. Stellen Sie sicher, dass die Datei im Ordner "" eindeutig benannt ist.

1. Kopieren Sie den Inhalt der `%ProgramFiles%\Microsoft Visual Studio\2017\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>\cl.xml`, schließen Sie sie ohne Änderungen zu speichern, und fügen Sie den Inhalt in der neuen XML-Datei. Sie können jede XML-Schema-Datei verwenden – Dies ist nur eine, die verwendet werden können, sodass Sie mit einer Vorlage beginnen.

1. Ändern Sie in der neuen XML-Datei des Inhalts gemäß Ihren Anforderungen. Stellen Sie sicher, dass die **Regelname** und **Rule.DisplayName** am Anfang der Datei.

1. Speichern Sie die Änderungen, und schließen Sie die Datei.

1. Das XML-Dateien im `%ProgramFiles%\Microsoft Visual Studio\2017\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>` werden beim Start von Visual Studio geladen. Aus diesem Grund, um die neue Datei zu testen, starten Sie Visual Studio an.

1. In **Projektmappen-Explorer**mit der rechten Maustaste auf ein Projekt, und klicken Sie dann auf **Eigenschaften**. In der **Eigenschaftenseiten** Fenster im linken Bereich, stellen Sie sicher, dass ein neuer Knoten mit dem Namen der Regel vorhanden ist.

## <a name="see-also"></a>Siehe auch

[MSBuild in der Befehlszeile – C++](msbuild-visual-cpp.md)
