---
title: 'MFC-ActiveX-Steuerelemente: Hinzufügen von benutzerdefinierten Eigenschaften'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], properties
- properties [MFC], custom
ms.assetid: 85af5167-74c7-427b-b8f3-e0d7b73942e5
ms.openlocfilehash: e02d5523b894f89aa93c8d2765a128920afa2353
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57284202"
---
# <a name="mfc-activex-controls-adding-custom-properties"></a>MFC-ActiveX-Steuerelemente: Hinzufügen von benutzerdefinierten Eigenschaften

Benutzerdefinierte Eigenschaften unterscheiden sich von vordefinierten Eigenschaften, da benutzerdefinierte Eigenschaften von noch nicht implementiert werden die `COleControl` Klasse. Eine benutzerdefinierte Eigenschaft wird verwendet, um einen bestimmten Zustand oder die Darstellung von ein ActiveX-Steuerelement ein Programmierer, die mit dem Steuerelement verfügbar zu machen.

In diesem Artikel wird beschrieben, wie eine benutzerdefinierte Eigenschaft hinzuzufügen, klicken Sie auf das ActiveX-Steuerelement mit dem Assistenten zum Hinzufügen von Eigenschaften und erläutert, die sich ergebende codeänderungen. Folgende Themen werden behandelt:

