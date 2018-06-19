---
title: Zeichenfolgen für Dokumentvorlagen, MFC-Anwendung-Assistenten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.exe.doctemp
dev_langs:
- C++
helpviewer_keywords:
- MFC Application Wizard, document template strings
ms.assetid: 8109f662-3182-4682-977a-2503321c678a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d6039459eed097af5e927c4bd2f30d3e7c3c4bc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373539"
---
# <a name="document-template-strings-mfc-application-wizard"></a>Zeichenfolgen für Dokumentvorlagen, MFC-Anwendungs-Assistent
Bereitstellen Sie auf dieser Seite des Assistenten für MFC-Anwendung, oder verfeinern Sie die folgenden Optionen zum Dokumentverwaltungsfunktionen und Lokalisierung zu verbessern. Zeichenfolgen für Dokumentvorlagen stehen für Anwendungen mit **Unterstützung der Dokument-/Ansichtarchitektur-Architektur** in der [Anwendungstyp](../../mfc/reference/application-type-mfc-application-wizard.md). Sie sind nicht verfügbar für Dialogfelder. Da die meisten Zeichenfolgen für Dokumentvorlagen sichtbar sind und von den Benutzern der Anwendung verwendet werden, sind sie in lokalisiert die **Ressourcensprache** gemäß der **"Anwendung"** Seite des Assistenten.  
  
 **Nicht lokalisierte Zeichenfolgen**  
 Gilt für Anwendungen, die Benutzerdokumente zu erstellen. Benutzer können öffnen, Drucken und Speichern von Dokumenten mehr einfach, wenn Sie eine Dateierweiterung und eine Datei Typ-ID bereitstellen Diese Elemente sind nicht lokalisiert werden, da sie vom System und nicht vom Benutzer verwendet werden.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Dateierweiterung**|Legt die Dateierweiterung der Dokumente, die der Benutzer speichert, wenn die Anwendung mit zugeordnet. Wenn Ihr Projekt Widget benannt wird, können Sie die Datei Erweiterung .wgt nennen. (Wenn Sie die Dateierweiterung eingeben, schließen Sie nicht den Zeitraum.)<br /><br /> Wenn Sie eine Dateierweiterung angeben, kann im Explorer Dokumente für Ihre Anwendung drucken, ohne die Anwendung starten, wenn der Benutzer das Symbol "Dokument" auf ein Druckersymbol ablegt.<br /><br /> Wenn Sie keine Erweiterung angeben, muss ein Benutzer Dateierweiterung angeben, wenn Sie Dateien speichern. Der Assistent bietet keine Standard-Dateierweiterung.|  
|**Datei-Typ-ID**|Legt die Bezeichnung für den Dokumenttyp in der systemregistrierung fest.|  
  
 **Lokalisierte Zeichenfolgen**  
 Erstellt Zeichenfolgen, die mit der Anwendung und das Dokument, das gelesen und von Benutzern der Anwendung verwendet werden, damit die Zeichenfolgen lokalisiert werden.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Sprache**|Gibt die Sprache, in der Zeichenfolgen, für alle Felder unter angezeigt werden **lokalisierte Zeichenfolgen**. Um den Wert in diesem Feld ändern möchten, wählen Sie die gewünschte Sprache unter **Ressourcensprache** in der [Anwendungstyp](../../mfc/reference/application-type-mfc-application-wizard.md) Seite des Assistenten für die MFC-Anwendung.|  
|**Hauptrahmens**|Legt den Text am oberen Rand der Hauptanwendungsrahmen angezeigt. Standardmäßig den Namen des Projekts.|  
|**Name des Dokumenttyps**|Identifiziert den Typ des Dokuments unter dem ein Dokument von der Anwendung gruppiert werden kann. Standardmäßig den Namen des Projekts. Ändern Sie die Standardeinstellung ändert sich nicht auf alle anderen Optionen in diesem Dialogfeld.|  
|**Name des Filters**|Legt den Namen, den Ihre Benutzer zum Suchen von Dateien mit dem Dateityp angeben können. Diese Option ist verfügbar, von der **Dateityp** und **Dateityp** Optionen in den standardmäßigen Windows **öffnen** und **Dateityp** Dialogfelder. Vom Standardwert, der Projektname plus Dateien, gefolgt von der Erweiterung in **Dateierweiterung**. Wenn Ihr Projekt Widget Namen und die Erweiterung der Ausgabedatei lautet .wgt, z. B. die **Filtername** Widget-Dateien (*.wgt) in der Standardeinstellung ist.|  
|**Neue kurze Dateinamen**|Legt den Namen in das Windows-Standarddialogfeld `New` (Dialogfeld), wenn mehr als ein neues Dokumentvorlage vorhanden ist. Wenn Ihre Anwendung ist ein [Automatisierungsservers](../../mfc/automation-servers.md), dieser Name wird verwendet, als den Kurznamen der Ihr Automation-Objekt. Standardmäßig den Namen des Projekts.|  
|**Lange Dateinamen für Typ**|Legt den Dateinamen für den Typ in der systemregistrierung fest. Wenn Ihre Anwendung eines Automatisierungsservers ist, wird dieser Name als den langen Namen für das Automatisierungsobjekt verwendet. Standardmäßig den Namen des Projekts plus. Dokument.|  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Anwendungs-Assistent](../../mfc/reference/mfc-application-wizard.md)

