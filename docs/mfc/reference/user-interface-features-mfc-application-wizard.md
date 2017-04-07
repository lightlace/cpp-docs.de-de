---
title: "Benutzeroberflächen-Features, MFC-Anwendungs-Assistent | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.exe.ui
dev_langs:
- C++
helpviewer_keywords:
- MFC Application Wizard, user interface features
ms.assetid: 59e7b829-a665-42eb-be23-3f2a36eb2dad
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 390d06ddb09786ac4e9960c1933e0b1a76531f5e
ms.lasthandoff: 04/01/2017

---
# <a name="user-interface-features-mfc-application-wizard"></a>Benutzeroberflächen-Funktionen, MFC-Anwendungs-Assistent
Dieser Artikel beschreibt die Optionen, die Sie verwenden können, um das Aussehen Ihrer Anwendung anzugeben. Features der Benutzeroberfläche für das Projekt verfügbaren hängt vom Typ der Anwendung, die Sie, in angegeben der [Anwendungstyp, MFC-Anwendungs-Assistent](../../mfc/reference/application-type-mfc-application-wizard.md) Seite des Assistenten für die MFC-Anwendung. Wenn Sie eine SDI-Anwendung erstellen, können nicht Sie z. B. Stile für untergeordnete Rahmen hinzufügen.  
  
 **Hauptframe-Stile**  
 Legt die Funktionen von der Anwendung im Hauptfenster Frame fest.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Breiten Rahmen**|Erstellt ein Fenster mit einem Rahmen. Der Standardwert.|  
|**Minimieren-Schaltfläche**|Enthält ein Minimieren-Feld in das Hauptrahmenfenster. Der Standardwert.|  
|**Maximieren-Schaltfläche**|Enthält ein Maximieren-Feld in das Hauptrahmenfenster. Der Standardwert.|  
|**Minimiert:**|Öffnet das Hauptrahmenfenster als Symbol an.|  
|**Maximiert:**|Öffnet das Hauptrahmenfenster auf die volle Größe der Anzeige.|  
|**Systemmenü**|Enthält ein Systemmenü im Hauptrahmenfenster. Der Standardwert.|  
|**Informationsfeld**|Enthält eine **zu** Feld für die Anwendung. Der Benutzer kann dieses Feld zugreifen, von der Anwendungsverzeichnis **Hilfe** Menü. Die Standardeinstellung und nicht geändert werden, es sei denn, Sie wählen **Dialogfeldern basierend**in der [Anwendungstyp, MFC-Anwendungs-Assistent](../../mfc/reference/application-type-mfc-application-wizard.md) Seite.<br /><br /> **Hinweis** eine Option abgeblendet ist in der Regel gibt an, dass der Assistent nicht die Option für das Projekt gilt, ob das dazugehörige Kontrollkästchen aktiviert oder deaktiviert ist. In diesem Fall fügt der Assistent immer ein **zu** Feld auf das Projekt, es sei denn, Sie zuerst das Projekt als Grundlage Dialogfeld angeben und dann das Kontrollkästchen deaktivieren.|  
|**Statusleiste**|Fügt eine Statusleiste für Ihre Anwendung. Die Statusleiste enthält automatische aufgeführten Indikatoren auf der Tastatur FESTSTELLTASTE, NUM-Taste, und führen Sie einen Bildlauf Schlüssel, und Meldungszeile, in der Hilfe angezeigt Zeichenfolgen für Befehle des Menüs und Symbolleisten-Schaltflächen. Durch Auswählen dieser Option werden auch Menübefehle zum Anzeigen oder ausblenden Statusleiste hinzugefügt. Standardmäßig verwendet eine Anwendung eine Statusleiste angezeigt. Für Typen von Dialogfeldern basierende Anwendung nicht verfügbar.|  
|**Geteilte Fenster**|Stellt eine Trennleiste bereit. Die Teilerleiste teilt Hauptansichten der Anwendung. In einer Anwendung von multiple Document Interface (MDI) Clientfenster untergeordneten MDI-Rahmens ein unterteiltes Fenster, und eine Anwendung einzelne Document Interface (SDI) und mehrere oberste Ebene Dokument-Anwendung, die Hauptframe-Clientfenster ist ein unterteiltes Fenster. Für Typen von Dialogfeldern basierende Anwendung nicht verfügbar.|  
  
 **Untergeordnete Rahmenstile**  
 Gibt die Darstellung und den Ausgangszustand der untergeordneten Frames in der Anwendung an. Untergeordnete Rahmenstile stehen für MDI-Anwendungen nur zur Verfügung.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Untergeordnete Minimieren-Schaltfläche**|Gibt an, ob ein untergeordnetes Fenster eine Schaltfläche "Minimieren" (standardmäßig aktiviert) hat.|  
