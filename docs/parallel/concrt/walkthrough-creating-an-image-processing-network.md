---
title: 'Exemplarische Vorgehensweise: Erstellen eines Bildverarbeitungsnetzwerks'
ms.date: 04/25/2019
helpviewer_keywords:
- image-processing networks, creating [Concurrency Runtime]
- creating image-processing networks [Concurrency Runtime]
ms.assetid: 78ccadc9-5ce2-46cc-bd62-ce0f99d356b8
ms.openlocfilehash: 03d95be8fae3565a51811357ed9553c3a2649674
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140753"
---
# <a name="walkthrough-creating-an-image-processing-network"></a>Exemplarische Vorgehensweise: Erstellen eines Bildverarbeitungsnetzwerks

In diesem Dokument wird veranschaulicht, wie ein Netzwerk von asynchronen Nachrichten Blöcken erstellt wird, die eine Bildverarbeitung durchführen.

Das Netzwerk bestimmt, welche Vorgänge für ein Abbild auf der Grundlage seiner Merkmale durchgeführt werden sollen. In diesem Beispiel wird das *Daten* Fluss Modell verwendet, um Bilder über das Netzwerk weiterzuleiten. Im Datenflussmodell kommunizieren unabhängige Komponenten eines Programms durch Senden von Nachrichten miteinander. Wenn eine Komponente eine Nachricht empfängt, kann Sie einige Aktionen ausführen und das Ergebnis dieser Aktion dann an eine andere Komponente übergeben. Vergleichen Sie dies mit dem *Ablauf Steuerungs* Modell, in dem eine Anwendung Steuerungsstrukturen verwendet, z. b. bedingte Anweisungen, Schleifen usw., um die Reihenfolge von Vorgängen in einem Programm zu steuern.

Ein Netzwerk, das auf einem Datenfluss basiert, erstellt eine *Pipeline* von Tasks. Jede Phase der Pipeline führt gleichzeitig einen Teil der gesamten Aufgabe aus. Eine Analogie hierzu ist eine Fertigungsstraße eines Fahrzeugherstellers. Wenn jedes Fahrzeug die assemblyzeile durchläuft, wird der Frame von einer Station zusammen mit einer anderen installiert, usw. Durch die Aktivierung der gleichzeitigen Zusammenstellung mehrerer Fahrzeuge kann die assemblylinie einen besseren Durchsatz bereitstellen als die Zusammenstellung der Fahrzeuge nacheinander.

## <a name="prerequisites"></a>Voraussetzungen

Lesen Sie die folgenden Dokumente, bevor Sie mit dieser exemplarischen Vorgehensweise beginnen:

- [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)

- [Vorgehensweise: Verwenden eines Nachrichtenblockfilters](../../parallel/concrt/how-to-use-a-message-block-filter.md)

- [Exemplarische Vorgehensweise: Erstellen eines Datenfluss-Agent](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)

Außerdem wird empfohlen, dass Sie die Grundlagen von GDI+ verstehen, bevor Sie mit dieser exemplarischen Vorgehensweise beginnen.

## <a name="top"></a> Abschnitte

Diese exemplarische Vorgehensweise enthält folgende Abschnitte:

- [Definieren der Bild Verarbeitungs Funktionalität](#functionality)

- [Erstellen des Abbild Verarbeitungs Netzwerks](#network)

- [Vollständiges Beispiel](#complete)

## <a name="functionality"></a>Definieren der Bild Verarbeitungs Funktionalität

In diesem Abschnitt werden die Unterstützungsfunktionen veranschaulicht, die vom Bild Verarbeitungs Netzwerk verwendet werden, um mit Bildern zu arbeiten, die vom Datenträger gelesen werden.

Die folgenden Funktionen, `GetRGB` und `MakeColor`, extrahieren und kombinieren die einzelnen Komponenten der angegebenen Farbe.

[!code-cpp[concrt-image-processing-filter#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_1.cpp)]

Die folgende Funktion, `ProcessImage`, ruft das angegebene [Std:: function](../../standard-library/function-class.md) -Objekt auf, um den Farbwert jedes Pixels in einem GDI+- [Bitmap](/windows/win32/api/gdiplusheaders/nl-gdiplusheaders-bitmap) -Objekt zu transformieren. Die `ProcessImage`-Funktion verwendet den " [parallelcurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) "-Algorithmus, um jede Zeile der Bitmap parallel zu verarbeiten.

[!code-cpp[concrt-image-processing-filter#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_2.cpp)]

Mit den folgenden Funktionen, `Grayscale`, `Sepiatone`, `ColorMask`und `Darken`wird die `ProcessImage`-Funktion aufgerufen, um den Farbwert jedes Pixels in einem `Bitmap` Objekt zu transformieren. Jede dieser Funktionen verwendet einen Lambda-Ausdruck, um die Farb Transformation von einem Pixel zu definieren.

[!code-cpp[concrt-image-processing-filter#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_3.cpp)]

Mit der folgenden Funktion, `GetColorDominance`, wird auch die `ProcessImage`-Funktion aufgerufen. Anstatt jedoch den Wert der einzelnen Farben zu ändern, verwendet diese Funktion [parallelcurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) -Objekte, um zu berechnen, ob die rote, grüne oder blaue Farbkomponente das Bild beherrscht.

[!code-cpp[concrt-image-processing-filter#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_4.cpp)]

Die folgende Funktion, `GetEncoderClsid`, Ruft den Klassen Bezeichner für den angegebenen MIME-Typ eines Encoders ab. Die Anwendung verwendet diese Funktion, um den Encoder für eine Bitmap abzurufen.

[!code-cpp[concrt-image-processing-filter#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_5.cpp)]

[[Nach oben](#top)]

## <a name="network"></a>Erstellen des Abbild Verarbeitungs Netzwerks

In diesem Abschnitt wird beschrieben, wie ein Netzwerk von asynchronen Nachrichten Blöcken erstellt wird, die eine Bildverarbeitung für jedes JPEG-Bild (JPG) in einem bestimmten Verzeichnis ausführen. Das Netzwerk führt die folgenden Abbild Verarbeitungsvorgänge aus:

1. Konvertieren Sie für jedes von Tom erstellte Image in Grayscale.

1. Entfernen Sie die grünen und blauen Komponenten für jedes Bild, das rot als vorherrschende Farbe hat, und wählen Sie es aus.

1. Wenden Sie für ein beliebiges anderes Bild den Typ "*" an.

Das Netzwerk wendet nur den ersten Abbild Verarbeitungsvorgang an, der mit einer dieser Bedingungen übereinstimmt. Wenn z. b. ein Bild von Tom erstellt wird und als seine dominierende Farbe Rot ist, wird das Bild nur in Graustufen konvertiert.

Nachdem das Netzwerk jeden Abbild Verarbeitungsvorgang durchführt, speichert es das Image als Bitmapdatei (BMP-Datei) auf dem Datenträger.

Die folgenden Schritte zeigen, wie Sie eine Funktion erstellen, die dieses Bild Verarbeitungs Netzwerk implementiert, und dieses Netzwerk auf jedes JPEG-Image in einem bestimmten Verzeichnis anwenden.

#### <a name="to-create-the-image-processing-network"></a>So erstellen Sie das Abbild Verarbeitungs Netzwerk

1. Erstellen Sie eine Funktion `ProcessImages`, die den Namen eines Verzeichnisses auf der Festplatte annimmt.

   [!code-cpp[concrt-image-processing-filter#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_6.cpp)]

1. Erstellen Sie in der `ProcessImages`-Funktion eine `countdown_event` Variable. Die `countdown_event`-Klasse wird weiter unten in dieser exemplarischen Vorgehensweise dargestellt.

   [!code-cpp[concrt-image-processing-filter#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_7.cpp)]

1. Erstellen Sie ein [Std:: Map](../../standard-library/map-class.md) -Objekt, das ein `Bitmap`-Objekt mit dem ursprünglichen Dateinamen verknüpft.

   [!code-cpp[concrt-image-processing-filter#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_8.cpp)]

1. Fügen Sie den folgenden Code hinzu, um die Elemente des Bild Verarbeitungs Netzwerks zu definieren.

   [!code-cpp[concrt-image-processing-filter#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_9.cpp)]

1. Fügen Sie folgenden Code hinzu, um eine Verbindung mit dem Netzwerk herzustellen.

   [!code-cpp[concrt-image-processing-filter#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_10.cpp)]

1. Fügen Sie den folgenden Code hinzu, um an den Anfang des Netzwerks den vollständigen Pfad der einzelnen JPEG-Dateien im Verzeichnis zu senden.

   [!code-cpp[concrt-image-processing-filter#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_11.cpp)]

1. Warten Sie, bis die `countdown_event` Variable Null erreicht hat.

   [!code-cpp[concrt-image-processing-filter#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_12.cpp)]

In der folgenden Tabelle werden die Member des Netzwerks beschrieben.

|Member|BESCHREIBUNG|
|------------|-----------------|
|`load_bitmap`|Ein [parallelcurrency:: Transformer](../../parallel/concrt/reference/transformer-class.md) -Objekt, das ein `Bitmap` Objekt von der Festplatte lädt und einen Eintrag zum `map`-Objekt hinzufügt, um das Bild dem ursprünglichen Dateinamen zuzuordnen.|
|`loaded_bitmaps`|Ein [parallelcurrency:: Unbounded_buffer](reference/unbounded-buffer-class.md) -Objekt, das die geladenen Bilder an die Bild Verarbeitungs Filter sendet.|
|`grayscale`|Ein `transformer` Objekt, das von Tom erstellte Bilder in Graustufen konvertiert. Der Autor verwendet die Metadaten des Bilds.|
|`colormask`|Ein `transformer`-Objekt, das die grünen und blauen Farbkomponenten aus Bildern entfernt, die als vorherrschende Farbe rot aufweisen.|
|`darken`|Ein `transformer`-Objekt, das Bilder, die rot sind, als bestimmende Farbe darktet.|
|`sepiatone`|Ein `transformer` Objekt, das die Sepia-Tonung auf Bilder anwendet, die nicht von Tom erstellt werden und nicht überwiegend rot sind.|
|`save_bitmap`|Ein `transformer`-Objekt, das den verarbeiteten `image` als Bitmap auf dem Datenträger speichert. `save_bitmap` Ruft den ursprünglichen Dateinamen aus dem `map`-Objekt ab und ändert die Dateinamenerweiterung in BMP.|
|`delete_bitmap`|Ein `transformer`-Objekt, das den Speicher für die Bilder freigibt.|
|`decrement`|Ein " [parallelcurrency:: Callcenter](../../parallel/concrt/reference/call-class.md) "-Objekt, das als Terminal Knoten im Netzwerk fungiert. Das `countdown_event` Objekt wird verringert, um an die Hauptanwendung zu signalisieren, dass ein Image verarbeitet wurde.|

Der `loaded_bitmaps`-Nachrichten Puffer ist wichtig, da er als `unbounded_buffer` Objekt `Bitmap` Objekten für mehrere Empfänger anbietet. Wenn ein Zielblock ein `Bitmap` Objekt akzeptiert, bietet das `unbounded_buffer`-Objekt keine `Bitmap`-Objekt für andere Ziele an. Daher ist die Reihenfolge, in der Sie Objekte mit einem `unbounded_buffer` Objekt verknüpfen, wichtig. Die `grayscale`-, `colormask`-und `sepiatone` Meldungs Blöcke verwenden jeweils einen Filter, um nur bestimmte `Bitmap` Objekte zu akzeptieren. Der `decrement`-Nachrichten Puffer ist ein wichtiges Ziel des `loaded_bitmaps` Nachrichten Puffers, da er alle `Bitmap` Objekte akzeptiert, die von den anderen Nachrichten Puffern abgelehnt werden. Ein `unbounded_buffer`-Objekt ist erforderlich, um Nachrichten in der Reihenfolge weiterzugeben Daher wird ein `unbounded_buffer` Objekt blockiert, bis ein neuer Zielblock damit verknüpft ist, und die Nachricht akzeptiert, wenn der aktuelle Zielblock diese Nachricht nicht akzeptiert.

Wenn die Anwendung erfordert, dass mehrere Nachrichten Blöcke die Nachricht verarbeiten, können Sie anstelle eines Nachrichten Blocks, der die Nachricht zum ersten Mal akzeptiert, einen anderen Nachrichten Blocktyp verwenden, z. b. `overwrite_buffer`. Die `overwrite_buffer`-Klasse enthält jeweils eine Nachricht, Sie gibt diese Nachricht jedoch an jedes ihrer Ziele weiter.

Die folgende Abbildung zeigt das Bildverarbeitungsnetzwerk:

![Bild Verarbeitungs Netzwerk](../../parallel/concrt/media/concrt_imageproc.png "Bildverarbeitungsnetzwerk")

Das `countdown_event`-Objekt in diesem Beispiel ermöglicht es dem Bild Verarbeitungs Netzwerk, die Hauptanwendung zu informieren, wenn alle Images verarbeitet wurden. Die `countdown_event`-Klasse verwendet ein [parallelcurrency:: Event](../../parallel/concrt/reference/event-class.md) -Objekt, um zu signalisieren, wenn ein Leistungs Zählers Null erreicht. Die Hauptanwendung erhöht den Zählers jedes Mal, wenn ein Dateiname an das Netzwerk gesendet wird. Der Terminal Knoten des Netzwerks Dekremente den Zählers, nachdem jedes Abbild verarbeitet wurde. Nachdem die Hauptanwendung das angegebene Verzeichnis durchlaufen hat, wartet Sie, bis das `countdown_event` Objekt signalisiert hat, dass der Wert 0 (null) erreicht hat.

Das folgende Beispiel zeigt die `countdown_event`-Klasse:

[!code-cpp[concrt-image-processing-filter#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_13.cpp)]

[[Nach oben](#top)]

## <a name="complete"></a>Das komplette Beispiel

Der folgende Code veranschaulicht das vollständige Beispiel. Die `wmain`-Funktion verwaltet die GDI+-Bibliothek und ruft die `ProcessImages`-Funktion auf, um die JPEG-Dateien im `Sample Pictures`-Verzeichnis zu verarbeiten.

[!code-cpp[concrt-image-processing-filter#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_14.cpp)]

Die folgende Abbildung zeigt eine Beispielausgabe. Jedes Quell Image liegt über dem entsprechenden geänderten Image.

![Beispielausgabe für das Beispiel](../../parallel/concrt/media/concrt_imageout.png "Beispielausgabe")

`Lighthouse` wird von Tom Alpha in erstellt und daher in Graustufen konvertiert. `Chrysanthemum`, `Desert`, `Koala`und `Tulips` haben als bestimmende Farbe Rot und haben daher die blauen und grünen Farbkomponenten entfernt und sind dann nicht mehr vorhanden. `Hydrangeas`, `Jellyfish`und `Penguins` entsprechen den Standardkriterien und sind daher auf "*" eingestellt.

[[Nach oben](#top)]

### <a name="compiling-the-code"></a>Kompilieren des Codes

Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `image-processing-network.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio-Eingabe Aufforderungs Fenster aus.

**cl. exe/DUNICODE/EHsc Image-Processing-Network. cpp/Link gdiplus. lib**

## <a name="see-also"></a>Weitere Informationen

[Exemplarische Vorgehensweisen für die Concurrency Runtime](../../parallel/concrt/concurrency-runtime-walkthroughs.md)
