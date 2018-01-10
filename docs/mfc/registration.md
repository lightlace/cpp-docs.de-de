---
title: Registrierung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- servers [MFC], initializing
- initializing servers [MFC]
- OLE, registration
- installing servers [MFC]
- registry [MFC], OLE item database
- registration databases [MFC]
- servers [MFC], installing
- OLE server applications [MFC], registering servers
ms.assetid: 991d5684-72c1-4f9e-a09a-9184ed12bbb9
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c0b97a249246a9f7f9d47880f75bdce2ca643ae3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="registration"></a>Registrierung
Wenn ein Benutzer ein OLE-Element in einer Anwendung einfügen möchte, bietet OLE eine Liste der Objekttypen zur Auswahl. OLE ruft diese Liste in die Systemdatenbank für die Registrierung, die durch alle serveranwendungen bereitgestellten Informationen enthält. Wenn ein Server selbst registriert, wird der Einträge, die sie in der Registrierung Systemdatenbank (Registrierung) legt beschreiben jeden Typ von ihm bereitgestellten Objekt, Erweiterungen und den Pfad auf sich selbst neben anderen Informationen die Datei.  
  
 Das Framework und die OLE-System Dynamic Link Libraries (DLL) verwenden diese Registrierung, um zu bestimmen, welche Typen von OLE-Elementen für das System verfügbar sind. Das OLE-System verwenden DLLs auch diese Registrierung um zu bestimmen, wie eine Server-Anwendung zu starten, wenn ein Objekt verknüpfte oder eingebettete aktiviert wird.  
  
 In diesem Artikel wird beschrieben, was jede Anwendung muss bei der Installation, und jedes Mal, die sie ausgeführt wird.  
  
 Ausführliche Informationen über die Registrierung Systemdatenbank und das Format der reg-Dateien verwendet, um es zu aktualisieren, finden Sie unter der *OLE Programmer's Reference*.  
  
##  <a name="_core_server_installation"></a>Server-Installation  
 Wenn Sie die Server-Anwendung zum ersten Mal installieren, sollten sie alle Typen von OLE-Elementen registrieren, es unterstützt. Sie können auch veranlassen, dass den Server die Systemdatenbank-Registrierung zu aktualisieren, jedes Mal, wenn sie als eigenständige Anwendung ausgeführt wird. Dadurch wird die Registrierungsdatenbank auf dem neuesten Stand, wenn der ausführbaren Serverdatei verschoben wird.  
  
