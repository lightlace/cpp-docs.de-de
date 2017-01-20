---
title: "/SECTION (Abschnittsattribute festlegen)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "/section"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SECTION (Linkeroption)"
  - "Abschnittsattribute"
  - "SECTION (Linkeroption)"
  - "-SECTION (Linkeroption)"
ms.assetid: 92b69d81-e421-462e-b46f-7d0dff9b9d16
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# /SECTION (Abschnittsattribute festlegen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SECTION:name,[[!]{DEKPRSW}][,ALIGN=#]  
```  
  
## Hinweise  
 Die \/SECTION\-Option ändert die Attribute eines Abschnitts, wobei die Attribute überschrieben werden, die festgelegt wurden, als die OBJ\-Datei für den Abschnitt kompiliert wurde.  
  
 Ein Abschnitt in einer portierbaren ausführbaren Datei \(PE\) entspricht ungefähr einem Segment oder den Ressourcen in einer nicht portierbaren ausführbaren Datei \(NE\).  Abschnitte enthalten entweder Code oder Daten.  Anders als Segmente setzen sich jedoch Abschnitte aus Blöcken fortlaufenden Speichers ohne Größenbeschränkungen zusammen.  Manche Abschnitte enthalten Code oder Daten, die Ihr Programm deklariert hat und direkt verwendet, während andere Datenabschnitte vom Linker und dem Bibliothek\-Manager \(**lib.exe**\) für Sie erstellt werden und wichtige Informationen für das Betriebssystem enthalten.  Weitere Informationen zu NE\-Dateien finden Sie im Knowledge Base\-Artikel "Executable\-File Header Format" \(Q65122\) \(nur auf Englisch verfügbar\).  Knowledge Base\-Artikel finden Sie in der MSDN Library oder an [http:\/\/support.microsoft.com](http://support.microsoft.com) suchen.  
  
 Geben Sie einen Doppelpunkt \(:\) und einen *Namen* für den Abschnitt an.  Beim *Namen* muss die Groß\-\/Kleinschreibung berücksichtigt werden.  
  
 Folgende Namen dürfen nicht verwendet werden, da dadurch Konflikte mit Standardbezeichnungen auftreten.  .sdata wird z. B. auf RISC\-Plattformen verwendet:  
  
-   .arch  
  
-   .bss  
  
-   .data  
  
-   .edata  
  
-   .idata  
  
-   .pdata  
  
-   .rdata  
  
-   .reloc  
  
-   .rsrc  
  
-   .sbss  
  
-   .sdata  
  
-   .srdata  
  
-   .text  
  
-   .xdata  
  
 Geben Sie für den Abschnitt ein oder mehrere Attribute an.  Bei den unten dargestellten Attributzeichen muss die Groß\-\/Kleinschreibung nicht beachtet werden.  Es müssen alle Attribute angeben werden, die dem Abschnitt zugewiesen werden sollen. Das Auslassen eines Attributzeichens kann dazu führen, dass das entsprechende Attribut\-Bit deaktiviert wird.  Wenn Sie weder **R**, **W** noch **E** angeben, bleibt der eingerichtete Lese\-, Schreib\- oder Ausführbarkeitsstatus unverändert.  
  
 Um ein Attribut zu negieren, setzen Sie vor das Zeichen ein Ausrufezeichen \(\!\).  Die Bedeutungen der Attributzeichen werden unten beschrieben.  
  
|Zeichen|Attribute|Bedeutung|  
|-------------|---------------|---------------|  
|E|Ausführen|Der betreffende Abschnitt ist ausführbar|  
|R|Read|Ermöglicht Lesevorgänge für Daten|  
|W|Write|Ermöglicht Schreibvorgänge für Daten|  
|S|Shared|Gibt den Abschnitt für alle Prozesse frei, die das Abbild laden|  
|D|Discardable \(Entfernbar\)|Kennzeichnet einen Abschnitt, der entfernt werden kann|  
|K|Cacheable \(Zwischenspeicherbar\)|Markiert einen Abschnitt, der nicht zwischengespeichert werden kann|  
|P|Pageable \(Auslagerbar\)|Markiert einen Abschnitt, der ausgelagert werden kann|  
  
 **K** und **P** unterscheiden sich insofern von den anderen Attributen, als die Abschnittsflags jeweils im negativen Sinn erfolgen.  Wenn Sie eines dieser Attribute im Abschnitt **.text** \(**\/SECTION:.text,K**\) angeben, werden bei Ausführung von [DUMPBIN](../../build/reference/dumpbin-options.md) mit der Option [\/HEADERS](../../build/reference/headers.md) bezüglich der Abschnittsmarkierungen keine Unterschiede auftreten, denn der Abschnitt wurde bereits implizit im Zwischenspeicher abgelegt.  Um die Standardeinstellung zu entfernen, geben Sie **\/SECTION:.text,\!K** an, woraufhin das **DUMPBIN** die Abschnittsmerkmale einschließlich "Not Cached." anzeigt.  
  
 Ein Abschnitt der PE\-Datei ohne **E**, **R** oder **W** ist wahrscheinlich ungültig.  
  
 Mit **ALIGN\=\#** können Sie einen Ausrichtungswert für einen bestimmten Abschnitt festlegen.  Weitere Informationen finden Sie unter [\/ALIGN \(Abschnittsausrichtung\)](../../build/reference/align-section-alignment.md).  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Option im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)