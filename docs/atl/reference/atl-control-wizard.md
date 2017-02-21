---
title: "ATL-Steuerelement-Assistent | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.control.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Steuerelement-Assistent"
  - "ATL-Projekte, Hinzufügen von Steuerelementen"
  - "Steuerelemente [ATL], Hinzufügen zu Projekten"
ms.assetid: 991f8e72-ffbc-4382-a4ce-e255acfba5b6
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# ATL-Steuerelement-Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fügt ein ATL\-Steuerelement in ein ATL\-Projekt \(oder in ein MFC\-Projekt mit ATL\-Unterstützung\) ein.  Mithilfe dieses Assistenten fügen Sie eine von drei Steuerelementarten ein:  
  
-   Standardsteuerelement  
  
-   Zusammengesetztes Steuerelement  
  
-   DHTML\-Steuerelement  
  
 Zusätzlich können Sie ein Minimal\-Steuerelement implementieren, indem Sie die Schnittstellen aus der Liste der [Schnittstellen](../../atl/reference/interfaces-atl-control-wizard.md) entfernen, die standardmäßig für die Steuerelemente bereitgestellt und in den meisten Containern geöffnet werden.  Die Schnittstellen, die für das Steuerelement unterstützt werden sollen, können auf der Seite **Schnittstellen** des Assistenten festgelegt werden.  
  
## Hinweise  
 Das von diesem Assistenten erstellte Registrierungsskript registriert die COM\-Komponenten unter HKEY\_CURRENT\_USER und nicht unter HKEY\_LOCAL\_MACHINE.  Um dieses Verhalten zu ändern, legen Sie die Option **Komponente für alle Benutzer registrieren** des ATL\-Assistenten fest.  
  
## Namen  
 Geben Sie die Namen für Objekt, Schnittstelle und Klassen an, die dem Projekt hinzugefügt werden sollen.  Mit Ausnahme von **Kurzname** können alle weiteren Felder unabhängig voneinander geändert werden.  Wenn Sie den Eintrag unter **Kurzer Name** ändern, wirkt sich die Änderung auf die Namen in allen anderen Feldern auf dieser Seite aus.  Wenn Sie den Namen unter **Coclass** im COM\-Abschnitt ändern, wirkt sich die Änderung auf die Felder **Typ** aus, der Name unter **Schnittstelle** und **Programm\-ID** bleibt jedoch unverändert.  Das Namenssystem ist so ausgelegt, dass alle Namen während der Entwicklung des Steuerelements leicht identifizierbar sind.  
  
> [!NOTE]
>  **Coclass** kann nur bei nicht attributierten Steuerelementen bearbeitet werden.  Verfügt das Projekt über Attribute, kann **Coclass** nicht bearbeitet werden.  
  
