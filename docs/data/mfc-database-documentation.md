---
title: "MFC-Datenbankdokumentation"
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
  - "DAO [C++], MFC"
  - "Datenbanken [C++], MFC"
  - "MFC [C++], Datenbankanwendungen"
  - "ODBC [C++], MFC"
ms.assetid: bb120282-cd0d-4bf4-a27c-93b3501fb3a0
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# MFC-Datenbankdokumentation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die MFC\-Dokumentation für DAO\- und ODBC\-Klassen besteht aus den in der folgenden Tabelle aufgeführten Komponenten.  
  
### MFC\-Datenbankdokumentation  
  
|Dokumentation über|Siehe|  
|------------------------|-----------|  
|Klassen für DAO und ODBC|Der Name der Klasse in derMFC\-Referenz|  
|Globale Funktionen und Makros für DAO und ODBC|Der Name der Funktion oder des Makros in der MFC\-Referenz|  
|Programmieren mit den MFC\-ODBC\-Klassen|[ODBC und MFC](../data/odbc/odbc-and-mfc.md)|  
|Technische Hinweise für DAO und ODBC|[Technische Hinweise zu MFC](../mfc/technical-notes-by-category.md)|  
  
##  <a name="_core_mfc_documentation_and_dao_documentation"></a> MFC\-Dokumentation und DAO\-Dokumentation  
 In der gesamten MFC\-Dokumentation zu den MFC\-DAO\-Klassen finden Sie Verweise auf Themen in der DAO SDK\-Dokumentation, die in der Onlinedokumentation enthalten ist.  Da die MFC DAO umschließt, gelten für die MFC\-Dokumentation folgende Punkte:  
  
-   Sie konzentriert sich auf MFC und darauf, wie sich diese von der zugrunde liegenden DAO\-Implementierung unterscheidet.  
  
-   Sie verweist für die zugrunde liegenden Einzelheiten auf Hilfethemen des DAO SDK.  Diese Querverweise werden immer wie folgt formuliert: "Thema "X" in der DAO\-Hilfe".  
  
-   Sie beschreibt, welche Aktionen von der MFC und DAO unterschiedlich gehandhabt werden.  MFC umschließt DAO nicht vollständig.  MFC stellt z. B keine Objekte für die DAO\-Sicherheitsfunktionen zur Verfügung.  
  
> [!NOTE]
>  Die DAO SDK\-Hilfe ist eine separate Hilfedatei.  In dieser Version von Visual C\+\+ gibt es keine Hypertext\-Links aus dieser Dokumentation zur DAO\-Hilfe.  
  
> [!NOTE]
>  Wenn Sie die Themen der DAO SDK\-Hilfe durchsuchen, müssen Sie eventuell übersetzen.  Die Beispiele in der DAO SDK\-Hauptdokumentation sind nämlich in der Programmiersprache Basic geschrieben, nicht in C\+\+. \(Das DAO SDK enthält jedoch eine Reihe von C\+\+\-Beispielen, die MFC nicht verwenden.\)  
  
##  <a name="_core_mfc_documentation_and_odbc_documentation"></a> MFC\-Dokumentation und ODBC\-Dokumentation  
 Die MFC\-Dokumentation für die MFC\-ODBC\-Klassen ist anders eingeteilt.  Die MFC\-ODBC\-Klassen bilden eine hohe Abstraktionsebene, die sich nicht auf einen Wrapper der ODBC\-API, sondern auf ODBC stützt.  Daher gibt es zwischen diesen beiden Dokumentationen weniger Verbindungspunkte als zwischen der MFC\- und der DAO\-Dokumentation.  In der ODBC\-Dokumentation wird die Sprache C verwendet, die C\+\+ wesentlich ähnlicher ist als Basic.  
  
## Siehe auch  
 [MFC\-Datenbankklassen \(ODBC und DAO\)](../data/mfc-database-classes-odbc-and-dao.md)   
 [Grundlagen zu ODBC](../data/odbc/odbc-basics.md)