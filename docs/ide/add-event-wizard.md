---
title: Assistent zum Hinzufügen von Ereignissen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.event.overview
dev_langs:
- C++
helpviewer_keywords:
- Add Event Wizard [C++]
ms.assetid: bdd2a7bb-13d5-44d7-abc9-e785ba4e05ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f92f871f22fb01f3f0f37677c393fcd481c08120
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33325194"
---
# <a name="add-event-wizard"></a>Assistent zum Hinzufügen von Ereignissen
Dieser Assistent fügt einem MFC-ActiveX-Steuerelementprojekt ein Ereignis hinzu. Sie können Ihr eigenes Ereignis festlegen, ein allgemeines vordefiniertes Ereignis anpassen oder aus einer Liste vordefinierter Ereignisse auswählen.  
  
 **Ereignisname**  
 Legt den Namen fest, der von den Automatisierungsclients verwendet wird, um ein Ereignis von der Klasse anzufordern. Geben Sie einen Namen ein, oder wählen Sie einen aus der Liste aus.  
  
 **Ereignistyp**  
 Gibt den Typ des hinzuzufügenden Ereignisses an. Nur verfügbar, wenn Sie aus der Liste **Ereignisnamen** auswählen.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Stock**|Gibt an, dass ein vordefiniertes Ereignis, z.B. ein Tastenklick, für diese Klasse implementiert wird. Vordefinierte Ereignisse werden in der MFC-Bibliothek (Microsoft Foundation Classes) definiert.|  
|**Benutzerdefiniert**|Gibt an, dass Sie Ihre eigene Implementierung des Ereignisses bereitstellen.|  
  
 **Interner Name**  
 Legt den Namen der Memberfunktion fest, die das Ereignis sendet. Nur für benutzerdefinierte Ereignisse verfügbar. Der Name basiert auf dem **Ereignisnamen**. Sie können den internen Namen ändern, wenn Sie einen Namen angeben möchten, der sich vom **Ereignisnamen** unterscheidet.  
  
 **Parametertyp**  
 Legt den Typ für den **Parameternamen** fest. Wählen Sie den Typ aus der Liste aus.  
  
 **Parametername**  
 Legt den Namen eines Parameters fest, der durch das Ereignis übergeben werden soll. Nachdem Sie den Namen eingegeben haben, müssen Sie auf **Hinzufügen** klicken, um ihn der Liste von Parametern hinzuzufügen.  
  
 Wenn Sie auf **Hinzufügen** klicken, wird der Parametername in der **Parameterliste** angezeigt.  
  
> [!NOTE]
>  Wenn Sie einen Parameternamen angeben und dann auf **Fertig stellen** klicken, bevor Sie auf **Hinzufügen** klicken, wird der Parameter dem Ereignis nicht hinzugefügt. Sie müssen die Methode suchen und den Parameter manuell einfügen. **Parameterliste**  
  
 **Add**  
 Fügt den Parameter und seinen Typ der **Parameterliste** hinzu, den Sie in **Parametername** festlegen. Klicken Sie auf **Hinzufügen**, um einen Parameter zur Liste hinzuzufügen.  
  
 **Entfernen**  
 Entfernt den in der **Parameterliste** ausgewählten Parameter aus der Liste.  
  
 **Parameterliste**  
 Zeigt alle Parameter, die der Methode derzeit hinzugefügt sind, mit ihren Typen an. Während Sie Parameter hinzufügen, aktualisiert der Assistent die **Parameterliste**, um jeden Parameter einschließlich seiner Typen anzuzeigen.  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen eines Ereignisses](../ide/adding-an-event-visual-cpp.md)