---
title: "ATL-Assistent f&#252;r Active Server Page-Komponenten"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.asp.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ASP-Komponenten, creating in ATL"
  - "ATL-Assistent für Active Server Page-Komponenten"
ms.assetid: 5a5cb904-dbbf-44ea-ad3d-2ddd14c1d3c5
caps.latest.revision: 13
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# ATL-Assistent f&#252;r Active Server Page-Komponenten
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit diesem Assistenten wird eine Active Server Pages \(ASP\)\-Komponente in das Projekt eingefügt.  In Microsoft Internet\-Informationsdienste \(IIS\) werden ASP\-Komponenten als Teil der erweiterten Entwicklungsarchitektur für Webseiten verwendet.  
  
 Mithilfe dieses Assistenten können Sie das für die Komponente verwendete Threadingmodell und die Aggregationsunterstützung festlegen.  Darüber hinaus können Sie Unterstützung für die Fehlerinformationsschnittstelle, für Verbindungspunkte und freethreaded Marshalling aktivieren.  
  
## Hinweise  
 Ab [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)] registriert das von diesem Assistenten erstellte Registrierungsskript seine COM\-Komponenten unter **HKEY\_CURRENT\_USER** statt unter **HKEY\_LOCAL\_MACHINE**.  Um dieses Verhalten zu ändern, legen Sie die Option **Komponente für alle Benutzer registrieren** des ATL\-Assistenten fest.  
  
## Namen  
 Geben Sie die Namen für Objekt, Schnittstelle und Klassen an, die dem Projekt hinzugefügt werden sollen.  Mit Ausnahme von **Kurzer Name** können alle weiteren Felder unabhängig voneinander bearbeitet werden.  Wenn Sie den Eintrag unter **Kurzer Name** ändern, wirkt sich die Änderung auf die Namen in allen anderen Feldern auf dieser Seite aus.  
  
 Wenn Sie den Namen unter **Coclass** im COM\-Abschnitt ändern, wirkt sich die Änderung auf die Felder **Typ** und **Programm\-ID** aus, der Name unter **Schnittstelle** bleibt jedoch unverändert.  Das Namenssystem ist so ausgelegt, dass alle Namen während der Entwicklung des Steuerelements leicht identifizierbar sind.  
  
### C\+\+  
 Liefert Informationen zu der für das Objekt erstellten C\+\+\-Klasse.  
  
 **Kurzer Name**  
 Legt den Stammnamen für das Objekt fest.  Der hier angegebene Name bestimmt die Namen unter `Class` und **Coclass**, die Namen der **.cpp\-Datei** und **.h\-Datei**, den Namen der **Schnittstelle**, die Namen unter **Typ** sowie die **Programm\-ID**, sofern Sie diese Felder nicht einzeln ändern.  
  
 **.h\-Datei**  
 Legt den Namen der Headerdatei für die neue Objektklasse fest.  Dieser Name basiert standardmäßig auf dem unter **Kurzer Name** angegebenen Namen.  Klicken Sie auf die Schaltfläche mit den Auslassungspunkten \(...\), um den Dateinamen am gewünschten Speicherort zu speichern oder um die Klassendeklaration an eine vorhandene Datei anzufügen.  Wenn Sie eine vorhandene Datei auswählen, wird sie vom Assistenten erst am ausgewählten Speicherort gespeichert, nachdem Sie im Assistenten auf **Fertig stellen** geklickt haben.  
  
 Der Assistent ist nicht in der Lage, Dateien zu überschreiben.  Wenn Sie den Namen einer vorhandenen Datei auswählen und dann auf **Fertig stellen** klicken, wird vom Assistenten eine Bestätigung angefordert, die Klassendeklaration an den Inhalt der Datei anzufügen.  Klicken Sie auf **Ja**, um die Datei anzufügen, und klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.  
  
 **Klasse**  
 Legt den Namen der zu erstellenden Klasse fest.  Dieser Name basiert auf dem unter **Kurzer Name** angegebenen Namen. Allerdings wird der Buchstabe C als typisches Präfix für einen Klassennamen vorangestellt.  
  
 **.cpp\-Datei**  
 Legt für die neue Objektklasse den Namen der Implementierungsdatei fest.  Dieser Name basiert standardmäßig auf dem unter **Kurzer Name** angegebenen Namen.  Klicken Sie auf die Schaltfläche mit den Auslassungspunkten \(...\), um den Dateinamen am gewünschten Speicherort zu speichern.  Die Datei wird erst am ausgewählten Speicherort gespeichert, wenn Sie im Assistenten auf **Fertig stellen** klicken.  
  
 Der Assistent ist nicht in der Lage, Dateien zu überschreiben.  Wenn Sie den Namen einer vorhandenen Datei auswählen und dann auf **Fertig stellen** klicken, werden Sie vom Assistenten gefragt, ob die Klassenimplementierung an den Inhalt der Datei angefügt werden soll.  Klicken Sie auf **Ja**, um die Datei anzufügen, und klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.  
  
 **Attributiert**  
 Gibt an, ob das Objekt Attribute verwendet.  Wenn Sie einem attributierten ATL\-Projekt ein Objekt hinzufügen, ist diese Option aktiviert und kann nicht geändert werden.  Dies bedeutet, dass einem Projekt, das mit Attributunterstützung erstellt wurde, nur attributierte Objekte hinzugefügt werden können.  
  
 Wenn Sie diese Option für ein ATL\-Projekt auswählen, das nicht über Attributunterstützung verfügt, werden Sie vom Assistenten gefragt, ob dem Projekt Attributunterstützung hinzugefügt werden soll.  
  
 Bei nicht attributierten Projekten werden alle Objekte, die nach Auswahl dieser Option hinzugefügt werden, standardmäßig als attributiert konfiguriert \(das Kontrollkästchen ist aktiviert\).  Sie können das Kontrollkästchen deaktivieren, um ein Objekt hinzuzufügen, das keine Attribute verwendet.  
  
 Weitere Informationen finden Sie unter [Anwendungseinstellungen, ATL\-Projekt\-Assistent](../../atl/reference/application-settings-atl-project-wizard.md) und [Grundlegende Funktionsweise von Attributen](../../windows/basic-mechanics-of-attributes.md).  
  
### COM  
 Bietet Informationen über die COM\-Funktionen des Objekts.  
  
 **Coclass**  
 Legt den Namen der Komponentenklasse fest. Sie enthält eine Liste der vom Objekt unterstützten Schnittstellen.  Falls das Projekt oder Objekt Attribute verwendet, können Sie diese Option nicht ändern, da ATL kein **coclass**\-Attribut einschließt.  
  
 **Text \[Type\]**  
 Legt die in der Registrierung für die Co\-Klasse verwendete Objektbeschreibung fest.  
  
 **Interface**  
 Legt die für das Objekt erstellte Schnittstelle fest.  Die Schnittstelle umfasst Ihre benutzerdefinierten Methoden.  
  
 **ProgID**  
 Legt den Namen fest, den Container anstelle der CLSID des Objekts verwenden können.  
  
## Siehe auch  
 [ATL Active Server Page Component](../../atl/reference/adding-an-atl-active-server-page-component.md)