---
title: Hinzufügen eines Ereignisses
ms.date: 11/12/2018
f1_keywords:
- vc.codewiz.event.overview
helpviewer_keywords:
- ActiveX controls [C++], adding events to
- MFC ActiveX controls [C++], adding events
- events [C++], ActiveX controls
- add event wizard [C++]
ms.assetid: fe34832a-edfc-4f86-aacb-8df77001873d
ms.openlocfilehash: 1d5a8f5666dd04e00f8a438fdbf00320c37e14f4
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "51693424"
---
# <a name="add-an-event"></a>Hinzufügen eines Ereignisses

In der Klassenansicht können Sie nur der Steuerelementklasse in Ihrem [MFC-ActiveX-Steuerelement](../mfc/reference/creating-an-mfc-activex-control.md)-Projekt mithilfe des [Assistenten zum Hinzufügen von Ereignissen](#add-event-wizard) ein Ereignis hinzufügen. Verwenden Sie die Schaltfläche **Ereignisse** im [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window), wenn ein Ereignis einer anderen Art von Projekt hinzugefügt werden soll.

**So fügen Sie Ihrem MFC-ActiveX-Steuerelement-Projekt ein Ereignis hinzu**

1. Erweitern Sie in der Klassenansicht den Projektknoten, um die Projektklassen anzuzeigen.

1. Klicken Sie mit der rechten Maustaste auf die Steuerelementklasse des Projekts.

1. Wählen Sie im Kontextmenü **Hinzufügen** und dann **Ereignis hinzufügen**, um den Assistenten zum Hinzufügen von Ereignissen anzuzeigen.

1. Geben Sie die Ereignisinformationen in den entsprechenden Feldern des Assistenten an.

1. Wählen Sie **Fertig stellen**, um das Ereignis dem Projekt hinzuzufügen.

## <a name="in-this-section"></a>In diesem Abschnitt

- [Assistent zum Hinzufügen von Ereignissen](#add-event-wizard)

## <a name="add-event-wizard"></a>Assistent zum Hinzufügen von Ereignissen

Dieser Assistent fügt einem MFC-ActiveX-Steuerelementprojekt ein Ereignis hinzu. Sie können Ihr eigenes Ereignis festlegen, ein typisches vordefiniertes Ereignis anpassen oder aus einer Liste vordefinierter Ereignisse auswählen.

- **Ereignisname**

   Legt den Namen fest, der von den Automatisierungsclients verwendet wird, um ein Ereignis von der Klasse anzufordern. Geben Sie einen Namen ein, oder wählen Sie einen aus der Liste aus.

- **Ereignistyp**

   Gibt den Typ des hinzuzufügenden Ereignisses an. Nur verfügbar, wenn Sie aus der Liste **Ereignisnamen** auswählen.

   |Option|Beschreibung |
   |------------|-----------------|
   |**Stock**|Gibt an, dass ein vordefiniertes Ereignis, z.B. ein Tastenklick, für diese Klasse implementiert wird. Vordefinierte Ereignisse werden in der MFC-Bibliothek (Microsoft Foundation Classes) definiert.|
   |**Benutzerdefiniert**|Gibt an, dass Sie Ihre eigene Implementierung des Ereignisses verwenden.|

- **Interner Name**

   Legt den Namen der Memberfunktion fest, die das Ereignis sendet. Nur für benutzerdefinierte Ereignisse verfügbar. Der Name basiert auf dem **Ereignisnamen**. Sie können den internen Namen ändern, wenn Sie einen Namen angeben möchten, der sich vom **Ereignisnamen** unterscheidet.

- **Parametertyp**

   Legt den Typ für den **Parameternamen** fest. Wählen Sie den Typ aus der Liste aus.

- **Parametername**

   Legt den Namen eines Parameters fest, der durch das Ereignis übergeben werden soll. Nachdem Sie den Namen eingegeben haben, müssen Sie **Hinzufügen** auswählen, um ihn der Liste von Parametern hinzuzufügen.

   Wenn Sie **Hinzufügen** auswählen, wird der Parametername in der **Parameterliste** angezeigt.

   > [!NOTE]
   > Wenn Sie einen Parameternamen angeben und dann **Fertig stellen** auswählen, bevor Sie **Hinzufügen** auswählen, wird der Parameter dem Ereignis nicht hinzugefügt. Sie müssen die Methode suchen und den Parameter manuell einfügen.

- **Add**

   Fügt den Parameter und seinen Typ der **Parameterliste** hinzu, den Sie in **Parametername** festlegen. Wählen Sie **Hinzufügen** aus, um der Liste einen Parameter hinzuzufügen.

- **Entfernen**

   Entfernt den in der **Parameterliste** ausgewählten Parameter aus der Liste.

- **Parameterliste**

   Zeigt alle Parameter, die der Methode derzeit hinzugefügt sind, mit ihren Typen an. Während Sie Parameter hinzufügen, aktualisiert der Assistent die **Parameterliste**, um jeden Parameter einschließlich seiner Typen anzuzeigen.
