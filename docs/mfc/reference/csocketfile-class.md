---
title: "CSocketFile Class"
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
  - "CSocketFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "archives [C++], Netzwerk"
  - "CSocketFile class"
  - "networks [C++], archive"
  - "networks [C++], serializing to"
  - "Serialisierung [C++], Netzwerk"
  - "SOCKET handle"
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
caps.latest.revision: 24
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CSocketFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Objekt `CFile` zum Senden und Empfangen von Daten über ein Netzwerk zu Windows Sockets.  
  
## Syntax  
  
```  
class CSocketFile : public CFile  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSocketFile::CSocketFile](../Topic/CSocketFile::CSocketFile.md)|Erstellt ein `CSocketFile`\-Objekt.|  
  
## Hinweise  
 Sie können das `CSocketFile`\-Objekt zu einem `CSocket`\-Objekt zu diesem Zweck anfügen.  Sie können auch und führen normalerweise, das `CSocketFile`\-Objekt zu einem `CArchive`\-Objekt anzufügen, um das Senden und Empfangen von Daten mit MFC\-Serialisierung zu vereinfachen.  
  
 Um \(senden\) Daten zu serialisieren, fügen Sie sie in das Archiv ein, das `CSocketFile`\-Memberfunktionen aufruft der Daten auf dem `CSocket`\-Objekt schreiben.  Um \(empfangen\) Daten zu deserialisieren, extrahieren Sie im Archiv.  Dadurch wird das Archivdatei, `CSocketFile`\-Memberfunktionen aufrufen, um Daten vom `CSocket`\-Objekt.  
  
> [!TIP]
>  Neben der Verwendung von `CSocketFile`, wie hier beschrieben, können Sie es, wie ein eigenständiges Dateiobjekt, als Sie mit `CFile`, kann seine Basisklasse verwenden.  Sie können `CSocketFile` auch mit allen archivbasierten MFC\-Serialisierungsfunktionen verwenden.  Da `CSocketFile` nicht die gesamte Funktionalität von `CFile` unterstützt, serialisieren einige Standard\-MFC\-Funktionen sind nicht kompatibel mit `CSocketFile`.  Dies ist von der Klasse `CEditView` insbesondere.  Versuchen Sie nicht, `CEditView` Daten über ein Objekt `CArchive` zu serialisieren, das einem Objekt unter Verwendung `CSocketFile``CEditView::SerializeRaw` angefügt wird, Verwendung **CEditView::Serialize** stattdessen.  Die `SerializeRaw`\-Funktion erwartet das Dateiobjekt, um Funktionen, z `Seek` verfügen, das `CSocketFile` nicht über verfügt.  
  
 Wenn Sie `CArchive` mit `CSocketFile` und `CSocket` verwenden, treten unter Umständen eine Situation an, in der **CSocket::Receive** eine Schleife \(durch **PumpMessages\(FD\_READ\)**\) auf die angeforderte Menge von Bytes wartenden eingibt.  Dies ist, da Windows Sockets nur einen recv Aufruf pro FD\_READ\-Benachrichtigung gewähren, aber `CSocketFile` und `CSocket` können mehrere recv Aufrufe pro FD\_READ.  Wenn Sie ein FD\_READ abrufen, wenn keine zu lesen, gibt Daten, hängt die Anwendung.  Wenn Sie nie ein anderes FD\_READ abrufen, beendet die Anwendung auf, über dem Socket zu kommunizieren.  
  
 Sie können dieses Problem wie folgt auflösen.  In der `OnReceive`\-Methode der Socketklasse, Aufruf **CAsyncSocket::IOCtl\(FIONREAD, ...\)**, bevor Sie die `Serialize`\-Methode der Nachrichtenklasse aufrufen, wenn die erwarteten vom Socket gelesen werden Daten, die Größe eines TCP\-Paket überschreiten \(maximale Übertragungseinheit des Netzwerkmediums, normalerweise mindestens 1096 Bytes\).  Wenn die Größe der verfügbaren Daten weniger als erforderlich ist, Sie warten alle empfangen werden nur Daten, und starten Sie dann den Lesevorgang.  
  
 Im folgenden Beispiel ist `m_dwExpected` die ungefähre Anzahl von Bytes, die der Benutzer erwartet, zu empfangen.  Es wird davon ausgegangen, dass Sie es an anderer Stelle im Code deklarieren.  
  
 [!CODE [NVC_MFCSocketThread#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSocketThread#4)]  
  
 Weitere Informationen finden Sie unter [Windows Sockets in MFC](../../mfc/windows-sockets-in-mfc.md), [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md) sowie [Windows Sockets 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Die C\-Datei](../../mfc/reference/cfile-class.md)  
  
 `CSocketFile`  
  
## Anforderungen  
 **Header:**  afxsock.h  
  
## Siehe auch  
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket Class](../../mfc/reference/casyncsocket-class.md)   
 [CSocket Class](../../mfc/reference/csocket-class.md)