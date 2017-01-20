---
title: "Steuern von Streams"
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
  - "Controlling Streams"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Steuern von Streams"
  - "Streams"
  - "Streams, Steuern"
ms.assetid: 267e9013-9afc-45f6-91e3-ca093230d9d9
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Steuern von Streams
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[fopen](../c-runtime-library/reference/fopen-wfopen.md) gibt die Adresse eines Objekts vom Typ `FILE` zurück.  Sie verwenden diese Adresse als das `stream`\-Argument zu einigen Bibliotheksfunktionen, um verschiedene Vorgänge in einer geöffneten Datei auszuführen.  Für einen Bytestrom gesamte Eingabe findet statt, als ob alle Zeichen gelesen wird, indem Sie [fgetc](../c-runtime-library/reference/fgetc-fgetwc.md) aufrufen, und ganz Ausgabe findet statt, als wäre jedes Zeichen geschrieben wird, indem Sie [fputc](../c-runtime-library/reference/fputc-fputwc.md) aufrufen.  Bei einem Breitzeichen Stream gesamte Eingabe findet statt, als ob alle Zeichen gelesen wird, indem Sie [fgetwc](../c-runtime-library/reference/fgetc-fgetwc.md) aufrufen, und ganz Ausgabe findet statt, als wäre jedes Zeichen geschrieben wird, indem Sie [fputwc](../c-runtime-library/reference/fputc-fputwc.md) aufrufen.  
  
 Sie können eine Datei schließen, indem Sie [fclose](../c-runtime-library/reference/fclose-fcloseall.md) aufrufen, nachdem ist `FILE` die Adresse des Objekts ungültig.  
  
 Ein `FILE`\-Objekt speichert den Zustand eines Streams und enthält:  
  
-   Ein festgelegter Wert ungleich 0 \(null\) des Fehlerindikators durch eine Funktion, die ein Lese\- bzw. ein Schreibfehler trifft.  
  
-   Ein festgelegter Wert ungleich 0 \(null\) des Dateiende\-Indikators durch eine Funktion, die das Ende der Datei beim Lesen trifft.  
  
-   Ein Stellungsanzeiger gibt die folgenden Bytes im Stream an, um zu lesen oder zu schreiben, wenn die Datei das Positionieren von Anforderungen unterstützen kann.  
  
-   [Streamzustand](../c-runtime-library/stream-states.md) gibt an, ob der Stream liest oder schreibt akzeptiert und ob der Stream ungebunden ist, byteorientiert oder weiter ausgerichtet.  
  
-   Ein Konvertierungszustand speichert den Zustand des assemblierten oder generierte generalisierten Mehrbytezeichens alle teilweise sowie an jeden Schichtzustand für die die Bytesequenz in der Datei\).  
  
-   Ein Dateipuffer gibt die Adresse und der Größe eines Arrayobjekts an, das Bibliotheksfunktionen verwenden können, um die Ausführungsleistung von Lese\- und Schreibvorgänge in den Stream zu verbessern.  
  
 Ändern Sie keinen Wert, der in einem `FILE`\-Objekt oder einem Dateipuffer gespeichert wird, den Sie für dieses Objekt angeben.  Sie können ein `FILE`\-Objekt sowie die Adresse der Kopie nicht als Argument portably `stream` verwenden zu einer Bibliotheksfunktion kopieren.  
  
## Siehe auch  
 [Dateien und Streams](../c-runtime-library/files-and-streams.md)