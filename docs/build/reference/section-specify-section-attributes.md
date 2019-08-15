---
title: /SECTION (Abschnittsattribute festlegen)
ms.date: 12/29/2017
f1_keywords:
- /section
helpviewer_keywords:
- SECTION linker option
- -SECTION linker option
- section attributes
- /SECTION linker option
ms.openlocfilehash: 0a52e9c9dcd53b01f17dc36825732b34771c75bb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492628"
---
# <a name="section-specify-section-attributes"></a>/SECTION (Abschnittsattribute festlegen)

> **/Section:** _Name_, [[ **!** ] {**Dekprsw**}] [ **, Align =** _Zahl_]

## <a name="remarks"></a>Hinweise

Die Option **/section** ändert die Attribute eines Abschnitts und überschreibt die Attribute, die beim Kompilieren der obj-Datei für den Abschnitt festgelegt wurden.

Ein *Abschnitt* in einer portablen ausführbaren Datei (PE) ist ein benannter zusammenhängender Speicherblock, der entweder Code oder Daten enthält. Einige Abschnitte enthalten Code oder Daten, die von Ihrem Programm deklariert und direkt verwendet werden, während andere Datenabschnitte vom Linker und Bibliothek-Manager (lib. exe) erstellt werden und wichtige Informationen für das Betriebssystem enthalten. Weitere Informationen finden Sie unter [PE-Format](/windows/win32/Debug/pe-format).

Geben Sie einen Doppelpunkt an (:) und einen Abschnitts *Namen*. Beim *Namen* wird Groß-/Kleinschreibung beachtet.

Verwenden Sie die folgenden Namen nicht, da diese mit Standardnamen in Konflikt stehen. Beispielsweise werden. sdata auf RISC-Plattformen verwendet:

- . Arch

- BSS

- . Data

- . edata

- . iData

- . pdata

- . rdata

- . reloc

- . rsrc

- SBSS

- sdata

- srdata

- . Text

- . XData

Geben Sie ein oder mehrere Attribute für den Abschnitt an. Bei den unten aufgeführten Attribut Zeichen wird die Groß-/Kleinschreibung nicht beachtet. Sie müssen alle Attribute angeben, die der Abschnitt enthalten soll. ein ausgelassenes Attribut Zeichen bewirkt, dass dieses Attribut Bit ausgeschaltet wird. Wenn Sie R, W oder E nicht angeben, bleibt der vorhandene Lese-, Schreib-oder ausführbare Status unverändert.

Um ein Attribut zu negieren, stellen Sie dem Zeichen ein Ausrufezeichen (!) voran. Die Bedeutungen der Attribut Zeichen sind in dieser Tabelle dargestellt:

|Zeichen|Attribut|Bedeutung|
|---------------|---------------|-------------|
|E|Ausführen|Der Abschnitt ist ausführbare Datei.|
|R|Lesen|Ermöglicht Lesevorgänge für Daten.|
|W|Write|Ermöglicht Schreibvorgänge für Daten.|
|S|Shared|Gibt den Abschnitt zu allen Prozessen frei, die das Bild laden.|
|D|Entfernbare|Markiert den Abschnitt als verworfen.|
|K|Zwischen speicherbar|Markiert den Abschnitt als nicht zwischen speicherbar.|
|P|Belegten Auslager baren|Markiert den Abschnitt als nicht zuladbar.|

K und P sind insofern ungewöhnlich, als die entsprechenden Abschnitts Flags im negativen Sinn verwendet werden. Wenn Sie eine dieser Werte im Textabschnitt mithilfe der Option **/section:. Text, K** angeben, gibt es keinen Unterschied in den Abschnitts Flags, wenn Sie [DUMPBIN](dumpbin-options.md) mit der Option [/Headers](headers.md) ausführen. der Abschnitt wurde bereits implizit zwischengespeichert. Um die Standardeinstellung zu entfernen, geben Sie **/section:. Text,! Stattdessen K** . DUMPBIN zeigt Abschnitts Merkmale an, einschließlich "nicht zwischengespeichert".

Ein Abschnitt in der PE-Datei, für den E, R oder W nicht festgelegt ist, ist wahrscheinlich ungültig.

Das **align =** _Number_ -Argument ermöglicht Ihnen das Angeben eines Ausrichtungs Werts für einen bestimmten Abschnitt. Das _Number_ -Argument ist in Bytes und muss eine Potenz von zwei sein. Weitere Informationen finden Sie unter [/align](align-section-alignment.md) .

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1.  > Wählen Sie die Eigenschaften Seite der Linkerbefehlszeile der **Konfigurations Eigenschaften** > .

1. Geben Sie die Option im Feld **zusätzliche Optionen** ein. Wählen Sie **OK** oder **anwenden** aus, um die Änderung zu übernehmen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
