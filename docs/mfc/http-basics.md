---
title: "Grundlagen zu HTTP"
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
  - "HTTP-Anforderungen, Rückgabecodes"
  - "HTTP, Rückgabecodes"
  - "Rückgabecodes"
ms.assetid: 5b7421bf-42c8-4f3a-8566-8ff5957f58cc
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Grundlagen zu HTTP
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie eine Internetanwendung schreiben, müssen Sie häufig und fügen die Informationen in unterschiedlichen HTTP\-Headerwerten hinzu.  Rückgabecodes geben den Erfolg oder das Fehlschlagen des angeforderten Ereignisses angezeigt.  Einige Rückgabecodes sind in der folgenden Tabelle aufgeführt.  
  
|Rückgabecode|Bedeutung|  
|------------------|---------------|  
|200|Die lokalisierte URL, Übertragung folgt|  
|400|Unverständliche Anforderung|  
|404|Angeforderte URL nicht gefunden|  
|405|Server nicht unterstützt angeforderte Methode|  
|500|Unbekannter Serverfehler|  
|503|Dienst nicht verfügbar|  
  
 Die HTTP\-Antworten sind wie in der folgenden Tabelle gezeigt.  
  
|Gruppieren|Bedeutung|  
|----------------|---------------|  
|200–299|Erfolgreich|  
|300–399|Information|  
|400–499|Anforderungsfehler|  
|500–599|Serverfehler|  
  
 Das Hypertext Transfer Protocol \(HTTP\) ist ein Protokoll auf Anwendungsebene für HypermediaInformationssysteme.  Weitere Informationen über HTTP und z Webbrowser und Server kommunizieren, finden Sie die Spezifikation des Hypertext Transfer Protocol \(HTTP\):  
  
 [http:\/\/www.w3.org\/pub\/WWW\/Protocols\/](http://www.w3.org/pub/WWW/Protocols/)  
  
## Siehe auch  
 [Grundlagen der MFC\-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)