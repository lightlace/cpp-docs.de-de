---
title: "Verbunddokumentunterstützung, MFC-Anwendung-Assistenten | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.mfc.exe.compdoc
dev_langs: C++
ms.assetid: 42e1af83-12c4-438d-92eb-13835afdb148
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9390f3849cd7511054f1248205c5d2c408cb7e71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compound-document-support-mfc-application-wizard"></a>Verbunddokumentunterstützung, MFC-Anwendungs-Assistent
Geben Sie auf dieser Seite des Assistenten für MFC-Anwendung an, zu welchem Grad die Anwendung zusammengesetzten und active Document-Unterstützung bietet. Die Anwendung muss die Dokument-/Ansichtarchitektur zur Unterstützung von Verbunddokumente und Dokumentvorlagen unterstützen.  
  
 Standardmäßig enthält die Anwendung keine Unterstützung für Verbunddokumente. Wenn Sie diese Standardeinstellung übernehmen, kann nicht für Ihre Anwendung die aktive Dokumente oder Verbunddateien unterstützen.  
  
 **Unterstützung für Verbunddokumente**  
 Bestimmt, ob Ihre Anwendung Container-Unterstützung, Unterstützung für Server oder beides enthält. Weitere Informationen zu diesem Bereich finden Sie unter:  
  
-   [Container: Implementieren eines Containers](../../mfc/containers-implementing-a-container.md)  
  
-   [Server: Implementieren eines Servers](../../mfc/servers-implementing-a-server.md)  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Keine**|Gibt keine Unterstützung für Object Linking and Embedding (OLE). Standardmäßig erstellt der Anwendungs-Assistent eine Anwendung ohne ActiveX-Unterstützung.|  
|**Container**|Enthält verknüpfte oder eingebettete Objekte.|  
|**Mini-server**|Gibt an, die Anwendung erstellen und Verwalten von zusammengesetzten Document-Objekte kann. Beachten Sie, dass Mini-Server können nicht eigenständig und nur eingebettete Elemente unterstützen.|  
|**Vollständiger server**|Gibt an, die Anwendung erstellen und Verwalten von zusammengesetzten Document-Objekte kann. Vollserver werden eigenständig und unterstützen sowohl verknüpfte eingebettete Elemente ausgeführt.|  
|**Container/vollständigen server**|Gibt an, dass die Anwendung einen Container und einem Server sein kann. Ein Container ist eine Anwendung, die eingebettete oder verknüpfte Elemente in einem eigenen Dokumente integrieren kann. Ein Server ist eine Anwendung, die Automation-Elemente für die Verwendung von containeranwendungen erstellen können.|  
  
 **Zusätzliche Optionen**  
 Gibt an, ob Ihre Anwendung aktive Dokumente unterstützt. Finden Sie unter [aktive Dokumente](../../mfc/active-documents.md) für Weitere Informationen zu dieser Funktion.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Active Document-server**|Gibt an, die Anwendung erstellen und verwalten aktive Dokumente kann. Wenn Sie diese Option auswählen, müssen Sie eine Dateierweiterung angeben, für den Server für aktive Dokument in der **Dateierweiterung** Feld der [Zeichenfolgen für Dokumentvorlagen](../../mfc/reference/document-template-strings-mfc-application-wizard.md) Seite des Assistenten. Finden Sie unter [aktive Dokumentserver](../../mfc/active-document-servers.md) für Weitere Informationen.|  
|**Active Document-container**|Gibt an, dass die Anwendung in deren Rahmen aktive Dokumente enthalten kann. Active Documents können z. B. Internet Explorer-Dokumente oder Office-Dokumente, wie z. B. Microsoft Word-Dateien oder Excel-Kalkulationstabellen, enthalten. Finden Sie unter [Active Document-Container](../../mfc/active-document-containment.md) für Weitere Informationen.|  
|**Unterstützung für Verbunddateien**|Die containeranwendung-Dokumenten, die mithilfe von Compound-Dateiformat wird nicht serialisiert werden. Diese Option erzwingt das Laden von einer vollständigen Datei, die mit Objekten in den Arbeitsspeicher. Inkrementelle speichert auf einzelne Objekte sind nicht verfügbar. Wenn ein Objekt geändert und anschließend gespeichert ist, werden alle Objekte in der Datei gespeichert.|  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Anwendungs-Assistent](../../mfc/reference/mfc-application-wizard.md)

