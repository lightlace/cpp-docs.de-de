---
title: "Exemplarische Vorgehensweise: Erstellen eines Bildverarbeitungsnetzwerks"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Erstellen von Bildverarbeitungsnetzwerken [Concurrency Runtime]"
  - "Bildverarbeitungsnetzwerke, Erstellen [Concurrency Runtime]"
ms.assetid: 78ccadc9-5ce2-46cc-bd62-ce0f99d356b8
caps.latest.revision: 15
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Erstellen eines Bildverarbeitungsnetzwerks
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Dokument wird das Erstellen eines Netzwerks asynchroner Nachrichtenblöcke für die Bildverarbeitung veranschaulicht.  
  
 Das Netzwerk bestimmt anhand der Eigenschaften, welche Vorgänge für ein Bild ausgeführt werden.  In diesem Beispiel wird das *Datenfluss*modell verwendet, um Bilder durch das Netzwerk zu leiten.  Im Datenflussmodell kommunizieren unabhängige Komponenten eines Programms durch den Austausch von Nachrichten.  Wenn eine Komponente eine Nachricht empfängt, kann sie eine Aktion ausführen und das Ergebnis an eine andere Komponente übergeben.  Vergleichen Sie dies mit dem *Ablaufsteuerung*smodell, in dem die Reihenfolge der Vorgänge in einem Programm von der Anwendung mithilfe von Steuerungsstrukturen wie Bedingungsanweisungen oder Schleifen kontrolliert wird.  
  
 In einem Netzwerk, das auf Datenfluss basiert, wird eine *Pipeline* von Aufgaben erstellt.  Die Teile der Gesamtaufgabe werden in den einzelnen Pipelinephasen nebenläufig ausgeführt.  Diese Vorgehensweise ist vergleichbar mit einem Fließband in der Automobilfertigung.  Jedes Fahrzeug durchläuft eine Reihe von Arbeitsstationen, an einer wird die Karosserie zusammengebaut, an einer anderen der Motor eingesetzt usw.  Wenn mehrere Fahrzeuge gleichzeitig zusammengebaut werden können, ist die Produktivität des Fließbands höher, als wenn nur jeweils ein Fahrzeug fertig gestellt werden kann.  
  
## Vorbereitungsmaßnahmen  
 Lesen Sie die folgenden Dokumente, bevor Sie mit dieser exemplarischen Vorgehensweise beginnen:  
  
