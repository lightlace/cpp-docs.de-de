---
title: "Schritte in einer typischen Internetclientanwendung | Microsoft Docs"
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
  - "Internetanwendungen, Clientanwendungen"
  - "Internetclientanwendungen, Allgemeine Tabelle"
  - "WinInet-Klassen, Programmieren"
ms.assetid: 7aba135c-7c15-4e2f-8c34-bbaf792c89a6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Schritte in einer typischen Internetclientanwendung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In der folgenden Tabelle werden die Schritte angezeigt, die Sie in einer typischen Internet\-Clientanwendung ausgeführt haben.  
  
|Das Ziel|Aktionen, die Sie ausführen|Effekte|  
|--------------|---------------------------------|-------------|  
|Starten Sie eine Internet\-Sitzung.|Erstellen Sie ein [CInternetSession](../mfc/reference/cinternetsession-class.md)\-Objekt.|Initialisiert WinInet\-Klassen und schließt am Server an.|  
|Legen Sie eine Internet\-Abfrageoption fest \(TIMEOUTgrenze oder die Anzahl der Wiederholungen, beispielsweise\).|Verwenden Sie [CInternetSession::SetOption](../Topic/CInternetSession::SetOption.md).|Gibt FALSE zurück, wenn Vorgang nicht erfolgreich war.|  
|Richten Sie eine Rückruffunktion ein, um den Status der Sitzung zu überwachen.|Verwenden Sie [CInternetSession::EnableStatusCallback](../Topic/CInternetSession::EnableStatusCallback.md).|Richtet einen Rückruf an [CInternetSession::OnStatusCallback](../Topic/CInternetSession::OnStatusCallback.md).  Überschreiben Sie `OnStatusCallback`, um eine eigene Rückrufroutine zu erstellen.|  
|Schließen Sie mit einem Internet\-Server, einen Intranetserver oder eine lokale Datei an.|Verwenden Sie [CInternetSession::OpenURL](../Topic/CInternetSession::OpenURL.md).|Analysiert die URL und öffnet eine Verbindung auf dem angegebenen Server.  Gibt [CStdioFile](../mfc/reference/cstdiofile-class.md) zurückgegeben \(wenn Sie `OpenURL` ein lokaler Dateiname übergeben\).  Dies ist das Objekt, durch das Sie auf Daten vom Server oder aus der Datei abgerufen haben.|  
|Lesen aus der Datei.|Verwenden Sie [CInternetFile::Read](../Topic/CInternetFile::Read.md).|Liest die angegebene Anzahl von Bytes mithilfe eines Puffers, den Sie angeben.|  
|Behandeln von Ausnahmen|Verwenden Sie die [CInternetException](../mfc/reference/cinternetexception-class.md)\-Klasse.|Behandelt alle gängigen Internet\-Ausnahmetypen.|  
|Beenden Sie die Internet\-Sitzung.|Löschen Sie sich das Objekt unter [CInternetSession](../mfc/reference/cinternetsession-class.md).|Bereinigt automatisch geöffnet Dateihandles und Verbindungen.|  
  
## Siehe auch  
 [Win32\-Interneterweiterungen \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Voraussetzungen für Internetclientklassen](../mfc/prerequisites-for-internet-client-classes.md)   
 [Schreiben einer Internetclientanwendung mithilfe von MFC\-WinInet\-Klassen](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)