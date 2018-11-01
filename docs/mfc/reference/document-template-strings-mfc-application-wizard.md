---
title: Zeichenfolgen für Dokumentvorlagen, MFC-Anwendungs-Assistent
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.doctemp
helpviewer_keywords:
- MFC Application Wizard, document template strings
ms.assetid: 8109f662-3182-4682-977a-2503321c678a
ms.openlocfilehash: 24a5fcaea272924e20c55b8c1f5d58111e4eba13
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622231"
---
# <a name="document-template-strings-mfc-application-wizard"></a>Zeichenfolgen für Dokumentvorlagen, MFC-Anwendungs-Assistent

Bereitstellen Sie auf dieser Seite des Assistenten für MFC-Anwendung, oder optimieren Sie die folgenden Optionen aus, um dokumentverwaltung und die Lokalisierung zu unterstützen. Zeichenfolgen für Dokumentvorlagen stehen für Anwendungen, die enthalten **Unterstützung für die Dokument-/Ansicht** in die [Anwendungstyp](../../mfc/reference/application-type-mfc-application-wizard.md). Sie sind nicht verfügbar, für Dialogfelder. Da die meisten Zeichenfolgen für Dokumentvorlagen angezeigt und von den Benutzern der Anwendung verwendet werden, werden sie in lokalisiert die **Ressourcensprache** angegeben, der **Anwendungstyp** Seite des Assistenten.

- **Nicht lokalisierte Zeichenfolgen**

   Gilt für Anwendungen, die Benutzerdokumente zu erstellen. Benutzer können zu öffnen, Drucken und Speichern von Dokumenten mehr ganz einfach, wenn Sie eine Dateierweiterung und ein Datei-Typ-ID angeben Diese Elemente sind nicht lokalisiert werden, da sie vom System nicht vom Benutzer verwendet werden.

   |Option|Beschreibung|
   |------------|-----------------|
   |**Dateierweiterung**|Legt fest, die Dateierweiterung, die mit der Dokumente, die der Benutzer speichert, wenn Sie die Anwendung zu verwenden. Wenn Ihr Projekt Widget genannt wird, können Sie z. B. die Datei Erweiterung .wgt nennen. (Wenn Sie die Dateierweiterung eingeben, schließen Sie nicht den Zeitraum.)<br /><br /> Wenn Sie eine Dateierweiterung angeben, kann im Explorer Ihrer Anwendung Dokumente drucken, ohne die Anwendung starten, wenn der Benutzer das Symbol "Dokument" auf einem Drucker (Symbol) ablegt.<br /><br /> Wenn Sie eine Erweiterung nicht angeben, muss Benutzer eine Dateierweiterung angeben, beim Speichern von Dateien. Der Assistent stellt keine Erweiterung standardmäßig bereit.|
   |**Dateityp-ID**|Legt die Bezeichnung für den Dokumenttyp in der systemregistrierung fest.|

- **Lokalisierte Zeichenfolgen**

   Erstellt Zeichenfolgen, die mit der Anwendung und das Dokument, das Lesen und von den Benutzern der Anwendung, verwendet werden, damit die Zeichenfolgen lokalisiert werden.

   |Option|Beschreibung|
   |------------|-----------------|
   |**Sprache**|Gibt die Sprache, die in der Zeichenfolgen, für alle Felder unter angezeigt werden **lokalisierte Zeichenfolgen**. Um den Wert in dieses Feld zu ändern, wählen Sie die entsprechende Sprache unter **Ressourcensprache** in die [Anwendungstyp](../../mfc/reference/application-type-mfc-application-wizard.md) Seite des Assistenten für die MFC-Anwendung.|
   |**Hauptrahmens**|Legt den Text am oberen Rand der hauptanwendung Frame angezeigt werden. Standardmäßig den Namen des Projekts.|
   |**Name des Dokumenttyps**|Gibt den Typ des Dokuments, die unter dem ein Dokument mit der Anwendung gruppiert werden kann. Standardmäßig den Namen des Projekts. Ändern Sie die Standardeinstellung wird keine weiteren Optionen in diesem Dialogfeld nicht geändert werden.|
   |**Filtername**|Legt den Namen, die, den Ihre Benutzer angeben können, um Dateien dieses Typs zu finden. Diese Option ist verfügbar, aus der **Dateityp** und **Dateityp** Optionen in der standardmäßigen Windows **öffnen** und **speichern als** Dialogfelder. Standardmäßig der Projektname sowie die Dateien, gefolgt von der Erweiterung, die im bereitgestellten **Dateierweiterung**. Wenn Ihr Projekt heißt Widget, und die Dateierweiterung .wgt, z. B. die **Filtername** Widget-Dateien (*.wgt) in der Standardeinstellung ist.|
   |**Neuer kurzer Dateiname**|Legt den Namen, die angezeigt werden, in der standardmäßigen Windows **neu** Dialogfeld, wenn mehr als eine Vorlage für neue Dokumente vorhanden ist. Wenn Ihre Anwendung ist eine [Automatisierungsserver](../../mfc/automation-servers.md), dieser Name dient als kurze Namen für Ihr Automation-Objekt. Standardmäßig den Namen des Projekts.|
   |**Lange Datei-Typname**|Legt den Dateinamen für den Typ in der Registrierung des Systems fest. Wenn Ihre Anwendung ein Automatisierungsserver ist, wird dieser Name als der lange Name Ihres Automation-Objekts verwendet. Standardmäßig den Namen des Projekts plus. Dokument.|

## <a name="see-also"></a>Siehe auch

[MFC-Anwendungs-Assistent](../../mfc/reference/mfc-application-wizard.md)

