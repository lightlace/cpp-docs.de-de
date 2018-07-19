---
title: Benutzeroberflächen-Features, MFC-Anwendungs-Assistent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.exe.ui
dev_langs:
- C++
helpviewer_keywords:
- MFC Application Wizard, user interface features
ms.assetid: 59e7b829-a665-42eb-be23-3f2a36eb2dad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c73a8990687633eb5fe6bc15a76563bd1237eaf
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885776"
---
# <a name="user-interface-features-mfc-application-wizard"></a>Benutzeroberflächen-Features, MFC-Anwendungs-Assistent
Dieser Artikel beschreibt die Optionen, die Sie verwenden können, um das Aussehen Ihrer Anwendung anzugeben. Für das Projekt verfügbaren Features der Benutzeroberfläche hängen von der Art der Anwendung, die Sie, in angegeben der [Anwendungstyp, MFC-Anwendungs-Assistent](../../mfc/reference/application-type-mfc-application-wizard.md) Seite des Assistenten für die MFC-Anwendung. Wenn Sie eine SDI-Anwendung erstellen, können nicht Sie z. B. untergeordnete Rahmenstile hinzufügen.  
  
 **Hauptrahmenstile**  
 Legt die Funktionen des Hauptfensters der Anwendung fest.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Breiten Rahmen**|Erstellt ein Fenster mit einem Rahmen. Der Standardwert.|  
|**Minimieren-Schaltfläche**|Enthält ein Minimieren-Feld in das Hauptrahmenfenster. Der Standardwert.|  
|**Maximieren-Schaltfläche**|Enthält ein Maximieren-Feld in das Hauptrahmenfenster. Der Standardwert.|  
|**Minimiert**|Öffnet das Hauptrahmenfenster als Symbol.|  
|**Maximiert**|Wird auf die volle Größe der Anzeige im Hauptrahmenfenster geöffnet.|  
|**Systemmenü**|Enthält ein Systemmenü im Hauptrahmenfenster. Der Standardwert.|  
|**Infofeld**|Enthält eine **zu** für die Anwendung. Der Benutzer kann dieses Feld zugreifen, von der Anwendung **Hilfe** Menü. Die Standardeinstellung, und nicht geändert werden, es sei denn, Sie wählen **auf Dialogfeldern basierend**in die [Anwendungstyp, MFC-Anwendungs-Assistent](../../mfc/reference/application-type-mfc-application-wizard.md) Seite.<br /><br /> **Beachten Sie** eine Option abgeblendet ist in der Regel gibt an, dass der Assistent nicht die Option für das Projekt, gilt, ob das dazugehörige Kontrollkästchen aktiviert oder deaktiviert ist. In diesem Fall fügt der Assistent immer ein **zu** Feld auf das Projekt, es sei denn, Sie zuerst das Projekt als Grundlage Dialogfeld angeben, und klicken Sie dann deaktivieren Sie das Kontrollkästchen.|  
|**Anfängliche Statusleiste**|Fügt eine Statusleiste Ihrer Anwendung hinzu. Die Statusleiste enthält automatische Indikatoren für die die FESTSTELLTASTE, NUM-Taste, und SCROLLEN Sie Tasten und Meldungszeile, in der Hilfe angezeigt Zeichenfolgen für Befehle des Menüs und Symbolleisten-Schaltflächen. Durch Aktivieren dieser Option fügt auch Befehle im Menü zum Anzeigen oder Ausblenden der Statusleiste. In der Standardeinstellung verfügt eine Anwendung eine Statusleiste. Für Typen von Dialogfeldern basierende Anwendung nicht verfügbar.|  
|**Geteilte Fenster**|Stellt eine Teilerleiste bereit. Die Teilerleiste teilt Hauptansichten der Anwendung. In eine Anwendung multiple Document Interface (MDI) untergeordneten MDI-Frame-Clientfenster ist ein Teilungsfenster und in eine Anwendung einzelne Document Interface (SDI) und Anwendung von multiple Top Level Document, den Hauptframe-Clientfenster ist ein Teilungsfenster. Für Typen von Dialogfeldern basierende Anwendung nicht verfügbar.|  
  
 **Untergeordnete Rahmenstile**  
 Gibt die Darstellung und den ursprünglichen Zustand der untergeordneten Frames in Ihrer Anwendung an. Untergeordnete Rahmenstile stehen für MDI-Anwendungen nur zur Verfügung.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Untergeordnete Minimieren-Schaltfläche**|Gibt an, ob ein untergeordnetes Fenster eine Minimierungsschaltfläche (standardmäßig aktiviert) hat.|  
|**Untergeordnete Maximieren-Schaltfläche**|Gibt an, ob ein untergeordnetes Fenster eine Maximierungsschaltfläche (standardmäßig aktiviert) hat.|  
|**Untergeordnete maximiert**|Gibt an, ob ein untergeordnetes Fenster anfänglich maximiert angezeigt wird, durch Festlegen der cs.style flag WS_MAXIMIZE in die [PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow) Memberfunktion `CChildFrame`.|  
  
 **Befehlsleisten (/ Symbolleiste/Menüband)**  
 Gibt an, ob Ihre Anwendung, Menüs, Symbolleisten und/oder ein Menüband enthält. Für Dialogfeld-basierten Anwendungen nicht verfügbar.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Klassisches Menü verwenden**|Gibt an, dass Ihre Anwendung auf einem klassischen, nicht draggable-Menü enthält.|  
|**Klassische andockbare Symbolleiste verwenden**|Ihre Anwendung hinzugefügt eine Windows-Standardsymbolleiste. Die Symbolleiste enthält Schaltflächen zum Erstellen eines neuen Dokuments. Öffnen und Speichern von Dokumentdateien; Ausschneiden, kopieren, kopieren oder Drucken von Text; und Hilfemodus eingeben. Durch Aktivieren dieser Option fügt auch die Befehle im Menü zum Anzeigen oder Ausblenden der Symbolleiste hinzu.|  
|**Verwenden Sie eine Browser-Stil-Symbolleiste**|Ihre Anwendung eine Stil von Internet Explorer-Symbolleiste hinzugefügt wird.|  
|**Verwenden von Menü- und Symbolleiste**|Gibt an, dass Ihre Anwendung eine ziehbare Menü- und eine Symbolleiste enthält.|  
|**Benutzerdefinierte Symbolleisten und Bilder**|Ermöglicht dem Benutzer, der Symbolleiste und die Symbolleistenbilder, zur Laufzeit anzupassen.|  
|**Personalisierte Menüs und Symbolleisten**|Gibt an, ob das Menü für die vollständige Liste der Elemente, die beim Öffnen enthält, oder sie nur die Befehle enthält, die der Benutzer am häufigsten verwendet.|  
|**Menüband verwenden**|Verwendet ein Menüband von Office 2007-ähnliche in Ihrer Anwendung statt einer Menüleiste oder eine Symbolleiste an.|  
  
 **Dialogfeldtitel**  
 Für [CDialog-Klasse](../../mfc/reference/cdialog-class.md)-basierten Anwendungen nur dieser Titel wird in der Titelleiste des Dialogfelds angezeigt. Sie müssen zunächst auswählen, um dieses Feld bearbeiten, die **auf Dialogfeldern basierend** option **Anwendungstyp**. Weitere Informationen finden Sie unter [Anwendungstyp, MFC-Anwendungs-Assistent](../../mfc/reference/application-type-mfc-application-wizard.md).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Anwendungs-Assistent](../../mfc/reference/mfc-application-wizard.md)

