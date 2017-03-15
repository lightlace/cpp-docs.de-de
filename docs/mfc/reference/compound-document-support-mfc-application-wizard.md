---
title: "Verbunddokumentunterst&#252;tzung, MFC-Anwendungs-Assistent | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.exe.compdoc"
dev_langs: 
  - "C++"
ms.assetid: 42e1af83-12c4-438d-92eb-13835afdb148
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Verbunddokumentunterst&#252;tzung, MFC-Anwendungs-Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Auf dieser Seite des MFC\-Anwendungs\-Assistenten geben Sie an, in welchem Umfang Verbunddokumente und Active Documents von der Anwendung unterstützt werden.  Damit Verbunddokumente und Dokumentvorlagen von der Anwendung unterstützt werden, muss die Anwendung die Dokument\-\/Ansichtarchitektur unterstützen.  
  
 Die Anwendung beinhaltet standardmäßig keine Unterstützung für Verbunddokumente.  Wenn Sie diese Standardeinstellung übernehmen, ist die Anwendung nicht in der Lage, Active Documents oder Verbunddateien zu unterstützen.  
  
 **Unterstützung für Verbunddokumente**  
 Legt fest, ob die Anwendung Container\- oder Serverunterstützung bzw. beides enthält.  Weitere Informationen über diesen Bereich finden Sie unter:  
  
-   [Container: Implementieren eines Containers](../../mfc/containers-implementing-a-container.md)  
  
-   [Server: Implementieren eines Servers](../../mfc/servers-implementing-a-server.md)  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|**Kein**|Gibt an, dass Object Linking and Embedding \(OLE\) nicht unterstützt wird.  Der Anwendungs\-Assistent erstellt standardmäßig eine Anwendung ohne ActiveX\-Unterstützung.|  
|**Container**|Enthält verknüpfte und eingebettete Objekte.|  
|**Miniserver**|Gibt an, dass die Anwendung Verbunddokumentobjekte erstellen und verwalten kann.  Beachten Sie, dass Miniserver nicht eigenständig ausgeführt werden können und nur eingebettete Elemente unterstützen.|  
|**Vollserver**|Gibt an, dass die Anwendung Verbunddokumentobjekte erstellen und verwalten kann.  Vollserver können eigenständig ausgeführt werden und unterstützen sowohl verknüpfte als auch eingebettete Elemente.|  
|**Container\/Voll\-Server**|Gibt an, dass die Anwendung sowohl ein Container als auch ein Server sein kann.  Bei einem Container handelt es sich um eine Anwendung, die eingebettete oder verknüpfte Elemente in ihre eigenen Dokumente integrieren kann.  Ein Server ist eine Anwendung, die Automatisierungselemente für Containeranwendungen erstellen kann.|  
  
 **Zusätzliche Optionen**  
 Gibt an, ob die Anwendung Active Documents unterstützt.  Weitere Informationen über dieses Feature finden Sie unter [Active Documents](../../mfc/active-documents.md).  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|**Active Document\-Server**|Gibt an, dass die Anwendung Active Documents erstellen und verwalten kann.  Bei Auswahl dieser Option müssen Sie im Feld **Dateierweiterung** auf der Seite [Zeichenfolgen für Dokumentvorlagen](../../mfc/reference/document-template-strings-mfc-application-wizard.md) des Assistenten eine Dateierweiterung für den Active Document\-Server angeben.  Weitere Informationen finden Sie unter [Active Document\-Server](../../mfc/active-document-servers.md).|  
|**Active Document\-Container**|Gibt an, dass im Anwendungsrahmen Active Documents enthalten sein können.  Active Documents können beispielsweise Internet Explorer\- oder Office\-Dokumente, wie Microsoft Word\-Dateien oder Excel\-Arbeitsblätter, enthalten.  Weitere Informationen finden Sie unter [Active Document\-Kapselung](../../mfc/active-document-containment.md).|  
|**Unterstützung für Verbunddateien**|Verhindert, dass die Dokumente der Containeranwendung mit dem Verbunddateiformat serialisiert werden.  Mit dieser Option wird eine Datei mit Objekten als Ganzes in den Arbeitsspeicher geladen.  Das inkrementelle Speichern in einzelnen Objekten ist nicht möglich.  Wenn ein Objekt geändert und anschließend gespeichert wird, werden alle in der Datei enthaltenen Objekte gespeichert.|  
  
## Siehe auch  
 [MFC\-Anwendungs\-Assistent](../../mfc/reference/mfc-application-wizard.md)