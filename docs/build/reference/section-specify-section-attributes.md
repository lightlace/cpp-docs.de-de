---
title: -Abschnitt (Abschnittsattribute festlegen) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
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
ms.assetid: 92b69d81-e421-462e-b46f-7d0dff9b9d16
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e3fd7e844d77b9a92408c0708542a4f8f5edf304
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="section-specify-section-attributes"></a>/SECTION (Abschnittsattribute festlegen)
```  
/SECTION:name,[[!]{DEKPRSW}][,ALIGN=#]  
```  
  
## <a name="remarks"></a>Hinweise  
 Mit der Option/Section ändert die Attribute eines Abschnitts, überschreiben die Attribute festgelegt, wenn die OBJ-Datei für den Abschnitt kompiliert wurde.  
  
 Ein Abschnitt in eine portierbare ausführbare Datei (PE)-Datei ist weitgehend ein Segment oder die Ressourcen in einer neuen Datei der ausführbaren Datei (NE). Abschnitte enthalten Code- oder Datenmenge. Im Gegensatz zu Segmente sind Abschnitte Blöcke zusammenhängender Arbeitsspeicher ohne Einschränkungen Größe. Einige Abschnitte enthalten Code- oder Datenmenge, die das Programm deklariert und direkt verwendet, während andere Datenabschnitte vom Linker und Bibliotheks-Manager (lib.exe) für Sie erstellt werden und wichtige Informationen für das Betriebssystem enthalten. Weitere Informationen zu NE-Dateien finden Sie in der Knowledgebase-Artikel "Ausführbare Datei Header Format" (Q65122). Sie finden Knowledge Base-Artikel in der MSDN Library oder unter [http://support.microsoft.com](http://support.microsoft.com).  
  
 Geben Sie einen Doppelpunkt (:)) und einen Abschnitt *Namen*. Die *Namen* Groß-/Kleinschreibung beachtet.  
  
 Verwenden Sie die folgenden Namen nicht aus, wie sie mit der standardmäßigen Namen in Konflikt steht. Beispielsweise ist ".sdata" auf RISC-Plattformen verwendet werden:  
  
-   .Arch  
  
-   ".BSS"  
  
-   .Data  
  
-   .edata  
  
-   .iData  
  
-   .pdata-Datensatz  
  
-   .rdata  
  
-   .reloc  
  
-   .rsrc  
  
-   .sbss  
  
-   ".sdata"  
  
-   .srdata  
  
-   .Text erstellen  
  
-   .XData  
  
 Geben Sie eine oder mehrere Attribute für den Abschnitt. Die Attributzeichen, die unten aufgeführten sind nicht in der Groß-/Kleinschreibung beachtet. Sie müssen alle Attribute angeben, die den Abschnitt zugewiesen werden soll. Ein ausgelassenes Attributzeichen bewirkt, dass dieses Attribut Bits ausgeschaltet werden muss. Wenn Sie keinen R, W oder E, Lese-, Schreib- oder ausführbaren Status unverändert bleibt.  
  
 Stellen Sie das Zeichen mit einem Ausrufezeichen (!) voran, um ein Attribut zu negieren. Die Bedeutung der Attributzeichen werden unten gezeigt.  
  
|Zeichen|Attribut|Bedeutung|  
|---------------|---------------|-------------|  
|E|Ausführen|Der Abschnitt ist ausführbar|  
|R|Lesen|Ermöglicht Lesevorgänge für Daten|  
|W|Write|Ermöglicht Schreibvorgänge für Daten|  
|S|Freigegeben|Teilt den Abschnitt für alle Prozesse, die das Image laden|  
|D|Entfernbar|Markiert den Abschnitt als entfernbar|  
|K|Übertragen von zwischenspeicherbaren|Markiert den Abschnitt als nicht zwischenspeicherbar|  
|P|Auslagerbarer|Markiert den Abschnitt als nicht auslagerbar|  
  
 K und P sind spezielle, dass der Abschnitt-Flags, die Ihnen entsprechen insofern negativ sind. Bei Angabe eines davon in Abschnitt .text (/ SECTION: .text, K), wird kein Unterschied in den Abschnitt Flags, die beim Ausführen [DUMPBIN](../../build/reference/dumpbin-options.md) mit der [/Headers](../../build/reference/headers.md) option; er wurde bereits implizit zwischengespeichert. Um die Standardeinstellung zu entfernen, geben Sie/Section:.Text! K und DUMPBIN wird Abschnittsmerkmale, einschließlich "Nicht zwischengespeichert." angezeigt.  
  
 Ein Abschnitt in der PE-Datei, die keine E, R oder W festgelegt sind, ist wahrscheinlich ungültig.  
  
 AUSRICHTEN *=#*  können Sie einen Ausrichtungswert für einen bestimmten Bereich angeben. Finden Sie unter [/AUSRICHTEN](../../build/reference/align-section-alignment.md) für Weitere Informationen.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Option in der **Zusatzoptionen** Feld.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)