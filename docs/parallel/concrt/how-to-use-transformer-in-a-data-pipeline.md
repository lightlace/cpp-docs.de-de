---
title: 'Vorgehensweise: Verwenden von Transformer in einer Datenpipeline'
ms.date: 11/04/2016
helpviewer_keywords:
- transformer class, example
- data pipelines, using transformer [Concurrency Runtime]
- using transformer in data pipelines [Concurrency Runtime]
ms.assetid: ca49cb3f-4dab-4b09-a9c9-d3a109ae4c29
ms.openlocfilehash: 59c4854eea985b3c91fad6e7dc6c47ca9b07d333
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57291469"
---
# <a name="how-to-use-transformer-in-a-data-pipeline"></a>Vorgehensweise: Verwenden von Transformer in einer Datenpipeline

Dieses Thema enthält ein einfaches Beispiel, das zeigt, wie Sie mit der [Concurrency:: transformer](../../parallel/concrt/reference/transformer-class.md) Klasse in einer Datenpipeline. Ein vollständigeres Beispiel, das eine Datenpipeline verwendet wird, um bildverarbeitung, finden Sie unter [Exemplarische Vorgehensweise: Erstellen eine Bildverarbeitungsnetzwerks](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).

*Datenpipelinefunktionen* ist ein gängiges Muster, bei der gleichzeitigen Programmierung. Eine Datenpipeline besteht aus einer Reihe von Phasen, wobei in jeder einzelnen Phase Arbeiten ausführt und das jeweilige Ergebnis dann an die nächste Phase weitergeleitet wird. Die `transformer`-Klasse ist eine Hauptkomponente in Datenpipelines, da sie einen Eingabewert empfängt, Arbeiten für diesen Wert ausführt und dann ein Ergebnis erzeugt, das von einer anderen Komponente verwendet werden kann.

## <a name="example"></a>Beispiel

Bei diesem Beispiel wird zur Ausführung einer Reihe von Transformationen, denen ein ursprünglicher Eingabewert zugrunde liegt, folgende Datenpipeline verwendet:

1. In der ersten Phase wird der absolute Wert der Eingabe berechnet.

1. In der zweiten Phase wird die Quadratwurzel der Eingabe berechnet.

1. In der dritten Phase wird das Quadrat der Eingabe berechnet.

1. In der vierten Phase wird die Eingabe negiert.

1. In der fünften Phase wird das Endergebnis in einen Meldungspuffer geschrieben.

Bei diesem Beispiel wird schließlich das Ergebnis der Pipeline auf der Konsole gedruckt.

[!code-cpp[concrt-data-pipeline#1](../../parallel/concrt/codesnippet/cpp/how-to-use-transformer-in-a-data-pipeline_1.cpp)]

Dieses Beispiel erzeugt die folgende Ausgabe:

```Output
The result is -42.
```

Es kommt bei einer Datenpipeline häufig vor, dass bei einer Phase ein Wert ausgegeben wird, dessen Typ sich vom Eingabewert unterscheidet. Bei diesem Beispiel wird in der zweiten Phase ein Wert des `int`-Typs als Eingabe verwendet und die Quadratwurzel dieses Werts (ein `double`) als Ausgabe erzeugt.

> [!NOTE]
>  Die Datenpipeline in diesem Beispiel dient zur Veranschaulichung. Da der Arbeitsmehraufwand jedes Transformationsvorgangs gering ist, kann der Mehraufwand zum Ausführen der Meldungsübergabe die Vorteile einer Datenpipeline zunichte machen.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `data-pipeline.cpp` und führen Sie dann den folgenden Befehl in einem Fenster von Visual Studio-Eingabeaufforderung.

**CL.exe/EHsc Data-pipeline.cpp**

## <a name="see-also"></a>Siehe auch

[Asynchrone Agents Library](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Exemplarische Vorgehensweise: Erstellen eines Bildverarbeitungsnetzwerks](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)
