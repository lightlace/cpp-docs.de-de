---
title: Registrierung
ms.date: 11/04/2016
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
ms.openlocfilehash: 1c8c0d32db202b8ba26afec708bcc8bab8e3282c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50461957"
---
# <a name="registration"></a>Registrierung

Wenn ein Benutzer ein OLE-Element in eine Anwendung eingefügt möchte, stellt OLE eine Liste von Objekttypen zur Auswahl. OLE ruft diese Liste ab, aus der Datenbank der System-Registrierung, die von serveranwendungen für alle bereitgestellte Informationen enthält. Selbst ein Server registriert wird, die Einträge, die in der Registrierungsdatenbank "System" (die Registrierung) wird beschrieben, jede Art von Objekt, das es bereitstellt, file Extensions und den Pfad zu sich selbst, u. a.

Das Framework und die OLE-System Dynamic Link Libraries (DLL) verwenden diese Registrierung, um zu bestimmen, welche Arten von OLE-Elemente auf dem System verfügbar sind. Das OLE-System Verwenden von DLLs auch diese Registrierung um zu bestimmen, wie eine Serveranwendung zu starten, wenn ein verknüpftes oder eingebettetes Objekt aktiviert wird.

In diesem Artikel wird beschrieben, was jede Anwendung muss bei der Installation, und jedes Mal, die sie ausgeführt wird.

Ausführliche Informationen über die Systemregistrierungsdatenbank und das Format der reg-Dateien verwendet, um es zu aktualisieren, finden Sie die *OLE-Programmierreferenz*.

##  <a name="_core_server_installation"></a> Server-Installation

Bei der Installation von Ihrer Serveranwendung sollten sie alle Typen von OLE-Elemente registrieren, die es unterstützt. Sie können auch festlegen, dass der Server, auf die Systemdatenbank für die Registrierung aktualisieren, jedes Mal, wenn sie als eigenständige Anwendung ausgeführt wird. Damit bleibt die Registrierungsdatenbank auf dem neuesten Stand, wenn die ausführbare Datei des Servers verschoben wird.

> [!NOTE]
>  MFC-Anwendungen, die automatisch vom Anwendungs-Assistenten generiert registrieren sich selbst, wenn sie als eigenständige Anwendungen ausgeführt werden.

Wenn Sie Ihre Anwendung während der Installation registrieren möchten, verwenden Sie das Programm RegEdit.exe. Wenn Sie ein Setup-Programm mit der Anwendung einschließen, haben Sie das Setup-Programm ausführen "RegEdit" / s " *Appname*. reg". (Das Flag "/ s" gibt an, automatischer Vorgang, d. h. nicht angezeigt im Dialogfeld reporting erfolgreichen Abschluss des Befehls). Weisen Sie andernfalls, den Benutzer an, "regedit" manuell ausführen.

> [!NOTE]
>  Die vom Anwendungs-Assistenten erstellte reg-Datei enthält den vollständigen Pfad für die ausführbare Datei keine. Ihr Installationsprogramm muss entweder die Registrierungsdatei, um den vollständigen Pfad zur ausführbaren Datei enthalten, oder Ändern der Umgebungsvariablen PATH, um das Installationsverzeichnis einzuschließen ändern.

"Regedit" führt den Inhalt der .reg-Textdatei in der Registrierungsdatenbank zusammen. Um die Datenbank zu überprüfen oder zu reparieren, verwenden Sie den Registrierungs-Editor. Achten Sie darauf, um löschen die wichtigen OLE-Einträge zu vermeiden.

##  <a name="_core_server_initialization"></a> Initialisierung

Wenn Sie eine Server-Anwendung mit der Anwendungs-Assistenten erstellen, schließt der Assistent alle Initialisierungsaufgaben für Sie automatisch ein. In diesem Abschnitt wird beschrieben, was Sie tun müssen, wenn Sie eine Serveranwendung manuell schreiben.

Wenn eine Serveranwendung eine Container-Anwendung gestartet wird, die OLE-System-DLLs fügen die Option "/ einbetten" des Servers Befehlszeile hinzu. Eine Serveranwendung Verhalten hängt davon ab, ob sie von einem Container gestartet wurde also eine Anwendung tun, Beginn der Ausführung als erstes überprüfen den "/ einbetten" oder "-Embedding" Option in der Befehlszeile. Wenn dieser Schalter vorhanden ist, laden Sie einen anderen Satz von Ressourcen, die der Server als entweder direkt aktiv angezeigt, oder öffnen Sie vollständig. Weitere Informationen finden Sie unter [Menüs und Ressourcen: Servererweiterungen](../mfc/menus-and-resources-server-additions.md).

Die Server-Anwendung sollte auch aufrufen, die `CWinApp::RunEmbedded` Funktion, um die Befehlszeile zu analysieren. Wenn sie einen Wert ungleich NULL zurückgibt, sollte die Anwendung nicht das Fenster angezeigt, da er von einer containeranwendung, nicht als eigenständige Anwendung ausgeführt wurde. Diese Funktion aktualisiert den Eintrag des Servers in der Registrierung der Systemdatenbank und ruft die `RegisterAll` Member-Funktion für Sie die Registrierung der Instanz.

Wenn die Server-Anwendung gestartet wird, müssen Sie sicherstellen, die Registrierung der Instanz ausgeführt werden kann. Registrierung der Instanz informiert der OLE-System-DLLs, dass es sich bei der Server aktiv ist und Anforderungen von Containern empfangen wird. Es ist nicht der Registrierungsdatenbank einen Eintrag hinzufügen. Führen Sie die Registrierung der Instanz des Servers durch Aufrufen der `ConnectTemplate` -Memberfunktion von definiert `COleTemplateServer`. Dies verbindet die `CDocTemplate` -Objekt an die `COleTemplateServer` Objekt.

Die `ConnectTemplate` Funktion akzeptiert drei Parameter: des Servers *CLSID*, ein Zeiger auf die `CDocTemplate` Objekt und ein Flag, das angibt, ob der Server mehrere Instanzen unterstützt. Ein Miniserver muss in der Lage, mehrere Instanzen unterstützen, d. h. es muss möglich sein für mehrere Instanzen des Servers, der gleichzeitig eine für jeden Container ausgeführt. Übergeben Sie daher **"true"** für dieses Flag, wenn ein Miniserver zu starten.

Wenn Sie ein Miniserver schreiben, wird durch Definition es immer von einem Container gestartet. Sie sollten immer noch die Befehlszeile zu prüfen, die Option "/ einbetten" analysiert werden. Das Fehlen dieser Option in der Befehlszeile bedeutet, dass der Benutzer versucht hat, um den Miniserver als eigenständige Anwendung zu starten. In diesem Fall registrieren den Server mit der System-Registrierungsdatenbank, und zeigen ein Meldungsfeld den Benutzer zum Starten der Miniserver von einer containeranwendung zu informieren.

## <a name="see-also"></a>Siehe auch

[OLE](../mfc/ole-in-mfc.md)<br/>
[Server](../mfc/servers.md)<br/>
[CWinApp::RunAutomated](../mfc/reference/cwinapp-class.md#runautomated)<br/>
[CWinApp::RunEmbedded](../mfc/reference/cwinapp-class.md#runembedded)<br/>
[COleTemplateServer-Klasse](../mfc/reference/coletemplateserver-class.md)
