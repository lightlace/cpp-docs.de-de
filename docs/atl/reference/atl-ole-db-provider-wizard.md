---
title: "ATL-OLE DB-Anbieter-Assistent"
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
  - "vc.codewiz.class.atl.provider.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-OLE DB-Anbieter-Assistent"
  - "ATL-Projekte, Hinzufügen von ATL-OLE DB-Anbietern"
ms.assetid: cf91ba78-01d1-4d12-b673-e95d96bfbebe
caps.latest.revision: 13
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# ATL-OLE DB-Anbieter-Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit diesem Assistenten werden die Klassen erstellt, aus denen sich ein OLE DB\-Anbieter zusammensetzt.  
  
## Hinweise  
 Ab [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)] registriert das von diesem Assistenten erstellte Registrierungsskript seine COM\-Komponenten unter **HKEY\_CURRENT\_USER** statt unter **HKEY\_LOCAL\_MACHINE**.  Um dieses Verhalten zu ändern, legen Sie die Option **Komponente für alle Benutzer registrieren** des ATL\-Assistenten fest.  
  
 In der folgenden Tabelle werden die Optionen für den ATL\-OLE DB\-Anbieter\-Assistenten beschrieben:  
  
 **Kurzer Name**  
 Geben Sie den kurzen Namen des zu erstellenden Anbieters ein.  Die anderen Eingabefelder im Assistenten werden automatisch basierend auf Ihrer Eingabe ausgefüllt.  Sie können die anderen Namensfelder bearbeiten, wenn Sie möchten.  
  
 **Coclass**  
 Der Name der Co\-Klasse.  Der ProgID\-Name wird geändert, um mit diesem Namen übereinzustimmen.  
  
 **Attributiert**  
 Diese Option legt fest, ob der Assistent Anbieterklassen unter Verwendung von Attributen oder von Vorlagendeklarationen erstellt.  Bei Auswahl dieser Option verwendet der Assistent Attribute anstelle von Vorlagendeklarationen \(die Standardoption, falls ein attributiertes Projekt erstellt wurde\).  Wenn Sie diese Option deaktivieren, verwendet der Assistent Vorlagendeklarationen anstelle von Attributen \(die Standardoption, falls ein nicht attributiertes Projekt erstellt wurde\).  
  
 Wenn Sie diese Option auswählen und ein nicht attributiertes Projekt erstellt haben, werden Sie vom Assistenten gewarnt, dass das Projekt in ein attributiertes Projekt konvertiert wird, und Sie werden gefragt, ob Sie fortfahren möchten oder nicht.  
  
 **ProgID**  
 Die Programm\-ID bzw. der programmatische Bezeichner ist eine Textzeichenfolge, die von der Anwendung anstelle einer GUID verwendet werden kann.  Die Programm\-ID hat das Format *Projektname*.*Co\-Klassenname*.  
  
 **Version**  
 Die Versionsnummer des Anbieters.  Der Standard ist 1.  
  
 **Datenquellenklasse**  
 Der Name der Datenquellenklasse im Format C`Shortname`Source.  
  
 **.h\-Datei der Datenquelle**  
 Die Headerdatei für die Datenquellklasse.  Sie können den Dateinamen bearbeiten oder eine vorhanden Headerdatei auswählen.  
  
 **Sitzungsklasse**  
 Der Name der Sitzungsklasse im Format C`Shortname`Session.  
  
 **.h\-Datei der Sitzung**  
 Die Headerdatei für die Sitzungsklasse.  Sie können den Dateinamen bearbeiten oder eine vorhanden Headerdatei auswählen.  
  
 **Befehlsklasse**  
 Der Name der Befehlsklasse im Format C`Shortname`Command.  
  
 **.h\-Datei des Befehls**  
 Die Headerdatei für die Befehlsklasse.  Der Name kann nicht bearbeitet werden und ist abhängig vom Namen der Rowset\-Headerdatei.  
  
 **Rowset\-Klasse**  
 Der Name der Rowsetklasse im Format C`Shortname`Rowset.  
  
 **Rowset .h\-Datei**  
 Die Headerdatei für die Rowset\-Klasse.  Sie können den Dateinamen bearbeiten oder eine vorhanden Headerdatei auswählen.  
  
 **Rowset .cpp\-Datei**  
 Die Implementierungsdatei des Anbieters.  Sie können den Dateinamen bearbeiten oder eine vorhandene Implementierungsdatei auswählen.  
  
## Siehe auch  
 [ATL OLE DB Provider](../../atl/reference/adding-an-atl-ole-db-provider.md)