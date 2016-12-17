---
title: "Zwei M&#246;glichkeiten zur Erstellung eines CArchive-Objekts"
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
  - "CArchive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchive-Klasse, Schließen des CArchive-Objekts"
  - "CArchive-Klasse, Konstruktor"
  - "CArchive-Objekte"
  - "CArchive-Objekte, Schließen"
  - "Datenspeicher [C++], CArchive-Klasse"
  - "E/A [MFC], Erstellen des CArchive-Objekts"
  - "Serialisierung [C++], CArchive-Klasse"
  - "Speicherung [C++], CArchive-Klasse"
ms.assetid: aefa28ce-b55c-40dc-9e42-5f038030985d
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Zwei M&#246;glichkeiten zur Erstellung eines CArchive-Objekts
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es gibt zwei Möglichkeiten, ein `CArchive`\-Objekt zu erstellen:  
  
-   [Implizite Erstellung eines CArchive\-Objekts zum Framework](#_core_implicit_creation_of_a_carchive_object_via_the_framework)  
  
-   [Explizite Erstellung eines CArchive\-Objekts](#_core_explicit_creation_of_a_carchive_object)  
  
##  <a name="_core_implicit_creation_of_a_carchive_object_via_the_framework"></a> Implizite Erstellung eines CArchive\-Objekts zum Framework  
 Die am häufigsten verwendete und einfachste Methode, das ist, dem Framework ein `CArchive`\-Objekt für das Dokument der im Namen speichern, speichern erstellen, z und Befehle im Menü Datei öffnen zu können.  
  
 Dies ist, was das Framework zur Verfügung, sofern der Benutzer der Anwendung der Befehl Speichern unter der Menü ausgibt:  
  
1.  Stellt das Dialogfeld **Speichern unter** dar und ruft den Dateinamen vom Benutzer ab.  
  
2.  Öffnet die Datei, die vom Benutzer als `CFile`\-Objekt befindet.  
  
3.  Erstellt ein `CArchive`\-Objekt, das auf diesem `CFile`\-Objekt.  Wenn das `CArchive`\-Objekt erstellt, wird das Framework den Modus auf "Speicher" \(schreiben, serialisieren Sie\), im Gegensatz zum "Last" fest \(Lesen, deserialisiert\).  
  
4.  Ruft die `Serialize`\-Funktion definiert im **CDocument** abgeleitete Klasse auf und übergibt ein Verweis auf das `CArchive`\-Objekt.  
  
 `Serialize`\-Funktion des Dokuments schreibt Daten dem Objekt `CArchive`, wie weiter unten erläutert.  Nach Rückgabe von der Funktion `Serialize`, zerstört das Framework `CArchive`\-Objekt und dann das `CFile`\-Objekt.  
  
 Wenn Sie das Framework `CArchive`\-Objekt für das Dokument erstellt haben, ist alles, das Sie ausführen müssen, die `Serialize`, Funktion des Dokuments zu implementieren, die in und aus dem Archiv schreibt und liest.  Sie müssen `Serialize` für jedes von `CObject` abgeleitete Objekte ebenfalls implementieren, dass die `Serialize`\-Funktion des Dokuments wiederum direkt oder indirekt serialisiert.  
  
##  <a name="_core_explicit_creation_of_a_carchive_object"></a> Explizite Erstellung eines CArchive\-Objekts  
 Neben Serialisieren eines Dokuments zu Framework, gibt es weitere Möglichkeiten, wenn Sie ein `CArchive`\-Objekt erfordern.  Beispielsweise können Sie Daten zu und von der Zwischenablage serialisieren, dargestellt durch ein `CSharedFile`\-Objekt.  Oder, sollten Sie eine Benutzeroberfläche zum Speichern einer Datei verwenden, die von der Zeichenfolge unterscheiden ist, die vom Framework bereitgestellt wird.  In diesem Fall können Sie ein `CArchive`\-Objekt explizit erstellen.  Hierzu dieselbe Methode, die das Framework durchführt, mithilfe der folgenden Prozedur.  
  
#### Um ein CArchive\-Objekt explizit erstellen  
  
1.  Erstellen Sie ein `CFile`\-Objekt oder ein Objekt, die von `CFile` abgeleitet werden.  
  
2.  Führen Sie das `CFile`\-Objekt an den Konstruktor für `CArchive`, wie im folgenden Beispiel gezeigt:  
  
     [!CODE [NVC_MFCSerialization#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSerialization#5)]  
  
     Das zweite Argument `CArchive` zum Konstruktor ist ein Enumerationswert, der angibt, ob das Archiv für das Speichern oder Laden von Daten in oder aus der Datei verwendet wird.  Die `Serialize`\-Funktion eines Objekts überprüft diesen Zustand, indem die Funktion `IsStoring` für das Archivobjekt aufruft.  
  
 Wenn Sie der Speichern sind, oder, Daten nach oder `CArchive` lädt, welches Objekt Sie, schließen Sie es.  Obwohl die Objekte `CArchive` \(und `CFile`\) automatisch das Archiv \(Datei\) und schließen, sollten Sie sich explizit dies jetzt, da Wiederherstellung von Fehlern erleichtert wird.  Informationen über die Fehlerbehandlung, finden Sie im Artikel [Ausnahmen: Ausnahmen abfangen und Löschen](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
#### Um das CArchive\-Objekt schließen  
  
1.  Das folgende Beispiel veranschaulicht, wie das `CArchive`\-Objekt enthält:  
  
     [!CODE [NVC_MFCSerialization#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSerialization#6)]  
  
## Siehe auch  
 [Serialisierung: Serialisieren eines Objekts](../mfc/serialization-serializing-an-object.md)