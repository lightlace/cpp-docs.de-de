---
title: "Hinzufügen eines Steuerelements (ATL-Lernprogramm, Teil 2) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
ms.assetid: c9575a75-1064-41f1-9697-7aada560c669
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aed69a5dd421e967e1da33bb3a2f2c41fa80698d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="adding-a-control-atl-tutorial-part-2"></a>Hinzufügen eines Steuerelements (ATL-Lernprogramm, Teil 2)
In diesem Schritt fügen Sie Ihrem Projekt ein Steuerelement hinzu, erstellen es und testen es auf einer Webseite.  
  
## <a name="procedures"></a>Verfahren  
  
#### <a name="to-add-an-object-to-an-atl-project"></a>So fügen Sie einem ATL-Projekt ein Objekt hinzu  
  
1.  Klicken Sie in der Klassenansicht mit der rechten Maustaste auf das Projekt "Polygon".  
  
2.  Zeigen Sie auf **hinzufügen** auf das Kontextmenü, und klicken Sie auf **Klasse** im Untermenü.  
  
     Die **Klasse hinzufügen** Dialogfeld wird angezeigt. Die verschiedenen Objektkategorien werden in der Struktur links aufgeführt.  
  
3.  Klicken Sie auf die **ATL** Ordner.  
  
4.  Wählen Sie in der Liste der Vorlagen auf der rechten Seite, **ATL-Steuerelement**. Klicken Sie auf **Hinzufügen**. Der ATL-Steuerelement-Assistent wird geöffnet, und Sie können das Steuerelement konfigurieren.  
  
5.  Typ `PolyCtl` als den Kurznamen ein, und beachten Sie, dass die anderen Felder automatisch vervollständigt werden. Klicken Sie nicht auf **Fertig stellen** noch, da einige Änderungen vorgenommen werden muss.  
  
 Der ATL-Steuerelement-Assistent **Namen** Seite enthält die folgenden Felder:  
  
|Feld|Inhalt|  
|-----------|--------------|  
|**Kurzname**|Der Name, den Sie für das Steuerelement eingegeben haben.|  
|**Klasse**|Der C++-Klassenname, der erstellt wurde, um das Steuerelement zu implementieren.|  
|**.h-Datei**|Die Datei, die erstellt wurde, um die Definition der C++-Klasse zu enthalten.|  
|**CPP-Datei**|Die Datei, die erstellt wurde, um die Implementierung der C++-Klasse zu enthalten.|  
|**Co-Klasse**|Der Name der Komponentenklasse für dieses Steuerelement.|  
|**Interface**|Der Name der Schnittstelle, auf der das Steuerelement die benutzerdefinierten Methoden und Eigenschaften implementiert.|  
|**Type**|Eine Beschreibung für das Steuerelement.|  
|**ProgID**|Der lesbare Name, der verwendet werden kann, um die CLSID des Steuerelements zu suchen.|  
  
 Sie müssen einige zusätzliche Einstellungen im ATL-Steuerelement-Assistenten vornehmen.  
  
#### <a name="to-enable-support-for-rich-error-information-and-connection-points"></a>So aktivieren Sie die Unterstützung für aussagekräftige Fehlerinformationen und Verbindungspunkte  
  
1.  Klicken Sie auf **Optionen** So öffnen die **Optionen** Seite.  
  
2.  Wählen Sie die **Verbindungspunkte** Kontrollkästchen. Dadurch wird die Unterstützung einer Ausgangsschnittstelle in der IDL-Datei erstellt.  
  
 Sie können das Steuerelement auch einfügbar machen. Das heißt, es kann in Anwendungen eingebettet werden, die eingebettete Objekten unterstützen, wie z. B. Excel oder Word.  
  
#### <a name="to-make-the-control-insertable"></a>So machen Sie das Steuerelement einfügbar  
  
1.  Klicken Sie auf **Darstellung** So öffnen die **Darstellung** Seite.  
  
