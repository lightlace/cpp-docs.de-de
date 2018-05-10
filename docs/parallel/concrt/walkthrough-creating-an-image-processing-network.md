---
title: 'Exemplarische Vorgehensweise: Erstellen einer Bildverarbeitungsnetzwerks | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- image-processing networks, creating [Concurrency Runtime]
- creating image-processing networks [Concurrency Runtime]
ms.assetid: 78ccadc9-5ce2-46cc-bd62-ce0f99d356b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e66de10879596b0e0877eb70f5ac95e082b8ae31
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="walkthrough-creating-an-image-processing-network"></a>Exemplarische Vorgehensweise: Erstellen eines Bildverarbeitungsnetzwerks
Dieses Dokument veranschaulicht, wie zum Erstellen eines Netzwerks asynchroner Nachrichtenblöcke die bildverarbeitung.  
  
 Das Netzwerk bestimmt, welche Vorgänge für die auf einem Bild auf der Basis seiner Eigenschaften. Dieses Beispiel verwendet die *Datenfluss* Modell Route Images über das Netzwerk. Im Datenflussmodell kommunizieren unabhängige Komponenten eines Programms durch Senden von Nachrichten miteinander. Wenn eine Komponente eine Nachricht empfängt, kann er eine Aktion ausführt, und klicken Sie dann das Ergebnis dieser Aktion an eine andere Komponente übergeben. Vergleichen Sie dies mit der *ablaufsteuerung* Modell, in dem eine Anwendung verwendet Steuerungsstrukturen, z. B., bedingungsanweisungen, Schleifen und So weiter, um die Reihenfolge der Vorgänge in einem Programm zu steuern.  
  
 Erstellt ein Netzwerk, das auf Datenfluss basiert eine *Pipeline* Aufgaben. Jede Phase der Pipeline führt gleichzeitig Teil des gesamten Tasks. Eine Analogie hierzu ist eine Fertigungsstraße eines Fahrzeugherstellers. Jedes Fahrzeug durchläuft die Fertigungsstraße einer Station assembliert den Frame, ein anderes Modul usw. installiert. Aktivieren Sie mehrere Fahrzeuge gleichzeitig montiert werden, enthält die Fertigungsstraße besseren Durchsatz als eine eines vollständigen Fahrzeugs zu einem Zeitpunkt zusammenstellen.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Lesen Sie die folgenden Dokumente, bevor Sie mit dieser exemplarischen Vorgehensweise beginnen:  
  
