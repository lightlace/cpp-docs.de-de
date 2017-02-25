---
title: "CHttpFile Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHttpFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHttpFile class"
  - "HTTP-Dateien"
  - "HTTP requests, requesting and reading files"
ms.assetid: 399e7c68-bbce-4374-8c55-206e9c7baac6
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CHttpFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität bereit, um Dateien auf einem HTTP\-Server anfordern und zu lesen.  
  
## Syntax  
  
```  
class CHttpFile : public CInternetFile  
```  
  
## Mitglieder  
  
### Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CHttpFile::CHttpFile](../Topic/CHttpFile::CHttpFile.md)|Erstellt ein `CHttpFile`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CHttpFile::AddRequestHeaders](../Topic/CHttpFile::AddRequestHeaders.md)|Fügt Header der Anforderung hinzu, die zu einem HTTP\-Server gesendet wird.|  
|[CHttpFile::EndRequest](../Topic/CHttpFile::EndRequest.md)|Beendet eine Anforderung, die zu einem HTTP\-Server mit der [SendRequestEx](../Topic/CHttpFile::SendRequestEx.md)\-Memberfunktion gesendet wird.|  
|[CHttpFile::GetFileURL](../Topic/CHttpFile::GetFileURL.md)|Ruft die URL für die angegebene Datei ab.|  
|[CHttpFile::GetObject](../Topic/CHttpFile::GetObject.md)|Ruft das Zielobjekt des Verbs in einer Anforderung zu einem HTTP\-Server ab.|  
|[CHttpFile::GetVerb](../Topic/CHttpFile::GetVerb.md)|Ruft das Verb ab, das in einer Anforderung zu einem HTTP\-Server verwendet wurde.|  
|[CHttpFile::QueryInfo](../Topic/CHttpFile::QueryInfo.md)|Gibt die Antwort oder der Anforderungsheader vom HTTP\-Server zurück.|  
|[CHttpFile::QueryInfoStatusCode](../Topic/CHttpFile::QueryInfoStatusCode.md)|Ruft den Statuscode ab, der mit einer HTTP\-Anforderung zugeordnet wird und platziert ihn im angegebenen `dwStatusCode`\-Parameter.|  
|[CHttpFile::SendRequest](../Topic/CHttpFile::SendRequest.md)|Sendet eine Anforderung zu einem HTTP\-Server.|  
|[CHttpFile::SendRequestEx](../Topic/CHttpFile::SendRequestEx.md)|Sendet eine Anforderung zu einem HTTP\-Server mithilfe der [Schreiben Sie](../Topic/CInternetFile::Write.md) oder [WriteString](../Topic/CInternetFile::WriteString.md)\-Methoden von `CInternetFile`.|  
  
## Hinweise  
 Wenn die Internet\-Sitzung Daten aus einem HTTP\-Server liest, müssen Sie eine Instanz von `CHttpFile` erstellen.  
  
 Um zu erfahren mehr zum `CHttpFile` mit den anderen MFC\-Internetklassen funktioniert, finden Sie im Artikel [Webprogrammierung mit WinInet\-Klassen](../../mfc/win32-internet-extensions-wininet.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Die C\-Datei](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CHttpFile`  
  
## Anforderungen  
 **Header:** afxinet.h  
  
## Siehe auch  
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile Class](../../mfc/reference/cgopherfile-class.md)   
 [CHttpConnection Class](../../mfc/reference/chttpconnection-class.md)