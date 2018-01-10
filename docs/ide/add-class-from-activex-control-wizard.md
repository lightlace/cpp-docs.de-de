---
title: "Hinzufügen von Klassen aus ActiveX-Steuerelement-Assistent | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.class.axcontrol
dev_langs: C++
helpviewer_keywords:
- ActiveX Control Wizard
- Add Class from ActiveX Control Wizard [C++]
ms.assetid: 668d801c-5fb6-4176-9191-5c38995a4713
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e2b3b1d2b15db47eea8ebc10b2a73cafba5d6952
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="add-class-from-activex-control-wizard"></a>Hinzufügen einer Klasse mit dem ActiveX-Steuerelement-Assistenten
Verwenden Sie diesen Assistenten, um eine MFC-Klasse aus einem verfügbaren ActiveX-Steuerelement hinzufügen. Der Assistent erstellt eine Klasse für jede Schnittstelle, die Sie aus dem ausgewählten ActiveX-Steuerelement hinzufügen.  
  
 **Fügen Sie Klasse aus**  
 Gibt den Speicherort der Typbibliothek, aus der Klasse erstellt wird.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Registry**|Die Typbibliothek ist im System registriert. Registrierte Typbibliotheken in aufgelisteten **verfügbare ActiveX-Steuerelemente**.|  
|**Datei**|Die Typbibliothek ist nicht unbedingt im System registriert, aber in einer Datei enthalten ist. Geben Sie den Dateispeicherort in **Speicherort**.|  
  
 **Verfügbare ActiveX-Steuerelemente**  
 Gibt an, die ActiveX-Steuerelemente, die zurzeit im System registriert. Wählen Sie ein ActiveX-Steuerelement aus dieser Liste anzuzeigende zugehörigen Schnittstellen in den **Schnittstellen** Liste. Finden Sie unter [MFC-ActiveX-Steuerelemente: Weitergabe von ActiveX-Steuerelementen](../mfc/mfc-activex-controls-distributing-activex-controls.md) für Weitere Informationen zum Registrieren von ActiveX-Steuerelemente.  
  
 Wenn Sie auf **Datei** unter **Klasse hinzufügen von**, dieses Feld ist für die Änderung nicht verfügbar.  
  
 **Speicherort**  
 Gibt den Speicherort des ActiveX-Steuerelements. Wenn Sie auf **Datei** unter **Klasse hinzufügen von**, können Sie den Speicherort der Datei mit der Typbibliothek angeben. Um auf den Speicherort der Datei zu suchen, klicken Sie auf die Schaltfläche mit den Auslassungspunkten.  
  
 Wenn Sie auf **Registrierung** unter **Klasse hinzufügen von**, dieses Feld ist für die Änderung nicht verfügbar.  
  
 **Schnittstellen**  
 Legt die Schnittstellen in der ActiveX-Steuerelement, die derzeit im ausgewählten **verfügbare ActiveX-Steuerelemente** oder in der Typbibliothek in der Datei im angegebenen **Speicherort**.  
  
|Übertragen Sie die Schaltfläche|Beschreibung|  
|---------------------|-----------------|  
|**>**|Die Schnittstelle, die derzeit im ausgewählten fügt die **Schnittstellen** Liste. Nicht verfügbar, wenn keine Schnittstelle ausgewählt ist.|  
|**>>**|Fügt alle Schnittstellen in der ActiveX-Steuerelement, die derzeit im ausgewählten **verfügbare ActiveX-Steuerelemente** oder in der Typbibliothek in der Datei im angegebenen **Speicherort**.|  
|**<**|Entfernt die Klasse, die derzeit im ausgewählten der **generierte Klassen** Liste. Nicht verfügbar, wenn keine Klasse derzeit, in ausgewählt ist der **generierte Klassen** Liste.|  
|**<\<**|Entfernt alle Klassen in der **generierte Klassen** Liste. Nicht verfügbar If der **generierte Klassen** Liste ist leer.|  
  
 **Generierte Klassen**  
 Gibt die Klassennamen zu generierenden über die Schnittstellen hinzugefügt, mit der  **>**  oder  **>>**  Schaltfläche. Sie können dieses Kontrollkästchen, um eine Klasse auszuwählen, und klicken Sie dann mithilfe der nach-oben oder nach-unten-Taste in der Liste einen Bildlauf Klicken anzeigen jedes Klassennamen in der `Class` Feld und der Dateiname in der **.h-Datei** Feld, das der Assistent generiert, wenn Sie auf das  **Fertig stellen**. Sie können nur eine Klasse zu einem Zeitpunkt in diesem Feld auswählen.  
  
 Sie können eine Klasse entfernen, indem Sie es in dieser Liste auswählen und auf  **<** . Sie müssen nicht auf eine Klasse in der **generierte Klassen** Feld, um alle Klassen zu entfernen; klicken  **<<** , entfernen Sie alle Klassen in der **generierte Klassen** Box.  
  
 `Class`  
 Gibt den Namen der Klasse, die im ausgewählten der **generierte Klassen** Feld, das vom Assistenten hinzugefügt, wenn Sie auf das **Fertig stellen**. Sie können den Namen im Bearbeiten der `Class` Feld.  
  
 **.h-Datei**  
 Legt den Namen der Headerdatei für die neue Klasse des Objekts. Standardmäßig basiert auf den Namen, die Sie, in angeben diesen Namen **generierte Klassen**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen an den Speicherort Ihrer Wahl speichern oder die Klassendeklaration an eine vorhandene Datei anfügen. Wenn Sie eine vorhandene Datei auswählen, der Assistent wird nicht zum Speichern an den ausgewählten Speicherort bis auf **Fertig stellen** im Assistenten.  
  
 Der Assistent überschreibt eine Datei nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, wenn Sie auf **Fertig stellen**, werden vom Assistenten aufgefordert, um anzugeben, ob die Klassendeklaration an den Inhalt der Datei angefügt werden sollen. Klicken Sie auf **Ja** anzufügende Datei ein, klicken Sie auf **keine** zum Assistenten zurückzukehren, und geben Sie einen anderen Dateinamen an.  
  
 **CPP-Datei**  
 Legt den Namen der Implementierungsdatei für das neue Objekt-Klasse. Standardmäßig basiert auf den Namen, die Sie, in angeben diesen Namen **generierte Klassen**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am Speicherort Ihrer Wahl zu speichern. Die Datei wird nicht an den ausgewählten Speicherort gespeichert, bis Sie auf **Fertig stellen** im Assistenten.  
  
 Der Assistent überschreibt eine Datei nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, wenn Sie auf **Fertig stellen**, werden vom Assistenten aufgefordert, um anzugeben, ob die Implementierung der Klasse mit dem Inhalt der Datei angefügt werden sollen. Klicken Sie auf **Ja** anzufügende Datei ein, klicken Sie auf **keine** zum Assistenten zurückzukehren, und geben Sie einen anderen Dateinamen an.  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen einer Klasse aus einem ActiveX-Steuerelement](../ide/adding-a-class-from-an-activex-control-visual-cpp.md)   
 [Automatisierungsclients: Verwenden von Typbibliotheken](../mfc/automation-clients-using-type-libraries.md)