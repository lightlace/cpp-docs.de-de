---
title: "Erstellen von Programmen, die Remoteautomatisierung verwenden"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Remoteautomatisierung, Erstellen von Programmen"
ms.assetid: 8eb31320-1037-4029-b1f3-fdc9406dbaf1
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Erstellen von Programmen, die Remoteautomatisierung verwenden
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Jedes Automatisierungsobjekt und entweder Automatisierungscontroller, ist in der Lage, die Automatisierung ohne Änderung am Quellcode, ohne die Notwendigkeit Neukompilierung und ohne die Notwendigkeit das erneute Binden zu verwenden.  Nachdem Sie eines Setup\- haben, das lokal \(das heißt, auf dem gleichen Computer\) funktioniert, müssen Sie nur einige Schritte durchlaufen, ihn remote auszuführen.  
  
#### So das Remoteautomatisierungsobjekt ausführen  
  
1.  Registrieren Sie die Anwendung auf dem Clientcomputer oder Computer.  
  
2.  Konfigurieren Sie den Clientzugriff zum Verwendungsremoteserver.  
  
3.  Installieren und registrieren Sie die Anwendung auf dem Servercomputer oder \-Computern.  
  
4.  Konfigurieren Sie den Server, um Remoteaktivierung zuzulassen.  
  
5.  Installieren Sie den Automatisierungs\-Manager auf den Servercomputern.  
  
6.  Führen Sie Automatisierungs\-Manager auf den Server aus.  
  
7.  Führen Sie die Anwendung auf den Clients aus.  
  
 Schritt 1 kann einfach erreicht, indem die Serveranwendung auf dem Clientcomputer geladen und ausgeführt wird, da die meisten Selbstregistrieren Server sind.  Wenn Sie das Setup lokal zuvor getestet haben, stellt diese Phase bereits abgeschlossen.  Wenn die Serveranwendung nicht das registrierende Auch ist, sollten Sie sie beliebig machen.  Andernfalls müssen Sie eine Registrierungsdatei bereitstellen, die vom lokalen Benutzer ausführen kann, um diesen Schritt auszuführen.  Wenn keine dieser Vorgänge müssen, oder Sie ein Administrator die Registrierung manuell bearbeiten, eine Prozedur, die nicht für nur die Benutzer höchstentwickelten empfohlen wird.  
  
 Schritt 2 wird die Verwendung des von Automatisierungs\-Verbindungs \(rac\)\- Manager mit ein.  Führen Sie RAC\-Manager aus und stellen Sie sicher, dass die Server\-Verbindungsregisterkarte oben ist.  Suchen Sie danach den Eintrag für das Serverobjekt im Bereich **OLE\-Klassen** und klicken Sie darauf.  Bewegen Sie auf **Netzwerkadresse** das Kombinationsfeld und den Namen des Servercomputers ein, auf dem die Remoterollen ausführbare Datei ausgeführt wird.  Beispielsweise geben Sie hier möglicherweise \\\\MyServer ein.  Wählen Sie dann das entsprechende Netzwerkprotokoll aus der Liste aus.  Möglicherweise müssen Sie sich mit dem Netzwerkadministrator überprüfen, um zu bestimmen, den Protokoll empfohlen wird.  In vielen Fällen ist dies TCP\/IP.  Schließlich sollten Sie eine Authentifizierungsebene auswählen.  In den meisten Fällen wird diese wie \(kein\) oder Standard belassen.  Klicken Sie nun auf den Server im Bereich **OLE\-Klassen** mit der rechten Maustaste.  Dies erzeugt ein Kontextmenü, von dem lokalen oder Fernbetrieb auswählen können.  Ausgewähltes remote.  
  
 Schritt 3 umfasst, die Serveranwendung auf ein mit dem ausgewählten \-Computern Servercomputer oder ordnungsgemäß installiert und registriert.  Auch wenn die Anwendung das registrierende Auch ist, registriert das Ausführen sie einmal sie auch.  
  
 Schritt 4, scrollen den Server konfigurieren, um die Ausführung zu ermöglichen.  Führen Sie RAC\-Manager auf dem Servercomputer aus, und stellen Sie sicher, dass die **Clientzugriff** Registerkarte den Fokus besitzt.  Wählen Sie das Aktivierungsmodell aus, das Sie soll \(normalerweise **Allow Remote Creates by Key**.  Wenn Sie diese Option auswählen, müssen Sie auch auf das Kontrollkästchen **Remoteaktivierung zulassen** klicken, um den Wert des Registrierungseintrags auf "Y festzulegen "\).  Wenn Sie Windows NT oder Windows 2000 ausführen, und Sie das Gewährs\-Remote erstellen \(ACL\-\) Option auswählen, haben Sie auch die Option, die Zugriffssteuerungsliste bearbeiten, indem Sie die Schaltfläche **ACL bearbeiten** betätigen.  
  
 Um die Automatisierung mit Taskleistenminiaturansichten zu ermöglichen, müssen Sie anschließend sicherstellen dass der Automatisierungs\-Manager installiert ist und ausgeführt wird auf dem Servercomputer oder die Computer.  Wenn sie nicht installiert ist, kopieren Sie AUTMGR32.EXE das Windows\-Systemverzeichnis.  Informationen, wie erreicht, finden Sie unter [Remote\- Automatisierungs\-Installation](../mfc/remote-automation-installation.md).  Um die Automatisierung zu starten, führen Sie den Automatisierungs\-Manager aus.  Sie zeigt ein kleines Statusfenster an, in dem einige Meldungen angezeigt werden.  Sobald sie gestartet, minimiert sie.  Wenn Sie fortfahren möchten, um Statusinformationen anzuzeigen, können Sie auf die Registerkarte **Automatisierungs\-Manager** in der Taskleiste klicken, um das Fenster wiederhergestellt.  
  
 Der letzte Schritt ist, die Clientanwendung auf dem Clientcomputer auszuführen.  Wenn Sie den Anweisungen oben befolgt haben, sollte an das Serverobjekt herstellen und langsamer wenig genau obwohl ausführen, der lokal, bereit.  
  
 Beachten Sie, dass der RAC\-Manager Sie auch Windows\-Tastenkombinationen zwischen Remoteautomatisierung und verteilten COM \(DCOM, auf diesen Plattformen, die DCOM unterstützen\), mit einem einzelnen Mausklick eines Optionsfelds kann.  Wenn Sie auswählen DCOM, können zahlreiche weitere Konfigurationsoptionen festlegen.  Siehe die DCOM\-Dokumentation für Details.  
  
## Siehe auch  
 [Remoteautomatisierung](../mfc/remote-automation.md)   
 [Ausführen von Remoteautomatisierung mithilfe von AUTOCLIK und AUTODRIV](../mfc/running-remote-automation-using-autoclik-and-autodriv.md)