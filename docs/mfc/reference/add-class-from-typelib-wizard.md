---
title: "Hinzufügen von Klassen aus der Typbibliothek-Assistenten | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.class.typelib
dev_langs:
- C++
helpviewer_keywords:
- Add Class from TypeLib Wizard [MFC]
- COM interfaces, adding classes
ms.assetid: 96152afd-9374-4649-a6ab-b0fa2a5592a3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4aad89b6f3227cac59b6429cc67975db3dad424
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="add-class-from-typelib-wizard"></a>Assistent zum Hinzufügen von Klassen aus der Typbibliothek
Verwenden Sie diesen Assistenten zum Hinzufügen einer MFC-Klasse aus einer Typbibliothek verfügbar. Der Assistent erstellt eine Klasse für jede Schnittstelle, die Sie aus der ausgewählten Typbibliothek hinzufügen.  
  
 **Fügen Sie Klasse aus**  
 Gibt den Speicherort der Typbibliothek, aus der Klasse erstellt wird.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Registry**|Die Typbibliothek ist im System registriert. Registrierte Typbibliotheken in aufgelisteten **verfügbaren Typbibliotheken**.|  
|**Datei**|Die Typbibliothek ist nicht unbedingt im System registriert, aber in einer Datei enthalten ist. Geben Sie den Dateispeicherort in **Speicherort**.|  
  
 **Verfügbare Typbibliotheken**  
 Listet die Typbibliotheken, die zurzeit im System registriert. Wählen Sie eine Typbibliothek aus dieser Liste anzuzeigende zugehörigen Schnittstellen in den **Schnittstellen** Liste.  
  
 Finden Sie unter "In Distributed COM: Type-Bibliotheken und Language Integration" in der MSDN Library für Weitere Informationen zum Registrieren von Typbibliotheken.  
  
 **Speicherort**  
 Gibt den Speicherort der Typbibliothek. Wenn Sie auf **Datei** unter **Klasse hinzufügen von**, können Sie den Speicherort der Datei mit der Typbibliothek angeben. Um auf den Speicherort der Datei zu suchen, klicken Sie auf die Schaltfläche mit den Auslassungspunkten.  
  
 **Schnittstellen**  
 Listet die Schnittstellen in der Typbibliothek, die derzeit im ausgewählten der **verfügbaren Typbibliotheken** Liste.  
  
|Übertragen Sie die Schaltfläche|Beschreibung|  
|---------------------|-----------------|  
|**>**|Die Schnittstelle, die derzeit im ausgewählten fügt die **Schnittstellen** Liste. Abgeblendet, wenn keine Schnittstelle aktiviert ist.|  
|**>>**|Fügt alle Schnittstellen in der Typbibliothek, die derzeit im ausgewählten der **verfügbaren Typbibliotheken** Liste.|  
|**<**|Entfernt die Klasse, die derzeit im ausgewählten der **generierte Klassen** Liste. Abgeblendet, wenn keine Klasse derzeit, in ausgewählt ist der **generierte Klassen** Liste.|  
|**<\<**|Entfernt alle Klassen in der **generierte Klassen** Liste. Abgeblendete If der **generierte Klassen** Liste ist leer.|  
  
 **Generierte Klassen**  
 Gibt die Klassennamen zu generierenden über die Schnittstellen hinzugefügt, mit der  **>**  oder  **>>**  Schaltfläche. Sie können dieses Kontrollkästchen, um eine Klasse auszuwählen, und klicken Sie dann mithilfe der nach-oben oder nach-unten-Taste in der Liste einen Bildlauf Klicken anzeigen jedes Klassennamen in der `Class` Feld und der Dateiname in der **Datei** Feld, das der Assistent generiert, wenn Sie auf das  **Fertig stellen**. Sie können nur eine Klasse zu einem Zeitpunkt in diesem Feld auswählen.  
  
 Sie können eine Klasse entfernen, indem Sie es in dieser Liste auswählen und auf  **<** . Sie müssen nicht im Feld generierte Klassen So entfernen Sie alle Klassen eine Klasse auswählen. durch Klicken auf  **<<** , entfernen Sie alle Klassen in der **generierte Klassen** Feld.  
  
 `Class`  
 Gibt den Namen der Klasse, die im ausgewählten der **generierte Klassen** Feld, das vom Assistenten hinzugefügt, wenn Sie auf das **Fertig stellen**. Sie können den Namen im Bearbeiten der `Class` Feld.  
  
 **Datei**  
 Legt den Namen der Headerdatei für die neue Klasse. Standardmäßig basiert auf den Namen, die Sie, in angeben diesen Namen **generierte Klassen**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen an den Speicherort Ihrer Wahl speichern oder die Klassendeklaration an eine vorhandene Datei anfügen. Wenn Sie eine vorhandene Datei auswählen, der Assistent wird nicht zum Speichern an den ausgewählten Speicherort bis auf **Fertig stellen** im Assistenten.  
  
 Der Assistent überschreibt eine Datei nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, wenn Sie auf **Fertig stellen**, werden vom Assistenten aufgefordert, um anzugeben, ob die Klassendeklaration an den Inhalt der Datei angefügt werden sollen. Klicken Sie auf **Ja** anzufügende Datei ein, klicken Sie auf **keine** zum Assistenten zurückzukehren, und geben Sie einen anderen Dateinamen an.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Klasse aus einer Typbibliothek](../../mfc/reference/adding-an-mfc-class-from-a-type-library.md)   
 [Automatisierungsclients: Verwenden von Typbibliotheken](../../mfc/automation-clients-using-type-libraries.md)

