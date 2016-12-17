---
title: "CGopherLocator Class"
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
  - "CGopherLocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CGopherLocator class"
  - "gopher locator"
  - "Internet, gopher searches"
ms.assetid: 6fcc015f-5ae6-4959-b936-858634c71019
caps.latest.revision: 22
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CGopherLocator Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft einen Gopher "Locator" aus einem Gopherserver ab, bestimmt den Typ des Locator, und macht den Locator so für [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md).  
  
> [!NOTE]
>  Die Klassen `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` und Member sind veraltet, da sie nicht an der Windows XP\-Plattform verwenden, aber sie werden weiterhin, um an früheren Plattformen zu arbeiten.  
  
## Syntax  
  
```  
class CGopherLocator : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CGopherLocator::CGopherLocator](../Topic/CGopherLocator::CGopherLocator.md)|Erstellt ein `CGopherLocator`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CGopherLocator::GetLocatorType](../Topic/CGopherLocator::GetLocatorType.md)|Analysiert einen Gopher\-Locator und bestimmt die Attribute.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CGopherLocator::operator LPCTSTR](../Topic/CGopherLocator::operator%20LPCTSTR.md)|Greift direkt auf die Zeichen zu, die in einem `CGopherLocator`\-Objekt als Zeichenfolge in C\-Format gespeichert werden.|  
  
## Hinweise  
 Eine Anwendung muss den Locator eines Gopherservers abrufen, bevor sie Informationen von diesem Server abrufen kann.  Sobald sie \- Locator hat, muss sie \- Locator als nicht transparenten Token behandeln.  
  
 Jeder Gopher\-Locator hat Attribute, die den Typ der Datei oder des Servers bestimmen, die gefunden werden.  Siehe [GetLocatorType](../Topic/CGopherLocator::GetLocatorType.md) für eine Liste von Typen aus Gopher\-Locatoren.  
  
 Eine Anwendung verwendet normalerweise den Locator für Aufrufe [CGopherFileFind::FindFile](../Topic/CGopherFileFind::FindFile.md), um eine bestimmte Informationen abzurufen.  
  
 Um zu erfahren mehr zum `CGopherLocator` mit den anderen MFC\-Internetklassen funktioniert, finden Sie im Artikel [Webprogrammierung mit WinInet\-Klassen](../../mfc/win32-internet-extensions-wininet.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CGopherLocator`  
  
## Anforderungen  
 **Header:**  afxinet.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CGopherFileFind Class](../../mfc/reference/cgopherfilefind-class.md)