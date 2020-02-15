---
title: /WHOLEARCHIVE (alle Bibliotheksobjekt Dateien einschließen)
ms.date: 02/12/2020
ms.assetid: ee92d12f-18af-4602-9683-d6223be62ac9
ms.openlocfilehash: 95685c9c0dfde45c42449bbcad67228a0e21b36a
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257532"
---
# <a name="wholearchive-include-all-library-object-files"></a>/WHOLEARCHIVE (alle Bibliotheksobjekt Dateien einschließen)

Erzwingen Sie, dass der Linker alle Objektdateien in der statischen Bibliothek in die verknüpfte ausführbare Datei einschließt.

## <a name="syntax"></a>Syntax

> **/WHOLEARCHIVE**\
> **/WHOLEARCHIVE:** _Bibliothek_

### <a name="arguments"></a>Argumente

*Bibliothek*\
Ein Optionaler Pfadname für eine statische Bibliothek. Der Linker schließt alle Objektdateien aus dieser Bibliothek ein.

## <a name="remarks"></a>Bemerkungen

Die/WHOLEARCHIVE-Option zwingt den Linker, jede Objektdatei aus einer angegebenen statischen Bibliothek einzubeziehen, oder, wenn keine Bibliothek angegeben ist, aus allen statischen Bibliotheken, die für den Link-Befehl angegeben sind. Um die/WHOLEARCHIVE-Option für mehrere Bibliotheken anzugeben, können Sie mehr als einen/WHOLEARCHIVE-Schalter in der Linkerbefehlszeile verwenden. Standardmäßig enthält der Linker nur Objektdateien in der verknüpften Ausgabe, wenn Sie Symbole exportieren, auf die von anderen Objektdateien in der ausführbaren Datei verwiesen wird. Mit der/WHOLEARCHIVE-Option werden alle Objektdateien, die in einer statischen Bibliothek archiviert werden, vom Linker behandelt, als ob Sie einzeln in der Linker-Befehlszeile angegeben wurden.

Die/WHOLEARCHIVE-Option kann verwendet werden, um alle Symbole aus einer statischen Bibliothek erneut zu exportieren. Auf diese Weise können Sie sicherstellen, dass der gesamte Bibliotheks Code, Ressourcen und Metadaten eingeschlossen werden, wenn Sie eine Komponente aus mehr als einer statischen Bibliothek erstellen. Wenn eine Warnung angezeigt wird LNK4264 Wenn Sie eine statische Bibliothek erstellen, die Windows-Runtime Komponenten für den Export enthält, verwenden Sie die Option/WHOLEARCHIVE, wenn Sie diese Bibliothek mit einer anderen Komponente oder App verknüpfen.

Die/WHOLEARCHIVE-Option wurde in Visual Studio 2015 Update 2 eingeführt.

### <a name="to-set-this-linker-option-in-visual-studio"></a>So legen Sie diese Linkeroption in Visual Studio fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Wählen Sie die Eigenschaften Seite **Befehlszeile** unter **Konfigurations Eigenschaften**, **Linker**aus.

1. Fügen Sie dem Textfeld **zusätzliche Optionen** die Option/WHOLEARCHIVE hinzu.

## <a name="see-also"></a>Weitere Informationen

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
