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
ms.openlocfilehash: 8fb73043c9c185adee0859bb81098eab022430c2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318562"
---
# <a name="section-specify-section-attributes"></a>/SECTION (Abschnittsattribute festlegen)

> **/ SECTION:**_Namen_, [[**!**] {**DEKPRSW**}] [**, ALIGN =**_Anzahl_]

## <a name="remarks"></a>Hinweise

Die **/SECTION** Option ändert die Attribute eines Abschnitts, überschreiben die Attribute festgelegt, wenn die OBJ-Datei für den Abschnitt kompiliert wurde.

Ein *Abschnitt* in eine portierbare ausführbare Datei (PE)-Datei ist eine benannte, zusammenhängenden Speicherblock, der entweder Code oder Daten enthält. Einige Abschnitte enthalten Code oder Daten, die Ihr Programm deklariert und direkt verwendet, während andere Datenabschnitte für Sie, die vom Linker und bibliotheksverwaltung (lib.exe erstellt werden) und wichtige Informationen für das Betriebssystem enthalten. Weitere Informationen finden Sie unter [PE-Format](/windows/desktop/Debug/pe-format).

Geben Sie einen Doppelpunkt (:)) und einen Abschnitt *Namen*. Die *Namen* Groß-/Kleinschreibung beachtet.

Verwenden Sie die folgenden Namen nicht aus, wie sie mit standard-Namen in Konflikt. Beispielsweise wird .sdata auf RISC-Plattformen verwendet werden:

- .Arch

- ".BSS"

- ".Data"

- .edata

- .idata

- .pdata

- .rdata

- .reloc

- rsrc

- .sbss

- .sdata

- .srdata

- .text

- .xdata

Geben Sie einen oder mehrere Attribute für den Abschnitt. Die Attributzeichen, die unten aufgeführten sind nicht in der Groß-/Kleinschreibung beachtet. Sie müssen alle Attribute angeben, die den Abschnitt zugewiesen werden soll. ein Attributzeichen für die ausgelassenen bewirkt, dass dieses Attribut Bit deaktiviert ist. Wenn Sie nicht, dass R, W oder E, Lese-, Schreib-angeben oder ausführbaren Status unverändert bleibt.

Um ein Attribut zu negieren, stehen Sie das Zeichen mit einem Ausrufezeichen (!). Die Bedeutung der Attribut-Zeichen sind in dieser Tabelle dargestellt:

|Zeichen|Attribut|Bedeutung|
|---------------|---------------|-------------|
|E|Ausführen|Der Abschnitt ist ausführbar.|
|R|Lesen|Ermöglicht Lesevorgänge für Daten|
|W|Write|Ermöglicht Schreibvorgänge für Daten|
|S|Shared|Teilt den Abschnitt für alle Prozesse, die das Bild zu laden|
|D|Entfernbare|Markiert den Abschnitt als entfernbar|
|K|Zwischengespeichert werden können|Markiert den Abschnitt als nicht zwischenspeicherbar|
|P|Auslagerbarer|Markiert den Abschnitt als nicht auslagerbar|

K "und" P sind ungewöhnlich, dass die Abschnitt-Flags, die sie entsprechen, im negativen Sinn verwendet werden. Wenn eines der im Abschnitt ".text" Sie über geben die **/Section:.Text, K** option, gibt es keinen Unterschied in den Abschnitt Flags beim Ausführen von [DUMPBIN](dumpbin-options.md) mit der  [ /Headers](headers.md)-Option Der Abschnitt wurde bereits implizit zwischengespeichert. Um die Standardeinstellung zu entfernen, geben   **/Section:.Text,! K** stattdessen. DUMPBIN zeigt Abschnittsmerkmale, einschließlich "Nicht zwischengespeichert."

Ein Abschnitt in der PE-Datei, die nicht E, R oder W ist wahrscheinlich ungültig.

Die **ALIGN =**_Anzahl_ Argument können Sie angeben, einen Ausrichtungswert für einen bestimmten Abschnitt. Die _Anzahl_ Argument in Bytes und muss eine Potenz von zwei sein. Finden Sie unter [/ALIGN](align-section-alignment.md) für Weitere Informationen.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die Option in der **zusätzliche Optionen** Feld. Wählen Sie **OK** oder **übernehmen** um die Änderung zu übernehmen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
