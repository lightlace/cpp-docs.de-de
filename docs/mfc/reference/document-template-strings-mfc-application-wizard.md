---
title: "Zeichenfolgen f&#252;r Dokumentvorlagen, MFC-Anwendungs-Assistent"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.exe.doctemp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC-Anwendungs-Assistent, Zeichenfolgen für Dokumentvorlagen"
ms.assetid: 8109f662-3182-4682-977a-2503321c678a
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Zeichenfolgen f&#252;r Dokumentvorlagen, MFC-Anwendungs-Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Auf dieser Seite des MFC\-Anwendungs\-Assistenten können Sie die folgenden Optionen festlegen bzw. exakter abstimmen, um die Verwaltung und Lokalisierung von Dokumenten zu erleichtern.  Zeichenfolgen für Dokumentvorlagen sind für Anwendungen verfügbar, deren [Anwendungstyp](../../mfc/reference/application-type-mfc-application-wizard.md) die **Unterstützung für die Dokument\-\/Ansichtarchitektur** beinhaltet.  Sie stehen nicht für Dialogfelder zur Verfügung.  Da die meisten Zeichenfolgen für Dokumentvorlagen sichtbar sind und von den Benutzern der Anwendung verwendet werden, werden sie in die **Ressourcensprache** übersetzt, die auf der Seite **Anwendungstyp** des Assistenten angegeben wird.  
  
 **Nicht lokalisierte Zeichenfolgen**  
 Bezieht sich auf Anwendungen, durch die Benutzerdokumente erstellt werden.  Benutzer können Dokumente einfacher öffnen, drucken und speichern, wenn Sie eine Dateierweiterung und eine Dateityp\-ID angeben.  Diese Elemente werden nicht lokalisiert, da sie vom System und nicht vom Benutzer verwendet werden.  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|**Dateierweiterung**|Legt die Dateierweiterung für die Dokumente fest, die der Benutzer beim Arbeiten in der Anwendung speichert.  Wenn das Projekt beispielsweise den Namen "Widget" hat, kann die Dateierweiterung .wgt lauten. \(Die Dateierweiterung muss ohne Punkt eingegeben werden.\)<br /><br /> Bei Angabe einer Dateierweiterung können die in der Anwendung erstellten Dokumente ohne Starten der Anwendung im Explorer gedruckt werden, sobald der Benutzer das Dokumentsymbol auf einem Druckersymbol ablegt.<br /><br /> Falls Sie keine Erweiterung angeben, muss der Benutzer beim Speichern von Dateien eigene Dateierweiterungen festlegen.  Der Assistent bietet keine Standarddateierweiterung.|  
|**Dateityp\-ID**|Legt die Bezeichnung des Dokumenttyps in der Systemregistrierung fest.|  
  
 **Lokalisierte Zeichenfolgen**  
 Erstellt Zeichenfolgen, die der Anwendung und dem Dokument zugeordnet sind und die vom Benutzer der Anwendung gelesen und verwendet werden. Daher werden diese Zeichenfolgen lokalisiert.  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|**Sprache**|Gibt die Sprache an, in der Zeichenfolgen für alle Felder unter **Lokalisierte Zeichenfolgen** angezeigt werden.  Um den Wert in diesem Feld zu ändern, wählen Sie unter **Ressourcensprache** auf der Seite [Anwendungstyp](../../mfc/reference/application-type-mfc-application-wizard.md) des MFC\-Anwendungs\-Assistenten die geeignete Sprache aus.|  
|**Hauptrahmenüberschrift**|Legt den Text fest, der im oberen Bereich des Hauptanwendungsrahmens erscheint.  Dies ist standardmäßig der Projektname.|  
|**Dokumenttypname**|Bezeichnet den Dokumenttyp, unter dem ein in der Anwendung erstelltes Dokument gruppiert werden kann.  Dies ist standardmäßig der Projektname.  Wenn Sie den Standardwert ändern, wird keine weitere Option in diesem Dialogfeld geändert.|  
|**Filtername**|Legt den Namen fest, den der Benutzer bei der Suche nach Dateien dieses Typs angeben kann.  Auf diese Option kann über die Option **Dateityp** in den Windows\-Standarddialogfeldern **Öffnen** und **Speichern unter** zugegriffen werden.  Dies ist standardmäßig der Projektname, gefolgt von "Files" \(Dateien\) und der unter **Dateierweiterung** angegebenen Erweiterung.  Wenn das Projekt beispielsweise den Namen "Widget" hat und die Dateierweiterung **.wgt** lautet, ist der Filtername standardmäßig **Widget Files \(\*.wgt\)**.|  
|**Neuer kurzer Dateiname**|Legt den Namen fest, der im Windows\-Standarddialogfeld **Neu** angezeigt wird, wenn mehr als eine Vorlage für neue Dokumente vorhanden ist.  Handelt es sich bei der Anwendung um einen [Automatisierungsserver](../../mfc/automation-servers.md), wird dieser Name als kurzer Name für das Automatisierungsobjekt verwendet.  Dies ist standardmäßig der Projektname.|  
|**Langer Dateitypname**|Legt den Namen des Dateityps in der Systemregistrierung fest.  Handelt es sich bei der Anwendung um einen Automatisierungsserver, wird dieser Name als langer Name für das Automatisierungsobjekt verwendet.  Dies ist standardmäßig der Projektname, gefolgt von ".Document".|  
  
## Siehe auch  
 [MFC\-Anwendungs\-Assistent](../../mfc/reference/mfc-application-wizard.md)