-   [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [Vorgehensweise: Verwenden eines Nachrichtenblockfilters](../../parallel/concrt/how-to-use-a-message-block-filter.md)  
  
-   [Exemplarische Vorgehensweise: Erstellen eines Datenfluss-Agent](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)  
  
 Zudem wird empfohlen, dass Sie wissen, dass die Grundlagen der [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] , bevor Sie diese exemplarische Vorgehensweise starten.  
  
##  <a name="top"></a> Abschnitte  
 Diese exemplarische Vorgehensweise enthält folgende Abschnitte:  
  
-   [Definieren der Funktionen für die Bildverarbeitung](#functionality)  
  
-   [Bildverarbeitungsnetzwerk erstellen](#network)  
  
-   [Vollständiges Beispiel](#complete)  
  
##  <a name="functionality"></a> Definieren der Funktionen für die Bildverarbeitung  
 In diesem Abschnitt wird gezeigt, die Supportfunktionen, die Bildverarbeitungsnetzwerk verwendet wird, zum Arbeiten mit Bildern, die vom Datenträger gelesen werden.  
  
 Die folgenden Funktionen `GetRGB` und `MakeColor`, extrahieren und kombinieren Sie jeweils die einzelnen Komponenten der angegebenen Farbe.  
  
 [!code-cpp[concrt-image-processing-filter#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_1.cpp)]  
  

 Die folgende Funktion `ProcessImage`, ruft die angegebene [Std:: Function](../../standard-library/function-class.md) Objekt, das den Farbwert jedes Pixels in transformiert eine [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] [Bitmap](https://msdn.microsoft.com/library/ms534420.aspx) Objekt. Die `ProcessImage` Funktion verwendet die [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) Algorithmus, um jede Zeile der Bitmap in parallelen verarbeiten.  

  
 [!code-cpp[concrt-image-processing-filter#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_2.cpp)]  
  
 Die folgenden Funktionen `Grayscale`, `Sepiatone`, `ColorMask`, und `Darken`, rufen Sie die `ProcessImage` Funktion zum Transformieren des Farbwert jedes Pixels in ein `Bitmap` Objekt. Jede dieser Funktionen verwendet einen Lambda-Ausdruck, um die Farbe Transformation von einem Pixel zu definieren.  
  
 [!code-cpp[concrt-image-processing-filter#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_3.cpp)]  
  
 Die folgende Funktion `GetColorDominance`, ruft auch die `ProcessImage` Funktion. Statt den Wert jeder Farbe ändern, verwendet diese Funktion jedoch [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) Objekte an, ob die Rot, Grün oder Blau-Komponente das Bild dominiert zu berechnen.  
  
 [!code-cpp[concrt-image-processing-filter#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_4.cpp)]  
  
 Die folgende Funktion `GetEncoderClsid`, ruft die Klassen-ID für den angegebenen MIME-Typ eines Encoders ab. Die Anwendung verwendet diese Funktion zum Abrufen des Encoders für eine Bitmap.  
  
 [!code-cpp[concrt-image-processing-filter#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_5.cpp)]  
  
 [[Nach oben](#top)]  
  
##  <a name="network"></a> Bildverarbeitungsnetzwerk erstellen  
 In diesem Abschnitt wird beschrieben, wie zum Erstellen eines Netzwerks asynchroner Nachrichtenblöcke die bildverarbeitung auf jede [!INCLUDE[TLA#tla_jpeg](../../parallel/concrt/includes/tlasharptla_jpeg_md.md)] (JPG) in einem angegebenen Verzeichnis. Das Netzwerk führt die folgenden bildverarbeitungs-Vorgänge:  
  
1.  Konvertieren Sie für jedes Bild, das von Tom erstellt wurde in Graustufen.  
  
2.  Entfernen Sie für jedes Bild, das die Farbe Rot dominiert hat die Komponenten grünen und blauen und dunkler Sie es.  
  
3.  Wenden Sie für eine beliebige andere Bild Sepia Ton aus.  
  
 Das Netzwerk gilt nur den ersten bildverarbeitungs-Vorgang, der eine der folgenden Bedingungen entspricht. Wenn ein Bild von Tom erstellt und die Farbe Rot dominiert, wird das Bild beispielsweise nur in Graustufen konvertiert.  
  
 Nachdem das Netzwerk jeden bildverarbeitungs-Vorgang ausführt, speichert das Bild auf dem Datenträger als Bitmap (BMP)-Datei.  
  
 Die folgenden Schritte zeigen, wie eine Funktion erstellen, die diese Bildverarbeitungsnetzwerk implementiert und das Netzwerk gilt allen [!INCLUDE[TLA#tla_jpeg](../../parallel/concrt/includes/tlasharptla_jpeg_md.md)] Bild in einem angegebenen Verzeichnis.  
  
#### <a name="to-create-the-image-processing-network"></a>So erstellen das Bildverarbeitungsnetzwerk  
  
1.  Erstellen Sie eine Funktion `ProcessImages`, die den Namen eines Verzeichnisses auf dem Datenträger belegt.  
  
     [!code-cpp[concrt-image-processing-filter#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_6.cpp)]  
  
2.  In der `ProcessImages` funktionieren, erstellen Sie eine `countdown_event` Variable. Die `countdown_event` ist weiter unten in dieser exemplarischen Vorgehensweise dargestellt.  
  
     [!code-cpp[concrt-image-processing-filter#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_7.cpp)]  
  
3.  Erstellen einer [Std:: Map](../../standard-library/map-class.md) -Objekt, das ordnet eine `Bitmap` Objekt mit dem ursprünglichen Dateinamen.  
  
     [!code-cpp[concrt-image-processing-filter#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_8.cpp)]  
  
4.  Fügen Sie den folgenden Code aus, um die Mitglieder der Bildverarbeitungsnetzwerks zu definieren.  
  
     [!code-cpp[concrt-image-processing-filter#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_9.cpp)]  
  
5.  Fügen Sie den folgenden Code aus, um das Netzwerk zu verbinden.  
  
     [!code-cpp[concrt-image-processing-filter#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_10.cpp)]  
  
6.  Fügen Sie den folgenden Code zum Senden an den Anfang des Netzwerks des vollständigen Pfads der einzelnen [!INCLUDE[TLA#tla_jpeg](../../parallel/concrt/includes/tlasharptla_jpeg_md.md)] Datei im Verzeichnis.  
  
     [!code-cpp[concrt-image-processing-filter#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_11.cpp)]  
  
7.  Warten Sie, den `countdown_event` Variablen auf 0 (null) erreicht.  
  
     [!code-cpp[concrt-image-processing-filter#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_12.cpp)]  
  
 In der folgenden Tabelle werden die Member des Netzwerks beschrieben.  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`load_bitmap`|Ein [Concurrency:: transformer](../../parallel/concrt/reference/transformer-class.md) -Objekt, das lädt eine `Bitmap` vom Datenträger-Objekt und fügt einen Eintrag in einen der `map` -Objekt, das Bild mit dem ursprünglichen Dateinamen zuzuordnen.|  
|`loaded_bitmaps`|Ein [Concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) -Objekt, das die geladenen Bilder an das Image paketverarbeitungsfiltern sendet.|  
|`grayscale`|Ein `transformer` -Objekt, das Bilder konvertiert, die von Tom in Graustufen erstellt werden. Die Metadaten des Images verwendet, um Autor zu bestimmen.|  
|`colormask`|Ein `transformer` -Objekt, das die grünen und blauen Farbkomponenten aus Images entfernt werden, die die Farbe Rot dominiert haben.|  
|`darken`|Ein `transformer` -Objekt, das Bilder dunkler, die die Farbe Rot dominiert aufweisen.|  
|`sepiatone`|Ein `transformer` -Objekt, das betrifft Sepia Ton Bilder, die nicht von Tom erstellt werden und sind nicht vorwiegend Rot.|  
|`save_bitmap`|Ein `transformer` Objekt, das die verarbeiteten speichert `image` auf den Datenträger als Bitmap. `save_bitmap` Ruft den ursprünglichen Dateinamen aus der `map` -Objekt an und ändert die Dateinamenerweiterung, BMP.|  
|`delete_bitmap`|Ein `transformer` -Objekt, das den Speicher für die Bilder freigegeben.|  
|`decrement`|Ein [Call](../../parallel/concrt/reference/call-class.md) -Objekt, das als Terminalknoten im Netzwerk fungiert. Es verringert den `countdown_event` Objekt, das die Hauptassembly der Anwendung zu signalisieren, dass ein Bild verarbeitet wurde.|  
  
 Die `loaded_bitmaps` Nachrichtenpuffer ist wichtig, daran, dass als ein `unbounded_buffer` -Objekt, er bietet `Bitmap` Objekte an mehrere Empfänger. Bei ein Zielblock akzeptiert eine `Bitmap` -Objekt, das `unbounded_buffer` Objekt nicht anbieten, `Bitmap` Objekt, das keine anderen Ziele. Deshalb die Reihenfolge, in dem Sie verknüpfen, Datenbankobjekte in einem `unbounded_buffer` Objekt ist wichtig. Die `grayscale`, `colormask`, und `sepiatone` Nachricht Blöcke jedes mithilfe eines Filters akzeptieren nur ein bestimmter `Bitmap` Objekte. Die `decrement` Nachrichtenpuffer ist ein wichtiges Ziel von den `loaded_bitmaps` Nachrichtenpuffer, da er alle akzeptiert `Bitmap` Objekte, die von anderen Nachrichtenpuffer abgelehnt werden. Ein `unbounded_buffer` Objekt ist erforderlich, um die Weitergabe von Nachrichten in der Reihenfolge. Aus diesem Grund eine `unbounded_buffer` Objekt blockiert, bis ein neuer Zielblock wird verknüpft und die Nachricht annimmt, wenn keine aktuelle Zielblock die Nachricht akzeptiert.  
  
 Wenn Ihre Anwendung erfordert von mehreren Nachrichtenblöcken Verarbeiten der Nachricht, statt nur die ein Nachrichtenblock, der die Nachricht zuerst akzeptiert können Sie einen anderen Nachrichtenblocktyp, z. B. `overwrite_buffer`. Die `overwrite_buffer` Klasse enthält eine Nachricht gleichzeitig, aber sie auf die einzelnen Ziele die Nachricht zurückgibt.  
  
 Die folgende Abbildung zeigt die Bildverarbeitungsnetzwerk:  
  
 ![Bildverarbeitungsnetzwerk](../../parallel/concrt/media/concrt_imageproc.png "Concrt_imageproc")  
  
 Die `countdown_event` Objekt in diesem Beispiel ermöglicht Bildverarbeitungsnetzwerk an die Hauptassembly der Anwendung zu benachrichtigen, wenn alle Abbilder verarbeitet wurden. Die `countdown_event` -Klasse verwendet eine [Concurrency:: Event](../../parallel/concrt/reference/event-class.md) -Objekt signalisiert wird, wenn ein Leistungsindikatorwert 0 (null) erreicht. Die Hauptassembly der Anwendung erhöht den Zähler jedes Mal, wenn die It einen Dateinamen mit dem Netzwerk sendet. Terminalknoten des Netzwerks verringert den Zähler, nachdem jedes Bild verarbeitet wurde. Nachdem die Hauptassembly der Anwendung im angegebene Verzeichnis durchläuft, wartet er den `countdown_event` -Objekt signalisiert, dass sein Zähler 0 (null) erreicht hat.  
  
 Das folgende Beispiel zeigt die `countdown_event` Klasse:  
  
 [!code-cpp[concrt-image-processing-filter#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_13.cpp)]  
  
 [[Nach oben](#top)]  
  
##  <a name="complete"></a> Vollständiges Beispiel  
 Der folgende Code veranschaulicht das vollständige Beispiel. Die `wmain` Funktion verwaltet die [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] -Bibliothek und ruft die `ProcessImages` Prozess-Funktion die [!INCLUDE[TLA#tla_jpeg](../../parallel/concrt/includes/tlasharptla_jpeg_md.md)] Dateien in die `Sample Pictures` Verzeichnis.  
  
 [!code-cpp[concrt-image-processing-filter#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_14.cpp)]  
  
 Die folgende Abbildung zeigt die Ausgabe des Beispiels. Jedes Quellbild liegt über dem entsprechenden geänderten Bild.  
  
 ![Beispielausgabe für das Beispiel](../../parallel/concrt/media/concrt_imageout.png "Concrt_imageout")  
  
 `Lighthouse` wurde von Tom Alphin erstellt, und daher in Graustufen konvertiert. `Chrysanthemum`, `Desert`, `Koala`, und `Tulips` haben Sie die Farbe Rot dominiert die blauen und grünen Farbkomponenten entfernt haben und daher dunkler sind. `Hydrangeas`, `Jellyfish`, und `Penguins` entsprechen die Standardkriterien und sind daher Sepia Farbtönen an.  
  
 [[Nach oben](#top)]  
  
### <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `image-processing-network.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe /DUNICODE/EHsc / Image-Verarbeitung-network.cpp/Link gdiplus.lib**  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweisen für die Concurrency Runtime](../../parallel/concrt/concurrency-runtime-walkthroughs.md)
