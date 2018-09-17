---
title: Zeichenfolgen für Dokumentvorlagen, MFC-Klassen-Assistenten hinzufügen | Microsoft-Dokumentation
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
ms.openlocfilehash: 247793199b1e865941659b970e4e59a688137a8e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712230"
---
# <a name="document-template-strings-mfc-add-class-wizard"></a>Zeichenfolgen für Dokumentvorlagen, MFC-Assistent zum Hinzufügen von Klassen
Auf dieser Seite des Assistenten ist verfügbar nur für Klassen, die die folgenden Kriterien erfüllen:  
  
-   Das MFC-Projekt unterstützt die Dokument-/Ansichtarchitektur.  
  
-   Die Basisklasse der neuen Klasse [CFormView](../../mfc/reference/cformview-class.md).  
  
-   Das Kontrollkästchen **DocTemplate-Ressourcen** wird geprüft, ob die **Namen** Teil der [MFC-Klassenassistent](../../mfc/reference/mfc-add-class-wizard.md).  
  
 Der Assistent bietet Standardeinstellungen für die folgenden Werte ein, um Forms Ansicht Entwurf, Verwaltung und Lokalisierung zu unterstützen. Da die meisten Zeichenfolgen für Dokumentvorlagen, vom Benutzer des Formulars verwendet wird, sind, werden sie in lokalisiert die **Ressourcensprache** angegeben, der [Anwendungstypen](../../mfc/reference/application-type-mfc-application-wizard.md) Seite des Assistenten für die MFC-Anwendung Wenn das Projekt erstellt wurde.  
  
> [!NOTE]
>  Der Assistent bietet keine automatische Unterstützung für den Druck, für die abgeleitete Klassen von `CFormView`.  
  
 Finden Sie unter [Dokumentvorlagen und der Erstellungsvorgang für Dokumente und Ansichten](../../mfc/document-templates-and-the-document-view-creation-process.md) für Weitere Informationen.  
  
## <a name="nonlocalized-strings"></a>Nicht lokalisierte Zeichenfolgen  
 Gilt für Anwendungen, die Benutzerdokumente zu erstellen. Benutzer können öffnen und Speichern Dokumente mehr ganz einfach der Dokumenttyp verfügt eine Dateierweiterung und eine Datei-Typ-ID. Diese Elemente sind nicht lokalisiert werden, da sie vom System nicht vom Benutzer verwendet werden.  
  
- **Dateierweiterung**

   Legt fest, die Dateierweiterung, die den Dokumenttyp für diese Anwendung für Forms zugeordnet. Der Standardwert des Datei-Erweiterung, die basierend auf den Namen der Klasse. Wenn es sich bei dem Namen der neuen MFC-Klasse z. B. `CWidget`, wird standardmäßig die Dateierweiterung. Ihre Die Dateierweiterung im Dateifilter verwendet wird und die **öffnen** und **speichern als** Dialogfelder.  
  
   Wenn Sie die Dateierweiterung ändern, wird die Änderung übernommen, der **Filtername** Feld.  
  
   > [!NOTE]
   > Wenn Sie die standardmäßige Dateierweiterung ändern, enthalten Sie nicht den Zeitraum.  
  
- **Dateityp-ID**

   Legt die Bezeichnung für den Dokumenttyp in der systemregistrierung fest.  
  
## <a name="localized-strings"></a>Lokalisierte Zeichenfolgen  
 Erstellt Zeichenfolgen im Zusammenhang mit der Formulare und Dokumente, die gelesen und von den Benutzern der Anwendung, verwendet werden, damit die Zeichenfolgen lokalisiert werden.  
  
- **Name des Dokumenttyps**

   Gibt den Typ des Dokuments, die unter dem ein Dokument mit der Anwendung gruppiert werden kann. Standardmäßig basiert sie auf den Namen der Klasse. Wenn es sich bei dem Namen der neuen MFC-Klasse z. B. **CWidget**, in der Standardeinstellung ist der Name des Dokumenttyps-Widget. Ändern Sie die Standardeinstellung wird keine weiteren Optionen in diesem Dialogfeld nicht geändert werden.  
  
- **Filtername**

   Legt den Namen, den Benutzer angeben können, um Dateien von den angegebenen Dateityp zu finden. Diese Option ist verfügbar, aus der **Dateityp** und **Dateityp** Optionen in der standardmäßigen Windows **öffnen** und **speichern als** Dialogfelder. Standardmäßig basiert auf den Namen des Projekts der Namen sowie Dateien, gefolgt von der Erweiterung im angegebenen **Dateierweiterung**. Wenn Ihr Projekt heißt Widget, und die Dateierweiterung .wid, z. B. die **Filtername** Widget-Dateien (*.wid) in der Standardeinstellung ist.  
  
- **Neuer kurzer Dateiname**

   Legt den Namen, die angezeigt werden, in der standardmäßigen Windows **neu** Dialogfeld, wenn das Projekt mehr als eine Dokumentvorlage aufweist. Wenn Ihre Anwendung ist eine [Automatisierungsserver](../../mfc/automation-servers.md), dieser Name dient als kurze Namen für Ihr Automation-Objekt. Dieser Name basiert standardmäßig auf den Namen der Klasse verwendet wird.  
  
- **Lange Datei-Typname**

   Legt den Dateinamen für den Typ in der Registrierung des Systems fest. Wenn Ihre Anwendung ein Automatisierungsserver ist, wird dieser Name als der lange Name Ihres Automation-Objekts verwendet. Dieser Name basiert standardmäßig auf den Namen der Klasse und verwendet wird. Dokument. Wenn der Klassenname ist z. B. `CWidget`, **Dateityp langen Namen** Widget-Dokument ist.  
  
- **"Document"-Klasse**

   Gibt die Dokumentklasse des Projekts an. Diese Klasse wird standardmäßig der hauptanwendung Dokumentklasse, gemäß der [erstellte Klassen überprüfen](../../mfc/reference/generated-classes-mfc-application-wizard.md) Seite des Assistenten für die MFC-Anwendung. Sie können ein anderes Dokumentenklasse aus der Liste auswählen, wenn Sie andere Document-Klassen im Projekt hinzugefügt haben.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Klassen-Assistenten hinzufügen](../../mfc/reference/mfc-add-class-wizard.md)   
 [MFC Class (MFC-Klasse)](../../mfc/reference/adding-an-mfc-class.md)   
 [Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)