2.  Wählen Sie die **einfügbar** Kontrollkästchen.  
  
 Das Polygon, das durch das Objekt angezeigt wird, verfügt über einfarbige Füllung. Deshalb müssen Sie eine `Fill Color`-Basiseigenschaft hinzufügen.  
  
#### <a name="to-add-a-fill-color-stock-property-and-create-the-control"></a>So fügen Sie eine Füllfarben-Basiseigenschaft hinzu und erstellen das Steuerelement  
  
1.  Klicken Sie auf **Basiseigenschaften** So öffnen die **Basiseigenschaften** Seite.  
  
2.  Klicken Sie unter **nicht unterstützt**, führen Sie einen Bildlauf nach unten in der Liste möglicher Basiseigenschaften. Doppelklicken Sie auf `Fill Color` verschoben werden sollen die **unterstützte** Liste.  
  
3.  Dies vervollständigt die Optionen für das Steuerelement. Klicken Sie auf **Fertig stellen**.  
  
 Während der Assistent das Steuerelement erstellte, wurden mehrere Codeänderungen und Dateihinzufügungen ausgeführt. Die folgenden Dateien wurden erstellt:  
  
|Datei|Beschreibung|  
|----------|-----------------|  
|PolyCtl.h|Sie enthält den größten Teil der Implementierung der C++-Klasse `CPolyCtl`.|  
|PolyCtl.cpp|Sie enthält die verbleibenden Teile von `CPolyCtl`.|  
|PolyCtl.rgs|Eine Textdatei, die das Registrierungsskript enthält, das verwendet wird, um das Steuerelement zu registrieren.|  
|PolyCtl.htm|Eine Webseite, die einen Verweis auf das neu erstellte Steuerelement enthält.|  
  
 Der Assistent führt auch die folgenden Codeänderungen aus:  
  
-   Er fügte den Dateien "stdafx.h" und "stdafx.cpp" eine `#include`-Anweisung hinzu, um die zur Unterstützung von Steuerelementen erforderlichen ATL-Dateien einzuschließen.  
  
-   Er änderte Polygon.idl, um Details des neuen Steuerelements einzuschließen.  
  
-   Er fügte das neue Steuerelement zur Objektzuordnung in Polygon.cpp hinzu.  
  
 Jetzt können Sie das Steuerelement erstellen, um es in Aktion zu sehen.  
  
## <a name="building-and-testing-the-control"></a>Erstellen und Testen des Steuerelements  
  
#### <a name="to-build-and-test-the-control"></a>So erstellen Sie das Steuerelement und testen es  
  
1.  Auf der **erstellen** Menü klicken Sie auf **Polygon erstellen**.  
  
     Sobald das Steuerelement erstellen beendet wurde, mit der rechten Maustaste PolyCtl.htm in **Projektmappen-Explorer** , und wählen Sie **in Browser anzeigen**. Die HTML-Webseite, die das Steuerelement enthält, wird angezeigt. Daraufhin sollte eine Seite mit dem Titel "ATL 8.0-Testseite für Objekt PolyCtl" und der Text **PolyCtl**. Dies ist Ihr Steuerelement.  
  
> [!NOTE]
>  Wenn Sie beim Abschließen dieses Lernprogramms eine Fehlermeldung erhalten, dass die DLL-Datei nicht erstellt werden kann, schließen Sie die Datei "PolyCtl.htm" und den Testcontainer für ActiveX-Steuerelemente und erstellen Sie die Projektmappe erneut. Wenn Sie die DLL immer noch nicht erstellen können, starten Sie den Computer neu oder melden Sie sich ab (wenn Sie die Terminaldienste verwenden).  
  
 Als Nächstes fügen Sie dem Steuerelement eine benutzerdefinierte Eigenschaft hinzu.  
  
 [Zurück zu Schritt 1](../atl/creating-the-project-atl-tutorial-part-1.md) &#124; [Weiter zu Schritt 3](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Lernprogramm](../atl/active-template-library-atl-tutorial.md)