-   [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [Gewusst wie: Verwenden eines Nachrichtenblockfilters](../../parallel/concrt/how-to-use-a-message-block-filter.md)  
  
-   [Exemplarische Vorgehensweise: Erstellen eines Datenfluss\-Agent](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)  
  
 Es wird außerdem empfohlen, sich vor der Verwendung dieser exemplarischen Vorgehensweise ggf. mit den Grundlagen von [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] vertraut zu machen.  Weitere Informationen zu [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] finden Sie unter [GDI\+](_gdiplus_GDI_start_cpp).  
  
##  <a name="top"></a> Abschnitte  
 Diese exemplarische Vorgehensweise enthält folgende Abschnitte:  
  
-   [Definieren der Bildverarbeitungsfunktionen](#functionality)  
  
-   [Erstellen des Bildverarbeitungsnetzwerks](#network)  
  
-   [Vollständiges Beispiel](#complete)  
  
##  <a name="functionality"></a> Definieren der Bildverarbeitungsfunktionen  
 In diesem Abschnitt werden die Unterstützungsfunktionen veranschaulicht, die vom Bildverarbeitungsnetzwerk zur Verarbeitung von Bildern von einem Datenträger verwendet werden.  
  
 Mit der `GetRGB`\-Funktion und der `MakeColor`\-Funktion werden die einzelnen Anteile der angegebenen Farbe extrahiert bzw. kombiniert.  
  
 [!CODE [concrt-image-processing-filter#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-image-processing-filter#2)]  
  
 Mit der `ProcessImage`\-Funktion wird das angegebene [std::function](../../standard-library/function-class.md)\-Objekt aufgerufen, um den Farbwert jedes Pixels in einem [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] [Bitmap](https://msdn.microsoft.com/en-us/library/ms534420.aspx)\-Objekt umzuwandeln.  Die Funktion `ProcessImage` verwendet den [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) Algorithmus, um die einzelnen Zeilen des Bitmaps mit zu verarbeiten.  
  
 [!CODE [concrt-image-processing-filter#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-image-processing-filter#3)]  
  
 Mit den Funktionen `Grayscale`, `Sepiatone`, `ColorMask` und `Darken` wird die `ProcessImage`\-Funktion aufgerufen, um den Farbwert jedes Pixels in ein `Bitmap`\-Objekt umzuwandeln.  Jede dieser Funktionen verwendet einen Lambda\-Ausdruck zum Definieren der Farbtransformation eines Pixels.  
  
 [!CODE [concrt-image-processing-filter#4](../CodeSnippet/VS_Snippets_ConcRT/concrt-image-processing-filter#4)]  
  
 Die `ProcessImage`\-Funktion wird ebenfalls von der `GetColorDominance`\-Funktion aufgerufen.  Anstatt jedoch, den Wert der einzelnen Farben zu ändern, berechnet diese Funktion [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md), um Objekte zu rechnen, ob der roten, grünen oder blauen Farbanteil dominiert das Bild.  
  
 [!CODE [concrt-image-processing-filter#5](../CodeSnippet/VS_Snippets_ConcRT/concrt-image-processing-filter#5)]  
  
 Mit der `GetEncoderClsid`\-Funktion wird der Klassenbezeichner für den angegebenen MIME\-Typ eines Encoders abgerufen.  Diese Funktion wird von der Anwendung verwendet, um den Encoder für ein Bitmap abzurufen.  
  
 [!CODE [concrt-image-processing-filter#6](../CodeSnippet/VS_Snippets_ConcRT/concrt-image-processing-filter#6)]  
  
 \[[Nach oben](#top)\]  
  
##  <a name="network"></a> Erstellen des Bildverarbeitungsnetzwerks  
 In diesem Abschnitt wird beschrieben, wie ein Netzwerk von asynchronen Nachrichtenblöcken für die Verarbeitung aller Bilder vom Typ [!INCLUDE[TLA#tla_jpeg](../../parallel/concrt/includes/tlasharptla_jpeg_md.md)] \(JPG\) in einem bestimmten Verzeichnis erstellt wird.  Folgende Bildverarbeitungsvorgänge werden im Netzwerk ausgeführt:  
  
1.  Jedes Bild, das von Tom erstellt wurde, wird in Graustufen konvertiert.  
  
2.  In jedem Bild, in dem die Farbe Rot dominiert, werden die grünen und blauen Farbanteile entfernt, und das Bild wird dunkler gemacht.  
  
3.  Auf alle anderen Bilder wird eine Sepiatönung angewendet.  
  
 Nur der erste Bildverarbeitungsvorgang, der einer dieser Bedingungen entspricht, wird vom Netzwerk ausgeführt.  Ein Bild, das von Tom erstellt wurde und in dem die Farbe Rot dominiert, wird beispielsweise nur in Graustufen konvertiert.  
  
 Nachdem die einzelnen Bildverarbeitungsvorgänge vom Netzwerk ausgeführt wurden, werden die Bilder als Bitmap\-Dateien \(.bmp\) auf dem Datenträger gespeichert.  
  
 In den folgenden Schritten wird veranschaulicht, wie eine Funktion zur Implementierung dieses Bildverarbeitungsnetzwerks erstellt und das Netzwerk auf alle Bilder vom Typ [!INCLUDE[TLA#tla_jpeg](../../parallel/concrt/includes/tlasharptla_jpeg_md.md)] in einem angegebenen Verzeichnis angewendet werden kann.  
  
#### So erstellen Sie das Bildverarbeitungsnetzwerk  
  
1.  Erstellen Sie die `ProcessImages`\-Funktion, die den Namen eines Verzeichnisses auf dem Datenträger übernimmt.  
  
     [!CODE [concrt-image-processing-filter#7](../CodeSnippet/VS_Snippets_ConcRT/concrt-image-processing-filter#7)]  
  
2.  Erstellen Sie in der in der `ProcessImages`\-Funktion eine `countdown_event`\-Variable.  Die `countdown_event`\-Klasse wird später in dieser exemplarischen Vorgehensweise beschrieben.  
  
     [!CODE [concrt-image-processing-filter#8](../CodeSnippet/VS_Snippets_ConcRT/concrt-image-processing-filter#8)]  
  
3.  Erstellen Sie ein [std::map](../../standard-library/map-class.md)\-Objekt, um ein `Bitmap`\-Objekt mit dem ursprünglichen Dateinamen zu verknüpfen.  
  
     [!CODE [concrt-image-processing-filter#9](../CodeSnippet/VS_Snippets_ConcRT/concrt-image-processing-filter#9)]  
  
4.  Fügen Sie den folgenden Code hinzu, um die Member des Bildverarbeitungsnetzwerks zu definieren.  
  
     [!CODE [concrt-image-processing-filter#10](../CodeSnippet/VS_Snippets_ConcRT/concrt-image-processing-filter#10)]  
  
5.  Fügen Sie den folgenden Code hinzu, um eine Verbindung zum Netzwerk herzustellen.  
  
     [!CODE [concrt-image-processing-filter#11](../CodeSnippet/VS_Snippets_ConcRT/concrt-image-processing-filter#11)]  
  
6.  Fügen Sie den folgenden Code hinzu, um den vollständigen Pfad jeder [!INCLUDE[TLA#tla_jpeg](../../parallel/concrt/includes/tlasharptla_jpeg_md.md)]\-Datei im Verzeichnis ab den Anfang des Netzwerks zu senden.  
  
     [!CODE [concrt-image-processing-filter#12](../CodeSnippet/VS_Snippets_ConcRT/concrt-image-processing-filter#12)]  
  
7.  Warten Sie, bis die Variable `countdown_event` den Wert 0 \(null\) erreicht hat.  
  
     [!CODE [concrt-image-processing-filter#13](../CodeSnippet/VS_Snippets_ConcRT/concrt-image-processing-filter#13)]  
  
 In der folgenden Tabelle werden die Member des Netzwerks beschrieben.  
  
|Member|**Beschreibung**|  
|------------|----------------------|  
|`load_bitmap`|Ein [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md)\-Objekt, das ein `Bitmap`\-Objekt vom Datenträger geladen und einem Eintrag dem `map`\-Objekt hinzufügt, um das Bild mit dem ursprünglichen Dateinamen zu verknüpfen.|  
|`loaded_bitmaps`|Ein [concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md), Objekt werden die geladenen Bilder an die Bildverarbeitungsfilter gesendet.|  
|`grayscale`|Mit einem `transformer`\-Objekt werden die Bilder, die von Tom erstellt wurden, in Graustufen konvertiert werden.  Der Autor des Bildes wird anhand der zugehörigen Metadaten ermittelt.|  
|`colormask`|Mit einem `transformer`\-Objekt werden die grünen und blauen Farbanteile auf Bildern entfernt, in denen die Farbe Rot dominiert.|  
|`darken`|Mit einem `transformer`\-Objekt werden die Bilder dunkler gemacht, in denen die Farbe Rot dominiert.|  
|`sepiatone`|Mit einem `transformer`\-Objekt wird eine Sepiatönung auf alle Bilder angewendet, die nicht von Tom erstellt wurden und in denen Rot nicht die dominierende Farbe ist.|  
|`save_bitmap`|Mit einem `transformer`\-Objekt wird das verarbeitete `image` als Bitmap auf einem Datenträger gespeichert.  Mit `save_bitmap` wird der ursprüngliche Dateiname vom `map`\-Objekt abgerufen, und die Dateinamenerweiterung wird in BMP geändert.|  
|`delete_bitmap`|Mit einem `transformer`\-Objekt wird der Speicher für die Bilder freigegeben.|  
|`decrement`|Ein [concurrency::call](../../parallel/concrt/reference/call-class.md), Objekt als Terminalknoten im Netzwerk auftritt.  Es verringert den Wert des `countdown_event`\-Objekts, um gegenüber der Hauptanwendung anzugeben, dass ein Bild verarbeitet wurde.|  
  
 Der Nachrichtenpuffer `loaded_bitmaps` ist wichtig, da er als `unbounded_buffer`\-Objekt `Bitmap`\-Objekte für mehrere Empfänger bereitstellt.  Wenn ein `Bitmap`\-Objekt einen Zielblock akzeptiert, wird das `Bitmap`\-Objekt vom `unbounded_buffer`\-Objekt nicht mehr für andere Ziele bereitgestellt.  Aus diesem Grund ist die Reihenfolge, in der die Objekte mit einem `unbounded_buffer`\-Objekt verknüpft werden, von Bedeutung.  Die Nachrichtenblöcke `grayscale`, `colormask` und `sepiatone` verwenden jeweils einen Filter, um nur bestimmte `Bitmap`\-Objekte zu akzeptieren.  Der Meldungspuffer `decrement` ist ein wichtiges Ziel des Nachrichtenpuffers `loaded_bitmaps`, da er alle `Bitmap`\-Objekte akzeptiert, die von den anderen Nachrichtenpuffer abgelehnt wurden.  Ein `unbounded_buffer`\-Objekt ist erforderlich, um Nachrichten der Reihenfolge nach zu verteilen.  Ein `unbounded_buffer`\-Objekt wird daher blockiert, bis ein neuer Zielblock damit verknüpft wird und die Nachricht akzeptiert, wenn diese nicht von einem aktuellen Zielblock akzeptiert wird.  
  
 Wenn die Nachricht in Ihrer Anwendung von mehreren Nachrichtenblöcken verarbeitet werden muss und nicht nur von dem Block, der sie zuerst akzeptiert hat, können Sie einen anderen Nachrichtenblocktyp wie `overwrite_buffer` verwenden.  Die `overwrite_buffer`\-Klasse enthält jeweils nur eine Nachricht, gibt diese jedoch an alle entsprechenden Ziele weiter.  
  
 In der folgenden Abbildung wird das Bildverarbeitungsnetzwerk veranschaulicht:  
  
 ![Bildverarbeitungsnetzwerk](../../parallel/concrt/media/concrt_imageproc.png "ConcRT\_ImageProc")  
  
 Das `countdown_event`\-Objekt in diesem Beispiel ermöglicht dem Bildverarbeitungsnetzwerk, die Hauptanwendung darüber zu informieren, dass alle Bilder verarbeitet wurden.  Die `countdown_event`\-Klasse ein Objekt verwendet [concurrency::event](../../parallel/concrt/reference/event-class.md), um zu signalisieren, wenn der Zähler den Wert erreicht.  Jedes Mal, wenn ein Dateiname an das Netzwerk gesendet wird, wird der Zähler von der Hauptanwendung inkrementiert.  Nachdem das Bild verarbeitet wurde, wird der Zähler vom Terminalknoten des Netzwerks dekrementiert.  Sobald das angegebene Verzeichnis von der Hauptanwendung durchlaufen wurde, wartet diese auf ein Signal des `countdown_event`\-Objekt, dass der Zähler den Wert 0 \(null\) erreicht hat.  
  
 Im folgenden Beispiel ist die `countdown_event`\-Klasse dargestellt:  
  
 [!CODE [concrt-image-processing-filter#14](../CodeSnippet/VS_Snippets_ConcRT/concrt-image-processing-filter#14)]  
  
 \[[Nach oben](#top)\]  
  
##  <a name="complete"></a> Vollständiges Beispiel  
 Der folgende Code veranschaulicht das vollständige Beispiel.  Die `wmain`\-Funktion verwaltet die [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)]\-Bibliothek und ruft die `ProcessImages`\-Funktion auf, um die [!INCLUDE[TLA#tla_jpeg](../../parallel/concrt/includes/tlasharptla_jpeg_md.md)]\-Dateien im Verzeichnis `Beispielbilder` zu verarbeiten.  
  
 [!CODE [concrt-image-processing-filter#15](../CodeSnippet/VS_Snippets_ConcRT/concrt-image-processing-filter#15)]  
  
 In der folgenden Abbildung wird eine Beispielausgabe veranschaulicht.  Jedes Quellbild befindet sich über dem entsprechenden geänderten Bild.  
  
 ![Beispielausgabe](../../parallel/concrt/media/concrt_imageout.png "ConcRT\_ImageOut")  
  
 `Lighthouse` wurde von Tom Alphin erstellt und wird daher in Graustufen konvertiert.  Bei `Chrysanthemum`, `Desert`, `Koala` und `Tulips` dominiert die Farbe Rot. Daher werden die blauen und grünen Farbanteile entfernt, und die Bilder werden dunkler gemacht.  Die Bilder `Hydrangeas`, `Jellyfish` und `Penguins` entsprechen den Standardkriterien und werden daher mit einer Sepiatönung versehen.  
  
 \[[Nach oben](#top)\]  
  
### Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio\-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `image-processing-network.cpp` ein, und dann folgenden Befehl in einem Visual Studio\-Eingabeaufforderung ausgeführt.  
  
 **cl.exe \/DUNICODE \/EHsc image\-processing\-network.cpp \/link gdiplus.lib**  
  
## Siehe auch  
 [Exemplarische Vorgehensweisen für die Concurrency Runtime](../../parallel/concrt/concurrency-runtime-walkthroughs.md)