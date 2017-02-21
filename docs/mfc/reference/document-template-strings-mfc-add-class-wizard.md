---
title: "Zeichenfolgen f&#252;r Dokumentvorlagen, MFC-Assistent zum Hinzuf&#252;gen von Klassen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.class.mfc.simple.doctemp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC-Assistent zum Hinzufügen von Klassen, Zeichenfolgen zur Dokumentsteuerung"
ms.assetid: 14e1c834-5e79-4dbd-811f-ec8f0a9cdcb2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Zeichenfolgen f&#252;r Dokumentvorlagen, MFC-Assistent zum Hinzuf&#252;gen von Klassen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Seite des Assistenten ist nur für Klassen verfügbar, die die folgenden Kriterien erfüllen:  
  
-   Das MFC\-Projekt unterstützt die Dokument\-\/Ansichtarchitektur.  
  
-   Die Basisklasse der neuen Klasse lautet [CFormView](../../mfc/reference/cformview-class.md).  
  
-   Das Kontrollkästchen **DocTemplate\-Ressourcen generieren** im Bereich **Namen** des [MFC\-Klassen\-Assistenten](../../mfc/reference/mfc-add-class-wizard.md) ist aktiviert.  
  
 Der Assistent bietet Standardeinstellungen für die folgenden Werte, um die Entwicklung von Formularansichten sowie die Verwaltung und die Lokalisierung zu erleichtern.  Da die meisten Zeichenfolgen für Dokumentvorlagen sichtbar sind und von den Benutzern des Formulars verwendet werden, werden sie in die **Ressourcensprache** übersetzt, die bei der Projekterstellung auf der Seite [Anwendungstyp](../../mfc/reference/application-type-mfc-application-wizard.md) des MFC\-Anwendungs\-Assistenten angegeben wird.  
  
> [!NOTE]
>  Der Assistent bietet keine automatische Druckunterstützung für Klassen, die von `CFormView` abgeleitet sind.  
  
 Weitere Informationen finden Sie unter [Dokumentvorlagen und der Erstellungsvorgang für Dokument und Ansicht](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## Nicht lokalisierte Zeichenfolgen  
 Bezieht sich auf Anwendungen, durch die Benutzerdokumente erstellt werden.  Benutzer können Dokumente einfacher öffnen und speichern, wenn der Dokumenttyp über eine Dateierweiterung und eine Dateityp\-ID verfügt.  Diese Elemente werden nicht lokalisiert, da sie vom System und nicht vom Benutzer verwendet werden.  
  
 **Dateierweiterung**  
 Legt die Dateierweiterung fest, die mit dem Dokumenttyp dieser Formularanwendung verknüpft ist.  Die standardmäßig verwendete Dateierweiterung basiert auf dem Klassennamen.  Hat die neue MFC\-Klasse beispielsweise den Namen **CWidget**, lautet die Dateierweiterung standardmäßig **.wid**.  Die Dateierweiterung wird in Dateifiltern und in den Dialogfeldern **Öffnen** und **Speichern unter** verwendet.  
  
 Wenn Sie die Dateierweiterung ändern, wird der geänderte Name im Feld **Filtername** angezeigt.  
  
> [!NOTE]
>  Die geänderte Standarddateierweiterung muss ohne Punkt eingegeben werden.  
  
 **Dateityp\-ID**  
 Legt die Bezeichnung des Dokumenttyps in der Systemregistrierung fest.  
  
## Lokalisierte Zeichenfolgen  
 Erstellt Zeichenfolgen, die den Formularen und Dokumenten zugeordnet sind, die von den Benutzern der Anwendung gelesen und verwendet werden. Daher werden diese Zeichenfolgen lokalisiert.  
  
 **Dokumenttypname**  
 Bezeichnet den Dokumenttyp, unter dem ein in der Anwendung erstelltes Dokument gruppiert werden kann.  Der Name basiert standardmäßig auf dem Namen der Klasse.  Hat die neue MFC\-Klasse beispielsweise den Namen **CWidget**, lautet der Dokumenttypname standardmäßig **Widget**.  Wenn Sie den Standardwert ändern, wird keine weitere Option in diesem Dialogfeld geändert.  
  
 **Filtername**  
 Legt den Namen fest, den der Benutzer bei der Suche nach Dateien dieses Typs angeben kann.  Auf diese Option kann über die Option **Dateityp** in den Windows\-Standarddialogfeldern **Öffnen** und **Speichern unter** zugegriffen werden.  Der Name entspricht standardmäßig dem Projektnamen, gefolgt von "Files" \(Dateien\) und der unter **Dateierweiterung** angegebenen Erweiterung.  Wenn das Projekt beispielsweise den Namen "Widget" und die Dateierweiterung **.wid** hat, lautet der Filtername standardmäßig **Widget Files \(\*.wid\)**.  
  
 **Neuer kurzer Dateiname**  
 Legt den Namen fest, der im Windows\-Standarddialogfeld **Neu** angezeigt wird, wenn das Projekt über mehr als eine Dokumentvorlage verfügt.  Handelt es sich bei der Anwendung um einen [Automatisierungsserver](../../mfc/automation-servers.md), wird dieser Name als kurzer Name für das Automatisierungsobjekt verwendet.  Dieser Name basiert standardmäßig auf dem Klassennamen.  
  
 **Langer Dateitypname**  
 Legt den Namen des Dateityps in der Systemregistrierung fest.  Handelt es sich bei der Anwendung um einen Automatisierungsserver, wird dieser Name als langer Name für das Automatisierungsobjekt verwendet.  Dieser Dateiname basiert standardmäßig auf dem Klassennamen, gefolgt von ".Document".  Lautet der Klassenname beispielsweise **CWidget**, lautet der Eintrag unter **Langer Dateitypname** standardmäßig **Widget Document**.  
  
 **Dokumentklasse**  
 Gibt die Dokumentklasse des Projekts an.  Diese Klasse entspricht standardmäßig der Dokumentklasse der Hauptanwendung, die auf der Seite [Erstellte Klassen überprüfen](../../mfc/reference/generated-classes-mfc-application-wizard.md) des MFC\-Anwendungs\-Assistenten aufgeführt ist.  Sie können eine andere Dokumentklasse aus der Liste auswählen, sofern dem Projekt weitere Dokumentklassen hinzugefügt wurden.  
  
## Siehe auch  
 [MFC\-Assistent zum Hinzufügen von Klassen](../../mfc/reference/mfc-add-class-wizard.md)   
 [MFC\-Klasse](../../mfc/reference/adding-an-mfc-class.md)   
 [Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)