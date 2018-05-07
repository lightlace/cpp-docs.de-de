---
title: 'MFC-ActiveX-Steuerelemente: Verwenden der Datenbindung in einem ActiveX-Steuerelement | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- bindable
- requestedit
- defaultbind
- displaybind
- dispid
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], data binding
- data binding [MFC], MFC ActiveX controls
- data-bound controls [MFC], MFC ActiveX controls
- controls [MFC], data binding
- bound controls [MFC], MFC ActiveX
ms.assetid: 476b590a-bf2a-498a-81b7-dd476bd346f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ab5195cc2381e515688182ad73452b07afd06b98
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-activex-controls-using-data-binding-in-an-activex-control"></a>MFC-ActiveX-Steuerelemente: Verwenden der Datenbindung in einem ActiveX-Steuerelement
Einer der leistungsfähigeren von ActiveX-Steuerelementen ist Datenbindung, wodurch eine Eigenschaft des Steuerelements an ein bestimmtes Feld in einer Datenbank gebunden werden soll. Wenn ein Benutzer Daten in dieser gebundenen Eigenschaft ändert, benachrichtigt das Steuerelement an die Datenbank und fordert an, dass der Datensatz das Feld aktualisiert werden. Anschließend benachrichtigt die Datenbank, die Kontrolle über den Erfolg oder Fehler der Anforderung.  
  
 Dieser Artikel behandelt die Steuerelement-Seite der Aufgabe. Implementieren die Daten binden von Interaktionen mit der Datenbank liegt in der Verantwortung des Steuerelementcontainers. Zum Verwalten von Datenbankinteraktionen im Container ist, würde den Rahmen dieser Dokumentation sprengen. Wie Sie das Steuerelement für die Datenbindung vorbereiten werden in den weiteren Verlauf dieses Artikels erläutert.  
  
 ![Konzeptionelle Darstellung der Daten&#45;gebundenes Steuerelement](../mfc/media/vc374v1.gif "vc374v1")  
Konzeptionelles Diagramm eines datengebundenen Steuerelements  
  
 Die `COleControl` Klasse bietet zwei Memberfunktionen, die Datenbindung für ein einfacher Vorgang implementiert. Die erste Funktion [BoundPropertyRequestEdit](../mfc/reference/colecontrol-class.md#boundpropertyrequestedit), wird verwendet, um die Berechtigung zum Ändern des Werts der Eigenschaft angefordert werden. [BoundPropertyChanged](../mfc/reference/colecontrol-class.md#boundpropertychanged), die zweite Funktion wird aufgerufen, nachdem der Eigenschaftswert erfolgreich geändert wurde.  
  
 In diesem Artikel werden die folgenden Themen behandelt:  
  
-   [Erstellen eine bindbare Systemeigenschaft](#vchowcreatingbindablestockproperty)  
  
-   [Erstellen eine bindbare Get/Set-Methode](#vchowcreatingbindablegetsetmethod)  
  
##  <a name="vchowcreatingbindablestockproperty"></a> Erstellen eine bindbare Systemeigenschaft  
 Es ist möglich, eine datengebundene-Systemeigenschaft erstellen, obwohl es wahrscheinlicher ist, Sie sollten eine [bindbare Get/Set-Methode](#vchowcreatingbindablegetsetmethod).  
  
> [!NOTE]
>  Vordefinierte Eigenschaften haben die **bindbare** und **Requestedit** Attribute standardmäßig.  
  
#### <a name="to-add-a-bindable-stock-property-using-the-add-property-wizard"></a>So fügen Sie eine bindbare Systemeigenschaft mithilfe des Assistenten zum Hinzufügen von Eigenschaften hinzu  
  
1.  Starten Sie ein Projekt mit der [MFC-ActiveX-Steuerelement-Assistent](../mfc/reference/mfc-activex-control-wizard.md).  
  
2.  Klicken Sie auf den Schnittstellenknoten des Steuerelements.  
  
     Dadurch wird das Kontextmenü geöffnet.  
  
3.  Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Eigenschaft hinzufügen**.  
  
4.  Wählen Sie einen der Einträge aus der **Eigenschaftsname** Dropdown-Liste. Sie können beispielsweise auswählen **Text**.  
  
     Da **Text** eine Systemeigenschaft ist die **bindbare** und **Requestedit** Attribute sind automatisch ausgewählt.  
  
5.  Die folgenden Kontrollkästchen aus der **IDL-Attribute** Registerkarte: **Displaybind** und **Defaultbind** um die Attribute auf die Eigenschaftsdefinition in des Projekts hinzuzufügen. IDL-Datei. Diese Attribute stellen das Steuerelement für den Benutzer sichtbar und der Systemeigenschaft bindbare Standardeigenschaft.  
  
 Zu diesem Zeitpunkt das Steuerelement kann Daten aus einer Datenquelle anzeigen, aber der Benutzer wird nicht in der Lage, Datenfelder zu aktualisieren. Wenn Sie möchten das Steuerelement in der auch in der Lage, Daten aktualisieren, ändern Sie die `OnOcmCommand` [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) Funktion wie folgt aussehen:  
  
 [!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]  
  
 Sie können jetzt das Projekt erstellen, das das Steuerelement zu registrieren. Wenn Sie das Steuerelement in einem Dialogfeld Einfügen der **Feld "Daten"** und **Datenquelle** Eigenschaften werden hinzugefügt wurden, und Sie können jetzt auswählen, eine Datenquelle und die im Steuerelement anzuzeigende Feld.  
  
##  <a name="vchowcreatingbindablegetsetmethod"></a> Erstellen eine bindbare Get/Set-Methode  
 Sie können auch erstellen, zusätzlich zu einem datengebundenen Get/Set-Methode, eine [bindbare Systemeigenschaft](#vchowcreatingbindablestockproperty).  
  
> [!NOTE]
>  Dieses Verfahren setzt voraus, dass Sie ein ActiveX-Steuerelement, Unterklassen ein Windows-Steuerelements Projekt haben.  
  
#### <a name="to-add-a-bindable-getset-method-using-the-add-property-wizard"></a>So fügen Sie eine bindbare Get/Set-Methode, die mithilfe des Assistenten zum Hinzufügen von Eigenschaften hinzu  
  
1.  Laden Sie das Steuerelementprojekt.  
  
2.  Auf der **Steuerelementeinstellungen** Seite, wählen Sie eine Fensterklasse für das Steuerelement auf die Unterklasse. Z. B. empfiehlt das Erstellen einer Unterklasse ein Bearbeitungssteuerelement.  
  
3.  Laden Sie das Steuerelementprojekt.  
  
4.  Klicken Sie auf den Schnittstellenknoten des Steuerelements.  
  
     Dadurch wird das Kontextmenü geöffnet.  
  
5.  Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Eigenschaft hinzufügen**.  
  
6.  Geben Sie den Eigenschaftennamen in der **Eigenschaftsname** Feld. Verwendung `MyProp` für dieses Beispiel.  
  
7.  Wählen Sie einen Datentyp aus der **Eigenschaftentyp** Dropdown Listenfeld aus. Verwendung **kurze** für dieses Beispiel.  
  
8.  Klicken Sie unter **Implementierungstyp**auf **Get/Set-Methoden**.  
  
9. Die folgenden Kontrollkästchen auf der Registerkarte IDL-Attribute: **bindbare**, **Requestedit**, **Displaybind**, und **Defaultbind** hinzufügen die Attribute auf die Eigenschaftsdefinition des Projekts. IDL-Datei. Diese Attribute stellen das Steuerelement für den Benutzer sichtbar und der Systemeigenschaft bindbare Standardeigenschaft.  
  
10. Klicken Sie auf **Fertig stellen**.  
  
11. Ändern Sie den Hauptteil der `SetMyProp` Funktion so, dass sie den folgenden Code enthält:  
  
     [!code-cpp[NVC_MFC_AxData#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_2.cpp)]  
  
12. Der Parameter zu übergeben, um die `BoundPropertyChanged` und `BoundPropertyRequestEdit` Funktionen ist die Dispid der-Eigenschaft, die der übergebene an die für die Eigenschaft in Parameter der. IDL-Datei.  
  
13. Ändern der [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) funktionieren, damit sie den folgenden Code enthält:  
  
     [!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]  
  
14. Ändern der `OnDraw` Funktion so, dass sie den folgenden Code enthält:  
  
     [!code-cpp[NVC_MFC_AxData#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_3.cpp)]  
  
15. Fügen Sie dem öffentlichen Abschnitt der Headerdatei die Headerdatei für eine Klasse die folgenden Definitionen (Konstruktoren) für Membervariablen hinzu:  
  
     [!code-cpp[NVC_MFC_AxData#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_4.h)]  
  
16. Stellen Sie der folgenden Zeile in die letzte Zeile der `DoPropExchange` Funktion:  
  
     [!code-cpp[NVC_MFC_AxData#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_5.cpp)]  
  
17. Ändern der `OnResetState` Funktion so, dass sie den folgenden Code enthält:  
  
     [!code-cpp[NVC_MFC_AxData#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_6.cpp)]  
  
18. Ändern der `GetMyProp` Funktion so, dass sie den folgenden Code enthält:  
  
     [!code-cpp[NVC_MFC_AxData#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_7.cpp)]  
  
 Sie können jetzt das Projekt erstellen, das das Steuerelement zu registrieren. Wenn Sie das Steuerelement in einem Dialogfeld Einfügen der **Feld "Daten"** und **Datenquelle** Eigenschaften werden hinzugefügt wurden, und Sie können jetzt auswählen, eine Datenquelle und die im Steuerelement anzuzeigende Feld.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)   

