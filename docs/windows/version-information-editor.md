---
title: Versionsinfo-Editor (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.version.F1
dev_langs:
- C++
helpviewer_keywords:
- Version Information editor [C++], about Version Information editor
- editors, Version Information
- resource editors [C++], Version Information editor
ms.assetid: 772e6f19-f765-4cec-9521-0ad3eeb99f9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b953343fa14d35ab387b0fd133d6e53db4551e1d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429252"
---
# <a name="version-information-editor-c"></a>Versionsinfo-Editor (C++)

Versionsinformationen bestehen aus einer Firmen- und einer Produkt-ID, einer Produktseriennummer und Copyright- und Markenbestimmungen. Mit der **Versionsinformationen** -Editor erstellt und verwaltet diese Daten, die in der Versionsinformationsressource gespeichert wird. Die Versionsinformationsressource ist für eine Anwendung nicht erforderlich, sie stellt aber einen sinnvollen Ort dar, alle Informationen zusammenzuführen, die zur Identifizierung der Anwendung dienen. Versionsinformationen werden auch von Setup-APIs verwendet.

Eine Versionsinformationsressource weist einen oberen Block und mindestens einen unteren Block auf: ein einzelner Block mit unveränderlichen Informationen oben und mindestens ein weiterer Versionsinformationsblock darunter (für andere Sprachen und/oder Zeichensätze). Der obere Block weist sowohl editierbare Zahlenfelder als auch auswählbare Dropdownlisten auf. Die unteren Blöcke weisen nur editierbare Textfelder auf.

> [!NOTE]
> Der Windows-Standard sieht nur eine Versionsressource mit dem Namen VS_VERSION_INFO vor.

Die **Versionsinformationen** -Editor können Sie:

- [Bearbeiten einer Zeichenfolge in einer Versionsinformationsressource](../windows/editing-a-string-in-a-version-information-resource.md)

- [Hinzufügen von Versionsinformationen für eine andere Sprache (neuer Versionsinformationsblock)](../windows/adding-version-information-for-another-language.md)

- [Löschen eines Versionsinformationsblocks](../windows/deleting-a-version-information-block.md)

- [Zugreifen auf Versionsinformationen aus dem Programm](../windows/accessing-version-information-from-within-your-program.md)

   > [!NOTE]
   > Bei der Verwendung der **Versionsinformationen** -Editor, in vielen Fällen, Sie können mit der rechten Maustaste, ein Kontextmenü mit ressourcenspezifische Befehle angezeigt. Beispielsweise wenn Sie klicken, während Sie auf einen Blockheadereintrag zeigen, zeigt das Kontextmenü der **neue Versionsblockinformationen** und **Versionsblockinformationen löschen** Befehle.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcen-Editor](../windows/resource-editors.md)<br/>
[Menüs und weitere Ressourcen](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)