---
title: Hinzufügen von Klassen aus Typelib-Assistent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/03/2018
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
ms.openlocfilehash: 0a54948fd98b5a5445aa1fdfafcf0fcd015bbf08
ms.sourcegitcommit: d1527eb2d50156bf923f2a32ec3af9efc7fc4304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2018
ms.locfileid: "48250379"
---
# <a name="add-class-from-typelib-wizard"></a>Assistent zum Hinzufügen von Klassen aus der Typbibliothek

Verwenden Sie diesen Assistenten, eine MFC-Klasse aus einer verfügbaren Typbibliothek hinzufügen. Der Assistent erstellt eine Klasse für jede Schnittstelle, die Sie über die ausgewählte Bibliothek hinzufügen.

> [!WARNING]
> Dieser Code-Assistenten ist veraltet und wird in einer zukünftigen Version von Visual Studio entfernt, in Visual Studio 2017 Version 15.9. Dieser Assistent ist nur selten verwendet. Allgemeine Unterstützung für ATL und MFC wird durch das Entfernen dieses Assistenten nicht beeinträchtigt. Wenn Sie uns Ihr Feedback zu dieser Einstellung freigeben möchten, füllen Sie bitte [diese Umfrage](https://www.surveymonkey.com/r/QDWKKCN). Ihr Feedback ist uns wichtig.

- **Klasse einfügen von**

   Gibt den Speicherort der Typbibliothek an, aus der die Klasse erstellt wird.

   |Option|Beschreibung|
   |------------|-----------------|
   |**Registry**|Die Typbibliothek ist im System registriert. Registrierte Typbibliotheken werden unter **Verfügbare Typbibliotheken** aufgeführt.|
   |**Datei**|Die Typbibliothek ist nicht unbedingt im System registriert, sondern in einer Datei enthalten. Sie müssen den Dateispeicherort unter **Speicherort** angeben.|

- **Verfügbare Typbibliotheken**

   Listet die derzeit im System registrierten Typbibliotheken. Wählen Sie eine Typbibliothek aus der Liste anzuzeigenden die Schnittstellen in den **Schnittstellen** Liste.

   Finden Sie unter "Innerhalb von Distributed COM: Type-Bibliotheken und Language Integration" in der MSDN Library Weitere Informationen zu den Typbibliotheken werden registriert.

- **Position**

   Gibt den Speicherort der Typbibliothek. Wenn Sie unter **Add Class From** (Klasse hinzufügen aus) auf **Datei** klicken, können Sie den Speicherort der Datei angeben, die die Typbibliothek enthält. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um nach dem Speicherort der Datei zu suchen.

- **Schnittstellen**

   Listet die Schnittstellen in der Typbibliothek, die derzeit im ausgewählten der **Verfügbare Typbibliotheken** Liste.

   |Schaltfläche „Übertragen“|Beschreibung|
   |---------------------|-----------------|
   |**>**|Fügt die Schnittstelle hinzu, die derzeit in der Liste **Schnittstellen** ausgewählt ist. Abgeblendet, wenn keine Benutzeroberfläche aktiviert ist.|
   |**>>**|Fügt alle Schnittstellen in der Typbibliothek, die derzeit im ausgewählten der **Verfügbare Typbibliotheken** Liste.|
   |**\<**|Entfernt die Klasse, die derzeit in der Liste **Generierte Klassen** ausgewählt ist. Abgeblendet, wenn keine Klasse derzeit, in ausgewählt ist der **generierte Klassen** Liste.|
   |**\<\<**|Entfernt alle Klassen in der Liste **Generierte Klassen**. Abgeblendete If der **generierte Klassen** Liste ist leer.|

- **Generierte Klassen**

   Gibt die Klassennamen an, die aus den Schnittstellen generiert werden sollen, die mithilfe der Schaltfläche **>** oder **>>** hinzugefügt wurden. Sie können dieses Kontrollkästchen, um eine Klasse auszuwählen, und klicken Sie dann die nach-oben oder nach-unten-Taste in der Liste einen Bildlauf klicken, der Anzeige von jeder Klassenname in der **Klasse** Feld und der Dateiname in der **Datei** Feld, dass der Assistent, wenn generiert Sie Klicken Sie auf **Fertig stellen**. Sie können nur eine Klasse in diesem Feld auswählen.

   Sie können eine Klasse entfernen, indem Sie diese in der Liste auswählen und auf **<** klicken. Sie müssen nicht so entfernen Sie alle Klassen im Klassen generiert eine Klasse auswählen. durch Klicken auf **<<**, entfernen Sie alle Klassen in der **generierte Klassen** Feld.

- **Klasse**

   Gibt den Namen der Klasse an, die im Feld **Generierte Klassen** ausgewählt ist. Dieses wird vom Assistenten hinzugefügt, wenn Sie auf **Fertig stellen** klicken. Sie können den Namen im Bearbeiten der **Klasse** Feld.

- **Datei**

   Legt den Namen der Headerdatei für die neue Klasse fest. Standardmäßig basiert dieser Name auf dem Namen, den Sie unter **Generierte Klassen** angeben. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am gewünschten Speicherort zu speichern oder um die Klassendeklaration an eine vorhandene Datei anzufügen. Wenn Sie eine vorhandene Datei auswählen, speichert der Assistent diese nicht am ausgewählten Speicherort, bis Sie im Assistenten auf **Fertig stellen** klicken.

   Der Assistent überschreibt Dateien nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, fordert der Assistent Sie dazu auf, anzugeben, ob die Klassendeklaration an die Inhalte der Datei angefügt werden sollen, wenn Sie auf **Fertig stellen** klicken. Klicken Sie auf **Ja**, um die Datei anzufügen. Klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.

## <a name="see-also"></a>Siehe auch

[MFC-Klasse aus einer Typbibliothek](../../mfc/reference/adding-an-mfc-class-from-a-type-library.md)<br/>
[Automatisierungsclients: Verwenden von Typbibliotheken](../../mfc/automation-clients-using-type-libraries.md)

