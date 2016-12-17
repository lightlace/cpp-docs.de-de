---
title: "Gewusst wie: Verwenden von transformer in einer Datenpipeline"
ms.custom: na
ms.date: "12/03/2016"
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
  - "transformer-Klasse, Beispiel"
  - "Datenpipelines [Concurrency Runtime], Verwenden von Transformer"
  - "Verwenden von Transformer in Datenpipelines [Concurrency Runtime]"
ms.assetid: ca49cb3f-4dab-4b09-a9c9-d3a109ae4c29
caps.latest.revision: 16
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Verwenden von transformer in einer Datenpipeline
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema enthält ein grundlegendes Beispiel dafür, wie die [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md)\-Klasse in einer Datenpipeline verwendet wird.  Ein ausführlicheres Beispiel, in dem die Bildverarbeitung mit einer Datenpipeline erfolgt, finden Sie unter [Exemplarische Vorgehensweise: Erstellen eines Bildverarbeitungsnetzwerks](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).  
  
 Bei *Datenpipelinefunktionen* handelt es sich um ein Muster, das häufig bei der gleichzeitigen Programmierung eingesetzt wird.  Eine Datenpipeline besteht aus einer Reihe von Phasen, wobei in jeder einzelnen Phase Arbeiten ausführt und das jeweilige Ergebnis dann an die nächste Phase weitergeleitet wird.  Die `transformer`\-Klasse ist eine Hauptkomponente in Datenpipelines, da sie einen Eingabewert empfängt, Arbeiten für diesen Wert ausführt und dann ein Ergebnis erzeugt, das von einer anderen Komponente verwendet werden kann.  
  
## Beispiel  
 Bei diesem Beispiel wird zur Ausführung einer Reihe von Transformationen, denen ein ursprünglicher Eingabewert zugrunde liegt, folgende Datenpipeline verwendet:  
  
1.  In der ersten Phase wird der absolute Wert der Eingabe berechnet.  
  
2.  In der zweiten Phase wird die Quadratwurzel der Eingabe berechnet.  
  
3.  In der dritten Phase wird das Quadrat der Eingabe berechnet.  
  
4.  In der vierten Phase wird die Eingabe negiert.  
  
5.  In der fünften Phase wird das Endergebnis in einen Meldungspuffer geschrieben.  
  
 Bei diesem Beispiel wird schließlich das Ergebnis der Pipeline auf der Konsole gedruckt.  
  
 [!CODE [concrt-data-pipeline#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-data-pipeline#1)]  
  
 In diesem Beispiel wird die folgende Ausgabe erzeugt:  
  
  **The result is \-42.** Es kommt bei einer Datenpipeline häufig vor, dass bei einer Phase ein Wert ausgegeben wird, dessen Typ sich vom Eingabewert unterscheidet.  Bei diesem Beispiel wird in der zweiten Phase ein Wert des `int`\-Typs als Eingabe verwendet und die Quadratwurzel dieses Werts \(ein `double`\) als Ausgabe erzeugt.  
  
> [!NOTE]
>  Die Datenpipeline in diesem Beispiel dient zur Veranschaulichung.  Da der Arbeitsmehraufwand jedes Transformationsvorgangs gering ist, kann der Mehraufwand zum Ausführen der Meldungsübergabe die Vorteile einer Datenpipeline zunichte machen.  
  
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio\-Projekt ein. Alternativ dazu können Sie ihn auch in eine Datei mit dem Namen `data-pipeline.cpp` einfügen und dann folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster ausführen.  
  
 **cl.exe \/EHsc data\-pipeline.cpp**  
  
## Siehe auch  
 [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)   
 [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Exemplarische Vorgehensweise: Erstellen eines Bildverarbeitungsnetzwerks](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)