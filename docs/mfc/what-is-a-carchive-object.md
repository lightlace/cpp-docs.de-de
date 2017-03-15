---
title: "Was ist ein CArchive-Objekt? | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CArchive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Archivobjekte [C++]"
  - "Archive [C++], für die Serialisierung"
  - "Puffern, Serialisierbare Objekte"
  - "Puffer, Serialisierbare Objekte"
  - "CArchive-Klasse, Informationen über die CArchive-Klasse"
ms.assetid: 843f1825-288d-4d89-a1fa-70e1f92d9b8b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Was ist ein CArchive-Objekt?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein `CArchive`\-Objekt stellt einen typsicheren Pufferungsmechanismus zum Schreiben bereit, oder lesende serialisierbare Objekte nach oder `CFile`\-Objekt.  Im Allgemeinen stellt das `CFile`\-Objekt einer Datenträgerdatei dar; jedoch kann dies eine Arbeitsspeicherdatei Objekt \(`CSharedFile` \) auch sein und die Zwischenablage möglicherweise darstellen.  
  
 Das angegebene `CArchive`\-Objekt entweder speichert \(schreibt, serialisiert\), Daten oder Daten der Lasten \(liest, deserialisiert\), jedoch nicht beide.  Die Lebensdauer eines Objekts `CArchive` ist einer Durchlauf Schreibenobjekte zu einer Datei oder Lesenobjekte aus einer Datei.  Deshalb werden zwei nacheinander erstellte `CArchive`\-Objekte benötigt, um Daten in eine Datei zu serialisieren und sie dann zu deserialisieren hinter aus der Datei.  
  
 Wenn einem Archiv Objekte in einer Datei speichert, fügt das Archiv `CRuntimeClass` den Namen den Objekten an.  Wenn ein anderes Archiv Objekte von einer Datei in den Arbeitsspeicher lädt, von `CObject` abgeleiteten Objekte werden dynamisch basierend auf `CRuntimeClass` der Objekte neu erstellt.  Das angegebene Objekt wurde mehrfach verwiesen werden, wenn sie der Datei durch das Archiv speichernde geschrieben wird.  Das Ladenarchiv jedoch rekonstruiert das Objekt nur einmal.  Die Details darüber, wie ein dem Archiv `CRuntimeClass` Informationen zu Objekten anfügt und Objekte rekonstruiert, mögliche mehrere Verweise berücksichtigend, werden in [Technischer Hinweis 2](../mfc/tn002-persistent-object-data-format.md) beschrieben.  
  
 Während Daten einem Archiv serialisiert werden, sammelt das Archiv die Daten, bis dessen Puffer voll ist.  Anschließend schreibt das Archiv den Puffer an `CFile`\-Objekt, das von dem `CArchive`\-Objekt dargestellt wird.  Entsprechend als Sie lesen Sie Daten von einem Archiv, liest sie Daten aus der Datei in den Puffer und dann aus dem Puffer dem deserialisierten Objekt.  Diese Pufferung reduziert wird die Häufigkeit, die eine Festplatte physisch gelesen und so verbessert die Leistung der Anwendung.  
  
## Siehe auch  
 [Serialisierung: Serialisieren eines Objekts](../mfc/serialization-serializing-an-object.md)