---
title: "CFileFind Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CFileFind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFileFind class"
  - "Dateien [C++], Suchen"
  - "Internet files [C++], Suchen"
  - "local files"
  - "local files, Suchen nach"
  - "URLs [C++], Suchen nach"
ms.assetid: 9990068c-b023-4114-9580-a50182d15240
caps.latest.revision: 22
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CFileFind Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Führt lokale Dateisuchen aus und ist die Basisklasse für [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) und [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md), die Internetdateisuchen ausführen.  
  
## Syntax  
  
```  
class CFileFind : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CFileFind::CFileFind](../Topic/CFileFind::CFileFind.md)|Erstellt ein `CFileFind`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CFileFind::Close](../Topic/CFileFind::Close.md)|Enthält die Anforderung.|  
|[CFileFind::FindFile](../Topic/CFileFind::FindFile.md)|Sucht in einem Verzeichnis für einen angegebenen Dateinamen.|  
|[CFileFind::FindNextFile](../Topic/CFileFind::FindNextFile.md)|Fügt eine Dateisuche aus einem früheren Aufruf [FindFile](../Topic/CFileFind::FindFile.md) fort.|  
|[CFileFind::GetCreationTime](../Topic/CFileFind::GetCreationTime.md)|Ruft die Zeit ab, die die Datei erstellt wurde.|  
|[CFileFind::GetFileName](../Topic/CFileFind::GetFileName.md)|Ruft den Namen, einschließlich der Erweiterung, der gesuchten Datei ab|  
|[CFileFind::GetFilePath](../Topic/CFileFind::GetFilePath.md)|Ruft den vollständigen Pfad der gesuchten Datei ab.|  
|[CFileFind::GetFileTitle](../Topic/CFileFind::GetFileTitle.md)|Ruft den Titel der gesuchten Datei ab.  Der Name enthält keine Erweiterung.|  
|[CFileFind::GetFileURL](../Topic/CFileFind::GetFileURL.md)|Ruft die URL, einschließlich den Dateipfad, der gesuchten Datei ab.|  
|[CFileFind::GetLastAccessTime](../Topic/CFileFind::GetLastAccessTime.md)|Ruft die Zeit ab, die auf die Datei zuletzt verwendet wurden.|  
|[CFileFind::GetLastWriteTime](../Topic/CFileFind::GetLastWriteTime.md)|Ruft die Zeit ab, die die Datei zuletzt geändert und gespeichert wurde.|  
|[CFileFind::GetLength](../Topic/CFileFind::GetLength.md)|Ruft die Länge der gesuchten Datei, in Bytes ab.|  
|[CFileFind::GetRoot](../Topic/CFileFind::GetRoot.md)|Ruft das Stammverzeichnis der gesuchten Datei ab.|  
|[CFileFind::IsArchived](../Topic/CFileFind::IsArchived.md)|Bestimmt, ob die gesuchte Datei protokolliert wird.|  
|[CFileFind::IsCompressed](../Topic/CFileFind::IsCompressed.md)|Bestimmt, ob die gesuchte Datei komprimiert wird.|  
|[CFileFind::IsDirectory](../Topic/CFileFind::IsDirectory.md)|Bestimmt, ob die gesuchte Datei ein Verzeichnis befindet.|  
|[CFileFind::IsDots](../Topic/CFileFind::IsDots.md)|Bestimmt, ob der Name der gesuchten Datei hat den Namen "." oder ". ", angibt, das eigentlich ein Verzeichnis befindet.|  
|[CFileFind::IsHidden](../Topic/CFileFind::IsHidden.md)|Bestimmt, ob die gesuchte Datei ausgeblendet ist.|  
|[CFileFind::IsNormal](../Topic/CFileFind::IsNormal.md)|Bestimmt, ob die gesuchte Datei normal ist \(das heißt, hat keine anderen Attribute\).|  
|[CFileFind::IsReadOnly](../Topic/CFileFind::IsReadOnly.md)|Bestimmt, ob die gesuchte Datei schreibgeschützt ist.|  
|[CFileFind::IsSystem](../Topic/CFileFind::IsSystem.md)|Bestimmt, ob die gesuchte Datei eine Systemdatei ist.|  
|[CFileFind::IsTemporary](../Topic/CFileFind::IsTemporary.md)|Bestimmt, ob die gesuchte Datei temporär ist.|  
|[CFileFind::MatchesMask](../Topic/CFileFind::MatchesMask.md)|Gibt die gewünschte Dateiattribute der zu durchsuchenden Datei an.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CFileFind::CloseContext](../Topic/CFileFind::CloseContext.md)|Enthält die Datei, die vom aktuellen Suchenhandle angegeben wird.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CFileFind::m\_pTM](../Topic/CFileFind::m_pTM.md)|Zeiger auf einen `CAtlTransactionManager`\-Objekt.|  
  
## Hinweise  
 `CFileFind` enthält Memberfunktionen ein, die eine Suche starten, eine Datei suchen und den Titel, den Namen oder den Pfad der Datei zurückgeben.  Für Internet\-Suchen gibt die Memberfunktion [GetFileURL](../Topic/CFileFind::GetFileURL.md) die URL der Datei zurück.  
  
 `CFileFind` ist die Basisklasse für zwei weitere MFC\-Klassen, die entwickelt wurden, um Typen des bestimmten Servers zu suchen: `CGopherFileFind` funktioniert speziell mit Gopherservern und `CFtpFileFind` Arbeiten speziell mit FTP\-Servern.  Zusammen ergeben diese drei Klassen einen nahtlosen Mechanismus bereit, damit der Client Dateien, unabhängig vom Serverprotokoll, den Dateityp oder Speicherort, entweder auf einem lokalen Computer oder einem Remoteserver sucht.  
  
 Im folgenden Code werden alle Dateien im aktuellen Verzeichnis auf und gibt den Namen jeder Datei:  
  
 [!CODE [NVC_MFCFiles#31](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCFiles#31)]  
  
 Um das Beispiel einfach zu übergeben, verwendet dieser Code die `cout`\-Standard\-C\+\+\-Bibliotheksklasse.  Die `cout` Zeile kann durch einen Aufruf `CListBox::AddString` beispielsweise in ein Programm ersetzt werden mit einer grafischen Benutzeroberfläche.  
  
 Weitere Informationen dazu, wie `CFileFind` und die anderen WinInet\-Klassen, finden Sie im Artikel [Webprogrammierung mit WinInet\-Klassen](../../mfc/win32-internet-extensions-wininet.md) verwendet.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CFileFind`  
  
## Anforderungen  
 **Header:**  afx.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind Class](../../mfc/reference/cftpfilefind-class.md)   
 [CGopherFileFind Class](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile Class](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile Class](../../mfc/reference/chttpfile-class.md)