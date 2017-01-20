---
title: "Text- und bin&#228;re Streams"
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
  - "C"
helpviewer_keywords: 
  - "Binäre Streams"
  - "Textstreams"
ms.assetid: 57035e4a-955d-4e04-a560-fcf67ce68b4e
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Text- und bin&#228;re Streams
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Textstream besteht aus einem oder mehrere Textzeilen, die geschrieben werden können einer textbezogenen angezeigt, damit sie gelesen werden können.  Beim Lesen von einen Textstream, liest das Programm `NL` \(Zeilenumbruch\) am Ende jeder Zeile.  Beim Schreiben auf einen Textstream, schreibt das Programm `NL`, um das Ende einer Zeile zu signalisieren.  Um unterschiedliche Konventionen unter Zielumgebung für die Darstellung des Texts in Dateien entspricht, können die Bibliotheksfunktionen die Anzahl und die Darstellung von Zeichen ändern, die zwischen dem Programm und einen Textstream gesendet werden.  
  
 So erhöhen innerhalb eines Textstreams ist eingeschränkt.  Sie können den aktuellen Stellungsanzeiger abrufen, indem Sie [fgetpos](../c-runtime-library/reference/fgetpos.md) oder [ftell](../c-runtime-library/reference/ftell-ftelli64.md) aufrufen.  Sie können einen Textstream in einer zu positionieren erhielten diese Methode oder am Anfang oder Ende des Streams, indem Sie [fsetpos](../c-runtime-library/reference/fsetpos.md) oder [fseek](../c-runtime-library/reference/fseek-fseeki64.md) aufrufen.  Jede beliebige andere Meinungsänderung kann sich wird unterstützt nicht hervor.  
  
 Maximale Portabilität sollte das Programm nicht schreiben:  
  
-   Leere Dateien.  
  
-   Leerzeichen am Ende einer Zeile.  
  
-   Partielle Zeilen \(durch Weglassen `NL` am Ende einer Datei\).  
  
-   Zeichen die nicht druckbaren Zeichen, NL und `HT` \(Horizontaler Tabulator\).  
  
 Wenn Sie diese Regeln befolgen, die eine Sequenz von Zeichen, die Sie aus einem Textstream \(entweder als Byte oder Mehrbytezeichen\) übereinstimmen die Folge von Zeichen lesen, Sie z Textstream schreiben, als Sie die Datei erstellt haben.  Andernfalls können die Bibliotheksfunktionen eine Datei aufheben, die Sie erstellen, wenn die Datei leer ist, wenn Sie sie schließen.  Oder sie können geändert oder Löschungszeichen, die Sie in die Datei schreiben.  
  
 Ein Binärstream besteht aus einem oder mehreren Bytes aus beliebigen Informationen.  Sie können den Wert schreiben, der in einem bestimmten Objekt zu \(gespeichert wird byteorientiertem\) Binärstream a und genau lesen, der im Objekt gespeichert wurde, als Sie ihn selbst.  Die Bibliotheksfunktionen ändern nicht die Bytes, die Sie zwischen dem Programm und einem Binärstream senden.  Sie können eine beliebige Anzahl von Nullbytes der Datei jedoch anfügen, die Sie mit einem Binärstream schreiben.  Das Programm muss diese zusätzlichen Nullbytes am Ende jedes möglichen Binärstreams verarbeiten.  
  
 Daher ist die Positionierung innerhalb eines Binärstreams, außer dem Positionieren relativ zum Ende des Streams genau definiert.  Sie können den aktuellen Stellungsanzeiger abrufen und ändern genauso wie für einen Textstream.  Darüber hinaus führt die Offsets, die von [ftell](../c-runtime-library/reference/ftell-ftelli64.md) und [fseek](../c-runtime-library/reference/fseek-fseeki64.md) Zählbytes vom Anfang des Streams verwendet werden \(der Byte \(null\), d die ganzzahlige arithmetischen auf diesen Offsets vorhersehbarer Ergebnisse.  
  
 Ein Bytestrom behandelt eine Datei als Bytesequenz.  Innerhalb des Programms wird der Stream wie dieselbe Bytesequenz, außer die möglichen Änderungen aus, die oben beschriebenen.  
  
## Siehe auch  
 [Dateien und Streams](../c-runtime-library/files-and-streams.md)