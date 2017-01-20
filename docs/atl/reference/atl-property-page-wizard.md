---
title: "ATL-Eigenschaftenseiten-Assistent"
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
  - "vc.codewiz.class.atl.ppg.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Projekte, Hinzufügen von Eigenschaftenseiten"
  - "ATL-Eigenschaftenseiten-Assistent"
ms.assetid: 6113e325-facd-4f68-b491-144d75209922
caps.latest.revision: 13
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# ATL-Eigenschaftenseiten-Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit diesem Assistenten [fügen Sie einem ATL\-Projekt eine Eigenschaftenseite hinzu](../../atl/reference/adding-an-atl-property-page.md) oder versehen ein MFC\-Projekt mit ATL\-Unterstützung.  Durch eine ATL\-Eigenschaftenseite wird eine Benutzeroberfläche bereitgestellt, in der Eigenschaften eines oder mehrerer COM\-Objekte festgelegt \(bzw. Methoden aufgerufen\) werden können.  
  
## Hinweise  
 Ab [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)] registriert das von diesem Assistenten erstellte Registrierungsskript seine COM\-Komponenten unter **HKEY\_CURRENT\_USER** statt unter **HKEY\_LOCAL\_MACHINE**.  Um dieses Verhalten zu ändern, legen Sie die Option **Komponente für alle Benutzer registrieren** des ATL\-Assistenten fest.  
  
## Namen  
 Geben Sie die Namen für Objekt, Schnittstelle und Klassen an, die dem Projekt hinzugefügt werden sollen.  Mit Ausnahme von **Kurzer Name** können alle weiteren Felder unabhängig voneinander bearbeitet werden.  Wenn Sie den Eintrag unter **Kurzer Name** ändern, wirkt sich die Änderung auf die Namen in allen anderen Feldern auf dieser Seite aus.  Wenn Sie den Namen unter **Coclass** im COM\-Abschnitt ändern, wirkt sich die Änderung auf die Felder **Typ** und **Programm\-ID** aus.  Dieses Namenssystem ist so ausgelegt, dass alle Namen während der Entwicklung der Eigenschaftenseite leicht identifizierbar sind.  
  
> [!NOTE]
>  **Coclass** kann nur bei nicht attributierten Projekten bearbeitet werden.  Verfügt das Projekt über Attribute, kann **Coclass** nicht bearbeitet werden.  
  
### C\+\+  
 Liefert Informationen über die C\+\+\-Klasse, die zur Implementierung des Objekts erstellt wurde.  
  
|||  
|-|-|  
|Begriff|Definition|  
|**Kurzer Name**|Legt den abgekürzten Namen für das Objekt fest.  Der hier angegebene Name bestimmt den Klassennamen sowie den unter **Coclass** angegebenen Namen, die Dateinamen \(**.cpp** und **.h**\), den unter **Typ** angegebenen Namen sowie die **Programm\-ID**, sofern Sie diese Felder nicht einzeln ändern.|  
|**.h\-Datei**|Legt den Namen der Headerdatei für die neue Objektklasse fest.  Dieser Name basiert standardmäßig auf dem unter **Kurzer Name** angegebenen Namen.  Klicken Sie auf die Schaltfläche mit den Auslassungspunkten \(...\), um den Dateinamen am gewünschten Speicherort zu speichern oder um die Klassendeklaration an eine vorhandene Datei anzufügen.  Wenn Sie eine vorhandene Datei auswählen, wird sie vom Assistenten erst am ausgewählten Speicherort gespeichert, nachdem Sie im Assistenten auf **Fertig stellen** geklickt haben.<br /><br /> Der Assistent ist nicht in der Lage, Dateien zu überschreiben.  Wenn Sie den Namen einer vorhandenen Datei auswählen und dann auf **Fertig stellen** klicken, wird vom Assistenten eine Bestätigung angefordert, die Klassendeklaration an den Inhalt der Datei anzufügen.  Klicken Sie auf **Ja**, um die Datei anzufügen, und klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.|  
|**Klasse**|Legt den Namen der Klasse fest, durch die das Objekt implementiert wird.  Dieser Name basiert auf dem unter **Kurzer Name** angegebenen Namen. Allerdings wird der Buchstabe C als typisches Präfix für einen Klassennamen vorangestellt.|  
|**.cpp\-Datei**|Legt für die neue Objektklasse den Namen der Implementierungsdatei fest.  Dieser Name basiert standardmäßig auf dem unter **Kurzer Name** angegebenen Namen.  Klicken Sie auf die Schaltfläche mit den Auslassungspunkten \(...\), um den Dateinamen am gewünschten Speicherort zu speichern.  Die Datei wird erst am ausgewählten Speicherort gespeichert, wenn Sie im Assistenten auf **Fertig stellen** klicken.<br /><br /> Der Assistent ist nicht in der Lage, Dateien zu überschreiben.  Wenn Sie den Namen einer vorhandenen Datei auswählen und dann auf **Fertig stellen** klicken, werden Sie vom Assistenten gefragt, ob die Klassenimplementierung an den Inhalt der Datei angefügt werden soll.  Klicken Sie auf **Ja**, um die Datei anzufügen, und klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.|  
|**Attributiert**|Gibt an, ob das Objekt Attribute verwendet.  Wenn Sie einem attributierten ATL\-Projekt ein Objekt hinzufügen, ist diese Option aktiviert und kann nicht geändert werden. Sie können attributierte Objekte also nur Projekten hinzufügen, die mit Attributunterstützung erstellt wurden.<br /><br /> Ein attributiertes Objekt kann lediglich einem ATL\-Projekt hinzugefügt werden, das Attribute verwendet.  Wenn Sie diese Option für ein ATL\-Projekt auswählen, das nicht über Attributunterstützung verfügt, werden Sie vom Assistenten gefragt, ob dem Projekt Attributunterstützung hinzugefügt werden soll.<br /><br /> Alle Objekte, die nach Auswahl dieser Option hinzugefügt wurden, werden automatisch als attributiert konfiguriert \(das Kontrollkästchen ist aktiviert\).  Sie können das Kontrollkästchen deaktivieren, um ein Objekt hinzuzufügen, das keine Attribute verwendet.<br /><br /> Weitere Informationen finden Sie unter [Anwendungseinstellungen, ATL\-Projekt\-Assistent](../../atl/reference/application-settings-atl-project-wizard.md) und [Grundlegende Funktionsweise von Attributen](../../windows/basic-mechanics-of-attributes.md).|  
  
### COM  
 Bietet Informationen über die COM\-Funktionen des Objekts.  
  
 **Coclass**  
 Legt den Namen der Komponentenklasse fest. Sie enthält eine Liste der vom Objekt unterstützten Schnittstellen.  
  
> [!NOTE]
>  Wenn Sie das Projekt unter Verwendung von Attributen erstellen oder auf dieser Seite des Assistenten angeben, dass die Eigenschaftenseite Attribute verwendet, können Sie diese Option nicht ändern, da das `coclass`\-Attribut nicht in ATL enthalten ist.  
  
 **Text \[Type\]**  
 Legt die in der Registrierung verwendete Objektbeschreibung fest.  
  
 **ProgID**  
 Legt den Namen fest, den Container anstelle der CLSID des Objekts verwenden können.  
  
## Siehe auch  
 [Optionen, ATL\-Eigenschaftenseiten\-Assistent](../../atl/reference/options-atl-property-page-wizard.md)   
 [Zeichenfolgen, ATL\-Eigenschaftenseiten\-Assistent](../../atl/reference/strings-atl-property-page-wizard.md)   
 [Example: Implementing a Property Page](../../atl/example-implementing-a-property-page.md)