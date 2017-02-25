---
title: "Windows Sockets: Datagrammsockets | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Datagrammsockets [C++]"
  - "Sockets [C++], Bidirektionaler Datenfluss"
  - "Sockets [C++], Datagramm"
  - "Windows-Sockets [C++], Bidirektionaler Datenfluss"
  - "Windows-Sockets [C++], Datagramm"
ms.assetid: bec16a1c-74c0-4ff9-8c18-c2d87897d264
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Windows Sockets: Datagrammsockets
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt Datagrammsockets, einen der beiden verfügbaren Windows Socket\-Typen. \(Die andere Art ist [Streamsocket](../mfc/windows-sockets-stream-sockets.md).\)  
  
 Datagrammsockets unterstützen einen bidirektionalen Datenfluss, der nicht garantiert ist sequenziell Relevanz werden oder unduplicated.  Datagramme auch wird nicht garantiert, um zuverlässig sein; sie können ungeordnet nicht können.  Datagrammdaten stammen gestört und möglicherweise dupliziert an, jedoch Datensatzgrenzen in Daten werden beibehalten, solange die Datensätze kleiner als die interne Größenbeschränkung des Empfängers sind.  Sie sind für das Verwaltensequentiell ordnen und Zuverlässigkeit des Codes zuständig. Zuverlässigkeit \(i, auf lokalen Netzen \[LAN\] jedoch kleiner so auf Fernnetzen \[WAN\], z dem Internet gut zu sein.\)  
  
 Datagramme sind "verbindungslos", d. h wird keine explizite Verbindung festgelegt; Sie übertragen eine Datagrammmeldung zu einem angegebenen Socket und Sie können keine Meldungen von einem angegebenen Socket empfangen.  
  
 Ein Beispiel eines Datagrammsockets ist eine Anwendung, die Systemuhren im Netzwerk synchronisiert wird.  Dies veranschaulicht eine zusätzliche Funktion von Datagrammsockets in mindestens einige Einstellungen: Übertragungsmeldungen zu vielen Endsystemadressen.  
  
 Datagrammsockets sind besser als Streamsockets für Datensatz\-ausgerichtete Daten.  Weitere Informationen über Datagrammsockets, finden Sie in der Windows Socket\-Spezifikation, die in [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] verfügbar ist.  
  
## Siehe auch  
 [Windows\-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)   
 [Windows Sockets: Hintergrund](../mfc/windows-sockets-background.md)