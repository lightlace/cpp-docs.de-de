---
title: "Hinzuf&#252;gen eines Steuerelements (ATL-Lernprogramm, Teil 2) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
ms.assetid: c9575a75-1064-41f1-9697-7aada560c669
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Hinzuf&#252;gen eines Steuerelements (ATL-Lernprogramm, Teil 2)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Schritt fügen Sie Ihrem Projekt ein Steuerelement hinzu, erstellen es und testen es auf einer Webseite.  
  
## Prozeduren  
  
#### So fügen Sie einem ATL\-Projekt ein Objekt hinzu  
  
1.  Klicken Sie in der Klassenansicht mit der rechten Maustaste auf das Projekt "Polygon".  
  
2.  Zeigen Sie auf **Hinzufügen** im Kontextmenü, und klicken Sie im Untermenü auf **Klasse**.  
  
     Das Dialogfeld **Klasse hinzufügen** wird angezeigt.  Die verschiedenen Objektkategorien werden in der Baumstruktur links aufgeführt.  
  
3.  Klicken Sie auf den Ordner **ATL**.  
  
4.  In der Liste der Vorlagen auf der rechten Seite, wählen Sie **ATL\-Steuerelement** aus.  Klicken Sie auf **Hinzufügen**.  Der ATL\-Steuerelement\-Assistent wird geöffnet, und Sie können das Steuerelement konfigurieren.  
  
5.  Geben Sie `PolyCtl` als den Kurznamen ein, und beachten Sie, dass die anderen Felder automatisch vervollständigt werden.  Klicken Sie noch nicht auf **Fertig stellen**, da Sie einige Änderungen vornehmen müssen.  
  
 Die Seite **Namen** des ATL\-Steuerelement\-Assistenten enthält die folgenden Felder:  
  
|Feld|Inhalt|  
|----------|------------|  
|**Kurzer Name**|Der Name, den Sie für das Steuerelement eingegeben haben.|  
|**Klasse**|Der C\+\+\-Klassenname, der erstellt wurde, um das Steuerelement zu implementieren.|  
|**.h\-Datei**|Die Datei, die erstellt wurde, um die Definition der C\+\+\-Klasse zu enthalten.|  
|**.cpp\-Datei**|Die Datei, die erstellt wurde, um die Implementierung der C\+\+\-Klasse zu enthalten.|  
|**Coclass**|Der Name der Komponentenklasse für dieses Steuerelement.|  
|**Schnittstelle**|Der Name der Schnittstelle, auf der das Steuerelement die benutzerdefinierten Methoden und Eigenschaften implementiert.|  
|**Typ**|Eine Beschreibung für das Steuerelement.|  
|**ProgID**|Der lesbare Name, der verwendet werden kann, um die CLSID des Steuerelements zu suchen.|  
  
 Sie müssen einige zusätzliche Einstellungen im ATL\-Steuerelement\-Assistenten vornehmen.  
  
#### So aktivieren Sie die Unterstützung für aussagekräftige Fehlerinformationen und Verbindungspunkte  
  
1.  Klicken Sie auf **Optionen**, um die Seite **Optionen** zu öffnen.  
  
2.  Aktivieren Sie das Kontrollkästchen **Verbindungspunkte**.  Dadurch wird die Unterstützung einer Ausgangsschnittstelle in der IDL\-Datei erstellt.  
  
 Sie können das Steuerelement auch einfügbar machen. Das heißt, es kann in Anwendungen eingebettet werden, die eingebettete Objekten unterstützen, wie z. B. Excel oder Word.  
  
#### So machen Sie das Steuerelement einfügbar  
  
1.  Klicken auf **Darstellung**, um die Seite **Darstellung** zu öffnen.  
  
2.  Aktivieren Sie das Kontrollkästchen **Einfügbar**.  
  
 Das Polygon, das durch das Objekt angezeigt wird, verfügt über einfarbige Füllung. Deshalb müssen Sie eine `Fill Color`\-Basiseigenschaft hinzufügen.  
  
#### So fügen Sie eine Füllfarben\-Basiseigenschaft hinzu und erstellen das Steuerelement  
  
1.  Klicken auf **Basiseigenschaften**, um die Seite **Basiseigenschaften** zu öffnen.  
  
2.  Führen Sie unter **Nicht unterstützt** auf der Liste möglicher Basiseigenschaften den Bildlauf nach unten durch.  Doppelklicken Sie auf `Fill Color`, um es in die Liste **Unterstützt** zu verschieben.  
  
3.  Dies vervollständigt die Optionen für das Steuerelement.  Klicken Sie auf **Fertig stellen**.  
  
 Während der Assistent das Steuerelement erstellte, wurden mehrere Codeänderungen und Dateihinzufügungen ausgeführt.  Die folgenden Dateien wurden erstellt:  
  
|Datei|Beschreibung|  
|-----------|------------------|  
|PolyCtl.h|Sie enthält den größten Teil der Implementierung der C\+\+\-Klasse `CPolyCtl`.|  
|PolyCtl.cpp|Sie enthält die verbleibenden Teile von `CPolyCtl`.|  
|PolyCtl.rgs|Eine Textdatei, die das Registrierungsskript enthält, das verwendet wird, um das Steuerelement zu registrieren.|  
|PolyCtl.htm|Eine Webseite, die einen Verweis auf das neu erstellte Steuerelement enthält.|  
  
 Der Assistent führt auch die folgenden Codeänderungen aus:  
  
-   Er fügte den Dateien "stdafx.h" und "stdafx.cpp" eine `#include`\-Anweisung hinzu, um die zur Unterstützung von Steuerelementen erforderlichen ATL\-Dateien einzuschließen.  
  
-   Er änderte Polygon.idl, um Details des neuen Steuerelements einzuschließen.  
  
-   Er fügte das neue Steuerelement zur Objektzuordnung in Polygon.cpp hinzu.  
  
 Jetzt können Sie das Steuerelement erstellen, um es in Aktion zu sehen.  
  
## Erstellen und Testen des Steuerelements  
  
#### So erstellen Sie das Steuerelement und testen es  
  
1.  Klicken Sie im Menü **Erstellen** auf **Polygon erstellen**.  
  
     Sobald die Erstellung des Steuerelements abgeschlossen ist, klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf PolyCtl.htm und wählen Sie **In Browser anzeigen** aus.  Die HTML\-Webseite, die das Steuerelement enthält, wird angezeigt.  Eine Seite mit dem Titel "ATL 8.0\-Testseite für Objekt PolyCtl" sowie der Text **PolyCtl** sollten angezeigt werden.  Dies ist Ihr Steuerelement.  
  
> [!NOTE]
>  Wenn Sie beim Abschließen dieses Lernprogramms eine Fehlermeldung erhalten, dass die DLL\-Datei nicht erstellt werden kann, schließen Sie die Datei "PolyCtl.htm" und den Testcontainer für ActiveX\-Steuerelemente und erstellen Sie die Projektmappe erneut.  Wenn Sie die DLL immer noch nicht erstellen können, starten Sie den Computer neu oder melden Sie sich ab \(wenn Sie die Terminaldienste verwenden\).  
  
 Als Nächstes fügen Sie dem Steuerelement eine benutzerdefinierte Eigenschaft hinzu.  
  
 [Zurück zu Schritt 1](../atl/creating-the-project-atl-tutorial-part-1.md) &#124; [Weiter zu Schritt 3](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md)  
  
## Siehe auch  
 [Lernprogramm](../atl/active-template-library-atl-tutorial.md)