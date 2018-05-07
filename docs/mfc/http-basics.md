---
title: Grundlagen zu HTTP | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTTP [MFC], return codes
- return codes [MFC]
- HTTP requests [MFC], return codes
ms.assetid: 5b7421bf-42c8-4f3a-8566-8ff5957f58cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 56a2692edd9d41f80023e44f4ca8172cba8f9d00
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="http-basics"></a>Grundlagen zu HTTP
Wenn Sie eine Internet-Anwendung zu schreiben, Sie häufig untersuchen und die Informationen im HTTP-Header hinzufügen. Geben Sie Rückgabecodes an, den Erfolg oder Fehler des angeforderten Ereignisses. Mehrere häufige Rückgabecodes werden in der folgenden Tabelle aufgeführt.  
  
|Rückgabecode|Bedeutung|  
|-----------------|-------------|  
|300|URL befindet, Übertragung folgt.|  
|400|Unzulässige Anforderung|  
|404|Angeforderte URL wurde nicht gefunden.|  
|405|Server unterstützt nicht die angeforderte Methode|  
|500|Unbekannter Serverfehler|  
|503|Dienst nicht verfügbar.|  
  
 Die HTTP-Antworten werden gruppiert, wie in der folgenden Tabelle gezeigt.  
  
|Gruppieren|Bedeutung|  
|-----------|-------------|  
|200-299|Erfolgreich|  
|300-399|Information|  
|400-499|Fehler beim Anfordern|  
|500-599|Serverfehler|  
  
 Das Hypertext Transfer-Protokoll (HTTP) ist ein Protokoll auf Anwendungsebene für Hypermedia-Systeme. Weitere Informationen über HTTP und die Kommunikation zwischen Webbrowsern und Servern finden Sie in der Spezifikation Hypertext Transfer Protocol (HTTP):  
  
 [http://www.w3.org/pub/WWW/Protocols/](http://www.w3.org/pub/www/protocols/)  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen der MFC-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)

