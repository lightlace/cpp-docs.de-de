---
title: "Windows Sockets: Umwandeln von Zeichenfolgen | Microsoft Docs"
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
  - "Sockets [C++], Multibytezeichenfolge-Konvertierungsprobleme"
  - "Zeichenfolgenkonvertierung, Mehrbytezeichenfolgen"
  - "Windows-Sockets [C++], Multibytezeichenfolgekonvertierung"
ms.assetid: 9df522b5-6b23-41e0-bb96-e4e623baf141
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Windows Sockets: Umwandeln von Zeichenfolgen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel und zwei Begleitartikel beschreiben einige Probleme bei der Windows Socket\-Programmierung.  Dieser Artikel enthält das Konvertieren von Zeichenfolgen.  Die anderen Probleme werden in [Windows Sockets: Blockieren](../mfc/windows-sockets-blocking.md) und [Windows Sockets: Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md) behandelt.  
  
 Wenn Sie von der [CAsyncSocket](../mfc/reference/casyncsocket-class.md) verwenden oder leiten, müssen Sie diese Probleme selbst verwalten.  Wenn Sie von der [CSocket](../mfc/reference/csocket-class.md) verwenden oder leiten, verwaltet MFC sie für Sie.  
  
## Konvertieren von Zeichenfolgen  
 Wenn Sie zwischen Anwendungen kommunizieren, die Zeichenfolgen verwenden, die in verschiedenen Breitzeichenformaten, wie Unicode oder Mehrbyte\-Zeichensätzen \(MBCS\) gespeichert werden oder zwischen einem dieser und einer Anwendung mithilfe ANSI\-Zeichenfolgen, müssen Sie die Konvertierungen sich unter `CAsyncSocket` verwalten.  Das `CArchive`\-Objekt, das einem `CSocket`\-Objekt verwendet wird, verwaltet diese Konvertierung für Sie von den Funktionen der [CString](../atl-mfc-shared/reference/cstringt-class.md).  Weitere Informationen finden Sie in der Windows Socket\-Spezifikation, in [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen finden Sie unter:  
  
-   [Windows Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Sockets: Hintergrund](../mfc/windows-sockets-background.md)  
  
-   [Windows Sockets: Streamsockets](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)  
  
## Siehe auch  
 [Windows\-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)