### C\+\+  
 Liefert Informationen über die C\+\+\-Klasse, die zur Implementierung des Objekts erstellt wurde.  
  
 **Kurzer Name**  
 Legt den abgekürzten Namen für das Objekt fest.  Der hier angegebene Name bestimmt den Klassennamen sowie den unter **Coclass** angegebenen Namen, die Dateinamen \(.cpp und .H\), den Schnittstellennamen, und die Namen der **Typen** sowie die ProgID, sofern Sie diese Felder nicht einzeln ändern.  
  
 **Klasse**  
 Legt den Namen der Klasse fest, durch die das Objekt implementiert wird.  Dieser Name basiert auf dem unter **Kurzer Name** angegebenen Namen. Allerdings wird der Buchstabe C als typisches Präfix für einen Klassennamen vorangestellt.  
  
 **.h\-Datei**  
 Legt den Namen der Headerdatei für die neue Objektklasse fest.  Dieser Name basiert standardmäßig auf dem unter **Kurzer Name** angegebenen Namen.  Klicken Sie auf die Schaltfläche mit den Auslassungspunkten \(...\), um den Dateinamen am gewünschten Speicherort zu speichern oder um die Klassendeklaration an eine vorhandene Datei anzufügen.  Wenn Sie eine vorhandene Datei auswählen, wird sie vom Assistenten erst am ausgewählten Speicherort gespeichert, nachdem Sie auf **Fertig stellen** geklickt haben.  
  
 Der Assistent ist nicht in der Lage, Dateien zu überschreiben.  Wenn Sie den Namen einer vorhandenen Datei auswählen und dann auf **Fertig stellen** klicken, wird vom Assistenten eine Bestätigung angefordert, die Klassendeklaration an den Inhalt der Datei anzufügen.  Klicken Sie auf **Ja**, um die Datei anzufügen, und klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.  
  
 **.cpp\-Datei**  
 Legt für die neue Objektklasse den Namen der Implementierungsdatei fest.  Dieser Name basiert standardmäßig auf dem unter **Kurzer Name** angegebenen Namen.  Klicken Sie auf die Schaltfläche mit den Auslassungspunkten \(...\), um den Dateinamen am gewünschten Speicherort zu speichern.  Die Datei wird erst am ausgewählten Speicherort gespeichert, wenn Sie im Assistenten auf **Fertig stellen** klicken.  
  
 Der Assistent ist nicht in der Lage, Dateien zu überschreiben.  Wenn Sie den Namen einer vorhandenen Datei auswählen und dann auf **Fertig stellen** klicken, werden Sie vom Assistenten gefragt, ob die Klassenimplementierung an den Inhalt der Datei angefügt werden soll.  Klicken Sie auf **Ja**, um die Datei anzufügen, und klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.  
  
 **Attributiert**  
 Gibt an, ob das Objekt Attribute verwendet.  Wenn Sie einem attributierten ATL\-Projekt ein Objekt hinzufügen, ist diese Option aktiviert und kann nicht geändert werden.  Dies bedeutet, dass einem Projekt, das mit Attributunterstützung erstellt wurde, nur attributierte Objekte hinzugefügt werden können.  
  
 Ein attributiertes Objekt kann lediglich einem ATL\-Projekt hinzugefügt werden, das Attribute verwendet.  Wenn Sie diese Option für ein ATL\-Projekt auswählen, das nicht über Attributunterstützung verfügt, werden Sie vom Assistenten gefragt, ob dem Projekt Attributunterstützung hinzugefügt werden soll.  
  
 Alle Objekte, die nach Auswahl dieser Option hinzugefügt wurden, werden automatisch als attributiert konfiguriert \(das Kontrollkästchen ist aktiviert\).  Sie können das Kontrollkästchen deaktivieren, um ein Objekt hinzuzufügen, das keine Attribute verwendet.  
  
 Weitere Informationen finden Sie unter [Anwendungseinstellungen, ATL\-Projekt\-Assistent](../../atl/reference/application-settings-atl-project-wizard.md) und [Grundlegende Funktionsweise von Attributen](../../windows/basic-mechanics-of-attributes.md).  
  
### COM  
 Bietet Informationen über die COM\-Funktionen des Objekts.  
  
 **Coclass**  
 Legt den Namen der Komponentenklasse fest. Sie enthält eine Liste der vom Objekt unterstützten Schnittstellen.  
  
> [!NOTE]
>  Wenn Sie das Projekt unter Verwendung von Attributen erstellen oder auf der entsprechenden Seite dieses Assistenten angeben, dass das Steuerelement Attribute verwendet, können Sie diese Option nicht ändern, da das **coclass**\-Attribut nicht in ATL enthalten ist.  
  
 **Interface**  
 Legt den Namen der Schnittstelle für das Objekt fest.  Dem Schnittstellennamen wird standardmäßig der Buchstabe "I" vorangestellt.  
  
 **Text \[Type\]**  
 Legt die in der Registrierung verwendete Objektbeschreibung fest.  
  
 **ProgID**  
 Legt den Namen fest, den Container anstelle der CLSID des Objekts verwenden können.  Dieses Feld wird nicht automatisch aufgefüllt.  Wenn Sie dieses Feld nicht manuell auffüllen, steht das Steuerelement möglicherweise anderen Tools nicht zur Verfügung.  ActiveX\-Steuerelemente, die ohne `ProgID` generiert werden, sind z. B. im Dialogfeld **ActiveX\-Steuerelement einfügen** nicht verfügbar.  Weitere Informationen über das Dialogfeld finden Sie unter [Dialogfeld "ActiveX\-Steuerelement einfügen"](../../mfc/insert-activex-control-dialog-box.md).  
  
## Siehe auch  
 [ATL Control](../../atl/reference/adding-an-atl-control.md)   
 [Adding Functionality to the Composite Control](../../atl/adding-functionality-to-the-composite-control.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)