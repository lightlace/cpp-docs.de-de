---
title: "Neues in Office Developer Tools f&#252;r Visual Studio 2013 – M&#228;rz 2014-Update"
ms.custom: na
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: e701c650-2a2b-4b18-9f7b-04d4fc59a05d
caps.latest.revision: 2
caps.handback.revision: "2"
ms.author: "shoag"
manager: "wpickett"
---
# Neues in Office Developer Tools f&#252;r Visual Studio 2013 – M&#228;rz 2014-Update
**Office Developer Tools für Visual Studio 2013 – Update März 2014** besitzt viele neue Funktionen, die die in Visual Studio 2013 für Cloud\-Business\-Apps enthaltenen Tools sowie die Apps für die Office\- und SharePoint\-Entwicklung verbessern.  Hiermit können Sie auch neue Typen von Apps für Office erstellen, die in Office 2013 SP1 und in Office 365 aktiviert sind.  
  
-   [Neues bei den Cloud-Business-Apps](#cba)  
  
-   [Neues bei der App für die Office-Entwicklung](#office)  
  
-   [Neues bei der App für die SharePoint-Entwicklung](#sharepoint)  
  
##  <a name="cba"></a> Neues bei den Cloud\-Business\-Apps  
 Visual Studio 2013 enthält die Projektvorlage für die Cloud\-Business\-App, mit der Sie moderne Geschäftsanwendungen schnell erstellen können, die in die Office 365\-Plattformfunktionen integriert werden und diese erweitern.  In dieser Version wurden einige neue Funktionen hinzugefügt, um die Verbindungsherstellung mit Enterprise\-Daten und die Integration von Dokumentbibliotheken sowie eine schnelle Anwendungsentwicklung besser zu unterstützen.  
  
### Anfügen an Enterprise\-Daten  
 **Neue SAP\-Datenquelle**  
  
 Enterprise\-Daten spielen in vielen Geschäftsanwendungen eine Schlüsselrolle.  Heutzutage gibt es viele unterschiedliche Typen von Enterprise\-Datenquellen auf dem Markt.  Neben den Datenbank\-, SharePoint\-, OData\-Dienst\- und WCF RIA\-Dienstdatenquellen bietet das Tools\-Update im März 2014 auch erstklassige Unterstützung für SAP Netweaver Gateway.  Wenn Sie eine Verbindung mit SAP herstellen, berücksichtigt die Cloud\-Business\-App nun SAP\-Anmerkungen für Phone, WebAdresse und E\-Mail. Dies vereinfacht die Konfiguration von Entitäten, die von SAP Netweaver Gateway genutzt werden.  
  
 **Verbesserungen des Assistenten zum Hinzufügen von Datenquellen**  
  
 Viele Enterprise\-Datenquellen speichern eine große Anzahl von Datenentitäten, in denen eine Cloud\-Business\-App wahrscheinlich mit nur einigen wenigen dieser Entitäten interagieren muss.  Um Ihnen die Suche nach den Entitäten zu erleichtern, mit denen Sie eine Verbindung herstellen möchten, können Sie nun im Dialogfeld **Assistent zum Hinzufügen von Datenquellen** anhand des Namens nach den Entitäten suchen und diese nach verschiedenen Kategorien filtern.  Es werden auch die Beziehungen der Entitäten innerhalb der Datenquelle angezeigt.  
  
 **Leistungsverbesserung beim Anfügen an große Datasets**  
  
 Wenn die Cloud\-Business\-App an einen großen Dataset angefügt werden muss, stellen Sie im Dialogfeld **Assistent zum Hinzufügen von Datenquellen** eine Verbesserung der Leistung fest.  Das Layout des Entity Designer wurde für große Datasets verbessert, sodass Sie die Beziehungen zwischen den Entitäten einfacher durchsuchen können.  Außerdem können Sie nun die Reihenfolge der Eigenschaften in einer Entität ändern.  
  
 **Verbesserungen des Geschäftstyps**  
  
 Neben einer großen Anzahl von Entitäten umfassen viele Enterprise\-Datenquellen anspruchsvolle Geschäftstypen, wie z. B. komplexe Typen.  Das Update im März 2014 bietet neue Unterstützung für komplexe Datentypen.  
  
 Wenn die Cloud\-Business\-App an eine SharePoint\-Liste angefügt wird, die die **Person**\-Typspalten enthält, werden diese Spalten beim Ausführen der App automatisch als Kontakte hervorgehoben.  Wenn z. B. Lync auf dem Computer installiert ist und dieser eine Verbindung mit dem gleichen Active Directory herstellt, das auch die SharePoint\-Website verwendet, werden in den Person\-Typspalten die Werte als Lync\-Kontakte angezeigt und die Lync\-Funktionen in der Cloud\-Business\-App automatisch aktiviert.  
  
### Integrieren von Dokumenten  
 Für viele Geschäftsanwendungen ist die Speicherung und der Abruf von Dokumenten eine Grundvoraussetzung.  Beispielsweise möchten Sie Zugriff auf eine Liste von produktbezogenen Dokumenten gewähren, wenn sich ein Benutzer die Produktdetails ansieht.  Möglicherweise möchten Sie den Benutzern auch die Verwaltung der Dokumente in der App ermöglichen.  Mit Cloud\-Business\-Apps können Sie nun Anhänge an eine SharePoint\-Dokumentbibliotheksliste anfügen und eine Beziehung zwischen der Listenentität und einer anderen Datenentität festlegen.  Dank dieser Funktion können Sie eine App schnell erstellen, die die Dokumente für ein bestimmtes Datenfeld anzeigt.  
  
 Wenn Sie darüber hinaus die App an eine gehostete SharePoint\-Webdokumentbibliothek anfügen, werden die App\-Bildschirme mit einem Satz neuer Dokumentsteuerelemente integriert. Diese ermöglichen es den Benutzern, neue Office\-Dokumente zu erstellen\(entweder leere Dokumente oder anhand von Dokumentvorlagen, die in der angefügten Dokumentbibliothek verfügbar sind\), Dokumente in der Office Web App oder im Office\-Client zu öffnen und vorhandene Dokumente hochzuladen.  Alle diese Funktionen werden von den Tools bereitgestellt, ohne dass Sie eingreifen müssen.  
  
### Verbesserungen der schnellen Anwendungsentwicklung  
 **Verbessertes Zusammenfassungssteuerelement**  
  
 Um die Arbeit mit unterschiedlichen Datentypen zu verbessern, wurde das Zusammenfassungssteuerelement so aktualisiert, dass das Standardsteuerelement für den zugrunde liegenden Semantiktyp angezeigt wird.  Wenn das Zusammenfassungssteuerelement einem **Person**\-Typ zugeordnet ist, wird das **Personenviewer**\-Steuerelement dank dieser Unterstützung vom Zusammenfassungssteuerelement verwendet, das zusätzliche Informationen zu einer Person darstellt \(beispielsweise den Namen und die Anrede der Person sowie das Anzeigebild\).  
  
> [!NOTE]
>  Die `contentItem.value`\-Eigenschaft für das Zusammenfassungssteuerelement gibt nun den Wert für die Summary\-Eigenschaft anstatt die gesamte Datenentität zurück.  Wenn Sie die `contentItem.value`\-Eigenschaft für ein Zusammenfassungssteuerelement verwendet haben, um die Entität für den Zugriff auf eine andere Eigenschaft in der Entität abzurufen, müssen Sie den Code aktualisieren, um stattdessen die `contentItem.data`\-Eigenschaft verwenden zu können.  
  
 **Integrierte Logik zum Filtern von großen Datasets auf Bildschirmen**  
  
 Das Update im März 2014 enthält eine integrierte Unterstützung für Datenfilterung.  Ohne dass Sie eine neue Aktion ausführen müssen, generiert die Cloud\-Business\-App für Mobilgeräte optimierte Bildschirme, mit denen die Benutzer nach Datentabellen suchen und die Tabelle anhand der Tabellenüberschriften sortieren können.  
  
 **Erstellen von Bildschirmsätzen**  
  
 Damit Sie häufig verwendete Bildschirme schnell erstellen können, die es den Benutzern ermöglichen, Daten in der App zu durchsuchen, anzuzeigen und zu bearbeiten, enthält diese Version eine übliche Bildschirmanordnung.  Anstatt die Bildschirme "Durchsuchen", "Ansicht" und "Neu\/Bearbeiten" nacheinander zu erstellen, können Sie jetzt einfach eine übliche Bildschirmanordnung erstellen, die alle diese drei Bildschirmarten gleichzeitig generiert.  Die übliche Bildschirmanordnung verknüpft auch die Datentabellen, die Beziehungen und die Navigation zwischen den Bildschirmen automatisch für Sie.  
  
 **Hinzufügen von App\-Lesezeichen**  
  
 Benutzer müssen häufig eine Seite in der App mit einem Lesezeichen versehen, um schnell zu dieser Seite zurückkehren zu können.  Cloud\-Business\-Apps in dieser Version unterstützen nun das Hinzufügen von Lesezeichen, ohne dass Sie Code schreiben müssen.  Dank dieser Funktion können Benutzer eine beliebige Seite in der App mit einem Lesezeichen versehen.  Sie können auf ihren Mobilgeräten auch eine Seite an die Startseite anheften.  
  
##  <a name="office"></a> Neues bei der App für die Office\-Entwicklung  
 **Neue Typen von Apps für Office**  
  
 Office 2013 SP1 und Office 365 unterstützen Inhalts\-Apps für PowerPoint und Access Web App und ermöglichen der Mail\-App die Aktivierung in Entwurfsvorlagen \(wenn zum Beispiel Benutzer eine neue E\-Mail\-Nachricht schreiben oder einen neuen Termin erstellen\).  Das Update im März 2014 unterstützt alle diese neuen App\-Typen im gesamten Entwicklungszyklus von der Projekterstellung, der Manifestbearbeitung, der Programmierung und dem Debugging bis hin zur Veröffentlichung.  Napa wurde auch aktualisiert, um diese neuen App\-Typen zu unterstützen.  
  
 **Aktualisierte Projektvorlagen**  
  
 Die App für den Assistenten zum Erstellen von Office\-Projekten in Office Developer Tools wurde so aktualisiert, dass es nun organisiertere Optionen für die App\-Erstellung gibt.  Diese Version bietet zwei Projektvorlagen, die besonders von Inhalts\-Apps verwendet werden können.  Eine Vorlage dient einfach zur Erstellung einer Standard\-App, die minimalen Beispielcode enthält. Die andere Vorlage enthält weitere Beispielcodes, um die Implementierung einer App für Excel und Access Web App zum Darstellen von Daten zu veranschaulichen.  Sie können im Projekterstellungs\-Assistenten zwischen diesen zwei Projektvorlagen auswählen, um einen Schnellstart für die App zu erstellen.  
  
 **Weitere Möglichkeiten zum Aktivieren der App**  
  
 Über die neuen App\-Typen hinausgehend, bieten Ihnen Office 2013 SP1 und Office 365 eine neue Methode zum Festlegen des Aktivierungszeitpunkts für die App.  Zusätzlich zu den App\-Hosts, in denen die App aktiviert werden kann \(Word, Excel, PowerPoint usw.\), wird eine Liste von API\-Sets definiert, von denen jeder eine Gruppe von Office JSOM\-APIs mit derselben Semantik darstellt \(Auswahl, TableBindings usw.\). Für diese Office\-APIs, die in den Schlüsselfunktionen der App aufgerufen werden, können Sie die entsprechenden API\-Sets im App\-Manifest hinzufügen, damit die App nicht in Office\-Hosts aktiviert wird, die diese APIs nicht unterstützen.  Hierdurch können Sie die App versionsübergreifend auf so vielen Hosts wie möglich aktivieren, ohne schwierige Programmierlogik hinzuzufügen.  
  
 Um diesen Typ der Aktivierung zu unterstützen, verfügt die App für Office\-Tools über eine Aktivierungsseite im Manifest\-Editor für die Aufgabenbereich\-App und Inhalts\-App.  Auf dieser Seite können Sie die API\-Sets für die App aktualisieren, und es wird angegeben, wo die App anhand der ausgewählten API\-Sets und API\-Hosts aktiviert wird.  
  
 **Bessere IntelliSense\-Unterstützung**  
  
 Um eine bessere Programmierung für die neuen App\-Typen und das neue App\-Aktivierungsmodell zu bieten, wurde auch IntelliSense weiterentwickelt.  IntelliSense zeigt nur die APIs an, die für die Ziel\-App\-Hosts gültig sind.  Wenn Sie beispielsweise eine Inhalts\-App erstellen, die nur für die Access Web App gilt, werden die APIs, die in der Access Web App unterstützt werden, in IntelliSense angezeigt. Andere APIs werden dagegen nicht angezeigt.  Wenn Sie eine Mail\-App nur für Entwurfsvorlagen erstellen, werden die Mail\-App\-APIs für Leseformulare in IntelliSense ausgeblendet, damit Sie die APIs nicht unsachgemäß verwenden.  Darüber hinaus enthält die Aktivierungsseite im Manifest\-Editor für die Aufgabenbereich\-App\/Inhalts\-App eine Option, die Sie auswählen können, um IntelliSense nur mit den APIs anzuzeigen, die zu den von Ihnen im Manifest angegebenen API\-Sets gehören.  
  
 **Verbesserungen beim Debugging**  
  
 Das Update im März 2014 bietet Ihnen auch mehr Debugoptionen.  Sie können die Aufgabenbereich\- und Inhalts\-Apps für Excel in der Office Web App und im Desktopclient debuggen.  Sie können mithilfe des Eigenschaftenfensters des App\-Projekts zwischen IE, Chrome und Firefox auswählen \(sofern diese Browser auf dem Computer installiert sind\), um die Office Web App zum Debuggen zu starten.  
  
 Zusätzlich zur Debugunterstützung für die Office Web App können Sie mit den neuen Tools auch "Nur mein Code" für die Apps für Office und SharePoint debuggen.  Wenn diese Option aktiviert ist, werden Sie nicht mehr von JavaScript\-Ausnahmen behindert, die für den Code nicht relevant sind.  
  
##  <a name="sharepoint"></a> Neues bei der App für die SharePoint\-Entwicklung  
 **Ausrichten auf verschiedene SharePoint\-Versionen**  
  
 Mit der App für SharePoint\-Tools können Sie nun die App auf SharePoint Server 2013 \(das mit SharePoint Online kompatibel ist\) oder nur auf SharePoint Online ausrichten.  Durch eine einfache Umstellung in der App für die Eigenschaftenseite des SharePoint\-Projekts aktualisieren die Tools entsprechend die SharePoint\-Versionsnummer und die Assemblyverweise der SharePoint\-Clientkomponenten, die im Projekt verwendet werden.  
  
 **MVS\-Unterstützung für Clientwebparts**  
  
 Um die Unterstützung für MVC\-Webanwendungen zu verbessern, bietet diese Version nun MVC\-Unterstützung für Clientwebpart\-Seiten.  Wenn Sie einen Clientwebpart hinzufügen und dann eine neue Webpartseite im Erstellungs\-Assistenten für Clientwebparts erstellen möchten, werden anstatt einer ASPX\-Seite ein Clientwebpart\-Controller und eine Standardansicht, die zum Clientwebpart\-Controller passt, in die MVC\-Anwendung eingefügt. Die App für SharePoint\-Projekte muss hierzu einer MVC\-Anwendung zugeordnet sein.  
  
 **Listeninstanzunterstützung für Remoteereignisempfänger**  
  
 In Visual Studio 2013 können Sie im Assistenten zum Erstellen von Remoteereignisempfängern nur eine Listenvorlage auswählen.  Nun werden im Assistenten auch alle Listeninstanzen im Projekt angezeigt, die Sie auswählen und zum Erstellen eines Remoteereignisempfängers nutzen können.  Die Tools erstellen das richtige Manifest anhand Ihrer Auswahl.  
  
 **Verbesserte Generierung von Listenvorlagen**  
  
 Diese Version enthält auch einen Patch für das SharePoint\-Listenvorlagenelement.  Mit dem Update im März 2014 wird das Typattribut im Listenvorlagenmanifest beim Erstellen einer SharePoint\-Listenvorlage auf den Typ der übergeordneten Vorlage festgelegt \(anstelle des vormals verwendeten Standardwerts "10000"\).  Aufgrund dieses Patches erbt die neue Listenvorlage kostenlos alle Eigenschaften der übergeordneten Vorlage.  Es ist besonders für die komplexen Listenvorlagentypen wie Dokumentbibliotheken nützlich, die viele benutzerdefinierte Funktionen enthalten.