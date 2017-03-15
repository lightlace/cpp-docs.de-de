---
title: "Automatisierungsclients | Microsoft Docs"
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
  - "Automatisierungsclients"
  - "Clients"
  - "Clients, Automatisierung"
  - "Typbibliotheken, Automatisierungsclients"
ms.assetid: 84e34a79-06f6-4752-a33b-ae0ede1d8ecf
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Automatisierungsclients
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Automatisierung ermöglicht es, sodass die Anwendung die Objekte behandelt, die in einer anderen Anwendung implementiert werden oder Objekte verfügbar gemacht werden, sodass sie bearbeitet werden.  Ein Automatisierungsclient ist eine Anwendung, die die verfügbar gemachten Objekte bearbeiten kann, die eine andere Anwendung gehören.  Die Anwendung, die die Objekte verfügbar macht, wird den Automatisierungsserver aufgerufen.  Der Client bearbeitet die Serveranwendung, indem er die Eigenschaften und die Funktionen dieser Objekte zugreift.  
  
### Typen von Automatisierungs\-Clients  
 Es gibt zwei Typen Automatisierungsclients:  
  
-   Clients, die dynamisch \(zur Laufzeit\) Informationen über die Eigenschaften und die Vorgänge des Servers abgerufen.  
  
-   Clients, die die statische Informationen besitzen \(zur Kompilierzeit\) bereitgestellt dass die Eigenschaften und den Vorgängen des Servers angeben.  
  
 Clients der ersten Art rufen Informationen über die Methoden und Eigenschaften Servers ab, indem sie den `IDispatch` abfragen OLE\- Systems Mechanismus.  Obwohl es angemessen ist, für dynamische Clients zu verwenden, ist `IDispatch`, schwierig für statische Clients zu verwenden, in denen die Objekte, die bestimmt werden, zur Kompilierungszeit bekannter müssen.  Für statische gebundene Clients bieten die Microsoft Foundations\-Klassen die [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md)\-Klasse.  
  
 Statische gebundene Clients verwenden eine Proxyklasse, die statisch mit der Anwendung verknüpft wird.  Diese Klasse stellt eine typsichere C\+\+\-Kapselung der Eigenschaften und der Vorgänge Serveranwendung.  
  
 Die `COleDispatchDriver`\-Klasse stellt die grundlegende Unterstützung für die Clientseite der Automatisierung.  Verwenden des Dialogfelds `Add New Item` erstellen Sie eine Klasse, die von `COleDispatchDriver` abgeleitet wird.  
  
 Geben Sie dann der Typbibliotheksdatei an, die die Eigenschaften und Funktionen des Objekts der Serveranwendung beschreibt.  Das Dialogfeld Element hinzufügen liest diese Datei und erstellt von `COleDispatchDriver` abgeleitete Klasse, mit Memberfunktionen, die die Anwendung aufrufen kann, um auf die Serveranwendung in C\+\+ in einer typsicheren Weise zugreifen.  Die zusätzlichen Funktionen, die von `COleDispatchDriver` geerbt werden, vereinfachen den Prozess des Aufrufens des richtigen Automatisierungsservers.  
  
### Behandeln von Ereignissen in den Automatisierungs\-Clients  
 Wenn Sie Ereignisse im Automatisierungsclient behandeln möchten, müssen Sie eine Senkenschnittstelle hinzufügen.  MFC stellt Assistentenunterstützung, um Senkenschnittstellen für ActiveX\-Steuerelemente, jedoch keine Unterstützung für andere COM\-Server hinzuzufügen.  Informationen dazu, wie einer Senkenschnittstelle in einem MFC\-Client für die Quellschnittstellen hinzufügt, die durch COM Server beschrieben werden, finden Sie HOWTO: Erstellen Sie eine Senken\-Schnittstelle im MFC\-basierten COM\-Clients \(181845 KB\) an [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;181845](http://support.microsoft.com/default.aspx?scid=kb;en-us;181845).  
  
## Siehe auch  
 [Automatisierungsclients: Verwenden von Typbibliotheken](../mfc/automation-clients-using-type-libraries.md)   
 [Automatisierung](../mfc/automation.md)   
 [MFC\-Anwendungs\-Assistent](../mfc/reference/mfc-application-wizard.md)