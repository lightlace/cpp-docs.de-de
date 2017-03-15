---
title: "Allgemeine Prinzipien f&#252;r den Klassenentwurf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.mfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Klassen [C++], MFC-Klassenentwurf"
  - "Entwerfen von Klassen"
  - "MFC [C++], Windows-API"
  - "Visual C, Windows-API-Aufrufe"
  - "Windows-API [C++], und MFC"
ms.assetid: e6861ae0-1581-4d9c-9ddf-63f9afcdb913
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Allgemeine Prinzipien f&#252;r den Klassenentwurf
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft Windows wurde entworfen, lange zuvor die Programmiersprache C\+\+ eingesetzt wurde.  Da Tausende Anwendungen die Programmierschnittstelle \(API\) Sprache C Windows\-Anwendung verwendet, wird diese Schnittstelle während der absehbaren Zukunft beibehalten.  Jede C\+\+\-Windows\-Oberfläche muss die Sprache C prozedurale API daher erstellt werden.  Dadurch wird sichergestellt, dass C\+\+\-Anwendungen in der Lage sind, mit C\-Anwendungen vorhanden sein.  
  
 Die Microsoft Foundation Class\-Bibliothek ist eine objektorientierte Schnittstelle zu Windows, die die folgenden Entwurfsziele erreicht:  
  
-   Bedeutende Reduzierung des verwendeten Aufwand, eine Anwendung für Windows zu schreiben.  
  
-   Ausführungsgeschwindigkeit vergleichbar mit der Sprache C der API.  
  
-   Minimaler Codegrößenmehraufwand.  
  
-   Fähigkeit, eine Funktion von C direkt aufzurufen.  
  
-   Einfachere Konvertierung vorhandener C\-Anwendungen zu C\+\+.  
  
-   Möglichkeit, aus vorhandenen Grundlage der Sprache C Windows nutzen Erfahrung \- Programmierung.  
  
-   Einfachere Verwendung der Windows\-API mit C\+\+ als mit C.  
  
-   Einfachen verwenden aber leistungsstarke Abstraktionen von schwierigen Funktionen wie ActiveX\-Steuerelemente, Datenbankunterstützung, Drucken, Symbolleisten und Statusleisten.  
  
-   Wahre Windows\-API für C\+\+, die C\+\+ effektiv verwendet.  
  
 Weitere für den Entwurf der MFC\-Bibliothek, finden Sie unter:  
  
-   [Das Anwendungsframework](../mfc/application-framework.md)  
  
-   [Beziehung zur Sprache C API](../mfc/relationship-to-the-c-language-api.md)  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)