- [Verwenden den Assistenten zum Hinzufügen einer Eigenschaft zum Hinzufügen einer benutzerdefinierten Eigenschaft](#_core_using_classwizard_to_add_a_custom_property)

- [Änderungen der Eigenschaft-Assistenten für benutzerdefinierte Eigenschaften hinzuzufügen](#_core_classwizard_changes_for_custom_properties)

Benutzerdefinierte Eigenschaften sind in vier Arten von Implementierung: Member-Variable, die Member-Variable mit der Benachrichtigung "," Get/Set-Methoden, als auch parametrisierte.

- Implementierung des Schnittstellenmembers Variable

   Diese Implementierung stellt der Zustand der Eigenschaft als eine Membervariable in der Steuerelementklasse dar. Verwenden Sie die Membervariablen Implementierung, wenn es nicht wichtig zu wissen, wenn der Eigenschaftswert geändert wird. Die drei Typen erstellt diese Implementierung Mindestmaß an Code für die Unterstützung für die Eigenschaft an. Ist das Makro für Dispatch den Eintrag für die Implementierung des Schnittstellenmembers Variable [DISP_PROPERTY](../mfc/reference/dispatch-maps.md#disp_property).

- Membervariablen Notification-Implementierung

   Diese Implementierung besteht aus einer Membervariablen gespeichert und eine Benachrichtigungsfunktion, die durch den Assistenten zum Hinzufügen einer Eigenschaft erstellt. Die Benachrichtigungsfunktion wird automatisch durch das Framework nach der Änderung der Eigenschaft-Wert aufgerufen werden. Verwenden Sie die Membervariablen durch Implementierung der Benachrichtigung, wenn Sie müssen benachrichtigt werden, nachdem sich ein Eigenschaftswert geändert hat. Diese Implementierung ist mehr Zeit erforderlich, da es sich um einen Funktionsaufruf erfordert. Das Makro für Dispatch den Eintrag für diese Implementierung wird [DISP_PROPERTY_NOTIFY](../mfc/reference/dispatch-maps.md#disp_property_notify).

- Get/Set-Methoden-Implementierung

   Diese Implementierung besteht aus einem Paar von Memberfunktionen in der Control-Klasse. Die Get/Set-Methoden Implementierung ruft automatisch die Get-Member-Funktion, wenn der Benutzer des Steuerelements auf den aktuellen Wert der Eigenschaft anfordert und die Set-Member-Funktion, wenn der Benutzer des Steuerelements fordert, dass die Eigenschaft geändert werden. Verwenden Sie diese Implementierung, wenn zum Berechnen des Wert einer Eigenschaft während der Laufzeit einen Benutzer des Steuerelements vor dem Ändern der tatsächlichen-Eigenschaft übergebenen Wert überprüfen, oder einen Lese- oder Schreibzugriff nur - Eigenschaftentyp implementieren. Das Makro für Dispatch den Eintrag für diese Implementierung wird [DISP_PROPERTY_EX](../mfc/reference/dispatch-maps.md#disp_property_ex). Im folgenden Abschnitt [mithilfe des Assistenten zum Hinzufügen von Eigenschaften zum Hinzufügen einer benutzerdefinierten Eigenschaft](#_core_using_classwizard_to_add_a_custom_property), verwendet die benutzerdefinierte CircleOffset-Eigenschaft dieser Implementierung veranschaulicht.

- Parametrisierte Implementierung

   Parametrisierte Implementierung wird von der Assistent zum Hinzufügen von Eigenschaften unterstützt. Eine parametrisierte Eigenschaft (manchmal als "eine Array-Eigenschaft" bezeichnet) kann verwendet werden, um einen Satz von Werten über eine einzelne Eigenschaft Ihres Steuerelements zugreifen. Das Makro für Dispatch den Eintrag für diese Implementierung ist DISP_PROPERTY_PARAM. Weitere Informationen zur Implementierung dieses Typs finden Sie unter [Implementieren einer parametrisierten Eigenschaft](../mfc/mfc-activex-controls-advanced-topics.md) in diesem Artikel ActiveX-Steuerelemente: Weiterführende Themen.

##  <a name="_core_using_classwizard_to_add_a_custom_property"></a> Mithilfe der Eigenschaft Assistenten zum Hinzufügen zum Hinzufügen einer benutzerdefinierten Eigenschaft

Das folgende Verfahren veranschaulicht das Hinzufügen einer benutzerdefinierten Eigenschaft, CircleOffset, die die Implementierung der Get/Set-Methoden verwendet. Die benutzerdefinierte CircleOffset-Eigenschaft kann Benutzer für den Kreis aus der Mitte des umschließenden Rechtecks des Steuerelements den offset des Steuerelements. Das Verfahren zum Hinzufügen von benutzerdefinierten Eigenschaften mit einer Implementierung als Get/Set-Methoden ist sehr ähnlich.

Dieses Verfahren kann auch verwendet werden, um weitere benutzerdefinierten Eigenschaften hinzufügen. Ersetzen Sie Ihr benutzerdefinierter Eigenschaftenname für die CircleOffset Eigenschaftennamen und Parameter.

#### <a name="to-add-the-circleoffset-custom-property-using-the-add-property-wizard"></a>Zum Hinzufügen der benutzerdefinierten CircleOffset-Eigenschaft, die mithilfe des Assistenten zum Hinzufügen von Eigenschaften

1. Laden Sie das Steuerelementprojekt.

1. Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.

1. Klicken Sie mit der rechten Maustaste auf den Schnittstellenknoten des Steuerelements (den zweiten Knoten des Bibliotheksknotens), um das Kontextmenü zu öffnen.

1. Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Eigenschaft hinzufügen**.

   Daraufhin wird die [Assistent zum Hinzufügen von Eigenschaften](../ide/names-add-property-wizard.md).

1. In der **Eigenschaftennamen** geben *CircleOffset*.

1. Klicken Sie unter **Implementierungstyp**auf **Get/Set-Methoden**.

1. In der **Eigenschaftentyp** Kontrollkästchen **kurze**.

1. Geben Sie eindeutige Namen für die Get- und Set-Funktion, oder übernehmen Sie die Standardnamen.

9. Klicken Sie auf **Fertig stellen**.

##  <a name="_core_classwizard_changes_for_custom_properties"></a> Hinzufügen von Eigenschaftenänderungen-Assistenten für benutzerdefinierte Eigenschaften

Wenn Sie die benutzerdefinierte CircleOffset-Eigenschaft hinzufügen, nimmt der Assistent zum Hinzufügen von Eigenschaften Änderungen an den Header (. H) und die Implementierung (. CPP)-Dateien von der Control-Klasse.

Die folgenden Zeilen werden hinzugefügt, um die. H-Datei, um zwei aufgerufenen Funktionen zu deklarieren `GetCircleOffset` und `SetCircleOffset`:

[!code-cpp[NVC_MFC_AxUI#25](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_1.h)]

Des Steuerelements wird die folgende Zeile hinzugefügt. IDL-Datei:

[!code-cpp[NVC_MFC_AxUI#26](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_2.idl)]

Diese Zeile weist der CircleOffset-Eigenschaft eine bestimmte ID-Nummer, stammt von der Position der Methode in der Liste von Methoden und Eigenschaften von den Assistenten zum Hinzufügen einer Eigenschaft an.

Darüber hinaus wird die folgende Zeile hinzugefügt, um die Dispatchzuordnung (in der. CPP-Datei von der Control-Klasse) zum Zuordnen der CircleOffset-Eigenschaft des Steuerelements zwei Handler Funktionen:

[!code-cpp[NVC_MFC_AxUI#27](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_3.cpp)]

Zum Schluss die Implementierungen der `GetCircleOffset` und `SetCircleOffset` Funktionen wurden hinzugefügt, bis zum Ende des Steuerelements. CPP-Datei. In den meisten Fällen ändern Sie die Get-Funktion, um den Wert der Eigenschaft zurückzugeben. Die Set-Funktion wird in der Regel Code enthalten, die entweder vor oder nach der Änderung der Eigenschaft ausgeführt werden soll.

[!code-cpp[NVC_MFC_AxUI#28](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_4.cpp)]

Beachten Sie, dass der Assistent zum Hinzufügen von Eigenschaften automatisch zu einen Aufruf fügt [SetModifiedFlag](../mfc/reference/colecontrol-class.md#setmodifiedflag), in den Hauptteil der Funktion. Das Aufrufen dieser Funktion markiert das Steuerelement als geändert. Wenn ein Steuerelement geändert wurde, wird sein neue Status gespeichert werden, wenn der Container gespeichert wird. Diese Funktion sollte aufgerufen werden, wenn sich eine Eigenschaft, die als Teil des persistenten Status des Steuerelements gespeichert Wert ändert.

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)<br/>
[MFC-ActiveX-Steuerelemente: Eigenschaften](../mfc/mfc-activex-controls-properties.md)<br/>
[MFC-ActiveX-Steuerelemente: Methoden](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl-Klasse](../mfc/reference/colecontrol-class.md)
