---
title: / SECTION (Abschnittsattribute festlegen) | Microsoft Docs
ms.custom: 
ms.date: 12/29/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /section
dev_langs: C++
helpviewer_keywords:
- SECTION linker option
- -SECTION linker option
- section attributes
- /SECTION linker option
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aa214c7efeeee595300204df900a333258052772
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="section-specify-section-attributes"></a>/SECTION (Abschnittsattribute festlegen)

> **/ SECTION:**_Namen_, [[**!**] {**DEKPRSW**}] [**, ALIGN =**_Anzahl_]

## <a name="remarks"></a>Hinweise

Die **/SECTION** Option ändert die Attribute eines Abschnitts, überschreiben die Attribute festgelegt, wenn die OBJ-Datei für den Abschnitt kompiliert wurde.

Ein *Abschnitt* in eine portierbare ausführbare Datei (PE)-Datei ist ein benannter Codeblock zusammenhängender Arbeitsspeicher, Code oder Daten enthält. Einige Abschnitte enthalten Code- oder Datenmenge, die das Programm deklariert und direkt verwendet, während andere Datenabschnitte vom Linker und Bibliotheks-Manager (lib.exe) für Sie erstellt werden und wichtige Informationen für das Betriebssystem enthalten. Weitere Informationen finden Sie unter [PE Format](https://msdn.microsoft.com/library/windows/desktop/ms680547).

Geben Sie einen Doppelpunkt (:)) und einen Abschnitt *Namen*. Die *Namen* Groß-/Kleinschreibung beachtet.

Verwenden Sie die folgenden Namen nicht aus, wie sie mit der standardmäßigen Namen in Konflikt. Beispielsweise ist ".sdata" auf RISC-Plattformen verwendet werden:

- .Arch

- ".BSS"

- .Data

- .edata

- .iData

- .pdata-Datensatz

- .rdata

- .reloc

- .rsrc

- .sbss

- ".sdata"

- .srdata

- .Text erstellen

- .XData

Geben Sie eine oder mehrere Attribute für den Abschnitt. Die Attributzeichen, die unten aufgeführten sind nicht in der Groß-/Kleinschreibung beachtet. Sie müssen alle Attribute angeben, die den Abschnitt zugewiesen werden soll. Ein ausgelassenes Attributzeichen bewirkt, dass dieses Attribut Bits ausgeschaltet werden muss. Wenn Sie keinen R, W oder E, Lese-, Schreib- oder ausführbaren Status unverändert bleibt.

Stellen Sie das Zeichen mit einem Ausrufezeichen (!) voran, um ein Attribut zu negieren. Die Bedeutung der Attributzeichen sind in dieser Tabelle dargestellt:

|Zeichen|Attribut|Bedeutung|
|---------------|---------------|-------------|
|E|Ausführen|Der Abschnitt ist ausführbar|
|R|Lesen|Ermöglicht Lesevorgänge für Daten|
|W|Write|Ermöglicht Schreibvorgänge für Daten|
|S|Freigegeben|Teilt den Abschnitt für alle Prozesse, die das Image laden|
|D|Entfernbar|Markiert den Abschnitt als entfernbar|
|K|Übertragen von zwischenspeicherbaren|Markiert den Abschnitt als nicht zwischenspeicherbar|
|P|Auslagerbarer|Markiert den Abschnitt als nicht auslagerbar|

K und P sind ungewöhnlich, dass der Abschnitt-Flags, die sie entsprechen negative insofern verwendet werden. Wenn eine von ihnen im Abschnitt ".text" Sie über geben die **/Section:.Text, K** aus, es besteht kein Unterschied in den Abschnitt-Flags, beim Ausführen von [DUMPBIN](../../build/reference/dumpbin-options.md) mit der  [ /Headers](../../build/reference/headers.md)option. Der Abschnitt wurde bereits implizit im Cache gespeichert. Um die Standardeinstellung zu entfernen, geben Sie   **/Section:.Text,! K** stattdessen. DUMPBIN eingeblendet Abschnittsmerkmale, einschließlich "Nicht zwischengespeichert."

Ein Abschnitt in der PE-Datei, die keine E, R oder W festgelegt sind, ist wahrscheinlich ungültig.

Die **ALIGN =**_Anzahl_ Argument können Sie einen Ausrichtungswert für einen bestimmten Bereich angeben. Die _Anzahl_ Argument in Bytes und muss eine Potenz von zwei sein. Finden Sie unter [/AUSRICHTEN](../../build/reference/align-section-alignment.md) für Weitere Informationen.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die Option in der **Zusatzoptionen** Feld. Wählen Sie **OK** oder **übernehmen** um die Änderung zu übernehmen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)  
[Linkeroptionen](../../build/reference/linker-options.md)  
