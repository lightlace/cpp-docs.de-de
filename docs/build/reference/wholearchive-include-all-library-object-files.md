---
title: / WHOLEARCHIVE (alle Bibliotheksobjektdateien einbeziehen)
ms.date: 11/04/2016
ms.assetid: ee92d12f-18af-4602-9683-d6223be62ac9
ms.openlocfilehash: db99816b18110b424647603196040997044e7fbd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316430"
---
# <a name="wholearchive-include-all-library-object-files"></a>/ WHOLEARCHIVE (alle Bibliotheksobjektdateien einbeziehen)

Erzwingen Sie den Linker an, die statische Bibliothek in die verknüpfte ausführbare Datei alle Objektdateien einschließt.

## <a name="syntax"></a>Syntax

> / WHOLEARCHIVE [:*Bibliothek*]

## <a name="remarks"></a>Hinweise

Die Option /WHOLEARCHIVE zwingt den Linker an, Includedatei jedes Objekt aus einer angegebenen statische Bibliothek, oder wenn keine Bibliothek angegeben wird, über alle statischen Bibliotheken, die auf den LINK angegebene Befehl. Um die /WHOLEARCHIVE-Option für mehrere Bibliotheken anzugeben, können Sie mehrere /WHOLEARCHIVE Switches in der Befehlszeile des Linkers. Standardmäßig enthält der Linker Objektdateien in der verknüpften Ausgabe, nur dann, wenn exportieren sie die Symbole, die auf die anderen Objektdateien in die ausführbare Datei verweist. Die /WHOLEARCHIVE-Option wird den Linker behandeln alle Objektdateien, die in einer statischen Bibliothek archiviert werden, als ob sie einzeln die Linker-Befehlszeile angegeben wurden.

Die /WHOLEARCHIVE-Option kann verwendet werden, um alle Symbole aus einer statischen Bibliothek erneut zu exportieren. Dadurch können Sie sicherstellen, dass alle Ihre Bibliothekscode, Ressourcen und Metadaten enthalten sind, wenn Sie eine Komponente aus mehr als eine statische Bibliothek erstellen. Wenn Sie sehen die Warnung LNK4264, wenn Sie eine statische Bibliothek, die erstellen Windows-Runtime-Komponenten für den Export enthält, verwenden Sie die Option /WHOLEARCHIVE, beim Verknüpfen von dieser Bibliothek in eine andere Komponente oder app.

Die /WHOLEARCHIVE-Option wurde in Visual Studio 2015 Update 2 eingeführt.

### <a name="to-set-this-linker-option-in-visual-studio"></a>So legen Sie diese Linkeroption in Visual Studio fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Befehlszeile** Eigenschaftenseite unter **Konfigurationseigenschaften**, **Linker**.

1. Die /WHOLEARCHIVE-Option zum Hinzufügen der **zusätzliche Optionen** Textfeld.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
