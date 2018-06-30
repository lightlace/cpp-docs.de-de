---
title: Zeichenfolgen für Dokumentvorlagen, MFC-Klassen-Assistenten hinzufügen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.class.mfc.simple.doctemp
dev_langs:
- C++
helpviewer_keywords:
- MFC Add Class Wizard, document control strings
ms.assetid: 14e1c834-5e79-4dbd-811f-ec8f0a9cdcb2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 79de28847809a9b9d7e0a160f2a4a45375f0e1fe
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121512"
---
# <a name="document-template-strings-mfc-add-class-wizard"></a>Zeichenfolgen für Dokumentvorlagen, MFC-Assistent zum Hinzufügen von Klassen
Auf dieser Seite des Assistenten ist verfügbar nur für Klassen, die die folgenden Kriterien erfüllen:  
  
-   Das MFC-Projekt unterstützt die Dokument-/Ansichtarchitektur.  
  
-   Ist die Basisklasse der neuen Klasse [CFormView](../../mfc/reference/cformview-class.md).  
  
-   Das Kontrollkästchen **DocTemplate-Ressourcen** wird geprüft, ob die **Namen** Teil der [MFC-Klassen-Assistent](../../mfc/reference/mfc-add-class-wizard.md).  
  
 Der Assistent stellt die Standardwerte für die folgenden Werte helfen Ihnen beim Entwurf der Forms-Ansicht, Verwaltung und Lokalisierung. Da die meisten Zeichenfolgen für Dokumentvorlagen sichtbar sind und von Benutzern für das Formular verwendet werden, sind sie in lokalisiert die **Ressourcensprache** gemäß der [Anwendungstypen](../../mfc/reference/application-type-mfc-application-wizard.md) Seite des Assistenten für die MFC-Anwendung Wenn das Projekt erstellt wurde.  
  
> [!NOTE]
>  Der Assistent bietet keine automatische druckunterstützung für Klassen abgeleitete `CFormView`.  
  
 Finden Sie unter [Dokumentvorlagen und der Erstellungsvorgang für die Dokument-/Ansichtarchitektur](../../mfc/document-templates-and-the-document-view-creation-process.md) für Weitere Informationen.  
  
## <a name="nonlocalized-strings"></a>Nicht lokalisierte Zeichenfolgen  
 Gilt für Anwendungen, die Benutzerdokumente zu erstellen. Benutzer können Dokumente mehr einfach der Dokumenttyp verfügt eine Dateierweiterung und eine Datei-Typ-ID. öffnen und speichern Diese Elemente sind nicht lokalisiert werden, da sie vom System und nicht vom Benutzer verwendet werden.  
  
 **Dateierweiterung**  
 Legt fest, die Dateierweiterung, die den Dokumenttyp für diese Forms-Anwendung zugeordnet. Der Standardwert des Datei-Erweiterung, die basierend auf den Klassennamen abrufen. Wenn die neue MFC-Klasse heißt beispielsweise `CWidget`, wird standardmäßig die Erweiterung der Ausgabedatei lautet. Verdrahtung-Verbindungsdiagramm Die Erweiterung wird verwendet, in der Dateifilter und der **öffnen** und **speichern als** Dialogfelder.  
  
 Wenn Sie die Erweiterung zu ändern, wird die Änderung übernommen, der **Filtername** Feld.  
  
> [!NOTE]
>  Wenn Sie die standarddateierweiterung ändern, schließen Sie den Zeitraum nicht.  
  
 **Datei-Typ-ID**  
 Legt die Bezeichnung für den Dokumenttyp in der systemregistrierung fest.  
  
## <a name="localized-strings"></a>Lokalisierte Zeichenfolgen  
 Erzeugt Zeichenfolgen zugeordnet, die Formulare und Dokumente, die gelesen und von Benutzern der Anwendung verwendet werden, damit die Zeichenfolgen lokalisiert werden.  
  
 **Name des Dokumenttyps**  
 Identifiziert den Typ des Dokuments unter dem ein Dokument von der Anwendung gruppiert werden kann. Standardmäßig basiert sie auf den Namen der Klasse. Wenn die neue MFC-Klasse heißt beispielsweise **CWidget**, sich ein Widget wird standardmäßig der Name des Dokumenttyps. Ändern Sie die Standardeinstellung ändert sich nicht auf alle anderen Optionen in diesem Dialogfeld.  
  
 **Name des Filters**  
 Legt den Namen, den Benutzer angeben können, um die Dateien des Typs angegebenen Datei zu suchen. Diese Option ist verfügbar, von der **Dateityp** und **Dateityp** Optionen in den standardmäßigen Windows **öffnen** und **Dateityp** Dialogfelder. Wird standardmäßig der Name auf den Namen des Projekts basiert, sowie Dateien, gefolgt von der Erweiterung im angegebenen **Dateierweiterung**. Wenn Ihr Projekt Widget Namen und die Erweiterung der Ausgabedatei lautet .wid, z. B. die **Filtername** Widget-Dateien (*.wid) in der Standardeinstellung ist.  
  
 **Neue kurze Dateinamen**  
 Legt den Namen in das Windows-Standarddialogfeld **neu** (Dialogfeld), wenn das Projekt mehr als eine Dokumentvorlage verfügt. Wenn Ihre Anwendung ist ein [Automatisierungsservers](../../mfc/automation-servers.md), dieser Name wird verwendet, als den Kurznamen der Ihr Automation-Objekt. Standardmäßig basiert dieser Name auf den Klassennamen abrufen.  
  
 **Lange Dateinamen für Typ**  
 Legt den Dateinamen für den Typ in der systemregistrierung fest. Wenn Ihre Anwendung eines Automatisierungsservers ist, wird dieser Name als den langen Namen für das Automatisierungsobjekt verwendet. Standardmäßig diesen Namen der Klassenname plus basiert. Dokument. Wenn der Klassenname ist z. B. `CWidget`, die **Dateityp langen Namen** Widget-Dokument ist.  
  
 **Dokumentklasse**  
 Gibt das Projekt Dokumentklasse an. Diese Klasse wird standardmäßig der hauptanwendung Dokumentklasse, gemäß der [Überprüfung generierte Klassen](../../mfc/reference/generated-classes-mfc-application-wizard.md) Seite des Assistenten für die MFC-Anwendung. Wenn Sie andere Document-Klassen im Projekt hinzugefügt haben, können Sie eine andere Dokumentklasse aus der Liste auswählen.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Klassen-Assistenten hinzufügen](../../mfc/reference/mfc-add-class-wizard.md)   
 [MFC Class (MFC-Klasse)](../../mfc/reference/adding-an-mfc-class.md)   
 [Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)