|**Untergeordnete Maximieren-Schaltfläche**|Gibt an, ob ein untergeordnetes Fenster eine Schaltfläche "Maximieren" (standardmäßig aktiviert) hat.|  
|**Untergeordnete maximiert**|Gibt an, ob ein untergeordnetes Fenster anfänglich maximiert ist, durch Festlegen des Kennzeichens cs.style **WS_MAXIMIZE** in der [PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow) Memberfunktion von `CChildFrame`.|  
  
 **Befehlsleisten (Menü/Symbolleiste/Menüband)**  
 Gibt an, ob Ihre Anwendung Menüs, Symbolleisten und/oder ein Menüband enthält. Für Dialogfeld-basierte Anwendungen nicht verfügbar.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Verwenden eines klassischen Menüs**|Gibt an, dass Ihre Anwendung ein klassisches, nicht verschiebbare Menü enthält.|  
|**Verwenden einer klassischen andockbaren Symbolleiste**|Fügt eine Windows-Standardsymbolleiste für Ihre Anwendung. Die Symbolleiste enthält Schaltflächen zum Erstellen eines neuen Dokuments. Öffnen und Speichern von Dokumentdateien; Ausschneiden, kopieren, einfügen oder Drucken von Text; und Hilfemodus eingeben. Die Aktivierung dieser Option werden auch Menübefehle zum Anzeigen oder Ausblenden der Symbolleiste hinzugefügt.|  
|**Verwenden Sie eine Browser Style-Symbolleiste**|Fügt eine Internet Explorer-Style-Symbolleiste für Ihre Anwendung.|  
|**Menü- und Symbolleiste verwenden**|Gibt an, dass die Anwendung eine verschiebbare Menüleiste und eine Symbolleiste enthält.|  
|**Benutzerdefinierte Symbolleisten und Bilder**|Ermöglicht es dem Benutzer auf der Symbolleiste und die Symbolleistenbilder zur Laufzeit anzupassen.|  
|**Personalisierte Menüs und Symbolleisten**|Gibt an, ob Sie im Menü die vollständige Liste der Elemente, die beim Öffnen enthält oder wenn sie nur die Befehle enthält, die der Benutzer am häufigsten verwendet.|  
|**Verwenden Sie ein Menüband**|Verwendet ein Office 2007-ähnliche-Menüband in der Anwendung statt einer Menüleiste oder einer Symbolleiste an.|  
  
 **Dialogfeldtitel**  
 Für [CDialog-Klasse](../../mfc/reference/cdialog-class.md)-basierte Anwendungen nur dieser Titel wird in der Titelleiste des Dialogfelds angezeigt. Sie müssen zuerst auswählen, um dieses Feld bearbeiten, die **Dialogfeldern basierend** unter option **Anwendungstyp**. Weitere Informationen finden Sie unter [Anwendungstyp, MFC-Anwendungs-Assistent](../../mfc/reference/application-type-mfc-application-wizard.md).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Anwendungs-Assistent](../../mfc/reference/mfc-application-wizard.md)