> [!NOTE]
>  MFC-Anwendungen, die automatisch generiert, indem Sie den Assistenten zum registrieren sich, wenn sie als eigenständige Anwendungen ausgeführt werden.  
  
 Wenn Sie Ihre Anwendung während der Installation registrieren möchten, verwenden Sie das Programm RegEdit.exe. (In Windows 95, Windows 98 und Windows ME ist RegEdit im Windows-Verzeichnis verwenden. In Windows NT und Windows 2000 ist RegEdit in das Verzeichnis "Windows" System32 ".) Wenn Sie ein Setupprogramm, das mit der Anwendung einschließen, haben Sie das Setup-Programm ausführen "RegEdit/s *Appname*reg". (Das Flag/s Zeigt automatischen Vorgang an, d. h. das Dialogfeld reporting erfolgreichen Abschluss des Befehls wird nicht angezeigt.) Andernfalls weisen Sie den Benutzer RegEdit manuell ausführen.  
  
> [!NOTE]
>  Die REG-Datei erstellt, die vom Anwendungs-Assistenten umfasst nicht den vollständigen Pfad für die ausführbare Datei. Das Installationsprogramm muss entweder die Registrierungsdatei, um den vollständigen Pfad zur ausführbaren Datei enthalten, oder ändern die PATH-Umgebungsvariable das Installationsverzeichnis Einbeziehung ändern.  
  
 RegEdit fügt den Inhalt der .reg-Textdatei in die Registrierungsdatenbank. Um die Datenbank zu überprüfen oder zu reparieren, verwenden Sie den Registrierungs-Editor. Achten Sie zum Löschen von wichtigen OLE-Einträge zu vermeiden. (In Windows 95, Windows 98 und Windows ME wird der Registrierungs-Editor RegEdit.exe. In Windows NT und Windows 2000 ist es RegEdit32.exe.)  
  
##  <a name="_core_server_initialization"></a>Server-Initialisierung  
 Wenn Sie eine Server-Anwendung mit dem Assistenten zum Erstellen, schließt der Assistent alle Initialisierungsaufgaben für Sie automatisch ein. In diesem Abschnitt wird beschrieben, was Sie tun müssen, wenn eine Serveranwendung manuell schreiben.  
  
 Wenn eine Serveranwendung durch eine Steuerelementcontainer-Anwendung gestartet wird, Hinzufügen der OLE-System-DLLs die Option "/ einbetten" auf dem Server über die Befehlszeile. Eine Serveranwendung Verhalten hängt davon ab, gibt an, ob es von einem Container gestartet wurde, als Erstes eine Anwendung tun, wenn die Ausführung begonnen gesucht wird der "/ einbetten" oder "-Embedding" Option in der Befehlszeile angegeben. Wenn diesem Switch vorhanden ist, laden Sie einen anderen Satz von Ressourcen, die der Server als wird entweder in-Place aktiv oder öffnen Sie vollständig zu. Weitere Informationen finden Sie unter [Menüs und Ressourcen: Servererweiterungen](../mfc/menus-and-resources-server-additions.md).  
  
 Die Server-Anwendung sollte auch aufrufen, dessen `CWinApp::RunEmbedded` Funktion, die über die Befehlszeile zu analysieren. Wenn sie einen Wert ungleich NULL zurückgibt, sollte das Fenster nicht angezeigt werden, da er in eine Steuerelementcontainer-Anwendung nicht als eigenständige Anwendung ausgeführt wurde. Diese Funktion aktualisiert der Servereintrag in die Registrierung der Systemdatenbank und ruft die `RegisterAll` Memberfunktion für die Sie die Registrierung der Instanz.  
  
 Wenn die Server-Anwendung gestartet wird, müssen Sie sicherstellen, dass sie die Registrierung der Instanz ausführen kann. Registrierung der Instanz informiert der OLE-System-DLLs, dass der Server aktiv und Anforderungen von Containern empfangen kann. Es fügt nicht die Registrierungsdatenbank einen Eintrag hinzu. Führen Sie die Registrierung der Instanz des Servers durch Aufrufen der `ConnectTemplate` Memberfunktion, die durch definierten `COleTemplateServer`. Dies stellt eine Verbindung her den `CDocTemplate` -Objekt an die `COleTemplateServer` Objekt.  
  
 Die `ConnectTemplate` Funktion akzeptiert drei Parameter: des Serverzertifikat **CLSID**, ein Zeiger auf die `CDocTemplate` Objekt und ein Flag, der angibt, ob der Server mehrere Instanzen unterstützt. Ein Miniserver muss in der Lage, mehrere Instanzen unterstützen, d. h. es muss möglich sein für mehrere Instanzen des Servers, eines für jeden Container gleichzeitig ausgeführt werden. Übergeben Sie daher **"true"** für dieses Flag beim Starten ein Miniserver.  
  
 Wenn Sie ein Miniserver definitionsgemäß schreiben, die immer von einem Container gestartet werden soll. Die Befehlszeile für die Option "/ einbetten" überprüfen sollten weiterhin analysiert werden. Das Fehlen dieser Option in der Befehlszeile bedeutet, dass der Benutzer versucht hat, um den Miniserver als eigenständige Anwendung zu starten. In diesem Fall registrieren Sie den Server mit der Registrierung-Systemdatenbank, und zeigen Sie anschließend ein Meldungsfeld informiert den Benutzer um den Miniserver in eine Steuerelementcontainer-Anwendung zu starten.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE](../mfc/ole-in-mfc.md)   
 [Server](../mfc/servers.md)   
 [CWinApp::RunAutomated](../mfc/reference/cwinapp-class.md#runautomated)   
 [CWinApp::RunEmbedded](../mfc/reference/cwinapp-class.md#runembedded)   
 [COleTemplateServer-Klasse](../mfc/reference/coletemplateserver-class.md)
