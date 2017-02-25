---
title: "ASP, ATL-Assistent f&#252;r Active Server Page-Komponenten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.asp.asp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Assistent für Active Server Page-Komponenten, ASP"
ms.assetid: 4d8cafd6-5e12-4461-8911-29288896af3c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# ASP, ATL-Assistent f&#252;r Active Server Page-Komponenten
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Auf dieser Seite des ATL\-Assistenten für Active Server Page\-Komponenten können Sie optionale Einstellungen zur Behandlung von Informationen und Zuständen der ASP\-Komponente festlegen.  
  
 **Optionale Methoden**  
 Fügt dem Objekt die optionalen ASP\-Methoden **OnStartPage** und **OnEndPage** hinzu.  Diese Option muss aktiviert sein, damit immanente Active Server Pages\-Objekte festgelegt werden können.  Die Option ist standardmäßig aktiviert.  
  
-   **OnStartPage\/OnEndPage** [OnStartPage](https://msdn.microsoft.com/en-us/library/ms691624.aspx) wird aufgerufen, wenn das Skript zum ersten Mal versucht, auf das Objekt zuzugreifen.  **OnEndPage** wird aufgerufen, wenn die Skriptverarbeitung durch das Objekt abgeschlossen ist.  
  
 **Immanente Objekte**  
 Die Option **OnStartPage\/OnEndPage** muss aktiviert sein, damit immanente ASP\-Objekte festgelegt werden können.  
  
|Option|Description|  
|------------|-----------------|  
|**Anforderung**|Ermöglicht den Zugriff auf das immanente Anforderungsobjekt der Active Server Pages.  Das Anforderungsobjekt wird zur Übergabe einer HTTP\-Anforderung verwendet.|  
|**Antwort**|Ermöglicht den Zugriff auf das immanente Antwortobjekt der Active Server Pages.  Das Antwortobjekt sendet als Reaktion auf eine Anforderung Informationen für den Benutzer an den Browser.|  
|**Sitzung**|Ermöglicht den Zugriff auf das immanente Sitzungsobjekt der Active Server Pages.  Das Sitzungsobjekt verwaltet Informationen über die aktuelle Benutzersitzung und wird zum Speichern und Abrufen von Zustandsinformationen verwendet.|  
|**Anwendung**|Ermöglicht den Zugriff auf das immanente Anwendungsobjekt der Active Server Pages.  Das Anwendungsobjekt wird zur Verwaltung des Zustands verwendet, der von mehreren ASP\-Objekten gemeinsam genutzt wird.|  
|**Server**|Ermöglicht den Zugriff auf das immanente Serverobjekt der Active Server Pages.  Mithilfe des Serverobjekts können andere ASP\-Objekte erstellt werden.|  
  
## Siehe auch  
 [ATL\-Assistent für Active Server Page\-Komponenten](../../atl/reference/atl-active-server-page-component-wizard.md)   
 [ATL Active Server Page Component](../../atl/reference/adding-an-atl-active-server-page-component.md)