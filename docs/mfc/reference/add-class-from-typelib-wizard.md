---
title: Hinzufügen von Klassen aus der Typbibliothek-Assistenten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.class.typelib
dev_langs:
- C++
helpviewer_keywords:
- Add Class from TypeLib Wizard [MFC]
- COM interfaces, adding classes
ms.assetid: 96152afd-9374-4649-a6ab-b0fa2a5592a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fc26f74de76205041228ce92e29309af1ce8959f
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951673"
---
# <a name="add-class-from-typelib-wizard"></a>Assistent zum Hinzufügen von Klassen aus der Typbibliothek
Verwenden Sie diesen Assistenten zum Hinzufügen einer MFC-Klasse aus einer Typbibliothek verfügbar. Der Assistent erstellt eine Klasse für jede Schnittstelle, die Sie aus der ausgewählten Typbibliothek hinzufügen.  
  
 **Fügen Sie Klasse aus**  
 Gibt den Speicherort der Typbibliothek an, aus der die Klasse erstellt wird.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Registry**|Die Typbibliothek ist im System registriert. Registrierte Typbibliotheken werden unter **Verfügbare Typbibliotheken** aufgeführt.|  
|**Datei**|Die Typbibliothek ist nicht unbedingt im System registriert, sondern in einer Datei enthalten. Sie müssen den Dateispeicherort unter **Speicherort** angeben.|  
  
 **Verfügbare Typbibliotheken**  
 Listet die Typbibliotheken, die zurzeit im System registriert. Wählen Sie eine Typbibliothek aus dieser Liste anzuzeigende zugehörigen Schnittstellen in den **Schnittstellen** Liste.  
  
 Finden Sie unter "In Distributed COM: Type-Bibliotheken und Language Integration" in der MSDN Library für Weitere Informationen zum Registrieren von Typbibliotheken.  
  
 **Position**  
 Gibt den Speicherort der Typbibliothek. Wenn Sie unter **Add Class From** (Klasse hinzufügen aus) auf **Datei** klicken, können Sie den Speicherort der Datei angeben, die die Typbibliothek enthält. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um nach dem Speicherort der Datei zu suchen.  
  
 **Schnittstellen**  
 Listet die Schnittstellen in der Typbibliothek, die derzeit im ausgewählten der **verfügbaren Typbibliotheken** Liste.  
  
|Schaltfläche „Übertragen“|Beschreibung|  
|---------------------|-----------------|  
|**>**|Fügt die Schnittstelle hinzu, die derzeit in der Liste **Schnittstellen** ausgewählt ist. Abgeblendet, wenn keine Schnittstelle aktiviert ist.|  
|**>>**|Fügt alle Schnittstellen in der Typbibliothek, die derzeit im ausgewählten der **verfügbaren Typbibliotheken** Liste.|  
|**<**|Entfernt die Klasse, die derzeit in der Liste **Generierte Klassen** ausgewählt ist. Abgeblendet, wenn keine Klasse derzeit, in ausgewählt ist der **generierte Klassen** Liste.|  
|**<\<**|Entfernt alle Klassen in der Liste **Generierte Klassen**. Abgeblendete If der **generierte Klassen** Liste ist leer.|  
  
 **Generierte Klassen**  
 Gibt die Klassennamen an, die aus den Schnittstellen generiert werden sollen, die mithilfe der Schaltfläche **>** oder **>>** hinzugefügt wurden. Sie können dieses Kontrollkästchen, um eine Klasse auszuwählen, und klicken Sie dann mithilfe der nach-oben oder nach-unten-Taste in der Liste einen Bildlauf Klicken anzeigen jedes Klassennamen in der **Klasse** Feld und der Dateiname in der **Datei** Feld, dass der Assistent, wenn generiert Sie Klicken Sie auf **Fertig stellen**. Sie können nur eine Klasse in diesem Feld auswählen.  
  
 Sie können eine Klasse entfernen, indem Sie diese in der Liste auswählen und auf **<** klicken. Sie müssen nicht im Feld generierte Klassen So entfernen Sie alle Klassen eine Klasse auswählen. durch Klicken auf **<<**, entfernen Sie alle Klassen in der **generierte Klassen** Feld.  
  
 **Klasse**  
 Gibt den Namen der Klasse an, die im Feld **Generierte Klassen** ausgewählt ist. Dieses wird vom Assistenten hinzugefügt, wenn Sie auf **Fertig stellen** klicken. Sie können den Namen im Bearbeiten der **Klasse** Feld.  
  
 **Datei**  
 Legt den Namen der Headerdatei für die neue Klasse fest. Standardmäßig basiert dieser Name auf dem Namen, den Sie unter **Generierte Klassen** angeben. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am gewünschten Speicherort zu speichern oder um die Klassendeklaration an eine vorhandene Datei anzufügen. Wenn Sie eine vorhandene Datei auswählen, speichert der Assistent diese nicht am ausgewählten Speicherort, bis Sie im Assistenten auf **Fertig stellen** klicken.  
  
 Der Assistent überschreibt Dateien nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, fordert der Assistent Sie dazu auf, anzugeben, ob die Klassendeklaration an die Inhalte der Datei angefügt werden sollen, wenn Sie auf **Fertig stellen** klicken. Klicken Sie auf **Ja**, um die Datei anzufügen. Klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Klasse aus einer Typbibliothek](../../mfc/reference/adding-an-mfc-class-from-a-type-library.md)   
 [Automatisierungsclients: Verwenden von Typbibliotheken](../../mfc/automation-clients-using-type-libraries.md)

